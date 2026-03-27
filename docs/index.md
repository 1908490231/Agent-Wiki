# Agent-Wiki 知识卡片导航索引

## 统计

总卡片数：**169** | 工程篇：39 | 模型算法篇：33 | 设计模式篇：19 | 工程实践篇：25 | 生态工具篇：24 | Prompt Engineering 篇：29

## 最近更新

- [OpenAI Agents SDK](../content/01_engineering/agent-sdks/openai-agents-sdk.md) - ⭐⭐⭐ - OpenAI 官方开源的轻量级多 Agent 编排框架，通过 Handoff、Guardrail、Tracing 三大原语构建生产级 Agent 应用。 (2026-03-26)
- [MCP（Model Context Protocol）](../content/01_engineering/core-concepts/mcp.md) - ⭐⭐⭐ - Anthropic 提出的开放标准协议，为 AI 应用提供连接外部工具与数据源的统一接口。 (2026-03-26)
- [Weaviate（AI 原生向量数据库）](../content/01_engineering/databases/weaviate.md) - ⭐⭐⭐ - 开源 AI 原生向量数据库，内置向量化模块和生成模块，支持多模态搜索与混合检索。 (2026-03-26)
- [AutoGen（微软多Agent框架）](../content/01_engineering/frameworks/autogen.md) - ⭐⭐⭐ - 微软开源的多智能体协作框架，通过异步消息驱动多个 Agent 角色分工完成复杂任务。 (2026-03-26)
- [AutoGPT（自主Agent平台）](../content/01_engineering/frameworks/autogpt.md) - ⭐⭐⭐ - 开源自主 Agent 平台，支持可视化搭建和部署持续运行的 AI Agent 工作流。 (2026-03-26)
- [Haystack（AI 应用框架）](../content/01_engineering/frameworks/haystack.md) - ⭐⭐⭐ - deepset 开源的 AI 编排框架，用模块化管道构建 RAG、语义搜索和 Agent 应用。 (2026-03-26)
- [LlamaIndex（数据框架）](../content/01_engineering/frameworks/llamaindex.md) - ⭐⭐⭐ - 专注于数据连接与检索的 LLM 数据框架，是构建 RAG 应用的核心工具。 (2026-03-26)
- [Phidata / Agno（Agent 构建框架）](../content/01_engineering/frameworks/phidata.md) - ⭐⭐ - 原名 Phidata，现更名为 Agno，用纯 Python 构建多模态 Agent 的轻量框架，开箱即用。 (2026-03-26)
- [RabbitMQ（消息代理）](../content/01_engineering/message-queues/rabbitmq.md) - ⭐⭐ - 基于 AMQP 协议的开源消息代理，用于应用间异步通信和任务分发。 (2026-03-26)
- [Redis（内存数据库/缓存）](../content/01_engineering/message-queues/redis.md) - ⭐⭐ - 高性能内存键值数据库，支持缓存、消息队列、向量搜索，是 AI Agent 系统的核心基础设施。 (2026-03-26)

## 目录结构导航

```
content/
├── 01_engineering（工程篇）
│   ├── agent-sdks/  (Agent SDK, 3 篇)
│   ├── containers/  (容器虚拟化, 2 篇)
│   ├── core-concepts/  (核心概念, 10 篇)
│   ├── databases/  (数据库架构, 7 篇)
│   ├── frameworks/  (AI 开发框架, 11 篇)
│   ├── message-queues/  (缓存消息队列, 4 篇)
│   └── web-frameworks/  (Web 开发架构, 2 篇)
├── 02_models（模型算法篇）
│   ├── core-techniques/  (核心技术, 4 篇)
│   ├── data-processing/  (数据处理工具, 0 篇，待补充)
│   ├── deployment/  (模型部署与服务化, 9 篇)
│   ├── dev-tools/  (开发工具, 0 篇，待补充)
│   ├── evaluation/  (评估体系, 3 篇)
│   ├── frontier/  (前沿方向, 5 篇)
│   ├── fundamentals/  (LLM 基础理论, 2 篇)
│   ├── model-series/  (主流模型系列, 3 篇)
│   ├── multimodal/  (多模态, 3 篇)
│   ├── observability/  (可观测性工具, 0 篇，待补充)
│   ├── ocr/  (OCR 服务, 0 篇，待补充)
│   ├── speech/  (语音处理, 0 篇，待补充)
│   └── training/  (训练技术, 4 篇)
├── 03_patterns（设计模式篇）
│   ├── agent-paradigms/  (Agent 经典范式, 3 篇)
│   ├── enterprise/  (企业级架构模式, 3 篇)
│   ├── multi-agent/  (多 Agent 协作模式, 6 篇)
│   ├── selection-guide/  (模式选型指南, 2 篇)
│   └── single-agent/  (单 Agent 模式, 5 篇)
├── 04_practices（工程实践篇）
│   ├── ai-dev-workflow/  (AI 辅助开发流程, 4 篇)
│   ├── cicd/  (CI/CD, 4 篇)
│   ├── performance/  (性能优化, 3 篇)
│   ├── project-management/  (项目管理, 3 篇)
│   ├── security/  (安全与合规, 5 篇)
│   └── testing/  (测试方法, 6 篇)
├── 05_ecosystem（生态工具篇）
│   ├── data-processing/  (数据处理工具, 4 篇)
│   ├── dev-tools/  (开发工具, 4 篇)
│   ├── evaluation/  (评估体系, 4 篇)
│   ├── observability/  (可观测性工具, 6 篇)
│   ├── ocr/  (OCR 服务, 3 篇)
│   └── speech/  (语音处理, 3 篇)
└── 06_prompt-engineering（Prompt Engineering 篇）
    ├── advanced-techniques/  (进阶推理技巧, 6 篇)
    ├── context-engineering/  (上下文工程, 5 篇)
    ├── optimization/  (优化与评估, 3 篇)
    ├── prompt-basics/  (提示词基础, 5 篇)
    ├── specialized-techniques/  (专项提示技巧, 5 篇)
    └── templates/  (场景模板, 5 篇)
```

