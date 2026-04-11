# Agent应用开发体系 - 模型算法篇

> 本篇聚焦大语言模型（LLM）的理论基础、模型系列、核心技术、训练方法、部署优化与选型指南。
>
> **不包含**：Agent 开发框架/技术栈（见工程篇）、Agent 设计模式（见设计模式篇）、提示词工程进阶技巧（见 Prompt Engineering 篇）

---

## 归类导航说明

### 子目录映射表

| outline 二级主题 | 对应 content 子目录 | 归类范围 |
|---|---|---|
| 一、LLM 大模型基础理论 | `content/02_models/fundamentals/` | 架构演进、预训练语言模型基础 |
| 二、主流大模型系列 | `content/02_models/model-series/` | GPT、BERT、开源模型家族 |
| 三、大模型核心技术 | `content/02_models/core-techniques/` | 注意力优化、位置编码、高效推理、长文本处理 |
| 四、大模型训练技术 | `content/02_models/training/` | 预训练、指令微调、对齐、持续学习 |
| 五、多模态大模型 | `content/02_models/multimodal/` | VLM、统一多模态模型、视觉定位与检测 |
| 六、模型部署与服务化 | `content/02_models/deployment/` | 本地部署、云端服务、推理引擎、软件部署架构、硬件支持 |
| 七、模型评估与选型 | `content/02_models/evaluation/` | 模型评估方法、按场景/规模选型 |
| 八、前沿技术方向 | `content/02_models/frontier/` | MoE、推理增强、长上下文、Agent 与工具使用、技术趋势 |

### 什么情况下优先归模型算法篇

1. 当知识点主要关注模型本身的原理、训练、推理、部署、评估或选型时，优先归模型算法篇。
2. 当主题是“模型如何工作、如何训练、如何部署、如何优化推理服务”时，即使会涉及工程组件，也应优先归本篇。
3. 推理引擎、模型服务软件架构、部署优化链路，默认先看 `六、模型部署与服务化`，不要先放工程篇。
4. 若知识点的主体是模型能力边界、参数规模、评测基准或推理效率，而不是 Agent 工作流本身，也应归本篇。

### 常见混淆项

| 容易混淆的概念 | 本篇归类 | 不归本篇的情况 | 判断关键点 |
|---|---|---|---|
| vLLM / SGLang / TGI / Triton | `deployment/` | 不放工程篇框架目录 | 这是模型服务与推理部署软件栈，不是 Agent 开发框架 |
| 多模态模型 vs OCR / 语音工具 | 模型原理、架构、统一多模态能力放 `multimodal/` | 具体 OCR 服务、Whisper 等工具化使用放生态工具篇 | 看重点是模型能力还是工具化应用 |
| 模型评估 vs Agent 评估 | 基准测试、模型能力评估、模型选型放 `evaluation/` | Agent 行为评估、RAG 评估平台放生态工具篇 | 看对象是“模型”还是“Agent 系统/工具” |
| Agent 与工具使用 | 作为模型能力前沿趋势时可放 `frontier/` | Tool Use 机制、MCP 协议、运行时编排放工程篇 | 看它是在讲模型研究方向还是工程实现机制 |

### 最低锚点规则

- 二级标题代表 `content/02_models/*` 的子目录主题。
- 三级标题代表可生成卡片的最小知识单元，可以是模型系列、训练方法、推理技术、部署工具或对比项。
- 若暂时没有同名三级条目，但已有可挂靠的二级主题，应先补三级锚点。

### 扩展部署主题锚点

新增部署相关知识点时，优先挂靠以下容器：

- `六、模型部署与服务化`：承载推理引擎、服务框架、部署拓扑、硬件协同
- `七、模型评估与选型`：承载模型评测体系、选型方法、成本与效果取舍
- `八、前沿技术方向`：承载尚未完全沉淀的新型推理、长上下文、MoE、Agent 化能力趋势

### 粒度说明

- **二级标题 = 子目录主题**，直接决定落入哪个 `content/02_models/*`。
- **三级标题 = 可生成卡片的最小粒度**，可以是一个模型家族、一个训练技术、一个部署引擎或一组对比主题。
- 列表项用于限定该卡片应覆盖的关键面向，如架构、优化点、适用场景与边界。

---

## 一、LLM 大模型基础理论

### 1.1 模型架构演进
- 循环神经网络（RNN/LSTM/GRU）
    - 序列建模基础
    - 长距离依赖问题
    - 梯度消失/爆炸
- Transformer 架构
    - 自注意力机制（Self-Attention）
    - 多头注意力（Multi-Head Attention）
    - 位置编码（Positional Encoding）
    - 前馈神经网络（FFN）
    - 层归一化（Layer Normalization）
    - Encoder-Decoder 架构
- Transformer 变体
    - Encoder-only（BERT 系列）
    - Decoder-only（GPT 系列）
    - Encoder-Decoder（T5、BART）

