# Agent-Wiki

> Agent 应用开发领域的知识百科与速查手册

## 项目简介

Agent-Wiki 是一个纯 Markdown 文档型开源知识库，覆盖 Agent 应用开发从概念到落地的完整知识图谱。

- **不是课程大纲，而是字典式知识库** — 每张知识卡片是一个最小知识单元，随查随用
- **结构化组织** — 6 大分篇、169+ 张卡片，按统一模板撰写
- **持续更新** — 跟踪 Agent 技术生态最新进展

### 每张卡片你能获得什么

| 内容模块 | 说明 |
|---------|------|
| 📖 通俗解释 | 用大白话讲清概念，拒绝照搬官方定义 |
| 📊 原理图解 | Mermaid 流程图 / 架构图，可视化核心逻辑 |
| 💻 代码示例 | 可直接运行的代码片段，附完整 import 和预期输出 |
| 🎯 应用场景 | 真实业务场景举例与常见误区，帮助理解何时该用、怎么避坑 |
| ⚖️ 同类对比 | 横向对比同类工具 / 模式的优劣势，辅助技术选型 |
| ✏️ 练习题 | 从概念理解 → 应用分析 → 架构设计的分层练习，巩固掌握 |

## 知识体系总览

| 分篇 | 目录 | 篇数 | 覆盖范围 |
|------|------|:----:|---------|
| 工程篇 | [`content/01_engineering/`](content/01_engineering/) | 39 | Agent 核心技术概念、开发框架、Agent SDK、数据库、Web 框架、消息队列、容器化 |
| 模型算法篇 | [`content/02_models/`](content/02_models/) | 33 | LLM 理论、模型系列、训练技术、多模态、部署优化、本地/云端模型、硬件、选型 |
| 设计模式篇 | [`content/03_patterns/`](content/03_patterns/) | 19 | Agent 经典范式、单 Agent 模式、多 Agent 协作模式、企业级架构模式 |
| 工程实践篇 | [`content/04_practices/`](content/04_practices/) | 25 | AI 辅助开发流程、Agent 测试、CI/CD、安全合规、性能优化 |
| 生态工具篇 | [`content/05_ecosystem/`](content/05_ecosystem/) | 24 | 可观测性工具、Agent 评估、OCR、语音处理、数据处理工具 |
| Prompt Engineering 篇 | [`content/06_prompt-engineering/`](content/06_prompt-engineering/) | 29 | 提示词基础、上下文工程、进阶推理技巧、场景模板 |

## 推荐阅读

不知道从哪开始？每个分篇精选一张代表性卡片：

| 分篇 | 推荐卡片 | 难度 | 简介 |
|------|---------|:----:|------|
| 工程篇 | [RAG（检索增强生成）](content/01_engineering/core-concepts/rag.md) | ⭐⭐⭐ | 通过检索外部知识库让 LLM 回答更准确的核心技术架构 |
| 模型算法篇 | [模型架构演进](content/02_models/fundamentals/model-architecture-evolution.md) | ⭐⭐⭐ | 从 RNN 到 Transformer 的演进历程，理解现代大模型的架构基础 |
| 设计模式篇 | [ReAct（推理与行动协同）](content/03_patterns/agent-paradigms/react.md) | ⭐⭐⭐ | 将推理与行动交替进行的 Agent 经典范式，让智能体能边想边做 |
| 工程实践篇 | [全链路 AI 辅助开发](content/04_practices/ai-dev-workflow/ai-driven-workflow.md) | ⭐⭐⭐ | 从需求分析到部署发布的全链路 AI 驱动开发工作范式 |
| 生态工具篇 | [Langfuse（可观测性平台）](content/05_ecosystem/observability/langfuse.md) | ⭐⭐⭐ | 开源的 LLM 应用可观测性平台，提供追踪、评估和成本监控 |
| PE 篇 | [提示词的基本结构](content/06_prompt-engineering/prompt-basics/prompt-structure.md) | ⭐⭐ | 系统提示、用户提示、角色定义和输出格式——写好提示词的前提 |