## 分篇导航（按元数据）

按卡片 YAML 头部的 `category` 字段分组：

### 一、工程篇（engineering）

**核心概念**

- [Agent Retry（重试机制）](../content/01_engineering/core-concepts/agent-retry.md) - ⭐⭐ - Agent 调用外部服务失败后，按策略自动重新尝试的容错机制。
- [Function Calling（函数调用）](../content/01_engineering/core-concepts/function-calling.md) - ⭐⭐ - 让大语言模型在需要时生成结构化调用指令，由外部系统执行真实函数并返回结果的机制。
- [Hooks（钩子机制）](../content/01_engineering/core-concepts/hooks.md) - ⭐⭐ - Agent 执行流程中的"哨卡"，在关键节点自动触发回调函数，实现监控、日志等扩展功能。
- [Human-in-the-Loop（人机协同）](../content/01_engineering/core-concepts/human-in-the-loop.md) - ⭐⭐ - AI 流程在关键决策点暂停，由人类审核后再继续执行。
- [MCP（Model Context Protocol）](../content/01_engineering/core-concepts/mcp.md) - ⭐⭐⭐ - Anthropic 提出的开放标准协议，为 AI 应用提供连接外部工具与数据源的统一接口。
- [Memory（Agent 记忆机制）](../content/01_engineering/core-concepts/memory.md) - ⭐⭐⭐ - Agent 通过分层记忆系统实现会话内连贯和跨会话知识积累。
- [RAG（检索增强生成）](../content/01_engineering/core-concepts/rag.md) - ⭐⭐⭐ - 让 LLM 先查资料再回答，大幅降低幻觉并支持知识实时更新的核心架构。
- [State Management（Agent 状态管理）](../content/01_engineering/core-concepts/state-management.md) - ⭐⭐⭐ - Agent 执行过程中对共享信息的定义、更新、传递和持久化管理机制。
- [Tool Use（工具使用）](../content/01_engineering/core-concepts/tool-use.md) - ⭐⭐ - LLM 通过调用外部工具突破自身能力边界的核心机制。
- [上下文工程（Context Engineering）](../content/01_engineering/core-concepts/context-engineering.md) - ⭐⭐⭐ - 动态构建和管理 LLM 输入信息的系统化方法，是 Prompt Engineering 的自然演进

**AI 开发框架**

- [AgentScope（多Agent平台）](../content/01_engineering/frameworks/agentscope.md) - ⭐⭐⭐ - 阿里开源的多 Agent 开发框架，消息驱动架构，原生支持分布式部署、容错和可视化调试。
- [AutoGPT（自主Agent平台）](../content/01_engineering/frameworks/autogpt.md) - ⭐⭐⭐ - 开源自主 Agent 平台，支持可视化搭建和部署持续运行的 AI Agent 工作流。
- [AutoGen（微软多Agent框架）](../content/01_engineering/frameworks/autogen.md) - ⭐⭐⭐ - 微软开源的多智能体协作框架，通过异步消息驱动多个 Agent 角色分工完成复杂任务。
- [CAMEL-AI（多Agent通信框架）](../content/01_engineering/frameworks/camel-ai.md) - ⭐⭐⭐ - 通过角色扮演驱动多智能体自主对话协作的开源框架，首创 Inception Prompting 机制。
- [DSPy（声明式 LLM 编程框架）](../content/01_engineering/frameworks/dspy.md) - ⭐⭐⭐ - 斯坦福开源的声明式 LLM 编程框架，用 Python 代码代替手写提示词，通过优化器自动编译出高质量 Prompt。
- [Haystack（AI 应用框架）](../content/01_engineering/frameworks/haystack.md) - ⭐⭐⭐ - deepset 开源的 AI 编排框架，用模块化管道构建 RAG、语义搜索和 Agent 应用。
- [LangChain（LLM 应用开发框架）](../content/01_engineering/frameworks/langchain.md) - ⭐⭐⭐ - 用管道符把 LLM、工具、提示词像乐高一样拼在一起的编排框架，快速构建 AI 应用。
- [LangGraph](../content/01_engineering/frameworks/langgraph.md) - ⭐⭐⭐ - LangChain 生态下的图编排框架，用有向图组织 Agent 多步骤流程，原生支持分支、循环和中断恢复。
- [Letta（有状态Agent框架）](../content/01_engineering/frameworks/letta.md) - ⭐⭐⭐ - 基于 MemGPT 论文的有状态 Agent 框架，Agent 能自编辑记忆、跨会话学习和持久化状态。
- [LlamaIndex（数据框架）](../content/01_engineering/frameworks/llamaindex.md) - ⭐⭐⭐ - 专注于数据连接与检索的 LLM 数据框架，是构建 RAG 应用的核心工具。
- [Phidata / Agno（Agent 构建框架）](../content/01_engineering/frameworks/phidata.md) - ⭐⭐ - 原名 Phidata，现更名为 Agno，用纯 Python 构建多模态 Agent 的轻量框架，开箱即用。

**Agent SDK**

- [Claude Agent SDK（Anthropic）](../content/01_engineering/agent-sdks/claude-agent-sdk.md) - ⭐⭐⭐ - Anthropic 官方 Agent 编排框架，内置工具集 + 流式循环 + MCP 扩展，支持 Python 和 TypeScript。
- [Google ADK（Agent Development Kit）](../content/01_engineering/agent-sdks/google-adk.md) - ⭐⭐⭐ - Google 开源的 Agent 开发套件，代码优先、模型无关，原生支持多 Agent 编排。
- [OpenAI Agents SDK](../content/01_engineering/agent-sdks/openai-agents-sdk.md) - ⭐⭐⭐ - OpenAI 官方开源的轻量级多 Agent 编排框架，通过 Handoff、Guardrail、Tracing 三大原语构建生产级 Agent 应用。

**数据库架构**