### 1.2 预训练语言模型（PLM）
- 预训练范式
    - 自回归语言模型（Autoregressive LM）
    - 自编码语言模型（Autoencoding LM）
    - 序列到序列模型（Seq2Seq）
- 预训练任务
    - 掩码语言模型（MLM）
    - 下一句预测（NSP）
    - 因果语言模型（CLM）
    - 去噪自编码器（Denoising AE）

---

## 二、主流大模型系列

### 2.1 GPT 系列（OpenAI）
- GPT-1：生成式预训练、单向 Transformer
- GPT-2：零样本学习、更大规模参数
- GPT-3：上下文学习（ICL）、少样本学习、1750 亿参数
- GPT-3.5/ChatGPT：指令微调（RLHF）、对话能力
- GPT-4：多模态、更强推理、长上下文
- GPT-4o：原生多模态统一模型
- o1/o3 系列：推理增强模型

### 2.2 BERT 系列（Google）
- BERT：双向 Transformer、MLM+NSP
- RoBERTa：动态掩码、更大数据
- ALBERT：参数共享、轻量化
- DistilBERT：知识蒸馏、模型压缩
- SpanBERT / ELECTRA / DeBERTa

### 2.3 开源大模型生态
- LLaMA 系列（Meta）：LLaMA/LLaMA-2/LLaMA-3，开源可商用
- Qwen 系列（阿里）：Qwen/Qwen2/Qwen2.5/Qwen3，多模态能力
- Baichuan 系列（百川）：中文优化、多尺寸
- GLM 系列（智谱）：ChatGLM/GLM-4，中文对话
- DeepSeek 系列：MoE 架构、推理增强
- Yi 系列（零一万物）：长上下文、多语言
- Mistral 系列：高效推理、MoE 架构

---

## 三、大模型核心技术

### 3.1 注意力机制优化
- 稀疏注意力（Longformer、BigBird、LongT5）
- 线性注意力（Performer、Linear Transformer）
- Flash Attention（IO 感知优化、内存效率）
- 滑动窗口注意力（Mistral SWA）

### 3.2 位置编码技术
- 绝对位置编码（正弦余弦、可学习）
- 相对位置编码（T5、Transformer-XL）
- 旋转位置编码（RoPE）：旋转矩阵、长度外推
- ALiBi 位置编码：线性偏置、无需训练

### 3.3 高效推理技术
- 模型量化：INT8/INT4、GPTQ/AWQ/GGUF、混合精度
- 模型压缩：知识蒸馏、剪枝（Pruning）、低秩分解
- KV Cache 优化：PagedAttention、KV Cache 共享、滑动窗口缓存

### 3.4 长文本处理技术
- 上下文扩展：位置插值（PI）、NTK-aware 插值、YaRN
- 滑动窗口与分块处理
- 外部记忆库与向量检索增强

---

## 四、大模型训练技术

### 4.1 预训练技术
- 数据准备：大规模语料收集、数据清洗与过滤、去重、质量评估
- 分布式训练：数据并行、张量并行、流水线并行、3D 并行策略
- 训练优化：混合精度训练（FP16/BF16）、梯度累积、激活检查点、ZeRO 优化器
- 训练框架：Megatron-LM、DeepSpeed、FSDP、Colossal-AI

### 4.2 指令微调（Instruction Tuning）
- 指令数据构建：人工标注、自动生成、Self-Instruct、Evol-Instruct
- 微调方法
    - 全参数微调
    - 参数高效微调（PEFT）：LoRA/QLoRA、AdaLoRA、Prefix Tuning、Prompt Tuning、P-Tuning v2
- 多任务微调：任务混合策略、任务平衡采样

### 4.3 对齐技术（Alignment）
- 人类反馈强化学习（RLHF）：奖励模型训练、PPO 算法、KL 散度约束
- AI 反馈强化学习（RLAIF）：AI 奖励模型、宪法 AI
- 直接偏好优化（DPO）：无需奖励模型、直接优化偏好
- 其他对齐方法：IPO、KTO、ORPO

### 4.4 持续学习与增量训练
- 持续预训练：领域适应、知识更新、灾难性遗忘缓解
- 增量微调：新任务学习、知识注入、参数隔离方法

---

## 五、多模态大模型

### 5.1 视觉-语言模型（VLM）
- 架构类型：双编码器、融合编码器、编码器-解码器
- 主流模型：CLIP、BLIP/BLIP-2、LLaVA、Qwen-VL、GPT-4V
- 视觉编码器：ViT、Swin Transformer、ConvNeXt
- 视觉-语言对齐：投影层、Q-Former、Cross-Attention

### 5.2 多模态统一模型
- 统一架构：GPT-4o、Gemini、Qwen2.5-Omni
- 多模态能力：图像理解与生成、视频理解、音频处理、跨模态检索

### 5.3 视觉定位与检测
- 视觉定位（Visual Grounding）
- 开放词汇检测：Grounding DINO、GLIP

---

## 六、模型部署与服务化

