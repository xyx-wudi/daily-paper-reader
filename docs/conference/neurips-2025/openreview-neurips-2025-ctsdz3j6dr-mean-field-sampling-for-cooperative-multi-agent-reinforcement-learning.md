---
title: Mean-Field Sampling for Cooperative Multi-Agent Reinforcement Learning
title_zh: 面向合作多智能体强化学习的平均场采样
authors: "Emile Timothy Anand, Ishani Karmarkar, Guannan Qu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CTsdZ3j6dR"
tags: ["query:marl"]
score: 9.0
evidence: 基于平均场采样和去中心化策略的合作多智能体强化学习
tldr: 该论文针对多智能体强化学习联合状态动作空间随智能体数量指数增长的问题，提出SUBSAMPLE-MFQ算法，通过平均场采样和去中心化随机策略，能在对k个智能体采样的多项式时间内学习策略，并证明策略收敛到最优策略的误差为O(1/√k)。为大规模合作MARL提供了理论保证的高效算法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctsdz3j6dr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1201, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctsdz3j6dr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctsdz3j6dr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 619, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ctsdz3j6dr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1462, \"height\": 464, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctsdz3j6dr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 571, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ctsdz3j6dr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1501, \"height\": 1331, \"label\": \"Table\"}]"
motivation: 联合空间指数增长，计算复杂度过高。
method: 提出SUBSAMPLE-MFQ算法，结合平均场采样和去中心化策略。
result: 证明策略收敛误差O(1/√k)，时间复杂度多项式。
conclusion: 为大规模合作MARL提供了可扩展的高效算法。
---

## Abstract
Designing efficient algorithms for multi-agent reinforcement learning (MARL) is fundamentally challenging because the size of the joint state and action spaces grows exponentially in the number of agents. These difficulties are exacerbated when balancing sequential global decision-making with local agent interactions. In this work, we propose a new algorithm $\texttt{SUBSAMPLE-MFQ}$ ($\textbf{Subsample}$-$\textbf{M}$ean-$\textbf{F}$ield-$\textbf{Q}$-learning) and a decentralized randomized policy for a system with $n$ agents. For any $k\leq n$, our algorithm learns a policy for the system in time polynomial in $k$. We prove that this learned policy converges to the optimal policy on the order of $\tilde{O}(1/\sqrt{k})$ as the number of subsampled agents $k$ increases. In particular, this bound is independent of the number of agents $n$.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：多智能体强化学习（MARL）中，联合状态-动作空间随智能体数量 \(n\) 呈指数增长，导致传统 Q-learning 和均值场 MARL 的计算复杂度分别为指数级（\(\exp(n)\)）和多项式级（\(\mathrm{poly}(n)\)），但仍难以扩展至大规模系统。
- **动机**：在合作性 MARL 场景（如机器人编队、交通协调）中，需要一个可扩展的算法，其运行时间和样本复杂度与全局智能体数量 \(n\) 解耦，仅依赖于采样的小规模子系统规模 \(k\)。
- **整体含义**：本文提出 **SUBSAMPLE-MFQ**（子采样均值场 Q-learning），通过随机采样 \(k \leq n\) 个局部智能体学习策略，证明该策略的累积奖励与最优策略的差距以 \(\tilde{O}(1/\sqrt{k})\) 的速度衰减，且上界与 \(n\) 无关。这为大规模合作 MARL 提供了首个亚多项式（polylogarithmic）运行时间的理论保证。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用智能体的同质性（homogeneous），将原 \(n\) 智能体系统的问题近似为大小为 \(k\) 的子系统的学习问题，并通过去中心化随机策略将子系统的策略扩展到全局。
- **关键技术细节**：
  1. **子系统定义**：全局智能体随机选择大小为 \(k\) 的局部智能体集合 \(\Delta\)，忽略其余 \(n-k\) 个智能体，仅基于该 \(k\) 个智能体构建 MDP。
  2. **值迭代（算法 1）**：
     - 若状态-动作空间较大（\(|Z_l|^k \leq |Z_l| k^{|Z_l|}\)），使用标准 Q-learning 更新 Q 表 \(\hat{Q}_{k,m}\)；否则使用均值场 Q-learning（更新基于经验分布 \(F_{z_\Delta}\)）。
     - 通过 \(m\) 个样本（从转移核 \(P_g, P_l\) 中采样）近似贝尔曼算子，得到固定点 \(\hat{Q}^{\text{est}}_{k,m}\) 和确定性策略 \(\hat{\pi}^{\text{est}}_{k,m}\)。
  3. **在线执行（算法 2）**：
     - 每时间步，全局智能体均匀随机采样 \(\Delta \sim \binom{[n]}{k}\)；每个局部智能体 \(i\) 均匀随机采样 \(\Delta_i \sim \binom{[n]\setminus i}{k-1}\)。
     - 各智能体基于子系统的确定性策略 \(\hat{\pi}^{\text{est}}_{k,m}\) 确定动作，形成随机策略 \(\pi^{\text{est}}_{k,m}\)。
  4. **理论分析**：
     - 证明 Q 函数关于分布间 TV 距离的 Lipschitz 连续性（定理 E.3）。
     - 利用无放回抽样的 DKW 不等式（定理 D.2）界定量：\(\mathrm{TV}(F_{z_\Delta}, F_{z_{[n]}}) \leq \sqrt{\frac{n-k+1}{8nk} \ln\frac{2|Z_l|}{\delta}}\)。
     - 结合性能差异引理（Performance Difference Lemma）导出最优性差距：\(\tilde{O}(1/\sqrt{k})\)，所需样本复杂度为 \(\tilde{O}(|S_g|^2|A_g|^2|A_l|^2|S_l|^2 k^{3.5+2|S_l||A_l|})\)。

