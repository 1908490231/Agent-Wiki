# Agent应用开发体系 - 工程篇

> 本篇聚焦 Agent 应用开发的核心技术概念与工程技术栈，涵盖从概念理解到技术选型的完整知识图谱。
>
> **不包含**：Agent 范式/设计模式（见设计模式篇）、模型理论与部署（见模型算法篇）、可观测性/OCR/语音工具（见生态工具篇）、开发流程/测试（见工程实践篇）、提示词工程（见 Prompt Engineering 篇）

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

### 1.8 State Management（状态管理）
- Agent 状态机设计
- LangGraph 的 State 设计模式
- 状态持久化
- 分布式状态管理
- 检查点与恢复

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
- 容器编排与调度
- Pod 与 Service 设计
- 自动扩缩容
- Agent 服务集群化部署
