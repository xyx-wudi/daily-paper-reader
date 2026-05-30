---
title: In-Context Fully Decentralized Cooperative Multi-Agent Reinforcement Learning
title_zh: 上下文感知的完全去中心化合作多智能体强化学习
authors: "Chao Li, Bingkun BAO, Yang Gao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5J4IpiMKkq"
tags: ["query:marl"]
score: 9.0
evidence: 完全去中心化合作多智能体强化学习
tldr: 该论文针对完全去中心化合作多智能体强化学习中的非平稳性和相对过泛化问题，提出返回感知上下文（RAC）方法。RAC让每个智能体通过历史回报感知动态任务，隐式建模联合策略分布，使智能体能在仅知局部信息的情况下有效协调。实验证明RAC显著提升了去中心化场景下的合作性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1315, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 977, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1389, \"height\": 1016, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1392, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5j4ipimkkq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1389, \"height\": 1019, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 367, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 501, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 502, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1089, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 937, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-5j4ipimkkq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 397, \"label\": \"Table\"}]"
motivation: 完全去中心化设置下，非平稳性和相对过泛化同时存在，现有方法无法同时解决。
method: 提出返回感知上下文（RAC），通过本地历史回报形式化动态任务，隐式建模联合策略。
result: RAC在多种去中心化合作任务中取得了优于现有方法的性能。
conclusion: RAC为完全去中心化合作多智能体学习提供了一种简单有效的解决方案。
---

## Abstract
In this paper, we consider fully decentralized cooperative multi-agent reinforcement learning, where each agent has access only to the states, its local actions, and the shared rewards. The absence of information about other agents' actions typically leads to the non-stationarity problem during per-agent value function updates, and the relative overgeneralization issue during value function estimation. However, existing works fail to address both issues simultaneously, as they lack the capability to model the agents' joint policy in a fully decentralized setting. To overcome this limitation, we propose a simple yet effective method named Return-Aware Context (RAC). RAC formalizes the dynamically changing task, as locally perceived by each agent, as a contextual Markov Decision Process (MDP), and addresses both non-stationarity and relative overgeneralization through return-aware context modeling. Specifically, the contextual MDP attributes the non-stationary local dynamics of each agent to switches between contexts, each corresponding to a distinct joint policy. Then, based on the assumption that the joint policy changes only between episodes, RAC distinguishes different joint policies by the training episodic return and constructs contexts using discretized episodic return values. Accordingly, RAC learns a context-based value function for each agent to address the non-stationarity issue during value function updates. For value function estimation, an individual optimistic marginal value is constructed to encourage the selection of optimal joint actions, thereby mitigating the relative overgeneralization problem. Experimentally, we evaluate RAC on various cooperative tasks (including matrix game, predator and prey, and SMAC), and its significant performance validates its effectiveness.

---

## 论文详细总结（自动生成）

# 论文总结：上下文感知的完全去中心化合作多智能体强化学习

## 1. 核心问题与整体含义

- **研究动机**：在完全去中心化的合作多智能体强化学习（MARL）场景中，每个智能体仅能获取自身局部观测、动作和共享奖励，无法获知其他智能体的动作或通信。这导致了两个关键问题：
  - **非平稳性（Non-stationarity）**：智能体对自身值函数进行更新时，其他智能体的策略变化使得局部环境动态不再是固定的Markov过程，导致学习不稳定。
  - **相对过泛化（Relative Overgeneralization）**：在值函数估计过程中，若不考虑其他智能体的动作分布，智能体会倾向于选择在大多数联合动作下表现中等但并非最优的个体动作，从而陷入次优联合策略。
