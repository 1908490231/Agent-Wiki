# Agent应用开发体系 - 工程篇

> 本篇聚焦 Agent 应用开发的核心技术概念与工程技术栈，涵盖从概念理解到技术选型的完整知识图谱。
>
> **不包含**：Agent 范式/设计模式（见设计模式篇）、模型理论与部署（见模型算法篇）、可观测性/OCR/语音工具（见生态工具篇）、开发流程/测试（见工程实践篇）、提示词工程（见 Prompt Engineering 篇）

---

## 归类导航说明

### 子目录映射表

| outline 二级主题 | 对应 content 子目录 | 归类范围 |
|---|---|---|
| 一、Agent 核心技术概念 | `content/01_engineering/core-concepts/` | RAG、Tool Use、MCP、Memory、Hooks、State Management、Agent Harness 等基础概念 |
| 二、AI 开发框架 | `content/01_engineering/frameworks/` | LangChain、LangGraph、AutoGen、LlamaIndex、DSPy 等开发框架 |
| 三、Agent SDK | `content/01_engineering/agent-sdks/` | Claude Agent SDK、OpenAI Agents SDK、Google ADK 等 SDK |
| 四、数据库架构 | `content/01_engineering/databases/` | 关系型数据库、文档数据库、向量数据库 |
| 五、Web 开发架构 | `content/01_engineering/web-frameworks/` | FastAPI、Uvicorn 等服务化 Web 技术 |
| 六、缓存消息队列 | `content/01_engineering/message-queues/` | Redis、Celery、RabbitMQ、Kafka |
| 七、容器虚拟化 | `content/01_engineering/containers/` | Docker、Kubernetes 等容器与编排能力 |

### 优先归入本篇的判断规则

1. 当知识点主要回答“Agent 系统由哪些技术栈和运行机制构成”时，优先归工程篇。
2. 当知识点关注的是框架、SDK、数据库、消息队列、Web 服务、容器化等工程底座，而不是生产流程或治理方法时，优先归工程篇。
3. `outline` 是第一归类依据；若与其他篇章重叠，按“技术构件 / 运行时机制”视角优先归本篇。
4. 只有当知识点更偏“测试、上线、安全实践、性能治理”时，才转去工程实践篇。

### 常见混淆项

| 容易混淆的概念 | 本篇归类 | 不归本篇的情况 | 判断关键点 |
|---|---|---|---|
| Agent Harness vs Harness Engineering | `Agent Harness` 放 `core-concepts/` | `Harness Engineering` 放工程实践篇 `project-management/` | 前者讲 Agent 运行时控制层，后者讲生产化工程方法 |
| Context Engineering | 运行时上下文注入、裁剪、状态衔接放 `core-concepts/` | 纯 Prompt 层上下文构建策略放 Prompt Engineering 篇 | 看关注点是“系统运行时管理”还是“提示词构造” |
| Guardrails | 作为 SDK 能力、运行时约束机制时可挂工程篇概念或 SDK 条目 | 作为安全治理实践、风控流程时放工程实践篇 | 看它是产品能力/系统机制，还是治理实践 |
| Hooks | Claude Code / Agent 框架事件钩子放本篇 | 将 Hook 用于流程规范、自动审查时可延展到工程实践篇 | 看重点是机制本身还是开发流程 |

### 最低锚点规则

- 二级标题代表子目录主题。
- 三级标题代表可直接生成卡片的知识点、工具或对比项。
- 如果暂时没有同名三级条目，但已有可挂靠的二级主题，必须先补三级锚点，不要因为缺少同名条目而停止。

### 扩展主题锚点

当新增知识点暂时找不到更细分类时，优先挂靠以下现有主题：

- `一、Agent 核心技术概念`：承载运行时机制、治理控制、上下文与状态相关概念
- `二、AI 开发框架`：承载新增框架或框架对比
- `三、Agent SDK`：承载新增 SDK、SDK 能力对比与编排接口

### 粒度说明

- **二级标题 = 子目录主题**，用于决定最终落入哪个 `content/01_engineering/*` 子目录。
- **三级标题 = 可生成卡片的最小知识点**，可以是概念、工具、SDK、框架或对比项。
- 同一三级标题下的列表项用于说明该卡片最少应覆盖的内容范围。

---

## 一、Agent 核心技术概念

### 1.1 RAG（检索增强生成）
- 基本原理：检索 + 生成的融合架构
- 核心组件：文档加载 → 文本分割 → 向量化 → 检索 → 生成
- 检索策略：稠密检索、稀疏检索、混合检索
- 重排序（Reranking）
- RAG 评估指标
- 进阶：Graph RAG、Agentic RAG、Corrective RAG

### 1.2 Tool Use（工具调用）
- 工具调用的基本概念与流程
- 工具定义与描述规范
- 工具选择策略
- 多工具组合调用
- 工具调用的错误处理

#### 1.2.1 MCP（Model Context Protocol）
- MCP 协议规范
- MCP Server / Client 架构
- MCP 工具注册与发现
- 主流 MCP 实现

#### 1.2.2 Function Calling（函数调用）
- OpenAI Function Calling 规范
- 结构化输出与函数调用
- 并行函数调用
- 各厂商 Function Calling 差异对比

### 1.3 Memory（记忆）
- 短期记忆（对话上下文）
- 长期记忆（持久化存储）
- 工作记忆（任务相关）
- 记忆检索策略
- 记忆压缩与摘要
- 向量化记忆存储