- [Chroma（向量数据库）](../content/01_engineering/databases/chroma.md) - ⭐⭐ - 轻量级开源向量数据库，pip 一装即用，专为 AI 应用的语义搜索和 RAG 场景设计。
- [Milvus（向量数据库）](../content/01_engineering/databases/milvus.md) - ⭐⭐⭐ - 开源云原生向量数据库，专为 AI 应用设计，支持 PB 级向量相似度搜索。
- [MongoDB（文档数据库）](../content/01_engineering/databases/mongodb.md) - ⭐⭐ - 文档型 NoSQL 数据库，用 JSON 风格存储数据，灵活无固定表结构，支持向量搜索。
- [MySQL（关系型数据库）](../content/01_engineering/databases/mysql.md) - ⭐⭐ - 全球最流行的开源关系型数据库，Agent 应用中常用于存储对话记录、用户信息和执行状态。
- [Pinecone（云原生向量数据库）](../content/01_engineering/databases/pinecone.md) - ⭐⭐ - 全托管云原生向量数据库，Serverless 架构零运维，适合快速搭建语义搜索和 RAG 应用。
- [Qdrant（向量搜索引擎）](../content/01_engineering/databases/qdrant.md) - ⭐⭐⭐ - 基于 Rust 的高性能向量搜索引擎，以过滤优先设计和极致性能著称，适合 RAG 和语义搜索场景。
- [Weaviate（AI 原生向量数据库）](../content/01_engineering/databases/weaviate.md) - ⭐⭐⭐ - 开源 AI 原生向量数据库，内置向量化模块和生成模块，支持多模态搜索与混合检索。

**Web 开发架构**

- [FastAPI（高性能Web框架）](../content/01_engineering/web-frameworks/fastapi.md) - ⭐⭐ - 基于类型注解的高性能 Python Web 框架，自动生成 API 文档，原生支持异步，是 AI 应用暴露接口的主流选择。
- [Uvicorn（ASGI 服务器）](../content/01_engineering/web-frameworks/uvicorn.md) - ⭐⭐ - 轻量级高性能 ASGI 服务器，运行 FastAPI、Starlette 等异步框架的首选。

**缓存消息队列**

- [Apache Kafka（分布式流处理平台）](../content/01_engineering/message-queues/kafka.md) - ⭐⭐⭐ - 分布式流处理平台，支持百万级吞吐量的消息传输和实时数据流处理。
- [Celery（分布式任务队列）](../content/01_engineering/message-queues/celery.md) - ⭐⭐⭐ - Python 分布式任务队列框架，支持异步任务执行、定时调度和多 Worker 水平扩展。
- [RabbitMQ（消息代理）](../content/01_engineering/message-queues/rabbitmq.md) - ⭐⭐ - 基于 AMQP 协议的开源消息代理，用于应用间异步通信和任务分发。
- [Redis（内存数据库/缓存）](../content/01_engineering/message-queues/redis.md) - ⭐⭐ - 高性能内存键值数据库，支持缓存、消息队列、向量搜索，是 AI Agent 系统的核心基础设施。

**容器虚拟化**

- [Docker（容器化平台）](../content/01_engineering/containers/docker.md) - ⭐⭐ - 轻量级容器化平台，把应用和依赖打包成独立容器，实现一次构建、到处运行。
- [Kubernetes（容器编排平台）](../content/01_engineering/containers/kubernetes.md) - ⭐⭐⭐ - 开源容器编排平台，自动化部署、扩缩容和管理容器化应用，是云原生领域的事实标准。

### 二、模型算法篇（models）

**LLM 基础理论**

- [模型架构演进（Model Architecture Evolution）](../content/02_models/fundamentals/model-architecture-evolution.md) - ⭐⭐⭐ - 从 RNN 到 Transformer 再到 MoE，理解现代大模型架构的演进脉络
- [预训练语言模型（Pre-trained Language Model）](../content/02_models/fundamentals/pretrained-language-models.md) - ⭐⭐⭐ - 先在海量文本上学通用语言知识，再用少量数据适配具体任务的两阶段训练范式

**主流模型系列**

- [BERT 系列模型](../content/02_models/model-series/bert-series.md) - ⭐⭐⭐ - BERT 及其派生模型的核心原理、架构差异与选型指南
- [GPT 系列模型（OpenAI）](../content/02_models/model-series/gpt-series.md) - ⭐⭐⭐ - OpenAI 从 GPT-1 到 GPT-5 的完整演进：参数扩展、对齐微调、多模态统一、推理增强四个阶段
- [开源大模型生态（Open-source LLM Ecosystem）](../content/02_models/model-series/open-source-llm-ecosystem.md) - ⭐⭐⭐ - 主流开源大模型系列总览，覆盖选型、架构差异、许可证与部署工具链

**核心技术**

- [位置编码（Positional Encoding）](../content/02_models/core-techniques/positional-encoding.md) - ⭐⭐⭐⭐ - Transformer 中让模型理解词序的关键机制，从正弦编码到 RoPE、ALiBi 的演进与对比。
- [注意力优化（Attention Optimization）](../content/02_models/core-techniques/attention-optimization.md) - ⭐⭐⭐⭐ - 通过分块计算、KV 共享、稀疏模式等手段优化 Transformer 注意力的速度和内存瓶颈。
- [长上下文处理（Long Context Handling）](../content/02_models/core-techniques/long-context-handling.md) - ⭐⭐⭐ - 让大语言模型突破固定上下文窗口限制、有效利用超长输入的一组核心技术
- [高效推理（Efficient Inference）](../content/02_models/core-techniques/efficient-inference.md) - ⭐⭐⭐ - 通过量化、缓存优化、解码加速等手段，降低大模型推理的显存占用和延迟

**训练技术**

