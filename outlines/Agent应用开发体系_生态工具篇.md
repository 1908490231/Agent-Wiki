# Agent应用开发体系 - 生态工具篇

> 本篇聚焦 Agent 开发生态中的辅助工具与服务，包括可观测性工具、OCR 服务、语音处理、评估体系以及数据处理工具。
>
> **不包含**：AI 开发框架/Agent SDK（见工程篇）、模型本身（见模型算法篇）、开发流程/CI/CD（见工程实践篇）

---

## 归类导航说明

### 子目录映射表

| outline 二级主题 | 对应 content 子目录 | 归类范围 |
|---|---|---|
| 一、可观测性工具 | `content/05_ecosystem/observability/` | Trace、监控、评估联动、Prompt 管理平台 |
| 二、Agent 评估体系 | `content/05_ecosystem/evaluation/` | 评估框架、评测平台、RAG 评估、行为评估工具 |
| 三、OCR 服务 | `content/05_ecosystem/ocr/` | 文档 OCR、版面分析、结构化提取 |
| 四、语音处理 | `content/05_ecosystem/speech/` | ASR、TTS、语音对话 Agent、Whisper 等 |
| 五、数据处理工具 | `content/05_ecosystem/data-processing/` | 文档解析、文本分割、Embedding 服务、清洗与预处理 |
| 六、开发辅助工具 | `content/05_ecosystem/dev-tools/` | Prompt 管理、低代码平台、API 代理、索引工具 |

### 什么情况下优先归生态工具篇

1. 当知识点主要关注“有哪些外部平台、工具、服务可以辅助 Agent 系统建设”时，优先归生态工具篇。
2. 当重点是评测平台、观测平台、OCR 服务、语音工具、数据处理链路，而不是底层模型原理或开发框架时，优先归本篇。
3. 若同一概念既可从模型角度解释，也可从工具使用角度解释，本篇优先收纳“工具化落地”那一侧。
4. 只要该知识点更像“配套工具 / 平台能力 / 生态产品”，而不是 Agent 架构本身，就优先归这里。

### 常见混淆项

| 容易混淆的概念 | 本篇归类 | 不归本篇的情况 | 判断关键点 |
|---|---|---|---|
| Eval-driven Testing vs 评估框架 / 平台 | RAGAS、DeepEval、TruLens、Promptfoo 等放 `evaluation/` | 测试流程设计、回归策略放工程实践篇 `testing/` | 看重点是“工具平台”还是“测试方法” |
| OCR / 语音模型工具 vs 多模态模型 | Whisper、TTS、OCR 服务、文档解析工具放本篇 | 多模态模型结构、训练与统一架构放模型算法篇 | 看重点是工具使用还是模型能力原理 |
| Whisper | 统一放 `speech/` | 不放 `ocr/`，也不优先放模型算法篇 | Whisper 在本项目中按语音处理工具归类 |
| 可观测性平台 vs 工程实践监控流程 | LangFuse、LangSmith、Weave 等平台放 `observability/` | 监控接入流程、上线治理方法放工程实践篇 | 看重点是平台能力还是工程流程 |

### 最低锚点规则

- 二级标题代表 `content/05_ecosystem/*` 的子目录主题。
- 三级标题代表可直接生成卡片的工具、平台、服务或比较项。
- 若没有同名三级条目，但已有可挂靠的二级主题，应先补三级锚点再继续。

### 扩展工具锚点

新增工具类知识点时，可优先挂靠以下扩展容器：

- `二、Agent 评估体系`：承载新评测框架、基准工具、评估平台
- `四、语音处理`：承载新 ASR/TTS/Realtime Voice 技术工具
- `五、数据处理工具`：承载解析、切分、Embedding、清洗链路工具
- `六、开发辅助工具`：承载低代码平台、网关代理、Prompt 管理与其他辅助设施

### 粒度说明

- **二级标题 = 子目录主题**，用于决定最终写入哪个 `content/05_ecosystem/*` 子目录。
- **三级标题 = 最小卡片单位**，可以是一种工具、一类平台、一个服务或一组对比主题。
- 列表项用于定义该卡片至少应覆盖的能力范围、边界与选型信息。

---

## 一、可观测性工具（Observability）

