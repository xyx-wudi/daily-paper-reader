---
title: "Incentivize without Bonus: Provably Efficient Model-based Online Multi-agent RL for Markov Games"
title_zh: 无需奖励加成：面向马尔可夫博弈的可证明高效在线多智能体强化学习
authors: "Tong Yang, Bo Dai, Lin Xiao, Yuejie Chi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ciUHD7jcT9"
tags: ["query:marl"]
score: 9.0
evidence: 面向马尔可夫博弈的可证明高效在线模型MARL
tldr: 马尔可夫博弈是研究多智能体强化学习的重要框架，但现有样本高效方法需复杂不确定性估计或玩家协调。本文提出VMG算法，通过偏置模型参数估计鼓励探索，在不使用奖励加成的情况下达到样本高效的纳什均衡和粗相关均衡。理论保证并实验验证。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ciuhd7jct9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1263, \"height\": 461, \"label\": \"Table\"}]"
motivation: 马尔可夫博弈中现有方法要么需定制不确定性估计，要么需玩家协调。
method: 提出VMG算法，通过偏置模型参数估计鼓励探索，无需额外奖励加成。
result: 理论证明可样本高效达到纳什均衡和粗相关均衡，实验验证。
conclusion: 无需奖励加成的模型方法可高效求解马尔可夫博弈的均衡。
---

## Abstract
Multi-agent reinforcement learning (MARL) lies at the heart of a plethora of applications involving the interaction of a group of agents in a shared unknown environment. A prominent framework for studying MARL is Markov games, with the goal of finding various notions of equilibria in a sample-efficient manner, such as the Nash equilibrium (NE) and the coarse correlated equilibrium (CCE). However, existing sample-efficient approaches either require tailored uncertainty estimation under function approximation, or careful coordination of the players. In this paper, we propose a novel model-based algorithm, called VMG, that incentivizes exploration via biasing the empirical
estimate of the model parameters towards those with a higher collective best-response values of all the players when fixing the other players' policies, thus encouraging the policy to deviate from its current equilibrium for more exploration. VMG is oblivious to different forms of function approximation, and permits simultaneous and uncoupled policy updates of all players. Theoretically, we also establish that VMG achieves a near-optimal regret for finding both the NEs of two-player zero-sum Markov games and CCEs of multi-player general-sum Markov games under linear function approximation in an online environment, which nearly match their counterparts with sophisticated uncertainty quantification.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 论文的核心问题与整体含义
- **研究动机与背景**：多智能体强化学习（MARL）在机器人、博弈论等领域有广泛应用，而马尔可夫博弈是研究MARL的标准框架。现有样本高效的MARL算法通常依赖“乐观面对不确定性”原则，通过构造置信区间或奖励加成（bonus）来引导探索。然而，这种不确定性量化在复杂函数近似（如神经网络）下设计困难，且往往需要精心协调各智能体。本文旨在探索一种**无需显式奖励加成**的探索策略，以适用于更通用的函数近似设置，同时支持各智能体独立、并行的策略更新。
- **核心问题**：能否提出一种在在线多玩家一般和马尔可夫博弈中，使用**价值激励探索**（value‑incentivized exploration）的可证明高效算法，且无需复杂的不确定性估计与玩家协调？

#### 2. 论文提出的方法论
- **核心思想**：提出名为 **VMG**（Value‑incentivized Markov Game solver）的基于模型算法。其关键创新在于：在更新模型参数时，不仅拟合已有数据，还通过一个**价值激励正则项**偏置模型估计，使得模型倾向于“当前其他玩家策略固定的情况下，所有玩家的集体最佳响应值更高”，从而鼓励当前策略偏离当前模型下的均衡，实现探索。该正则项本质上是最大化当前策略下的对偶间隔（duality gap），驱动模型远离当前估计。
- **关键技术细节**：
  - **两阶段交替**：每轮迭代进行模型更新与数据收集。
  - 模型更新：最小化带正则项的目标函数，包含对历史数据的负对数似然（或平方损失）以及所有玩家的最佳响应值之和（或其组合）。
  - 策略更新：基于更新后的模型，计算各玩家的最佳响应策略，并收集新样本。
  - 支持两种重要均衡：纳什均衡（NE）——两玩家零和博弈；粗相关均衡（CCE）——多玩家一般和博弈。
  - 算法可退化到单智能体MDP、矩阵博弈、线性bandit等场景，且当使用KL正则化时，正则项有闭式解，计算高效。