### 3. 实验设计：数据集 / 场景、基准、对比方法
- **场景 1：约束探索（Constrained Exploration）**
  - 设置：\(M\times M\) 网格（\(M=6\)），全局智能体约束局部智能体在 \(d\times d\) 区域内移动，模拟仓库事故后有限区域清理任务。
  - 参数：\(n=8\)，\(m=20\)，对比 \(k=1,2,\dots,8\) 下的累积折扣奖励。
- **场景 2：高斯挤压（Gaussian Squeeze, GS）**
  - 设置：每个局部智能体选择动作 \(a_i \in \{0,\dots,9\}\)，全局目标为最大化 \(r(x)=xe^{-(x-\mu)^2/\sigma^2}\)，其中 \(x=\sum a_i\)；模拟交通拥堵控制。
  - 参数：\(n=8\)（小规模）和 \(n=50\)（大规模），\(m=20\)，对比不同 \(k\) 下的奖励和运行时间。
- **基准**：未报告与现有最先进 MARL 算法的全面对比；主要作为自对比，验证 \(k\) 越大奖励越接近最优（\(k=n\) 为均值场/标准值迭代基线）。
- **对比方法**：仅与 \(k=n\)（即完整均值场 Q-learning）比较，未包括其他基线（如 V-learning、CTDE 方法等）。

### 4. 资源与算力
- 论文明确说明所有实验在 **2 核 CPU、12GB RAM** 的服务器上运行。
- 未提及 GPU 或大规模分布式训练，也未报告具体训练时长（除图 2b 中的计算时间标为分钟）。

### 5. 实验数量与充分性
- 实验数量：
  - 约束探索：1 组实验（\(n=8\)，各 \(k\) 值运行 300 步，重复次数未说明）。
  - 高斯挤压：小规模（\(n=8\)）和大规模（\(n=50\)）各 1 组，展示了累计奖励和计算时间。
  - 消融实验：仅变化 \(k\)，未消融其他超参数（如样本数 \(m\)、迭代次数 \(T\)）。
- 充分性评价：实验主要验证理论趋势（单调改进、计算复杂度降低），但缺乏与现有多智能体算法的横向对比，也未进行统计显著性检验（例如误差棒范围未明确说明是标准差还是 min-max，仅在图中展示）。因此从实验全面性看，不足以证明算法在实际复杂任务中的竞争力。

### 6. 论文的主要结论与发现
- 提出 **SUBSAMPLE-MFQ** 算法，能够在多项式时间（关于 \(k\)）内学习接近最优的策略。
- 最优性差距以 \(\tilde{O}(1/\sqrt{k})\) 衰减，且与全局智能体数量 \(n\) 无关。
- 数值实验显示：当 \(k\) 从 \(1\) 增加到 \(n\) 时，累积折扣奖励单调提升，而计算时间呈指数级（?）实际为多项式）增长但远低于全规模计算。
- 当取 \(k = O(\log n)\) 时，实现亚线性（polylog）运行时间，而差距随 \(n\) 增大消失。

### 7. 优点
- **理论贡献**：首次给出子采样策略的高概率收敛界，且与 \(n\) 无关，填补了大规模合作 MARL 理论空白。
- **算法简洁**：结合子采样和均值场，避免了存储和计算指数级 Q 表。
- **可扩展性**：展示了从离线学习到在线执行的完整框架，支持去中心化执行（CTDE）。
- **鲁棒性**：分析了贝尔曼噪声、随机奖励等扩展，证明了方法在多种条件下的稳定性。

### 8. 不足与局限
- **实验覆盖不足**：仅验证两个合成场景，未与 State-of-the-Art 方法（如 G2ANet、QMIX、MAPPO 等）对比，缺乏在常见基准（如 StarCraft II、SMAC）上的评估。
- **强假设**：局部智能体必须同质（状态-动作空间一致），且要求有限状态/动作空间（虽有连续扩展，但增加额外误差）。
- **依赖均匀采样**：在线执行要求每步随机采样 \(k\) 个智能体，通信开销可能较大；论文提出的“共享随机性”版本（附录 K）缺乏理论保证。
- **偏差风险**：奖励结构和转移核为结构化类型（如全局与局部可分解），通用性未经验证。
- **计算复杂度**：虽然关于 \(n\) 为 polylog，但关于 \(k\) 的指数因子（\(|S_l|^k\)）仍然存在，当 \(k\) 较大时对 \(|S_l|\) 敏感。

（完）
