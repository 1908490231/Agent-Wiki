# Agent应用开发体系 - 设计模式篇

> 本篇聚焦 Agent 系统中的可复用设计模式与协作范式，覆盖从经典单 Agent 推理模式到多 Agent 协作与企业级架构模式。
>
> **不包含**：具体框架 API 与工程技术栈（见工程篇）、模型原理与训练（见模型算法篇）、提示词技巧本身（见 Prompt Engineering 篇）

---

## 归类导航说明

### 子目录映射表

| outline 二级主题 | 对应 content 子目录 | 归类范围 |
|---|---|---|
| 一、Agent 经典范式 | `content/03_patterns/agent-paradigms/` | ReAct、Plan-and-Solve、Reflection、Reflexion 等经典范式 |
| 二、单 Agent 模式 | `content/03_patterns/single-agent/` | Router、Tool-Using、Planner-Executor 等单 Agent 结构 |
| 三、多 Agent 协作模式 | `content/03_patterns/multi-agent/` | Master-Worker、Handoff、GroupChat、Blackboard 等协作模式 |
| 四、企业级架构模式 | `content/03_patterns/enterprise/` | Workflow + Agent、事件驱动、分层治理、编排架构 |
| 五、模式选型指南 | `content/03_patterns/selection-guide/` | 模式比较、适用场景、复杂度权衡 |

### 什么情况下优先归设计模式篇

1. 当知识点主要关注“任务如何被组织、拆解、协作、回收结果”时，优先归设计模式篇。
2. 当主题描述的是一种可复用的结构、角色关系、决策流或协作机制，而不是具体 SDK API 时，优先归本篇。
3. 当同一个词既可表示 Prompt 技巧，又可表示 Agent 工作流模式时，本篇收纳“系统协作结构”那一侧。
4. 只要知识点的核心问题是“这种组织方式适合什么任务、如何权衡复杂度”，就优先归本篇。

### 常见混淆项

| 容易混淆的概念 | 本篇归类 | 不归本篇的情况 | 判断关键点 |
|---|---|---|---|
| ReAct 范式 vs ReAct Prompting | ReAct 作为 Agent 推理-行动范式放 `agent-paradigms/` | ReAct 提示模板、Thought/Action/Observation 提示写法放 Prompt Engineering 篇 | 看重点是“工作流结构”还是“提示模板” |
| Master-Worker / Handoff / GroupChat | 作为协作模式放 `multi-agent/` | 某个框架里具体 API 用法放工程篇 | 看重点是模式抽象还是框架实现 |
| Planner-Executor | 作为任务拆解模式放本篇 | 如果讲的是某个 SDK 的 Planner 节点具体实现，可在工程篇框架卡中展开 | 看是否在抽象可复用结构 |
| Workflow + Agent | 企业级架构模式放 `enterprise/` | 单纯讲 CI/CD 工作流、上线流程放工程实践篇 | 看对象是 Agent 架构还是开发流程 |

### 最低锚点规则

- 二级标题代表 `content/03_patterns/*` 的子目录主题。
- 三级标题代表可直接生成卡片的模式、范式、协作结构或对比项。
- 没有同名三级条目时，只要存在可挂靠的二级主题，就先补锚点再写卡。

### 待细分协作模式锚点

新增协作类知识点时，可优先挂靠以下扩展容器：

- `三、多 Agent 协作模式`：承载新型角色分工、协议式协作、群体协作结构
- `四、企业级架构模式`：承载大规模系统整合、治理分层、工作流混编架构
- `五、模式选型指南`：承载模式对比、模式迁移建议、复杂度与收益分析

### 粒度说明

- **二级标题 = 子目录主题**，用于决定最终落在哪个 `content/03_patterns/*` 子目录。
- **三级标题 = 最小卡片单元**，可以是一种模式、范式、协作协议、架构组合或比较项。
- 列表项描述该模式卡片的最低覆盖范围，如角色结构、执行流程、优缺点与适用场景。

---

## 一、Agent 经典范式

### 1.1 ReAct（Reason + Act）
- 推理与行动交替执行
- Thought / Action / Observation 循环
- 适用场景：需要边推理边调用工具的任务
- 优点与局限

