---
title: "From Debate to Equilibrium: Belief‑Driven Multi‑Agent LLM Reasoning via Bayesian Nash Equilibrium"
title_zh: 从辩论到均衡：基于贝叶斯纳什均衡的信念驱动多智能体LLM推理
authors: "Xie Yi, Zhanke Zhou, Chentao Cao, Qiyu Niu, Tongliang Liu, Bo Han"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=RQwexjUCxm"
tags: ["query:marl"]
score: 7.0
evidence: 将多智能体协调建模为不完全信息博弈并利用强化学习求解贝叶斯纳什均衡
tldr: 针对多智能体LLM推理计算成本高且缺乏收敛保证的问题，将多LLM协调建模为不完全信息博弈并寻求贝叶斯纳什均衡。提出ECON框架，采用分层强化学习范式，结合分布式推理与集中式最终输出。每个LLM基于对其他智能体策略的信念独立选择响应以最大化期望奖励。实验表明ECON有效提升了推理效率并保证了收敛。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1731, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 884, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1760, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1036, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 964, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1389, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1382, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1381, \"height\": 880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1384, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1381, \"height\": 877, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1494, \"height\": 937, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1727, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1631, \"height\": 722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 832, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 2165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 2247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 1502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 687, \"height\": 1770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 689, \"height\": 1773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 686, \"height\": 1775, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 689, \"height\": 1778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 686, \"height\": 1774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 688, \"height\": 1778, \"label\": \"Table\"}]"
motivation: 多智能体LLM推理存在计算开销大和缺乏收敛保证的问题。
method: 将多LLM协调视为不完全信息博弈，提出ECON分层RL框架实现分布式推理与集中输出。
result: ECON在提升推理效率的同时保证了收敛性。
conclusion: 将多智能体协调与博弈论结合是提升LLM推理能力的有效途径。
---

## Abstract
Multi-agent frameworks can substantially boost the reasoning power of large language models (LLMs), but they typically incur heavy computational costs and lack convergence guarantees. To overcome these challenges, we recast multi-LLM coordination as an incomplete-information game and seek a Bayesian Nash equilibrium (BNE), in which each agent optimally responds to its probabilistic beliefs about the strategies of others. We introduce Efficient Coordination via Nash Equilibrium (ECON), a hierarchical reinforcement-learning paradigm that marries distributed reasoning with centralized final output. Under ECON, each LLM independently selects responses that maximize its expected reward, conditioned on its beliefs about co-agents, without requiring costly inter-agent exchanges.
We mathematically prove that ECON attains a markedly tighter regret bound than non-equilibrium multi-agent schemes. Empirically, ECON outperforms existing multi-LLM approaches by 11.2% on average across six benchmarks spanning complex reasoning and planning tasks. Further experiments demonstrate ECON’s ability to flexibly incorporate additional models, confirming its scalability and paving the way toward larger, more powerful multi-LLM ensembles. The code is publicly available at: https://github.com/tmlr-group/ECON.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
多智能体框架能显著增强大型语言模型（LLM）的推理能力，但现有方法（如多智能体辩论MAD）存在三大障碍：
- **高计算开销**：智能体间大量显式消息交换消耗海量token；
- **上下文窗口限制**：多轮交换的信息量易超出LLM的上下文容量，限制可扩展性；
- **缺乏收敛保证**：无明确定义的协调协议时，系统可能性能不佳，甚至不如简单集成或自一致性方法。

因此，需要一种**有理论保证、可扩展且高效**的多LLM协调方案。本文提出将多LLM协调建模为**不完全信息博弈**，并寻求**贝叶斯纳什均衡（BNE）**，从而以信念替代直接通信，降低开销并保证收敛。

## 2. 论文提出的方法论
### 2.1 核心思想
- 将多智能体LLM系统形式化为**去中心化部分可观察马尔可夫决策过程（DEC-POMDP）**。
- 每个执行LLM维护一个**信念网络**，将局部历史与观测映射为信念状态，并输出动作（提示嵌入：温度与重复惩罚参数）。
- 引入**协调器LLM**生成策略与格式，指导执行LLM。
- 通过**信念编码器**聚合所有信念状态为组级表示，并由**集中式混合网络**优化全局Q值，推动系统收敛至BNE。

### 2.2 关键技术细节
- **个体信念网络**：Bi(τ_i, o_i; θ_Bi) → 信念状态b_i → 动作e_i=[T_i, p_i] + 局部Q值。
- **信念编码器**：多头注意力机制聚合信念状态，生成组级表示E。
- **集中式混合网络**：结合局部Q值和特征变换，计算全局Q值Q_tot，通过TD损失和相似性损失（L_SD）训练，保证单调性（局部Q值改进推动全局改进）。
- **奖励设计**：三部分奖励——动作似然奖励（与协调器输出相似度）、任务特定奖励、协作贡献奖励，加权组合（动态调整权重）。
- **早期停止**：基于输出稳定性、平均奖励阈值、损失收敛三个条件。
- **算法流程**（算法1）：初始化参数→每轮并行执行LLM获取输出与奖励→更新信念编码器与混合网络→检查收敛。