- [对齐技术（Alignment）](../content/02_models/training/alignment-techniques.md) - ⭐⭐⭐ - 通过人类或 AI 反馈让模型行为符合人类价值观的训练技术体系
- [持续学习（Continual Learning）](../content/02_models/training/continual-learning.md) - ⭐⭐⭐ - 让模型持续吸收新知识而不遗忘旧知识的训练范式，核心挑战是灾难性遗忘。
- [指令微调（Instruction Tuning）](../content/02_models/training/instruction-tuning.md) - ⭐⭐⭐ - 用"指令-回答"数据对预训练模型进行微调，让模型学会听懂并执行人类指令。
- [预训练技术（Pretraining Techniques）](../content/02_models/training/pretraining-techniques.md) - ⭐⭐⭐⭐ - 大规模语言模型从零开始获取通用语言能力的核心训练技术体系

**多模态**

- [统一多模态模型（Unified Multimodal Models）](../content/02_models/multimodal/unified-multimodal-models.md) - ⭐⭐⭐ - 用单一模型统一处理和生成文本、图像、音频、视频等多种模态的架构范式
- [视觉定位与检测（Visual Grounding & Detection）](../content/02_models/multimodal/visual-grounding-detection.md) - ⭐⭐⭐ - 用自然语言告诉 AI 要找什么物体，AI 在图像中定位并框出它们，无需预定义类别。
- [视觉语言模型（Vision-Language Models, VLM）](../content/02_models/multimodal/vision-language-models.md) - ⭐⭐⭐ - 同时理解图像和文本并生成语言输出的多模态模型，是给 LLM 装上"眼睛"的核心技术

**模型部署与服务化**

- [AI 硬件概述（Hardware Overview）](../content/02_models/deployment/hardware-overview.md) - ⭐⭐ - AI 计算硬件的类型、核心指标与选型逻辑，帮助开发者理解"用什么跑模型"。
- [FlagOS（模型服务平台）](../content/02_models/deployment/flagos.md) - ⭐⭐⭐ - 智源开源的大模型系统软件栈，支持多种芯片一键部署推理服务
- [SGLang（高效LLM推理引擎）](../content/02_models/deployment/sglang.md) - ⭐⭐⭐ - 高性能 LLM 推理服务框架，通过 RadixAttention 前缀复用和结构化输出约束大幅提升推理效率。
- [vLLM（高性能LLM推理引擎）](../content/02_models/deployment/vllm.md) - ⭐⭐⭐ - 基于 PagedAttention 的高性能 LLM 推理引擎，显著提升吞吐量和内存利用率。
- [云端模型服务概述](../content/02_models/deployment/cloud-services-overview.md) - ⭐⭐ - 通过 API 调用云端大模型，无需自建 GPU 集群，按量付费、即开即用。
- [推理引擎（Inference Engines）](../content/02_models/deployment/inference-engines.md) - ⭐⭐⭐ - 让大语言模型跑得更快、更省显存的专用软件引擎，是模型从训练到上线的关键一环
- [本地模型概述（Local Model Deployment）](../content/02_models/deployment/local-models-overview.md) - ⭐⭐ - 在个人电脑或私有服务器上运行大语言模型的核心概念与工具选择。
- [部署架构（Deployment Architecture）](../content/02_models/deployment/deployment-architecture.md) - ⭐⭐⭐ - 大模型从训练完成到上线服务的推理部署架构体系，覆盖内存管理、调度和扩展
- [部署系统（Deployment System）](../content/02_models/deployment/deployment-system.md) - ⭐⭐⭐ - 大模型从"能跑通"到"能上线"的完整工程体系，涵盖硬件、引擎、服务、调度四层

**评估体系**

- [按场景选型（模型选择指南）](../content/02_models/evaluation/model-selection-by-scenario.md) - ⭐⭐⭐ - 根据任务场景在性能、成本、延迟三角中找到最优模型组合
- [按规模选型（Model Selection by Parameter Size）](../content/02_models/evaluation/model-selection-by-scale.md) - ⭐⭐⭐ - 根据参数规模选择合适的 LLM，平衡性能、成本和硬件需求
- [模型评估方法（Model Evaluation Methods）](../content/02_models/evaluation/model-evaluation-methods.md) - ⭐⭐⭐ - 通过标准化基准和量化指标，系统衡量大语言模型在各维度上的真实能力

**前沿方向**

- [Agent 与工具使用（Tool-Augmented LLM）](../content/02_models/frontier/agent-and-tool-usage.md) - ⭐⭐⭐ - LLM 通过工具调用扩展能力边界，从"只能说"进化到"能做事"的核心机制。
- [技术趋势（Technology Trends）](../content/02_models/frontier/technology-trends.md) - ⭐⭐⭐ - 从效率、能力、安全、应用四个维度，梳理 2025-2026 年 AI 与大模型的前沿发展方向。
- [推理增强（Reasoning Enhancement）](../content/02_models/frontier/reasoning-enhancement.md) - ⭐⭐⭐ - 通过训练时强化学习和推理时计算扩展，让 LLM 学会"先想再答"的推理范式
- [混合专家模型（Mixture of Experts, MoE）](../content/02_models/frontier/mixture-of-experts.md) - ⭐⭐⭐ - 通过路由器动态选择少量专家子网络处理每个 Token，用更多参数换更强能力而不增加推理成本。
- [长上下文技术（Long Context Technology）](../content/02_models/frontier/long-context-technology.md) - ⭐⭐⭐⭐ - 让 LLM 从 4K 扩展到百万级 token 窗口的核心技术体系，涵盖位置编码外推、注意力优化、KV 缓存压缩三大方向

### 三、设计模式篇（patterns）

**Agent 经典范式**

- [Plan-and-Solve（计划与执行）](../content/03_patterns/agent-paradigms/plan-and-solve.md) - ⭐⭐⭐ - 先制定计划、再按计划执行的 Agent 范式，适合结构清晰的多步骤任务
- [ReAct（推理与行动协同）](../content/03_patterns/agent-paradigms/react.md) - ⭐⭐⭐ - 将推理与行动交替进行的 Agent 经典范式，让模型能够边想边做、边做边调整。
- [Reflection（反思/自我纠错模式）](../content/03_patterns/agent-paradigms/reflection.md) - ⭐⭐⭐ - Agent 对自身输出进行批判性审视并迭代改进的设计模式。