> **难度分级说明**：⭐ 入门科普 · ⭐⭐ Hello World 级别 · ⭐⭐⭐ 生产环境实战 · ⭐⭐⭐⭐ 源码/底层原理 · ⭐⭐⭐⭐⭐ 算法推导/内核优化

## 知识卡片导航

完整的卡片目录索引（含分篇导航、最近更新、统计数据）：

**[查看完整导航索引 → docs/index.md](docs/index.md)**

## 如何使用本知识库

- **入门学习**：从「推荐阅读」中的 ⭐⭐ 卡片开始，建立基础概念后逐步深入
- **按分篇浏览**：点击「知识体系总览」中的目录链接，系统性学习某个方向
- **速查某个技术点**：打开 [完整导航索引](docs/index.md)，按标签或分类快速定位
- **关键词搜索**：在 GitHub 页面按 `T` 键搜索文件名，或用 `Ctrl+F` 在索引页中查找

## 内容结构

```
content/
├── 01_engineering/
│   ├── agent-sdks/        # Agent SDK
│   ├── core-concepts/     # 核心概念（RAG、MCP、Tool Use、Memory）
│   ├── frameworks/        # AI 开发框架
│   ├── databases/         # 数据库
│   ├── web-frameworks/    # Web 框架
│   ├── message-queues/    # 消息队列
│   └── containers/        # 容器化
├── 02_models/
│   ├── fundamentals/      # LLM 基础理论
│   ├── model-series/      # 主流模型系列
│   ├── training/          # 训练技术
│   ├── multimodal/        # 多模态
│   ├── core-techniques/   # 核心技术
│   ├── deployment/        # 部署优化
│   ├── evaluation/        # 评估方法
│   └── frontier/          # 前沿进展
├── 03_patterns/
│   ├── agent-paradigms/   # Agent 经典范式
│   ├── single-agent/      # 单 Agent 模式
│   ├── multi-agent/       # 多 Agent 协作
│   ├── enterprise/        # 企业级架构
│   └── selection-guide/   # 模式选型指南
├── 04_practices/
│   ├── ai-dev-workflow/   # AI 辅助开发流程
│   ├── testing/           # Agent 测试
│   ├── cicd/              # CI/CD
│   ├── security/          # 安全合规
│   ├── performance/       # 性能优化
│   └── project-management/ # 项目管理
├── 05_ecosystem/
│   ├── observability/     # 可观测性工具
│   ├── evaluation/        # Agent 评估体系
│   ├── ocr/               # OCR 工具
│   ├── speech/            # 语音处理
│   ├── data-processing/   # 数据处理
│   └── dev-tools/         # 开发工具
└── 06_prompt-engineering/
    ├── prompt-basics/     # 提示词基础
    ├── context-engineering/ # 上下文工程
    ├── advanced-techniques/ # 进阶推理技巧
    ├── specialized-techniques/ # 专项技巧
    ├── optimization/      # 优化方法
    └── templates/         # 场景模板
```

## 内容大纲

每个分篇都有对应的内容大纲（种子文件），描述该分篇的完整知识范围和规划：

| 分篇 | 大纲文件 |
|------|---------|
| 工程篇 | [`outlines/Agent应用开发体系_工程篇.md`](outlines/Agent应用开发体系_工程篇.md) |
| 模型算法篇 | [`outlines/Agent应用开发体系_模型算法篇.md`](outlines/Agent应用开发体系_模型算法篇.md) |
| 设计模式篇 | [`outlines/Agent应用开发体系_设计模式篇.md`](outlines/Agent应用开发体系_设计模式篇.md) |
| 工程实践篇 | [`outlines/Agent应用开发体系_工程实践篇.md`](outlines/Agent应用开发体系_工程实践篇.md) |
| 生态工具篇 | [`outlines/Agent应用开发体系_生态工具篇.md`](outlines/Agent应用开发体系_生态工具篇.md) |
| Prompt Engineering 篇 | [`outlines/Agent应用开发体系_PromptEngineering篇.md`](outlines/Agent应用开发体系_PromptEngineering篇.md) |

## 许可证

本项目采用开源许可证，详情见 [LICENSE](LICENSE)。
