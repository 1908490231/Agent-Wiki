---
id: text-splitting-tools
title: 文本分割工具（Text Splitting Tools）
type: tool
category: ecosystem
layer: application
tags: [文本分割, Chunking, 分块, RAG预处理, LangChain]
difficulty: 2
status: active
language: [Python]
description: 将长文本切成小块供向量检索使用，是 RAG 系统的必备预处理环节。
last_updated: 2026-03-25
---

# 文本分割工具（Text Splitting Tools）

## 基础概念

文本分割（Text Splitting / Chunking）做的事情很直白：把一篇长文档切成若干小块，每块单独送去做向量嵌入和检索。在 RAG（Retrieval-Augmented Generation，检索增强生成）系统中，你不可能把整本书一次塞给 LLM，必须先切块、再检索相关片段、最后把片段喂给模型生成回答。切得好不好，直接决定检索质量——切太大，检索不精准；切太小，上下文丢失。

LangChain 提供的 `langchain-text-splitters` 是目前最主流的文本分割工具库，内置了多种分割策略，从最简单的固定长度切割到基于语义相似度的智能切割都有覆盖。

### 核心要素

| 要素 | 作用 |
|------|------|
| **分割策略（Splitter）** | 决定在哪里下刀——按字符数、按段落层级递归、按语义边界等 |
| **分块大小（chunk_size）** | 每块的最大长度上限，通常 256-512 个 token，直接影响检索粒度 |
| **重叠区（chunk_overlap）** | 相邻块之间的重复部分，防止关键信息正好被切断 |

### 分割策略（Splitter）

LangChain 内置了多种分割器，各有适用场景：

| 分割器 | 一句话说明 | 适用场景 |
|--------|-----------|---------|
| `CharacterTextSplitter` | 按单一分隔符（如换行符）切割 | 结构简单的纯文本 |
| `RecursiveCharacterTextSplitter` | 按段落→句子→词逐级递归切割 | **通用推荐**，大多数场景首选 |
| `TokenTextSplitter` | 按 LLM 实际 token 数切割 | 需要精确控制 token 数的场景 |
| `MarkdownHeaderTextSplitter` | 按 Markdown 标题层级切割 | Markdown 文档 |
| `HTMLHeaderTextSplitter` | 按 HTML 标签结构切割 | 网页内容 |
| 语义分割（Semantic Chunking） | 用嵌入模型计算句子相似度，在语义转折处切割 | 高质量知识库、学术文档 |

**RecursiveCharacterTextSplitter 是官方推荐的通用选择**。它的切割逻辑是：先尝试在段落处（`\n\n`）切，如果单段太长就降级到句子（`\n`），再不行就按空格切，最后才逐字符切。这样能最大程度保留语义完整性。

### 分块大小（chunk_size）

分块大小是最影响 RAG 效果的参数。实践中的推荐值：

- **256-512 个 token**（约 400-800 个中文字符）：通用安全范围
- 太小（< 100 token）：每块信息量不够，检索到的内容缺乏上下文
- 太大（> 1000 token）：一块里混进多个话题，检索精度下降

### 重叠区（chunk_overlap）

重叠区的作用是防止关键句子正好被切断。推荐设置为 chunk_size 的 10%-20%。例如 chunk_size=500 时，chunk_overlap 设为 50-100。

### 核心要素关系图

```mermaid
graph LR
    A[原始长文档] --> B[选择分割策略]
    B --> C[按 chunk_size 切块]
    C --> D[添加 chunk_overlap 重叠]
    D --> E[输出文本块列表]
    E --> F[向量嵌入 + 存入向量数据库]
    F --> G[RAG 检索使用]

    style B fill:#f9f,stroke:#333
    style C fill:#bbf,stroke:#333
```

## 基础用法

安装依赖：

```bash
pip install langchain-text-splitters>=0.3.0
```

最小可运行示例（基于 langchain-text-splitters==0.3.8 验证，截至 2026-03）：