**单 Agent 模式**

- [Code Agent（代码型 Agent）](../content/03_patterns/single-agent/code-agent.md) - ⭐⭐⭐ - Agent 通过动态生成代码并在沙箱中执行来解决问题的设计模式，以代码作为通用行动接口。
- [RAG Agent（检索增强型 Agent）](../content/03_patterns/single-agent/rag-agent.md) - ⭐⭐⭐ - 让 Agent 自主决定何时检索、检索什么、检索几次，实现智能化的知识问答。
- [对话型 Agent（Conversational Agent）](../content/03_patterns/single-agent/conversational-agent.md) - ⭐⭐ - 通过多轮对话理解用户意图、收集信息、执行任务的交互式 Agent 模式。
- [工具型 Agent（Tool Agent）](../content/03_patterns/single-agent/tool-agent.md) - ⭐⭐⭐ - LLM 通过结构化工具调用与外部系统交互的单智能体模式，是现代 Agent 应用的基础设施。
- [自主型 Agent（Autonomous Agent）](../content/03_patterns/single-agent/autonomous-agent.md) - ⭐⭐⭐ - 给定目标后能自主分解任务、迭代执行、反思改进的 Agent 设计模式

**多 Agent 协作模式**

- [Handoff 模式（任务移交）](../content/03_patterns/multi-agent/handoff.md) - ⭐⭐⭐ - Agent 之间按条件主动移交控制权和上下文，实现专业化分工协作
- [Master-Worker 模式（主从分发）](../content/03_patterns/multi-agent/master-worker.md) - ⭐⭐⭐ - 一个主 Agent 拆任务、分任务，多个 Worker Agent 并行干活，最后主 Agent 汇总结果。
- [分层模式（Hierarchical）](../content/03_patterns/multi-agent/hierarchical.md) - ⭐⭐⭐ - 多层级 Agent 树状组织，通过逐层委托实现大规模任务的分解与协调。
- [流水线模式（Pipeline）](../content/03_patterns/multi-agent/pipeline.md) - ⭐⭐⭐ - 多个 Agent 按固定顺序依次处理，前一个的输出作为后一个的输入，形成单向流水线。
- [群聊模式（Group Chat）](../content/03_patterns/multi-agent/groupchat.md) - ⭐⭐⭐ - 多个 Agent 在共享对话中轮流发言、由主持人动态调度的多 Agent 协作模式。
- [辩论/竞争模式（Debate & Competition）](../content/03_patterns/multi-agent/debate-competition.md) - ⭐⭐⭐ - 多个 Agent 对同一问题各自作答、互相质证，通过多轮辩论逼近更可靠答案的协作模式。

**企业级架构模式**

- [数据流编排模式（Data Flow Orchestration）](../content/03_patterns/enterprise/data-flow-orchestration.md) - ⭐⭐⭐⭐ - 通过 DAG 和状态机将多 Agent 任务组织为可追踪、可恢复的有向数据流。
- [知识密集型架构（Knowledge-Intensive Architecture）](../content/03_patterns/enterprise/knowledge-intensive-architecture.md) - ⭐⭐⭐⭐ - 面向企业海量知识处理的分层平台架构，通过数据治理、模型管理和引擎拆分实现知识的安全利用与灵活组合。
- [自主 Agent 架构（Autonomous Agent Architecture）](../content/03_patterns/enterprise/autonomous-agent-architecture.md) - ⭐⭐⭐⭐ - 以 LLM 为核心控制器，集规划、记忆、工具使用于一体的端到端自主 Agent 系统架构。

**模式选型指南**

- [按场景选型（Pattern Selection by Scenario）](../content/03_patterns/selection-guide/pattern-selection-by-scenario.md) - ⭐⭐⭐ - 根据任务特征选择最合适的 Agent 设计模式，避免过度设计或能力不足
- [按复杂度选型（Pattern Selection by Complexity）](../content/03_patterns/selection-guide/pattern-selection-by-complexity.md) - ⭐⭐⭐ - 根据任务复杂度从低到高选择匹配的 Agent 设计模式，避免过度设计或能力不足。

### 四、工程实践篇（practices）

**AI 辅助开发流程**

- [AI 代码审查（AI Code Review）](../content/04_practices/ai-dev-workflow/ai-code-review.md) - ⭐⭐⭐ - 用 LLM 自动审查 PR 中的代码变更，提前发现风格、安全、逻辑问题。
- [AI 编码助手（AI Coding Assistants）](../content/04_practices/ai-dev-workflow/ai-coding-assistants.md) - ⭐⭐ - 由大语言模型驱动、实时辅助代码编写与调试的智能开发伙伴。
- [AI 辅助文档生成（AI Documentation Generation）](../content/04_practices/ai-dev-workflow/ai-documentation-generation.md) - ⭐⭐⭐ - 用 LLM 从代码自动生成注释、API 文档和更新日志，解决文档滞后和风格不统一问题
- [AI 驱动开发流程（AI-Driven Development Workflow）](../content/04_practices/ai-dev-workflow/ai-driven-workflow.md) - ⭐⭐⭐ - 以 LLM 为核心驱动力、贯穿需求→设计→编码→测试→部署全链路的开发范式

**测试方法**