### 1.1 LangFuse
- 开源 LLM 可观测性平台
- Trace 追踪与调试
- Prompt 管理与版本控制
- 评估与评分
- 成本监控
- 自部署支持

### 1.2 LangSmith
- LangChain 官方可观测性平台
- 运行追踪与调试
- 数据集管理
- 在线评估
- Hub 集成（Prompt 分享）

### 1.3 Weave（Weights & Biases）
- W&B 的 LLM 可观测性工具
- 实验追踪
- 数据版本管理
- 模型评估
- 团队协作

### 1.4 BrainTrust
- LLM 评估与可观测性平台
- 在线评估框架
- Prompt 迭代管理
- A/B 测试支持

### 1.5 Arize
- AI 可观测性平台
- 模型监控
- 漂移检测
- 性能分析
- 根因分析

### 1.6 可观测性工具横向对比
- 功能对比维度：追踪、评估、Prompt 管理、成本监控、自部署
- 选型建议

---

## 二、Agent 评估体系（Evaluation）

### 2.1 评估框架
- 评估指标设计
    - 准确性（Accuracy）
    - 相关性（Relevance）
    - 忠实度（Faithfulness）
    - 有害性（Harmfulness）
    - 延迟（Latency）
    - 成本（Cost）
- LLM-as-Judge（大模型做评审）
- 人工评估 vs 自动评估
- 评估数据集构建

### 2.2 RAG 评估
- 检索质量评估：召回率、精确率、MRR
- 生成质量评估：RAGAS 框架
- 端到端评估

### 2.3 Agent 行为评估
- 工具调用准确率
- 任务完成率
- 多步骤推理正确性
- 安全性评估

### 2.4 评估工具
- RAGAS
- DeepEval
- TruLens
- Promptfoo
- OpenAI Evals

### 2.5 评测平台与框架边界（扩展锚点）
- 平台型工具 vs 轻量评估库
- 在线评测 vs 离线评测
- 与工程实践测试流程的边界

---

## 三、OCR 服务

### 3.1 MinerU
- 文档解析与提取
- PDF/Word/图片解析
- 表格提取
- 版式分析
- 与 RAG 管道集成

### 3.2 多模态模型 OCR
- 使用视觉语言模型进行 OCR
- GPT-4V / Qwen-VL 等模型的 OCR 能力
- 优劣势与适用场景

### 3.3 传统 OCR 工具
- Tesseract
- PaddleOCR
- EasyOCR
- 适用场景与对比

---

## 四、语音处理

### 4.1 Whisper（OpenAI）
- 语音识别（ASR）
- 多语言支持
- 本地部署方案
- 流式识别
- 与 Agent 系统集成

### 4.2 语音合成（TTS）
- OpenAI TTS
- Edge TTS
- CosyVoice（阿里）
- Fish Speech
- 语音克隆技术

### 4.3 语音对话 Agent
- 实时语音交互架构
- VAD（语音活动检测）
- 语音到语音的端到端方案
- WebRTC 集成

### 4.4 Speech-to-Text / Text-to-Speech 对比（扩展锚点）
- ASR 与 TTS 的角色差异
- 流式与离线模式
- 语音系统选型维度

---

## 五、数据处理工具

### 5.1 文档解析工具
- Unstructured：多格式文档解析
- PyPDF / PDFPlumber：PDF 解析
- python-docx：Word 文档处理
- 文档解析在 RAG 中的应用

### 5.2 文本分割工具
- LangChain Text Splitters
- 递归字符分割
- 语义分割
- 自定义分割策略

### 5.3 Embedding 模型与服务
- OpenAI Embedding
- BGE 系列（BAAI）
- M3E
- Jina Embedding
- Embedding 模型选型与对比

### 5.4 数据清洗与预处理
- 文本清洗策略
- 数据去重
- 数据质量评估
- 数据标注工具

---

## 六、开发辅助工具

### 6.1 Prompt 管理工具
- PromptLayer
- Humanloop
- Prompt 版本控制最佳实践

### 6.2 知识库管理工具
- Dify
- FastGPT
- MaxKB
- 低代码 Agent 平台对比

### 6.3 API 网关与代理
- LiteLLM：统一 LLM API 代理
- OpenRouter：多模型路由
- One API：API 聚合管理

### 6.4 向量化与索引工具
- FAISS：高效向量检索库
- Annoy
- HNSWlib
- 向量索引算法对比