- **公式/算法**（文字说明）：
  - 对于矩阵博弈：每轮基于当前参数ωt‑1计算NE (μt,νt)，然后通过最小化平方损失减去α乘以前最佳响应值之差来更新ωt，最后计算最佳响应策略并采样。
  - 对于马尔可夫博弈：每轮基于当前模型ft‑1计算均衡πt，然后通过最小化负对数似然减去α乘以所有玩家的最佳响应值之和来更新ft，最后计算最佳响应策略并采样完整轨迹。

#### 3. 实验设计
- **实验覆盖**：论文为**纯理论工作**，未包含任何实验。所有结论通过数学证明获得。
- **Benchmark与对比方法**：无实验，但理论结果与现有的基于奖励加成的方法（如MEX）进行了理论对比，指出VMG在计算复杂度和适用范围上更优。
- **学习与评估场景**：论文定义了两种场景：两玩家零和矩阵博弈（线性函数近似）与多玩家一般和有限/无限期马尔可夫博弈（线性混合模型）。在每个场景下分析了遗憾界（regret bound）和样本复杂度。

#### 4. 资源与算力
- **未提及任何算力需求**。由于是纯理论工作，不涉及实际训练，因此没有GPU型号、数量、训练时长等信息。

#### 5. 实验数量与充分性
- **无实验**。论文仅提供了理论分析与证明，未进行数值验证。因此无法评价实验的充分性与客观性。
- 理论分析本身是严谨的，覆盖了不同博弈设置，并给出了详细的证明步骤（附录占大量篇幅）。

#### 6. 论文的主要结论与发现
- VMG算法在**线性函数近似**下，对于两玩家零和矩阵博弈达到 **Õ(d√T)** 的遗憾界，对于多玩家一般和马尔可夫博弈（有限期）达到 **Õ(d√H³T)** 的遗憾界。
- 样本复杂度方面：两玩家零和矩阵博弈中需 **Õ(d²/ε²)** 样本达到ε‑NE；多玩家一般和有限期博弈中需 **Õ(N d²H⁴/ε²)** 样本（或 **Õ(N d²H³/ε²)** 轨迹）达到ε‑CCE；无限期折扣场景下需 **Õ(N d²/((1‑γ)⁴ε²))** 样本。
- 这些结果与需要显式不确定性量化的最优算法匹配（仅差对数因子），证明了价值激励探索的可证明高效性。
- VMG可退化到单智能体MDP、线性bandit等场景，并恢复或提出新的正则化形式。

#### 7. 优点
- **无需定制奖励加成**：避免构造不确定性置信区间，便于与各种函数近似（如神经网络）结合。
- **对称且解耦的更新**：所有玩家可同时独立更新策略，适合大规模多智能体系统。
- **统一框架**：能同时处理NE（零和）和CCE（一般和），并退化到单智能体及bandit情形。
- **计算可处理**：当使用KL正则化时，模型更新与策略计算均有闭式解。
- **理论保证强**：遗憾界与现有基于奖励加成方法相当，且在多个重要场景下近乎最优。

#### 8. 不足与局限
- **缺乏实验验证**：完全是理论分析，未在仿真或真实环境中验证算法实际性能，对实际应用中的效果、数值稳定性等未提供实证支持。
- **线性函数近似假设**：理论主要基于线性混合模型，对更通用的非线性函数近似（如深度神经网络）仅提到“可兼容”，但未给出相应理论保证。
- **样本复杂度中的因子**：在多玩家一般和场景中，样本复杂度存在因子H（有限期）或1/(1‑γ)⁴（无限期），可能较大，且与已有最优结果相比有额外的因子。
- **仅分析固定总迭代数T下的遗憾**：未讨论算法在非平稳环境或对抗性环境中的表现。
- **实际实现复杂性**：虽然理论计算可处理，但在大规模状态动作空间中求解模型更新正则项仍可能面临优化困难。

（完）