- [Agent 测试金字塔（Testing Pyramid for AI Agents）](../content/04_practices/testing/agent-testing-pyramid.md) - ⭐⭐⭐ - 针对 LLM Agent 非确定性特性设计的分层测试框架，用概率性验证替代精确断言。
- [LLM 输出测试（LLM Output Testing）](../content/04_practices/testing/llm-output-testing.md) - ⭐⭐⭐ - LLM 输出测试的分层方法论，从格式校验到语义评估到 LLM-as-Judge 的完整评估体系。
- [回归测试（Regression Testing）](../content/04_practices/testing/regression-testing.md) - ⭐⭐⭐ - 每次变更后用已验证的测试集重新跑一遍，确保没有破坏已有功能。
- [对话质量测试（Conversation Quality Testing）](../content/04_practices/testing/conversation-quality-testing.md) - ⭐⭐⭐ - 系统化评估 Agent 多轮对话中连贯性、意图理解和上下文保持能力的测试方法体系。
- [工具调用测试（Tool Calling Testing）](../content/04_practices/testing/tool-calling-testing.md) - ⭐⭐⭐ - 验证 Agent 能否选对工具、传对参数、按合理顺序执行并正确处理返回结果的测试方法
- [性能与压力测试（Performance & Stress Testing）](../content/04_practices/testing/performance-stress-testing.md) - ⭐⭐⭐ - 通过延迟、吞吐量、Token 成本和并发能力四个维度评估 Agent 应用的生产就绪程度

**CI/CD**

- [Agent CD 部署（持续部署）](../content/04_practices/cicd/agent-cd-deployment.md) - ⭐⭐⭐ - Agent 应用通过分环境、分阶段、可回滚的自动化流程实现安全上线
- [Agent CI 流水线（Agent CI Pipeline）](../content/04_practices/cicd/agent-ci-pipeline.md) - ⭐⭐⭐ - Agent 项目的持续集成流水线，在传统 CI 基础上增加 LLM 输出评估环节，保障非确定性系统的质量。
- [模型版本管理（Model Version Management）](../content/04_practices/cicd/model-version-management.md) - ⭐⭐⭐ - 对 LLM 应用中的模型、Prompt、配置进行统一版本化管理，实现可追溯、可回滚、可对比。
- [自动化工具链（Automation Toolchain）](../content/04_practices/cicd/automation-toolchain.md) - ⭐⭐⭐ - 从代码提交到生产部署的全流程自动化体系，覆盖传统 CI/CD 与 Agent 特有的 Prompt/模型评估流水线

**安全与合规**

- [Agent 安全实践（Agent Security Practices）](../content/04_practices/security/agent-security-practices.md) - ⭐⭐⭐ - Agent 系统全生命周期的安全防护体系，覆盖身份认证、权限控制、输入输出验证、运行时监控与审计
- [Prompt 注入防御（Prompt Injection Defense）](../content/04_practices/security/prompt-injection-defense.md) - ⭐⭐⭐ - Agent 应用面临的首要安全威胁——提示词注入攻击的原理、攻击分类与多层防御体系。
- [合规审计（Compliance Audit）](../content/04_practices/security/compliance-audit.md) - ⭐⭐⭐ - 对 Agent 系统的所有关键操作进行不可篡改的追踪记录，满足监管合规要求
- [数据安全（Data Security）](../content/04_practices/security/data-security.md) - ⭐⭐⭐ - AI 系统中敏感数据的识别、脱敏、加密与全生命周期防护体系
- [访问控制（Access Control）](../content/04_practices/security/access-control.md) - ⭐⭐⭐ - Agent 应用中限制"谁能用什么工具、碰什么数据"的安全机制

**性能优化**

- [可靠性优化（Reliability Optimization）](../content/04_practices/performance/reliability-optimization.md) - ⭐⭐⭐ - 通过重试、熔断、Fallback 和优雅降级确保 Agent 应用在故障下仍能稳定运行
- [延迟优化（Latency Optimization）](../content/04_practices/performance/latency-optimization.md) - ⭐⭐⭐ - LLM 推理与 Agent 应用中降低响应延迟的核心策略体系
- [成本优化（Cost Optimization）](../content/04_practices/performance/cost-optimization.md) - ⭐⭐⭐ - 通过缓存、模型路由、上下文压缩等手段降低 Agent 应用的 LLM 调用成本

**项目管理**

- [Agent 项目结构（Agent Project Structure）](../content/04_practices/project-management/agent-project-structure.md) - ⭐⭐ - Agent 应用的推荐目录组织方式，让代码、配置、工具、提示词各归其位
- [团队协作（Team Collaboration）](../content/04_practices/project-management/team-collaboration.md) - ⭐⭐⭐ - Agent 开发团队如何通过 Prompt 版本管理、行为评估和知识库共享实现高效协同
- [开发规范（Development Standards）](../content/04_practices/project-management/development-standards.md) - ⭐⭐⭐ - Agent 应用开发中代码、Prompt、版本号与文档的标准化规范体系

### 五、生态工具篇（ecosystem）

**评估体系**

- [Agent 行为评估（Agent Behavior Evaluation）](../content/05_ecosystem/evaluation/agent-behavior-evaluation.md) - ⭐⭐⭐ - 通过多维量化指标对 Agent 的工具调用、推理、任务完成和安全性进行系统化评估
- [Agent 评估工具（Evaluation Tools）](../content/05_ecosystem/evaluation/evaluation-tools.md) - ⭐⭐⭐ - Agent 和 RAG 系统的核心评估工具，涵盖 RAGAS、DeepEval、TruLens、Promptfoo 等主流框架
- [RAG 评估](../content/05_ecosystem/evaluation/rag-evaluation.md) - ⭐⭐⭐ - 系统化评估 RAG 系统的检索质量与生成质量，定位瓶颈并指导优化。
- [评估框架（Evaluation Framework）](../content/05_ecosystem/evaluation/evaluation-framework.md) - ⭐⭐⭐ - 用于系统化测量 LLM/Agent 系统输出质量与行为可靠性的指标体系和方法论

**可观测性工具**

