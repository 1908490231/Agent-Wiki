# Agent-Wiki

> 一站式 Agent 应用开发知识库 —— 从零开始搞懂 AI Agent

## 这个项目是什么？

如果你对 AI Agent 感兴趣，但面对铺天盖地的概念和工具不知从何下手，这个知识库就是为你准备的。

Agent-Wiki 把 Agent 应用开发涉及的知识拆成一张张知识卡片，每张卡片讲清一个知识点。用大白话解释概念，配上图解和伪代码示例，让你不用翻论文也能看懂。

## 看完你能学到什么？

- **搞懂核心概念** —— RAG、Tool Use、Function Calling、MCP 这些高频词到底是什么意思
- **认识主流工具** —— LangChain、LlamaIndex、AutoGen 等框架各自能干嘛、怎么选
- **理解设计模式** —— ReAct、Plan-and-Solve、多 Agent 协作，Agent 到底是怎么"思考"和"行动"的
- **了解工程实践** —— 测试、部署、安全、性能优化，把 Agent 从 Demo 变成产品需要关注什么
- **掌握 Prompt 技巧** —— 从提示词基础到 Chain-of-Thought、上下文工程，写出更好的提示词

## 每张卡片长什么样？

每张卡片都按统一结构组织，一般包含：

- **通俗解释** —— 用大白话讲清概念，不照搬官方定义
- **原理图解** —— Mermaid 流程图 / 架构图，看图就能理解
- **代码示例** —— 展示核心逻辑和关键实现，帮你建立直观理解
- **应用场景** —— 什么时候该用、常见的坑有哪些
- **同类对比** —— 类似工具 / 方案的优劣对比，帮你做选择
- **练习题** —— 巩固理解，从概念到应用逐步深入

## 知识体系总览

整个知识库分成 6 大板块，覆盖从理论到实战的完整链路：

| 板块 | 篇数 | 你会学到 |
|------|:----:|---------|
| [工程篇](content/01_engineering/) | 39 | Agent 核心概念（RAG、MCP、Memory）、主流开发框架、数据库、Web 框架 |
| [模型算法篇](content/02_models/) | 33 | 大模型原理、GPT/开源模型系列、训练技术、多模态、模型部署与选型 |
| [设计模式篇](content/03_patterns/) | 19 | Agent 经典范式（ReAct、反思）、单/多 Agent 模式、企业级架构 |
| [工程实践篇](content/04_practices/) | 25 | AI 辅助开发、测试策略、CI/CD、安全合规、性能优化 |
| [生态工具篇](content/05_ecosystem/) | 24 | 可观测性平台、评估工具、OCR、语音处理、数据处理工具链 |
| [Prompt Engineering 篇](content/06_prompt-engineering/) | 29 | 提示词基础、上下文工程、思维链、场景模板 |

## 不知道从哪开始？

如果你是新手，推荐从这几张卡片入门：

| 推荐卡片 | 难度 | 一句话介绍 |
|---------|:----:|---------|
| [RAG（检索增强生成）](content/01_engineering/core-concepts/rag.md) | ⭐⭐⭐ | 让大模型能查资料再回答，大幅减少"胡说八道" |
| [ReAct（推理+行动）](content/03_patterns/agent-paradigms/react.md) | ⭐⭐⭐ | Agent 最经典的范式——边想边做，像人一样解决问题 |
| [提示词的基本结构](content/06_prompt-engineering/prompt-basics/prompt-structure.md) | ⭐⭐ | 搞懂 System Prompt、User Prompt 这些基本概念 |
| [LangChain](content/01_engineering/frameworks/langchain.md) | ⭐⭐⭐ | 最流行的 Agent 开发框架，快速上手 |
| [Chain-of-Thought](content/06_prompt-engineering/advanced-techniques/chain-of-thought.md) | ⭐⭐ | 让大模型"一步一步想"的经典技巧 |
| [模型架构演进](content/02_models/fundamentals/model-architecture-evolution.md) | ⭐⭐⭐ | 从 RNN 到 Transformer，理解现代大模型的来龙去脉 |

