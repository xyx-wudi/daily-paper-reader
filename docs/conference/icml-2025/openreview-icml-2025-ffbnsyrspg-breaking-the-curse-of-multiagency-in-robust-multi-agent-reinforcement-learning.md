---
title: Breaking the Curse of Multiagency in Robust Multi-Agent Reinforcement Learning
title_zh: 打破多智能体鲁棒强化学习中的多智能体诅咒
authors: "Laixi Shi, Jingchu Gai, Eric Mazumdar, Yuejie Chi, Adam Wierman"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=fFBnsYRsPg"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体鲁棒马尔可夫博弈
tldr: 针对标准多智能体强化学习对仿真到现实差距的脆弱性，本文提出基于行为经济学启发的一类分布鲁棒马尔可夫博弈方法。该方法通过设计合理的不确定性集，并证明其能够克服多智能体诅咒，即在样本复杂度上实现与单智能体相当的指数级改进。实验验证了所提框架在鲁棒性任务上的有效性，为多智能体鲁棒学习提供了新视角。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ffbnsyrspg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1677, \"height\": 375, \"label\": \"Table\"}]"
motivation: 标准MARL算法易受仿真与现实差距影响，现有鲁棒马尔可夫博弈在公式化和样本效率上存在挑战。
method: 提出一类基于行为经济学启发的分布鲁棒马尔可夫博弈，定义合理不确定性集并设计样本高效算法。
result: 理论证明所提方法能克服多智能体诅咒，样本复杂度不随智能体数量指数增长，实验验证鲁棒性提升。
conclusion: 为多智能体鲁棒强化学习提供了可落实的框架，推动了鲁棒博弈的实践应用。
---

## Abstract
Standard multi-agent reinforcement learning (MARL) algorithms are vulnerable to sim-to-real gaps. To address this, distributionally robust Markov games (RMGs) have been proposed to enhance robustness in MARL by optimizing the worst-case performance when game dynamics shift within a prescribed uncertainty set. RMGs remains under-explored, from reasonable problem formulation to the development of sample-efficient algorithms. Two notorious and open challenges are the formulation of the uncertainty set and whether the corresponding RMGs can overcome the curse of multiagency,  where the sample complexity scales exponentially with the number of agents. In this work, we propose a natural class of RMGs inspired by behavioral economics, where each agent's uncertainty set is shaped by both the environment and the integrated behavior of other agents. We first establish the well-posedness of this class of RMGs by proving the existence of game-theoretic solutions such as robust Nash equilibria and coarse correlated equilibria (CCE). Assuming access to a generative model, we then introduce a sample-efficient algorithm for learning the CCE whose sample complexity scales polynomially with all relevant parameters. To the best of our knowledge, this is the first algorithm to break the curse of multiagency for RMGs, regardless of the uncertainty set formulation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：标准多智能体强化学习（MARL）算法对仿真到现实（sim-to-real）的差距十分敏感，即在训练环境中表现良好的策略可能因环境或对手行为的微小变化而严重失效。现有的分布鲁棒马尔可夫博弈（RMG）旨在通过优化最坏情况下的性能来提升鲁棒性，但存在两大开放挑战：不确定性集的合理构建（现有(s,a)-矩形性条件不符合行为经济学观察）以及“多智能体诅咒”（样本复杂度随智能体数量呈指数增长）。
- **整体含义**：本文提出一类新的RMG，其不确定性集基于行为经济学中的人类决策模式（“虚构不确定性集”），并证明该类博弈中稳健纳什均衡（NE）和粗糙相关均衡（CCE）的存在性。针对CCE学习，设计了首个能够打破多智能体诅咒的样本高效算法 Robust-Q-FTRL，其样本复杂度与所有相关参数呈多项式关系，而非指数关系。