### 1.4 Hooks（钩子）
- 生命周期钩子
- 事件驱动钩子
- 自定义钩子实现
- 钩子在 Agent 框架中的应用

### 1.5 Agent Retry（代理重试）
- 重试策略（指数退避、固定间隔）
- 错误分类与重试条件
- 最大重试次数与熔断
- 重试与幂等性

### 1.6 Human-in-the-Loop（人在环路）
- 人工审批节点设计
- 交互式确认机制
- 人工反馈注入
- 半自动化工作流

### 1.7 Context Engineering（上下文工程）
- 上下文窗口管理
- 上下文注入策略
- 动态上下文构建
- 上下文压缩与裁剪
- 与 Prompt Engineering 篇中“提示词级上下文工程”的边界

### 1.8 State Management（状态管理）
- Agent 状态机设计
- LangGraph 的 State 设计模式
- 状态持久化
- 分布式状态管理
- 检查点与恢复

### 1.9 Agent Harness（Agent 脚手架 / 运行时控制层）
- 核心概念：让模型能够作为 Agent 运行的系统层，负责输入处理、工具编排与结果返回
- 典型组成：任务入口、工具调度、状态与上下文管理、记忆、权限控制、验证反馈回路
- 关键能力：长任务连续性维护、结构化交接、外部评估、自我修正
- 与 Agent Framework 的区别：Harness 更偏运行时控制与工程约束层，Framework 更偏开发框架与组件封装
- 与 Harness Engineering、Context Engineering、Guardrails、Eval 的关系

---

## 二、AI 开发框架

### 2.1 LangChain
- 核心概念：Chain、Agent、Tool、Memory
- LCEL（LangChain Expression Language）
- 主要模块与用法

### 2.2 LangGraph
- 图结构工作流编排
- State 状态管理
- 节点与边的定义
- 条件路由与循环
- 检查点与恢复

### 2.3 AutoGen
- 多 Agent 对话框架
- Agent 角色定义
- 群聊模式（GroupChat）
- 代码执行能力

### 2.4 AgentScope
- 阿里开源 Agent 框架
- 分布式 Agent 支持
- 消息传递机制

### 2.5 Camel AI
- 角色扮演框架
- 多 Agent 协作
- 任务分解与执行

### 2.6 LlamaIndex
- 数据索引与检索
- RAG 管道构建
- 多种数据源接入
- 查询引擎

### 2.7 DSPy
- 声明式语言模型编程
- 自动提示优化
- 模块化编程范式

### 2.8 AutoGPT
- 自主 Agent 架构
- 目标驱动执行
- 长期记忆管理

### 2.9 Letta（原 MemGPT）
- 长期记忆 Agent
- 记忆层次管理
- 上下文扩展

### 2.10 PhiData
- 轻量级 Agent 框架
- 工具集成
- 知识库管理

### 2.11 Haystack
- 端到端 NLP 管道
- 检索与生成管道
- 模块化组件

---

## 三、Agent SDK

### 3.1 Claude Agent SDK（Anthropic）
- SDK 架构与核心概念
- Tool Use 实现
- 多轮对话管理
- 最佳实践

### 3.2 OpenAI Agents SDK
- Agent 定义与配置
- Handoff 机制
- Guardrails（护栏）
- Tracing（追踪）

### 3.3 Google ADK（Agent Development Kit）
- ADK 架构设计
- 多 Agent 编排
- 工具集成
- 部署方案

---

## 四、数据库架构

### 4.1 关系型数据库
#### MySQL
- Agent 应用中的结构化数据存储
- 对话历史存储设计
- 用户与权限管理

### 4.2 文档数据库
#### MongoDB
- 非结构化数据存储
- Agent 配置管理
- 日志与轨迹存储

### 4.3 向量数据库
#### Milvus
- 分布式向量数据库
- 大规模向量检索
- 混合查询

#### Chroma
- 轻量级向量数据库
- 嵌入式部署
- 快速原型开发

#### Weaviate
- 语义搜索引擎
- 多模态向量存储
- GraphQL API

#### Pinecone
- 云原生向量数据库
- 全托管服务
- 实时索引

#### Qdrant
- 高性能向量搜索
- 过滤与负载支持
- Rust 实现

---

## 五、Web 开发架构

### 5.1 FastAPI
- 异步 API 框架
- 自动文档生成
- 依赖注入
- WebSocket 支持
- Agent 服务化开发

### 5.2 Uvicorn
- ASGI 服务器
- 高性能异步处理
- 与 FastAPI 配合部署

---

## 六、缓存消息队列

### 6.1 Redis
- 缓存加速
- 会话存储
- 分布式锁
- Agent 状态缓存

### 6.2 Celery
- 异步任务队列
- 定时任务调度
- Agent 异步执行

### 6.3 RabbitMQ
- 消息队列
- 发布/订阅模式
- Agent 间消息传递

### 6.4 Kafka
- 流处理消息队列
- 高吞吐量日志收集
- 事件驱动架构

---

## 七、容器虚拟化

### 7.1 Docker
- 容器化基础
- Dockerfile 编写
- Docker Compose 编排
- Agent 应用容器化

### 7.2 Kubernetes
- 容器编排
- 服务发现与负载均衡
- 弹性伸缩
- Agent 集群部署