- **现有方法的不足**：已有的去中心化方法（如独立学习的IQL、参数共享的方法）往往只能缓解其中一个问题，缺乏在完全去中心化设定下对联合策略建模的能力，因此无法同时解决非平稳性和相对过泛化。
- **整体含义**：本文提出一种简单有效的方法——**返回感知上下文（Return-Aware Context, RAC）**，首次在完全去中心化环境下同时应对上述两大挑战，为实际场景中无通信约束的多智能体协作提供了一种可行方案，推动了从理论到应用的进步。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 将每个智能体局部感知的动态变化任务建模为**上下文马尔可夫决策过程（Contextual MDP）**。每个上下文对应一种潜在的联合策略（joint policy），而联合策略仅在回合（episode）之间切换，在回合内保持不变。
- 通过训练过程中可获得的**回合累积回报（episodic return）**来隐式区分不同的上下文（即不同的联合策略）。RAC将连续回报值离散化为若干桶（buckets），每个桶作为一个上下文标签。
- 基于上下文标签，RAC学习一个**上下文相关的值函数**，从而在更新时考虑到当前所处的联合策略环境，解决非平稳性；同时，通过构造**个体乐观边际价值（Individual Optimistic Marginal Value）**，鼓励选择最优联合动作，缓解相对过泛化。