- [Arize AI（AI 可观测性平台）](../content/05_ecosystem/observability/arize.md) - ⭐⭐⭐ - 开源 AI 可观测性平台，基于 OpenTelemetry 提供 LLM 应用的 Tracing、评估和 Prompt 管理。
- [Braintrust（AI 产品评估平台）](../content/05_ecosystem/observability/braintrust.md) - ⭐⭐⭐ - 以评估为核心的 AI 应用质量管理平台，支持实验追踪、自动评分、数据集版本控制和 Prompt 优化。
- [LangSmith（LLM 开发平台）](../content/05_ecosystem/observability/langsmith.md) - ⭐⭐⭐ - LangChain 官方可观测性与评估平台，提供端到端追踪、自动化评估和生产监控。
- [Langfuse（开源 LLM 可观测性平台）](../content/05_ecosystem/observability/langfuse.md) - ⭐⭐⭐ - 开源 LLM 可观测性平台，提供追踪、Prompt 管理、评估和成本监控，支持自托管。
- [Weave（W&B AI 可观测性工具）](../content/05_ecosystem/observability/weave.md) - ⭐⭐⭐ - W&B 推出的 AI 应用可观测性平台，用装饰器自动追踪 LLM 调用链路、评估模型效果。
- [可观测性工具对比](../content/05_ecosystem/observability/observability-tools-comparison.md) - ⭐⭐⭐ - 5 款主流 LLM 可观测性工具的核心差异、选型决策和适用场景对比。

**OCR 服务**

- [MinerU（文档智能解析工具）](../content/05_ecosystem/ocr/mineru.md) - ⭐⭐⭐ - 开源 PDF 文档解析工具，将复杂 PDF 转换为 Markdown/JSON，适合 RAG 系统的文档预处理。
- [传统 OCR（光学字符识别）](../content/05_ecosystem/ocr/traditional-ocr.md) - ⭐⭐⭐ - 从模板匹配到深度学习，传统 OCR 的核心流水线与三大主流工具的原理拆解
- [多模态 OCR（Vision Language Model OCR）](../content/05_ecosystem/ocr/multimodal-ocr.md) - ⭐⭐⭐ - 用视觉语言大模型直接"看图识字"，不只提取字符，还能理解文档结构和语义。

**语音处理**

- [Whisper（OpenAI 语音识别模型）](../content/05_ecosystem/speech/whisper.md) - ⭐⭐ - OpenAI 开源的自动语音识别系统，支持 99 种语言，本地运行无需联网。
- [文本转语音（Text-to-Speech, TTS）](../content/05_ecosystem/speech/text-to-speech.md) - ⭐⭐ - 将文本自动转换为自然人声的技术，支持多语言、情感控制和语音克隆
- [语音对话 Agent（Voice Conversation Agent）](../content/05_ecosystem/speech/voice-conversation-agent.md) - ⭐⭐⭐ - 能实时听说、理解意图并执行任务的语音智能体系统，支持自然对话与中断。

**数据处理工具**

- [Embedding 模型（嵌入模型）](../content/05_ecosystem/data-processing/embedding-models.md) - ⭐⭐ - 把文本变成数字向量的工具，是语义搜索和 RAG 系统的基础组件。
- [数据清洗与预处理（Data Cleaning & Preprocessing）](../content/05_ecosystem/data-processing/data-cleaning-preprocessing.md) - ⭐⭐⭐ - 将原始混乱数据转化为干净、结构化、模型可用格式的系统化过程
- [文本分割工具（Text Splitting Tools）](../content/05_ecosystem/data-processing/text-splitting-tools.md) - ⭐⭐ - 将长文本切成小块供向量检索使用，是 RAG 系统的必备预处理环节。
- [文档解析工具（Document Parsing Tools）](../content/05_ecosystem/data-processing/document-parsing-tools.md) - ⭐⭐ - 将 PDF、Word 等非结构化文档转为结构化数据的工具，是 RAG 系统的第一道工序。

**开发工具**

- [API 网关与代理（API Gateway & Proxy）](../content/05_ecosystem/dev-tools/api-gateway-proxy.md) - ⭐⭐⭐ - 统一多家 LLM 提供商的 API 接口，实现模型路由、故障转移和成本追踪。
- [向量索引工具（Vector Indexing Tools）](../content/05_ecosystem/dev-tools/vector-indexing-tools.md) - ⭐⭐⭐ - 对向量数据进行高效索引和近似最近邻检索的开源库（FAISS、HNSWlib、Annoy）及核心算法对比
- [提示词管理工具（Prompt Management Tools）](../content/05_ecosystem/dev-tools/prompt-management-tools.md) - ⭐⭐ - 管理、版本控制和评估 LLM 提示词的平台工具，支持协作编辑、A/B 测试和多环境部署。
- [知识库工具（Knowledge Base Tools）](../content/05_ecosystem/dev-tools/knowledge-base-tools.md) - ⭐⭐ - 集文档处理、向量检索、问答生成于一体的低代码/零代码 RAG 平台，让非技术人员也能快速搭建 AI 知识问答系统。

### 六、Prompt Engineering 篇（prompt-engineering）

**提示词基础**

- [少样本提示（Few-Shot Prompting）](../content/06_prompt-engineering/prompt-basics/few-shot-prompting.md) - ⭐⭐ - 在提示词中嵌入少量示例，引导 LLM 通过上下文学习完成新任务的技术
- [指令工程（Instruction Engineering）](../content/06_prompt-engineering/prompt-basics/instruction-engineering.md) - ⭐⭐ - 通过清晰、具体、结构化的指令设计，让 LLM 准确理解意图并稳定输出的方法论
- [提示词的基本结构（Prompt Structure）](../content/06_prompt-engineering/prompt-basics/prompt-structure.md) - ⭐⭐ - 提示词由角色、指令、上下文和输出格式四部分组成，理解结构才能写出可控的提示词
- [系统提示词设计（System Prompt Design）](../content/06_prompt-engineering/prompt-basics/system-prompt-design.md) - ⭐⭐⭐ - 通过角色定义、行为规则和安全护栏，让 AI 在每次对话中保持一致行为的设计方法
- [零样本提示（Zero-Shot Prompting）](../content/06_prompt-engineering/prompt-basics/zero-shot-prompting.md) - ⭐⭐ - 不提供任何示例，仅靠自然语言指令驱动 LLM 完成任务的提示技术

**上下文工程**