> **难度说明**：⭐ 零基础可看 · ⭐⭐ 入门级 · ⭐⭐⭐ 实战级 · ⭐⭐⭐⭐ 进阶原理 · ⭐⭐⭐⭐⭐ 深度优化

## 完整目录

所有卡片的完整索引（含分类导航、最近更新）：

**[查看完整导航索引 → docs/index.md](docs/index.md)**

## 内容结构

```
content/
├── 01_engineering/          # 工程篇
│   ├── core-concepts/       #   核心概念（RAG、MCP、Tool Use、Memory）
│   ├── frameworks/          #   AI 开发框架（LangChain、LlamaIndex 等）
│   ├── agent-sdks/          #   Agent SDK
│   ├── databases/           #   数据库（向量库、关系库）
│   ├── web-frameworks/      #   Web 框架
│   ├── message-queues/      #   消息队列
│   └── containers/          #   容器化（Docker、K8s）
├── 02_models/               # 模型算法篇
│   ├── fundamentals/        #   大模型基础理论
│   ├── model-series/        #   主流模型系列（GPT、开源生态）
│   ├── training/            #   训练技术
│   ├── multimodal/          #   多模态
│   ├── core-techniques/     #   核心技术（注意力、推理优化）
│   ├── deployment/          #   部署（vLLM、云服务、本地部署）
│   ├── evaluation/          #   评估与选型
│   └── frontier/            #   前沿进展
├── 03_patterns/             # 设计模式篇
│   ├── agent-paradigms/     #   经典范式（ReAct、反思、规划）
│   ├── single-agent/        #   单 Agent 模式
│   ├── multi-agent/         #   多 Agent 协作
│   ├── enterprise/          #   企业级架构
│   └── selection-guide/     #   模式选型指南
├── 04_practices/            # 工程实践篇
│   ├── ai-dev-workflow/     #   AI 辅助开发流程
│   ├── testing/             #   测试策略
│   ├── cicd/                #   CI/CD
│   ├── security/            #   安全合规
│   ├── performance/         #   性能优化
│   └── project-management/  #   项目管理
├── 05_ecosystem/            # 生态工具篇
│   ├── observability/       #   可观测性工具（Langfuse、LangSmith 等）
│   ├── evaluation/          #   Agent 评估体系
│   ├── ocr/                 #   OCR 工具
│   ├── speech/              #   语音处理
│   ├── data-processing/     #   数据处理
│   └── dev-tools/           #   开发工具
└── 06_prompt-engineering/   # Prompt Engineering 篇
    ├── prompt-basics/       #   提示词基础
    ├── context-engineering/  #   上下文工程
    ├── advanced-techniques/  #   进阶技巧（CoT、ToT）
    ├── specialized-techniques/ # 专项技巧
    ├── optimization/        #   优化方法
    └── templates/           #   场景模板
```

## 内容大纲

每个板块都有对应的内容大纲，描述该板块的完整知识范围：

| 板块 | 大纲文件 |
|------|---------|
| 工程篇 | [`outlines/Agent应用开发体系_工程篇.md`](outlines/Agent应用开发体系_工程篇.md) |
| 模型算法篇 | [`outlines/Agent应用开发体系_模型算法篇.md`](outlines/Agent应用开发体系_模型算法篇.md) |
| 设计模式篇 | [`outlines/Agent应用开发体系_设计模式篇.md`](outlines/Agent应用开发体系_设计模式篇.md) |
| 工程实践篇 | [`outlines/Agent应用开发体系_工程实践篇.md`](outlines/Agent应用开发体系_工程实践篇.md) |
| 生态工具篇 | [`outlines/Agent应用开发体系_生态工具篇.md`](outlines/Agent应用开发体系_生态工具篇.md) |
| Prompt Engineering 篇 | [`outlines/Agent应用开发体系_PromptEngineering篇.md`](outlines/Agent应用开发体系_PromptEngineering篇.md) |

## 许可证

本项目采用开源许可证，详情见 [LICENSE](LICENSE)。