### 6.1 本地部署模型
- 文本生成类：Qwen3 系列
- 视觉多模态类：Qwen2.5-VL、Qwen3-VL 系列
- 原生多模态类：Qwen3.5 系列（可理解视频）
- 统一多模态类：Qwen2.5-Omni-7B、Wan-AI/Wan2.2-TI2V-5B
- BERT/NLP 类：bert-base-chinese
- 视觉问答类：MiniCPM-V、InternLM-XComposer
- 视觉定位类：YOLO、Qwen-VL 系列
- GUI（具身智能）：Magma-8B

### 6.2 云端模型服务
- 豆包（Doubao）—— 字节跳动
- 通义千问（Qwen）—— 阿里云
- DeepSeek
- Gemini —— Google
- SiliconFlow —— 硅基流动
- ModelScope —— 魔搭

### 6.3 硬件支持
- NVIDIA（GPU 显卡）
- 华为（昇腾系列）
- 沐曦（国产 GPU）

### 6.4 软件部署架构
- vLLM：PagedAttention、连续批处理、流式输出
- SGLang：灵活调度、RadixAttention、Python 原生
- FlagOS：模型部署平台
- 与 Agent 工程框架的边界

### 6.5 推理引擎
- TensorRT-LLM：NVIDIA 优化、FP8 支持
- llama.cpp：CPU 推理、量化支持、跨平台

### 6.6 部署架构体系
- 模型部署五层架构（基础设施层 → 模型优化层 → 推理引擎层 → 服务层 → 应用层）
- 部署优化策略
    - 模型并行：张量并行（TP）、流水线并行（PP）、专家并行（EP）
    - 批处理优化：静态/动态/连续批处理
    - 显存优化：激活重计算、梯度检查点、KV Cache 优化
- 服务化部署
    - API 服务框架：FastAPI + Uvicorn、TGI、Triton Inference Server
    - 负载均衡：请求队列、多实例部署、自动扩缩容
    - 监控与日志

---

## 七、模型评估与选型

### 7.1 模型评估方法
- 基准测试：MMLU、HellaSwag、WinoGrande、HumanEval、GSM8K、C-Eval、CMMLU
- 能力评估维度：语言理解、推理、代码、数学、多语言、长文本
- 安全性评估：有害内容检测、偏见评估、对抗攻击测试

### 7.2 按场景选型
| 场景 | 推荐模型 | 理由 |
|------|---------|------|
| 通用对话 | GPT-4、Claude、Qwen-Max | 综合能力强 |
| 长文本处理 | Claude-3、GPT-4-Turbo | 上下文窗口大 |
| 代码生成 | GPT-4、DeepSeek-Coder | 代码能力强 |
| 数学推理 | GPT-4、Gemini、Qwen-Max | 逻辑推理强 |
| 多模态理解 | GPT-4V、Gemini、Qwen-VL | 视觉理解强 |
| 轻量化部署 | LLaMA-3-8B、Qwen-7B、Mistral-7B | 推理成本低 |
| 中文场景 | Qwen、GLM-4、Baichuan | 中文能力强 |

### 7.3 按规模选型
| 参数规模 | 典型模型 | 适用场景 | 硬件需求 |
|---------|---------|---------|---------|
| 7B | LLaMA-3-8B、Qwen-7B | 轻量级应用 | 1×A100/4090 |
| 13-14B | Qwen-14B、Baichuan-13B | 中等复杂度 | 2×A100 |
| 30-40B | Yi-34B、Qwen-32B | 复杂推理 | 4×A100 |
| 70B | LLaMA-3-70B、Qwen-72B | 高质量生成 | 8×A100 |
| 100B+ | GPT-4、Claude-3 | 最复杂任务 | 大规模集群 |

---

## 八、前沿技术方向

### 8.1 混合专家模型（MoE）
- MoE 架构：专家网络、路由机制、负载均衡
- 主流 MoE 模型：Mixtral、DeepSeek-MoE、Grok-1
- MoE 优化：专家选择策略、通信优化、显存优化

### 8.2 推理能力增强
- 推理时计算扩展（Test-time Compute Scaling）
- 思维链/思维树/思维图（见 Prompt Engineering 篇详细展开）
- 自我反思与自我纠正

### 8.3 长上下文技术
- 上下文窗口扩展：位置编码外推、长文本训练、上下文压缩
- 长文本推理优化：分块注意力、稀疏注意力、线性注意力

### 8.4 Agent 与工具使用
- 工具学习：工具调用、工具组合、工具创建
- 自主 Agent：任务规划、自我反思、多 Agent 协作
- 具身智能：机器人控制、环境感知、动作执行

### 8.5 技术发展趋势
- 效率提升：更小模型实现更强能力、训练效率提升、推理成本降低
- 能力扩展：多模态融合、长期记忆与持续学习、具身智能
- 安全与对齐：可解释性、安全性增强、价值观对齐、隐私保护
- 应用深化：垂直领域专业化、端侧部署普及、多 Agent 协作、人机协同
