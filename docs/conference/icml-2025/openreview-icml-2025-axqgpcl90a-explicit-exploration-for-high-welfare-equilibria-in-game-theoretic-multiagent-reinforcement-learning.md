---
title: Explicit Exploration for High-Welfare Equilibria in Game-Theoretic Multiagent Reinforcement Learning
title_zh: 博弈论多智能体强化学习中高福利均衡的显式探索
authors: "Austin A. Nguyen, Anri Gu, Michael P. Wellman"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AxqgpcL90a"
tags: ["query:marl"]
score: 9.0
evidence: 聚焦于博弈论多智能体强化学习中的均衡选择
tldr: 在博弈论多智能体强化学习中，存在多个均衡时如何选择高福利均衡是挑战。本文在策略空间响应谱框架中引入显式探索，通过模仿高福利行为生成探索策略，并训练正则化响应。实验表明该方法能发现更优福利均衡，且计算成本低。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1683, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 690, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1646, \"height\": 783, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 1360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1606, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1552, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-axqgpcl90a/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1623, \"height\": 1719, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 415, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1358, \"height\": 981, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 890, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 747, \"height\": 469, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 894, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1341, \"height\": 1476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-axqgpcl90a/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1236, \"height\": 1516, \"label\": \"Table\"}]"
motivation: 多种均衡存在时，需要偏好高福利均衡，现有方法缺乏显式探索。
method: 在PSRO框架中，通过模仿高福利行为生成探索策略，并添加正则化。
result: 在典型博弈任务中找到更高福利的均衡。
conclusion: 显式探索能有效引导博弈论多智能体强化学习向高福利均衡收敛。
---

## Abstract
Iterative extension of empirical game models through deep reinforcement learning (RL) has proved an effective approach for finding equilibria in complex games. When multiple equilibria exist, we may also be interested in finding solutions with particular characteristics. We address this issue of equilibrium selection in the context of Policy Space Response Oracles (PSRO), a flexible game-solving framework based on deep RL, by skewing the strategy exploration process towards higher-welfare solutions. At each iteration, we create an exploration policy that imitates high welfare-yielding behavior and train a response to the current solution, regularized to be similar to the exploration policy. With no additional simulation expense, our approach, named Ex$^2$PSRO, tends to find higher welfare equilibria than vanilla PSRO in two benchmarks: a sequential bargaining game and a social dilemma game. Further experiments demonstrate Ex$^2$PSRO's composability with other PSRO variants and illuminate the relationship between exploration policy choice and algorithmic performance.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究问题**：在博弈论多智能体强化学习（MARL）中，存在多个纳什均衡时，如何选择具有更高整体福利（即所有玩家收益之和更大）的均衡？标准方法（如PSRO）虽然能够找到均衡，但未必导向高福利的解。
- **研究动机**：现有策略空间响应谱（PSRO）框架通过迭代扩展策略集来求解均衡，但策略探索过程主要依赖“最佳响应”机制，容易收敛到低福利均衡（例如协调失败的情形）。作者希望在不增加额外仿真开销的前提下，引导策略探索偏向高福利方向，实现均衡选择。
- **整体含义**：提出了一种显式探索方法（Ex²PSRO），利用已产生的仿真轨迹来提取高福利行为，并通过策略正则化影响后续策略生成，从而在不改变游戏求解框架的前提下，提高最终均衡的福利水平。

## 2. 论文提出的方法论
- **核心思想**：在PSRO的每次迭代中，从历史轨迹中筛选出高福利的轨迹，用行为克隆训练一个“探索策略”，然后在训练最佳响应时添加KL散度正则化项，使新策略接近该探索策略，从而偏向高福利行为。
- **关键技术细节**：
  - **轨迹筛选**：使用最大化最小福利准则 $C(\tau_j) = \min_p V^p_j$（对称游戏）选择前N条轨迹存入缓冲池 $B$。
  - **探索策略构建**：利用行为克隆在缓冲池 $B$ 上训练策略 $\pi^i_{\text{ex}}$，最大化 $\pi^i_{\text{ex}}(a|o) = \arg\max_{\pi_\theta} \mathbb{E}[ \pi_\theta(a_k|o_k) ]$。
  - **正则化目标**：修改最佳响应目标为 $\pi^i_\theta \approx \arg\max_{\pi_\theta} (J_i(\theta) - \beta_i R_i(\theta))$，其中 $R_i(\theta) = D_{\text{KL}}(\pi^i_{\text{ex}} \parallel \pi_\theta)$，$\beta_i$ 随时间线性退火。
  - **算法流程**：初始化随机策略 → 更新博弈模型 → 提取轨迹 → 训练探索策略 → 正则化训练响应 → 加入策略集 → 更新元策略求解器（MSS）→ 重复。
- **公式说明**：正则化项通过采样近似，使用Soft Actor-Critic（SAC）作为基础RL算法，将KL散度加入actor损失中。

## 3. 实验设计
- **使用场景/数据集**：
  - **人造MDP**：一个2玩家交替移动的协调博弈，展示Ex²PSRO能发现高福利均衡。
  - **社会困境游戏 Harvest**：两种地图变体（Harvest-Dense和Harvest-Sparse），玩家收集苹果并可能射击对手，存在过度采集与协作的权衡。
  - **讨价还价游戏 Bargaining**：两种折现因子设置（γ=0.99和γ=0.95），玩家就物品分配进行轮流出价，存在多个均衡。