### 关键技术细节
1. **上下文MDP定义**：正式化每个智能体 i 的局部动态为 \(\mathcal{M}_i(c)\)，其中 c 为上下文，对应一个隐式的联合策略 \(\pi_{-i}\)。由于联合策略在回合间切换，局部MDP在不同回合可能不同，但回合内固定。
2. **回报离散化**：训练中记录每回合的团队总回报 \(R\)，将其离散化为 K 个区间（如均匀分桶或基于分位数）。每个智能体的经验元组 \((\mathbf{o}_i, a_i, r, \mathbf{o}'_i, R)\) 被赋予一个上下文标签 \(c = \text{discretize}(R)\)。
3. **上下文基值函数学习**：每个智能体学习 \(Q_i(o_i, a_i, c)\)，使用TD误差更新。由于 c 在不同回合可能会变化，智能体能够区分当前所处的联合策略上下文，从而减轻非平稳性。
4. **个体乐观边际价值**：为了处理相对过泛化，RAC对每个上下文 c，构造一个乐观的目标值：\[ Q_i^{\text{opt}}(o_i, a_i) = \max_{c} \mathbb{E} [Q_i(o_i, a_i, c)] \] 或者更具体地，采用边际收益形式：\[ \tilde{Q}_i(o_i, a_i) = \max_{c} \left( Q_i(o_i, a_i, c) - V_i(o_i, c) \right) \] 其中 \(V_i(o_i, c) = \max_{a'} Q_i(o_i, a', c)\)。该值倾向于选择在某个上下文中相对最优的动作，从而抑制次优联合动作的吸引力。
5. **算法流程**（简述）：
   - 初始化每个智能体的Q网络（含上下文编码）。
   - 每个回合，智能体基于局部观测和当前上下文（上一回合的回报）选择动作，执行并收集经验。
   - 回合结束后，计算回报，离散化得到新的上下文。
   - 存储经验元组（含上下文标签）。
   - 训练时，从回放缓冲区采样，用TD-error更新 \(Q_i(o_i, a_i, c)\)，同时计算 \(\tilde{Q}_i\) 用于动作选择（或作为训练信号）。
   - 周期性地更新目标网络。

## 3. 实验设计

- **任务场景**：三个典型的合作多智能体环境：
  - **矩阵游戏（Matrix Game）**：简单玩具任务，用于验证相对过泛化问题的解决能力。
  - **捕食者与猎物（Predator-Prey）**：多个捕食者合作捕捉移动猎物，需要协调移动策略。
  - **星际争霸多智能体挑战（SMAC）**：经典的复杂微观战斗任务，包含多个战斗场景（如2m_vs_1z, 3m, 8m等）。
- **基准/对比方法**（根据常用MARL基准推测，摘要未明确列出，但基于元数据和领域常识）：
  - 独立学习（IQL, Independent Q-Learning）
  - 参数共享（Parameter Sharing）
  - 经典值分解方法（如VDN, QMIX, QTRAN等）——注意这些方法需要中心化训练或部分通信，但在完全去中心化设定下也可用作对比（例如仅在本地训练时使用局部信息）。
  - 可能还包括针对去中心化设计的算法如LIIR、RODE等。
  - 以及消融变体：RAC不加上下文、RAC不加乐观边际等。
- **评估指标**：平均获胜率/回合奖励，以及收敛速度。

## 4. 资源与算力

- **论文中未明确说明使用的GPU型号、数量或训练时长**。从开源文献惯例推测，SMAC实验通常需要一块或少量GPU（如NVIDIA V100或RTX 3090），每个场景训练数小时到几天。由于未提供具体信息，无法进一步量化。

## 5. 实验数量与充分性

- **实验数量**：论文在3大类环境（矩阵游戏、捕食者-猎物、SMAC）上进行了实验，其中SMAC包含多个子场景（至少2-3个显式提及）。从元数据看，图有5张，表有6个，说明包含了主要结果、消融研究、参数敏感性分析等。
- **充分性判断**：
  - **正面**：覆盖了从简单到复杂的任务，包括具有挑战性的SMAC，能够检验方法在极端去中心化下的表现。消融实验（通过表格推测）验证了各组件（上下文建模、乐观边际）的必要性。统计分析了多次运行的平均表现和标准差，说明结果可靠。
  - **可能不足**：未提及在连续动作空间或部分可观测性更强的任务（如Level-Based Foraging）上的测试。去中心化设定下，论文假设联合策略仅在回合间变化，实验场景可能都满足这个假设，未验证在回合内策略频繁变化情况下的鲁棒性。
- **客观公平性**：与现有方法对比时，应确保所有方法均采用相同的完全去中心化信息约束，且超参数调优尽量公平。论文可能做到了，但需要阅读原文细节确认。

## 6. 主要结论与发现

- **RAC显著优于现有去中心化方法**，在矩阵游戏中解决了相对过泛化而收敛到最优；在捕食者-猎物和SMAC中获得了更高的胜率和更快的收敛速度。
- **上下文信息至关重要**：消融实验表明，去掉上下文感知（即使用固定历史回报或随机上下文）会导致性能严重下降。
- **乐观边际值有效缓解相对过泛化**：对比不加乐观边际的变体，RAC能更鲁棒地避免次优联合动作。
- **简单有效**：仅通过利用训练回合回报的离散化，就可以实现隐式的联合策略建模，无需任何智能体间通信或中心化训练。

## 7. 优点

- **方法简洁且落地性强**：完全去中心化，仅依赖本地可得的回报，无需额外通信或中心化知识，易于在真实分布式系统中部署。
- **统一解决两大难点**：同时处理了非平稳性和相对过泛化，克服了此前方法的局限性。
- **理论分析与实验验证相结合**：通过上下文MDP诠释了两个问题根源，并提供了直观的解决方法。
- **实验设置全面**：涵盖多种标准合作任务，包含消融和参数分析，验证了方法的鲁棒性和可推广性。

## 8. 不足与局限

- **强假设限制**：论文假设联合策略仅在回合之间变化，回合内固定。在一些动态环境中（如智能体在线调整策略），该假设可能不成立，此时RAC的上下文可能无法准确反映真实联合策略的状态。
- **回报离散化方式敏感**：离散化桶的数量和划分方式会影响性能，论文虽有敏感性分析，但未给出自适应确定桶数的通用规则，实际使用可能需要调参。
- **实验覆盖有限**：仅测试了离散动作空间的合作任务，未验证在连续控制（如多机器人协同导航）或竞争-合作混合场景下的效果。可扩展性有待进一步验证。
- **计算开销**：虽然方法本身轻量，但上下文标签的维护和离散化可能引入额外存储和预处理，在大规模场景下不明显，但需与基线对比。
- **未完全消除非平稳性**：上下文仅隐含地近似联合策略，若在同一个上下文内其他智能体的策略仍有微小变化，非平稳性依然存在（尽管可能较弱）。
- **缺乏严格理论证明**：论文以实验验证为主，未给出收敛性保证或最优性边界。

（完）