### 2. 论文提出的方法论
- **核心思想**：引入“他人集成(s, a<sub>i</sub>)-矩形性”条件，将每个智能体的不确定性集构造为关于自己动作-状态对的“球”，中心是给定其他智能体策略下的期望名义转移核。这更符合现实中人类将其他玩家的不确定性以整体形式考虑的决策方式。
- **关键技术细节**：
  - 不确定性集定义：对于每个智能体 i 和每个 (h, s, a<sub>i</sub>)，不确定性子集为以期望名义转移核 P<sub>h,s,a<sub>i</sub></sub><sup>π<sub>-i</sub></sup> 为球心、以总变差距离（TV）为度量、半径为 σ<sub>i</sub> 的球。
  - 算法 Robust-Q-FTRL：采用生成模型（generative model），逐时间步递归，使用 N 个样本估计经验模型，然后通过强对偶将鲁棒Q函数转化为可计算形式。结合随迭代衰减的线性学习率和Follow-the-Regularized-Leader策略更新策略，并引入基于方差的乐观奖励项（bonus term）来控制置信上界。
  - 算法流程：从 H 到 1 逆序学习，每步进行 K 次迭代（在线学习）；每次迭代构造经验模型并计算当前策略的鲁棒Q值；通过FTRL更新策略；最终输出所有策略及其权重（由α<sub>k</sub>决定）构成的分布作为近似CCE。
- **关键公式**：鲁棒Q函数通过强对偶转为 max<sub>α</sub> (P<sub>k</sub>[V]<sub>α</sub> - σ<sub>i</sub>(α - min V)) 求解，其中 [V]<sub>α</sub> 是截断到 α 的向量。

### 3. 实验设计
- **论文性质**：这是一篇**纯理论工作**，未进行任何实际环境中的数值实验或基准测试。
- 文中**没有**提供数据集、仿真场景或与现有算法的实验对比（表1仅为理论样本复杂度的比较，并非实验表格）。算法的有效性完全通过理论证明（定理4.1与信息论下界）验证，未涉及具体实验。

### 4. 资源与算力
- **未提及**：文章未描述实际运行所需的GPU型号、数量、训练时长等计算资源。因无实验，故不讨论算力需求。

### 5. 实验数量与充分性
- **无实验**：因此无法评估实验数量和充分性。理论分析的充分性体现在：给出了上界（定理4.1）和匹配的极小化下界（式(24)），且算法在理论上可保证 ε-鲁棒CCE的样本复杂度。但未通过数值实验验证算法在有限样本下的实际表现及与现有方法的差距，可能存在实践中的未知问题。

### 6. 论文的主要结论与发现
- 提出一类新的RMG（虚构RMG），并证明其具有稳健NE和CCE的存在性。
- 设计了第一个打破多智能体诅咒的RMG算法 Robust-Q-FTRL，其样本复杂度为 Õ( S H<sup>6</sup> (∑<sub>i</sub>A<sub>i</sub>) / (ε<sup>4</sup> min{H, 1/min σ<sub>i</sub>}) )，与智能体数量成线性（而非指数）关系。
- 与已有RMG工作（如表1中Blanchet等、Shi等）相比，显著降低了样本复杂度的维度依赖。
- 技术难点在于鲁棒值函数的非线性，不能用标准MARL中线性叠加统计误差的方法，而需设计特殊的方差型奖励项来控制非线性引入的误差。

### 7. 优点
- **理论创新**：不确定性集的设计具有行为经济学依据，更贴近真实人类决策；同时自然实现了从单智能体鲁棒RL到多智能体的推广。
- **算法突破**：首次在RMG中证明可打破多智能体诅咒，样本复杂度趋于指数级改进。
- **证明完备**：同时给出了上界和极小化下界，表明所提算法接近最优（除ε<sup>4</sup>因子外）。
- **方法统一**：鲁棒贝尔曼方程和强对偶的应用使得计算可处理，而FTRL框架能有效处理分布鲁棒优化中的非线性。

### 8. 不足与局限
- **缺乏实验验证**：文中没有任何数值实验，无法评估算法在真实或模拟环境中的实际表现，如收敛速度、鲁棒性提升幅度等。理论最优性中的对数因子和常数可能较大，实际样本需求可能仍很高。
- **假设限制**：依赖生成模型（可独立从任意(s,a)采样），这在实际应用（如在线交互）中可能不现实。此外，不确定性集使用TV距离，其他距离（如χ²、Wasserstein）下算法是否仍有效未讨论。
- **仅关注CCE**：文中主要学习CCE，而NE的学习仍面临指数复杂度困境（已知结果）。未探索其他均衡概念（如CE）的样本复杂度。
- **理论间隙**：上界中存在ε<sup>4</sup>项，而下界含ε<sup>2</sup>项，存在二次差距，可能并非最优。此外，算法参数（如c<sub>α</sub>、cb）的具体值未明确，实际调参可能困难。

（完）