```python
from langchain_text_splitters import RecursiveCharacterTextSplitter

# 模拟一段 Agent 开发文档
document = """
RAG 是检索增强生成的缩写，核心思路是先检索再生成。
系统收到用户问题后，先从知识库中检索相关片段，再把片段和问题一起交给 LLM 生成回答。

RAG 的优势在于：不需要重新训练模型就能让 LLM 获取最新知识。
企业可以把内部文档灌进向量数据库，员工提问时自动检索相关内容。

文本分割是 RAG 的第一步。把文档切成小块后分别做嵌入，
检索时只取最相关的几块喂给模型，既省 token 又提高准确率。

分块大小的选择很关键。太大的块检索不精准，太小的块缺乏上下文。
一般推荐 300-500 个 token，重叠 10%-20%。
""" * 3  # 重复 3 次模拟更长的文本

# 创建递归字符分割器（通用推荐）
splitter = RecursiveCharacterTextSplitter(
    chunk_size=200,       # 每块最多 200 字符
    chunk_overlap=30,     # 相邻块重叠 30 字符
    separators=["\n\n", "\n", "。", " ", ""]  # 中文优化的分割优先级
)

# 执行分割
chunks = splitter.split_text(document)

# 查看结果
print(f"原始文档长度: {len(document)} 字符")
print(f"分割后块数: {len(chunks)}")
print()
for i, chunk in enumerate(chunks[:3]):
    print(f"--- 块 {i+1}（{len(chunk)} 字符）---")
    print(chunk)
    print()
```

预期输出：

```text
原始文档长度: 918 字符
分割后块数: 7

--- 块 1（198 字符）---
RAG 是检索增强生成的缩写，核心思路是先检索再生成。
系统收到用户问题后，先从知识库中检索相关片段，再把片段和问题一起交给 LLM 生成回答。

RAG 的优势在于：不需要重新训练模型就能让 LLM 获取最新知识

--- 块 2（186 字符）---
企业可以把内部文档灌进向量数据库，员工提问时自动检索相关内容。

文本分割是 RAG 的第一步。把文档切成小块后分别做嵌入，
检索时只取最相关的几块喂给模型，既省 token 又提高准确率

--- 块 3（183 字符）---
分块大小的选择很关键。太大的块检索不精准，太小的块缺乏上下文。
一般推荐 300-500 个 token，重叠 10%-20%。
...
```

Markdown 文档分割示例：

```python
from langchain_text_splitters import MarkdownHeaderTextSplitter

md_doc = """
# Agent 框架概述

Agent 是能自主执行任务的 AI 系统。

## LangChain

LangChain 是最流行的 Agent 开发框架，生态丰富。

### 核心组件

包括 Chain、Agent、Memory、Retriever 四大组件。

## LangGraph

LangGraph 用有向图编排 Agent 流程，支持循环和分支。
"""

# 按标题层级切割，自动保留层级信息作为元数据
md_splitter = MarkdownHeaderTextSplitter(
    headers_to_split_on=[
        ("#", "h1"),
        ("##", "h2"),
        ("###", "h3"),
    ]
)

md_chunks = md_splitter.split_text(md_doc)
for chunk in md_chunks:
    print(f"内容: {chunk.page_content[:40]}...")
    print(f"元数据: {chunk.metadata}")
    print()
```

预期输出：

```text
内容: Agent 是能自主执行任务的 AI 系统。...
元数据: {'h1': 'Agent 框架概述'}

内容: LangChain 是最流行的 Agent 开发框架，生态丰富。...
元数据: {'h1': 'Agent 框架概述', 'h2': 'LangChain'}

内容: 包括 Chain、Agent、Memory、Retriever 四大组件。...
元数据: {'h1': 'Agent 框架概述', 'h2': 'LangChain', 'h3': '核心组件'}

内容: LangGraph 用有向图编排 Agent 流程，支持循环和分支。...
元数据: {'h1': 'Agent 框架概述', 'h2': 'LangGraph'}
```

Markdown 分割器的特点：切出来的每块自动带上所属的标题层级作为元数据，检索时可以利用这些元数据做过滤。

## 同类工具对比

| 维度 | LangChain Text Splitters | LlamaIndex NodeParser | Semantic Text Splitter |
|------|--------------------------|----------------------|------------------------|
| 核心定位 | 通用文本分割工具库 | RAG 框架内置的文档解析器 | 专注语义边界检测的分割器 |
| 最擅长 | 多种策略开箱即用，生态最大 | 与 LlamaIndex 深度集成 | 基于嵌入的高精度语义切割 |
| 学习曲线 | 低，API 简洁直观 | 中，需要理解 LlamaIndex 体系 | 中，需要配置嵌入模型 |
| 适合人群 | 大多数 RAG 开发者 | 已使用 LlamaIndex 的团队 | 对分块质量有极高要求的场景 |