- [上下文与 Agent（Context & Agent）](../content/06_prompt-engineering/context-engineering/context-and-agent.md) - ⭐⭐⭐ - Agent 运行时的上下文管理机制，涵盖信息注入、压缩、多 Agent 传递等核心问题。
- [上下文压缩（Context Compression）](../content/06_prompt-engineering/context-engineering/context-compression.md) - ⭐⭐⭐ - 在保留关键信息的前提下，减少送入 LLM 的 token 数量，降低成本和延迟。
- [上下文构建策略（Context Building Strategy）](../content/06_prompt-engineering/context-engineering/context-building-strategy.md) - ⭐⭐⭐ - 在运行时动态组装最优上下文，让 LLM 在正确的信息环境中完成任务
- [上下文窗口管理（Context Window Management）](../content/06_prompt-engineering/context-engineering/context-window-management.md) - ⭐⭐⭐ - 将上下文窗口视为有限资源，通过预算分配、压缩和优先级策略最大化信息利用率
- [多轮对话上下文管理（Multi-turn Context Management）](../content/06_prompt-engineering/context-engineering/multi-turn-context.md) - ⭐⭐⭐ - 在多轮对话中管理对话历史和上下文的策略，平衡信息保留与 Token 消耗

**进阶推理技巧**

- [ReAct 提示技巧（Reasoning + Acting）](../content/06_prompt-engineering/advanced-techniques/react-prompting.md) - ⭐⭐⭐ - 通过 Thought-Action-Observation 循环，让 LLM 边推理边调用工具，解决纯思考无法完成的任务。
- [思维图（Graph-of-Thought, GoT）](../content/06_prompt-engineering/advanced-techniques/graph-of-thought.md) - ⭐⭐⭐⭐ - 用图结构对 LLM 推理建模，支持思路融合、精化和反馈循环，突破链式和树形推理的结构限制
- [思维树（Tree-of-Thought, ToT）](../content/06_prompt-engineering/advanced-techniques/tree-of-thought.md) - ⭐⭐⭐ - 通过树形结构探索多条推理路径并自主评估回溯，解决线性思维链无法应对的复杂决策问题。
- [思维链（Chain-of-Thought, CoT）](../content/06_prompt-engineering/advanced-techniques/chain-of-thought.md) - ⭐⭐ - 引导 LLM 展示中间推理步骤的提示技巧，显著提升多步推理任务的准确率。
- [结构化输出（Structured Output）](../content/06_prompt-engineering/advanced-techniques/structured-output.md) - ⭐⭐⭐ - 通过 Schema 约束和约束解码技术，让 LLM 输出严格符合指定格式的结构化数据。
- [自一致性（Self-Consistency）](../content/06_prompt-engineering/advanced-techniques/self-consistency.md) - ⭐⭐⭐ - 对同一问题采样多条推理路径，通过多数投票选出最一致的答案，提升 LLM 推理准确性

**专项提示技巧**

- [元提示（Meta Prompting）](../content/06_prompt-engineering/specialized-techniques/meta-prompting.md) - ⭐⭐⭐ - 用提示词来生成、优化或编排其他提示词的高阶提示技术
- [分解提示（Decomposition Prompting）](../content/06_prompt-engineering/specialized-techniques/decomposition-prompting.md) - ⭐⭐⭐ - 将复杂问题显式拆分为多个简单子问题，逐步求解再合并结果的提示技术族
- [多模态提示（Multimodal Prompting）](../content/06_prompt-engineering/specialized-techniques/multimodal-prompting.md) - ⭐⭐⭐ - 通过组合图像、文本等多种信息形式来引导多模态模型完成视觉理解与推理任务的提示技术
- [检索增强提示（RAG Prompting）](../content/06_prompt-engineering/specialized-techniques/rag-prompting.md) - ⭐⭐⭐ - RAG 场景下的提示词设计方法，涵盖上下文注入、模板结构、引用归因等核心技术
- [角色扮演提示（Role Prompting）](../content/06_prompt-engineering/specialized-techniques/role-prompting.md) - ⭐⭐ - 通过为 LLM 分配特定角色身份来引导其输出风格、语气和知识侧重的提示词技术

**优化与评估**

- [提示词优化（Prompt Optimization）](../content/06_prompt-engineering/optimization/prompt-optimization.md) - ⭐⭐⭐ - 从手动迭代到自动搜索，系统掌握提示词优化的四大方法与工程实践。
- [提示词版本管理（Prompt Versioning）](../content/06_prompt-engineering/optimization/prompt-versioning.md) - ⭐⭐⭐ - 像管理代码一样管理提示词的版本、环境和发布，保证线上可追溯、可回滚
- [提示词评估（Prompt Evaluation）](../content/06_prompt-engineering/optimization/prompt-evaluation.md) - ⭐⭐⭐ - 用科学的指标体系和对比实验方法量化提示词质量的完整评估方法论

**场景模板**

- [Agent 场景提示模板（Agent Prompt Templates）](../content/06_prompt-engineering/templates/agent-templates.md) - ⭐⭐⭐ - Agent 应用中引导模型推理、调用工具和协作的三类标准化提示结构
- [代码生成场景提示（Code Generation Prompts）](../content/06_prompt-engineering/templates/code-generation-templates.md) - ⭐⭐⭐ - 通过结构化提示词策略引导 LLM 生成高质量、可运行的代码
- [数据分析场景提示词模板（Data Analysis Prompt Templates）](../content/06_prompt-engineering/templates/data-analysis-templates.md) - ⭐⭐⭐ - 用结构化模板帮助 LLM 从原始数据中提取洞察、生成图表描述和分析报告的提示词设计方法
- [文本生成场景（Writing/Translation/Summarization）](../content/06_prompt-engineering/templates/text-generation-templates.md) - ⭐⭐ - 面向写作、翻译、摘要三大文本生成任务的提示词模板设计方法与核心要素
- [知识问答场景（QA Prompt Templates）](../content/06_prompt-engineering/templates/qa-templates.md) - ⭐⭐ - 通过结构化提示词模板，让 LLM 基于给定信息准确回答问题、减少幻觉

---