### 2.3 理论贡献
- 证明BNE存在性（通过Glicksberg不动点定理）。
- 推导次线性遗憾界：**O(N√T/(1-γ))**（N为智能体数，T为迭代次数），而现有MAD方法为线性遗憾Ω(NT/(1-γ)）。

## 3. 实验设计
### 3.1 数据集/场景
- 5个推理任务：**GSM8K、GSM-Hard、MATH、SVAMP**（数学推理），**StrategyQA**（常识推理）。
- 规划任务：**TravelPlanner**（使用GPT-4-Turbo评估）。

### 3.2 Benchmark与方法对比
- **单轮CoT**：零样本/少样本CoT。
- **多轮CoT**：Self-Consistency（SC@maj64）。
- **值引导搜索**：TS-LLM、PPO-MCTS。
- **多轮自改进**：ToT、RAP、ReAct。
- **多LLM推理框架**：rStar、Multi-Agent Debate（MAD）。

### 3.3 模型
- 执行LLM：LLaMA3.1 8B/70B/405B、Mistral-7B、Mixtral-8x22B、Qwen1.5 110B。
- 协调器LLM：通常与执行LLM同构或更强（实验中固定为LLaMA3.1 70B，部分实验用GPT-4）。

### 3.4 实验设置
- 默认：1协调器+3执行LLM（零样本）。
- 协调器策略生成长度约束：软50 token，硬70 token（含重试机制）。

## 4. 资源与算力
论文**未明确说明**训练所使用GPU型号、数量及训练时长。仅提及“learnable params ~1.7M（8B模型）或~2.5M（405B模型）”，暗示模型轻量，但具体算力细节缺失。

## 5. 实验数量与充分性
- **主实验**：在5个推理数据集上对比9种方法，报告平均准确率（图3）及每个数据集详细结果（附录E）。
- **TravelPlanner实验**：对比Greedy Search、CoT、ReAct、Reflexion等，ECON取得最高最终通过率（7.2%验证集，9.3%测试集）。
- **异构/同构实验**（表2）：验证不同LLM组合效果，包括强协调器+弱执行、弱协调器+强执行、同构/异构组。
- **Token效率实验**（表3）：对比ECON、MAD、RAP、SC在MATH、GSM8K、GSM-Hard上的token消耗与性能，ECON token减少21.4%（vs MAD）。
- **可扩展性实验**（图4、5）：从3执行LLM逐步增加至9，并引入多协调器层级结构，性能提升18.1%。
- **消融实验**（表5、6）：研究奖励组件（R1/R2/R3）、策略类型（S1/S2/S3）及模块（信念编码器、连接层）的影响。
- **BNE达成前后对比**（表5）：性能平均提升14%。
- **完整信息vs不完整信息对比**（表4）：加入直接通信后性能仅提升1.1%但token增加42.4%。

**充分性评价**：实验覆盖广泛，包括不同模型大小、异构组合、可扩展性、Token效率、消融研究；对比方法多样且最新；但缺乏对训练稳定性的详细分析，且未在更真实场景（如开放域对话）中验证。

## 6. 论文的主要结论与发现
- **ECON方法有效**：在6个基准上平均优于单智能体方法10.9%，优于现有多智能体方法11.2%。
- **BNE收敛理论验证**：更紧的遗憾界（O(N√T) vs Ω(NT)）得到实证支持（策略趋于稳定）。
- **Token效率高**：相比MAD节省21.4% token，且不依赖直接通信。
- **可扩展性强**：通过层级结构（多协调器）可扩展至9+执行LLM，性能持续提升。
- **异构模型仍有效**：弱模型组合通过BNE协调可超越基线的少样本CoT。
- **战略设计关键**：协调器提供策略（而非直接答案）能引导执行LLM更好协作。

## 7. 优点
- **理论严谨**：首次将BNE引入多LLM推理，给出存在性证明与遗憾分析。
- **高效简洁**：用信念替代消息传递，大幅降低通信成本，同时保持甚至提升性能。
- **模块化设计**：信念网络、编码器、混合网络可独立优化，便于扩展与集成新模型。
- **实验充分**：覆盖多种模型规模、任务类型、对比方法，消融实验验证各组件贡献。
- **可扩展方案**：提出层级协调机制（局部+全局协调器）实现大规模部署，实证有效。

## 8. 不足与局限
- **算力信息缺失**：未报告训练具体GPU型号、数量及时间，难以复现成本评估。
- **任务范围有限**：仅测试数学推理与规划任务，未涉及文本生成、问答、代码生成等，泛化性待验证。
- **奖励设计依赖人工**：协作贡献奖励需依赖协调器评估，可能存在偏见；动态权重调整未深入分析稳定性。
- **早期停止阈值敏感性**：参数ϵ_C、R_th、ϵ_L需手动设定，不同任务可能需调整。
- **异构模型表现略差**：虽仍优于基线，但同构模型在BNE达成上更优，实际部署可能需平衡模型统一性。
- **未讨论训练时间**：虽然提到模型轻量，但实际训练迭代次数（如120-200 episodes）及时间未知。

（完）