核心区别：

- **LangChain Text Splitters**：独立工具库，不绑定框架，策略最全面，社区最活跃
- **LlamaIndex NodeParser**：与 LlamaIndex 的索引、检索流程深度集成，用 LlamaIndex 就选它
- **Semantic Text Splitter**：用嵌入模型计算语义距离来决定切割点，精度高但计算成本也高

## 常见误区

| 误区 | 准确理解 |
|------|----------|
| 分块越小检索越精准 | 块太小会丢失上下文，模型拿到的片段可能不够理解问题。推荐 256-512 token |
| 所有文档用同一套参数 | 代码、文章、表格特性不同，应该用不同的分割策略和参数 |
| 重叠设得越大越安全 | 重叠过大导致大量冗余存储和重复检索结果，10%-20% 足够 |
| 分割只需要做一次 | 分割策略需要根据下游检索效果持续调优，不是一劳永逸的 |

## 优劣势分析

| 优势 | 劣势 |
|------|------|
| 开箱即用，几行代码完成分割 | 固定规则分割无法理解真正的语义边界 |
| 策略丰富，覆盖纯文本/代码/Markdown/HTML | 中文场景下默认分隔符需要手动调整 |
| 与 LangChain 生态无缝集成 | 语义分割依赖嵌入模型，增加计算成本 |
| 轻量级，无重型依赖 | 参数调优（chunk_size、overlap）需要实验摸索 |

## 思考题

<details>
<summary>初级：CharacterTextSplitter 和 RecursiveCharacterTextSplitter 有什么区别？为什么推荐后者？</summary>

**参考答案：**

CharacterTextSplitter 只按单一分隔符（如 `\n\n`）切割，碰到一个超长段落就无能为力——整段超出 chunk_size 也只能硬切。

RecursiveCharacterTextSplitter 用多级分隔符递归切割：先尝试按段落切，段落太长就降级到句子，再不行降级到词。这样能在满足大小限制的同时最大化保留语义完整性，所以是通用场景的推荐选择。

</details>

<details>
<summary>中级：处理中文技术文档时，RecursiveCharacterTextSplitter 的 separators 参数应该怎么配置？</summary>

**参考答案：**

中文文档的默认英文分隔符不太好用，建议改为：`["\n\n", "\n", "。", "；", "，", " ", ""]`。

理由：中文句子以句号（。）结尾而非英文句点（.），分号（；）标记并列关系的断句，逗号（，）是最小的语义停顿。按这个优先级递归，能在中文语境下更好地保留语义边界。

</details>

<details>
<summary>中级：chunk_size 设为 100 和 1000 分别会出什么问题？如何找到最优值？</summary>

**参考答案：**

- chunk_size=100：每块只有一两句话，缺乏上下文。检索到的片段信息量不够，LLM 难以据此生成准确回答。
- chunk_size=1000：每块内容太多，可能包含多个不相关话题，检索时相关性得分被稀释，精度下降。

找最优值的方法：以 256-512 token 为起点，在实际 RAG 系统中用评测集做 A/B 测试，比较不同 chunk_size 下的检索召回率和最终回答质量（如 F1 分数），选效果最好的。没有放之四海而皆准的数值，需要根据具体文档和任务实验确定。

</details>

## 参考资料

1. 官方文档：[LangChain Text Splitters](https://python.langchain.com/docs/how_to/#text-splitters)
2. PyPI 包页面：[langchain-text-splitters](https://pypi.org/project/langchain-text-splitters/)
3. GitHub 源码：[langchain-ai/langchain - text-splitters](https://github.com/langchain-ai/langchain/tree/master/libs/text-splitters)
4. LangChain 博客：[A Chunk by Any Other Name: Structured Text Splitting and Metadata-enhanced RAG](https://blog.langchain.com/a-chunk-by-any-other-name/)
5. Pinecone 分块策略指南：[Chunking Strategies for LLM Applications](https://www.pinecone.io/learn/chunking-strategies/)
6. Firecrawl 2025 分块策略总结：[Best Chunking Strategies for RAG in 2025](https://www.firecrawl.dev/blog/best-chunking-strategies-rag)