### 1.2 Plan-and-Solve
- 先规划后执行
- 分阶段任务拆解
- 适用场景：复杂多步骤任务
- 与 ReAct 的区别

### 1.3 Reflection（反思模式）
- 执行后自我评估
- 基于反馈修正输出
- 单轮反思 vs 多轮反思

### 1.4 Reflexion
- 将反思写入记忆并影响后续决策
- 自我改进循环
- 与普通 Reflection 的区别

### 1.5 Self-Consistency / Self-Refine（扩展锚点）
- 多路径生成与结果选择
- 迭代式自我优化
- 与 Prompt 层同名技术的边界

---

## 二、单 Agent 模式

### 2.1 Router 模式
- 根据输入意图进行任务路由
- 路由规则：分类器、评分器、LLM 判断
- 适用场景：多工具/多流程入口

### 2.2 Tool-Using Agent
- 以单一 Agent 为中心调用多个工具
- 工具选择与错误恢复
- 上下文组织方式

### 2.3 Planner-Executor 模式
- 规划器与执行器职责划分
- 串行执行与动态重规划
- 适用场景：复杂任务分解

### 2.4 Critic-Executor（扩展锚点）
- 执行与审查分离
- 质量回路与反馈闭环
- 与 Reflection 模式的区别

---

## 三、多 Agent 协作模式

### 3.1 Master-Worker 模式
- 主控 Agent 拆任务，子 Agent 执行
- 结果汇总与质量控制
- 适用场景：任务可并行拆分
- 优点与风险：扩展性高，但调度复杂

### 3.2 Handoff 模式
- 当前 Agent 将任务移交给更适合的 Agent
- 能力边界清晰，减少单 Agent 负担
- 常见于客服、流程审批、多角色系统

### 3.3 GroupChat / 群聊模式
- 多 Agent 在共享上下文中协作
- 适用场景：头脑风暴、复杂问题讨论、角色辩论
- 风险：信息冗余、对话失控、成本上升

### 3.4 Blackboard 模式
- 通过共享黑板/工件进行间接协作
- 适用场景：异步协作、多阶段问题求解
- 与 GroupChat 的差异

### 3.5 Supervisor / Orchestrator 模式（扩展锚点）
- 中央调度器统一分配工作
- 动态选择专家 Agent
- 与 Master-Worker 的边界

---

## 四、企业级架构模式

### 4.1 Workflow + Agent 混合架构
- 确定性流程 + 非确定性 Agent 能力结合
- 适用场景：关键节点需可控、局部允许智能决策
- 优点：兼顾稳定性与灵活性

### 4.2 事件驱动 Agent 架构
- 基于事件总线触发 Agent 行为
- 与消息队列结合的异步处理模型
- 适用场景：企业内部自动化、复杂系统联动

### 4.3 分层治理架构
- 决策层 / 执行层 / 审核层分离
- 安全边界、审批与可追溯性设计
- 适用场景：高风险、高合规要求场景

### 4.4 人在环企业架构
- 人工审批、人工纠偏、人工接管
- 与纯自动系统的差异
- 风险控制收益

### 4.5 企业级多 Agent 平台模式（扩展锚点）
- 多租户、权限隔离、统一监控
- 平台化工具接入与策略治理
- 与单项目多 Agent 系统的边界

---

## 五、模式选型指南

### 5.1 按任务复杂度选型
- 简单任务：单 Agent + Tool Use
- 中等复杂：Planner-Executor / ReAct
- 高复杂与跨领域：Multi-Agent 协作

### 5.2 按可控性要求选型
- 高可控：Workflow + Agent
- 中可控：Planner-Executor
- 高自主：多 Agent 协作模式

### 5.3 常见模式对比
- ReAct vs Plan-and-Solve
- Reflection vs Reflexion
- Master-Worker vs Handoff vs GroupChat
- Workflow + Agent vs 完全自主式 Multi-Agent

### 5.4 反模式与误用提醒
- 任务不复杂却过度多 Agent 化
- 用 Prompt 技巧冒充架构模式
- 把框架功能名直接当成模式名
- 角色切分过细导致通信成本失控