- **Benchmark**：使用基于DeepMind OpenSpiel实现的PSRO框架，元策略求解器采用正则化复制动态（RRD）。
- **对比方法**：
  - **Vanilla PSRO**：无正则化的标准PSRO。
  - **Ex²PSRO**：本文提出的方法。
  - **Ablation-πex**：四种探索策略变体（Uniform、MinWelfare、MaxWelfare、PrevBR），用于消融研究。
  - **GRO**（Generalized Response Objectives）：一种优化社会福利的PSRO变体，与Ex²PSRO组合测试。
- **评估指标**：最终均衡的福利（所有玩家总收益）和后悔值（regret）。

## 4. 资源与算力
- **硬件**：实验在密歇根大学研究计算集群的CPU上运行，未使用GPU。
- **耗时**：每个PSRO/Ex²PSRO/Ablation-πex运行需2-4天（训练30个策略）。额外后悔计算另需3-4天。
- **内存**：Vanilla PSRO需5GB RAM；Ex²PSRO及变体需8-15GB RAM（存储轨迹缓冲池）。
- **总计**：4个基准场景共740次试验，每次需上述资源。作者注明计算限制导致Ex²PSRO部分调参试验仅5次重复（最终结果10次），而Vanilla PSRO直接进行10次重复。

## 5. 实验数量与充分性
- **数量**：
  - Vanilla PSRO：对每个λ参数进行10次重复（共4个环境×4-5个λ值）。
  - Ex²PSRO：网格搜索 λ 和 β_init，每次5次重复，选出最佳参数后再加5次重复，共10次最终结果。
  - Ablation-πex：每个变体10次重复，共享Ex²PSRO的最佳参数。
  - GRO+Ex²PSRO组合：使用固定超参数，进行10次重复。
- **充分性**：
  - 覆盖了多个游戏类型（协调、社会困境、讨价还价）及不同难度设置。
  - 进行了详尽的消融实验（探索策略变体、超参数敏感性）。
  - 统计检验采用Welch's t检验，比较Ex²PSRO与其他方法。
  - **客观性**：调参过程保守（Ex²PSRO仅5次重复选择参数，可能错过更优配置；Vanilla PSRO充分调参）。后悔计算时，Ex²PSRO额外评估了所有正则化策略，导致评估更严格，但仍表现出更低后悔，支持方法有效性。
  - **公平性**：作者承认调参差异可能导致比较偏向Vanilla PSRO，但结果仍显示Ex²PSRO优势，说明方法鲁棒。

## 6. 主要结论与发现
1. **福利提升**：Ex²PSRO在所有四个基准测试中均显著高于Vanilla PSRO，p值均低于0.05。
2. **探索策略选择的重要性**：Ex²PSRO（使用最大化最小福利准则+行为克隆）通常优于其他探索策略变体（Uniform、MinWelfare、MaxWelfare、PrevBR），尤其在讨价还价游戏中表现突出。
3. **收敛速度**：Ex²PSRO通常比Vanilla PSRO更快达到较低后悔值，且最终均衡的后悔值相当或更低。
4. **可组合性**：Ex²PSRO可与GRO结合，进一步提升福利（在大多数场景中优于单独使用GRO）。
5. **结构依赖性**：在社会困境游戏（Harvest）中，任何正则化（包括均匀策略）都能提升福利，因为减少过度采集有助于苹果重生；而在讨价还价游戏中，正则化方向需要更精细的设计。

## 7. 优点
- **无额外仿真开销**：仅利用已有轨迹数据，无需额外环境交互。
- **简单有效**：正则化项直接嵌入SAC训练，易于实现。
- **模块化**：可与多种PSRO变体（如GRO）组合。
- **鲁棒性**：在多个游戏类型和参数设置下表现一致。
- **理论分析**：通过人造MDP清晰地展示了机制——传统最佳响应无法发现高福利策略，而Ex²PSRO通过探索策略引导成功发现。

## 8. 不足与局限
- **计算成本**：尽管无额外仿真，但存储大量轨迹（最多10万条）导致内存需求增加（12-15GB vs 5GB）。
- **调参敏感**：β_init（初始正则化强度）和λ（MSS正则化）需要网格搜索，且受随机性影响，保守调参可能限制最佳性能。
- **假设对称游戏**：论文假设玩家对称，扩展至非对称游戏需调整准则（如进行收益归一化和构建独立探索策略），但作者在扩展讨论中提及。
- **轨迹选择准则**：采用最大化最小福利，未考虑收益分布的其他细节（如方差），可能导致偶然高福利轨迹被选中。
- **基准多样性有限**：仅测试了两种游戏（社会困境和讨价还价），未涵盖更大规模或零和博弈。
- **统计检验**：虽然进行了t检验，但未进行多重假设校正（如Bonferroni），部分低p值可能因重复检验而膨胀。
- **后悔估计偏差**：Ex²PSRO的后悔评估集大于Vanilla PSRO，使其后悔值更准确（更不易低估），但文中结果仍显示Ex²PSRO后悔相当或更低，说明方法稳健。

（完）
