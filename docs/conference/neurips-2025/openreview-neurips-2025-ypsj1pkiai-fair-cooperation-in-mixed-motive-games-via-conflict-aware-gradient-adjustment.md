---
title: Fair Cooperation in Mixed-Motive Games via Conflict-Aware Gradient Adjustment
title_zh: 混合动机博弈中通过冲突感知梯度调整实现公平合作
authors: "Woojun Kim, Katia P. Sycara"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yPsJ1PKiAi"
tags: ["query:marl"]
score: 8.0
evidence: 通过梯度调整在混合动机博弈中促进合作并保证公平
tldr: 多智能体混合动机博弈中，代理需要平衡个体与集体目标。现有奖励重塑方法未明确考虑个体奖励公平性。本文提出自适应冲突感知梯度调整方法，在促进合作的同时保证个体奖励的公平性，动态平衡策略梯度方向，实验表明该方法在多个博弈场景中优于现有方法，兼顾了合作与公平。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypsj1pkiai/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 697, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypsj1pkiai/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1396, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypsj1pkiai/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 722, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypsj1pkiai/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1412, \"height\": 1069, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypsj1pkiai/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 500, \"height\": 310, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ypsj1pkiai/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 732, \"height\": 436, \"label\": \"Table\"}]"
motivation: 混合动机博弈中现有方法促进合作但忽视了个体奖励的公平性。
method: 提出冲突感知梯度调整方法，动态平衡策略梯度以兼顾合作与公平。
result: 在多个混合动机博弈任务上，该方法在促进合作的同时实现了更公平的个体回报。
conclusion: 本文为多智能体合作中公平性问题提供了一种有效的梯度调整方案。
---

## Abstract
Multi-agent reinforcement learning in mixed-motive settings presents a fundamental challenge: agents must balance individual interests with collective goals, which are neither fully aligned nor strictly opposed. To address this, reward restructuring methods such as gifting and intrinsic motivation have been proposed. However, these approaches primarily focus on promoting cooperation by managing the trade-off between individual and collective returns, without explicitly addressing fairness with respect to agents’ task-specific rewards. In this paper, we propose an adaptive conflict-aware gradient adjustment method that promotes cooperation while ensuring fairness in individual rewards. The proposed method dynamically balances policy gradients derived from individual and collective objectives in situations where the two objectives are in conflict. By explicitly resolving such conflicts, our method improves collective performance while preserving fairness across agents. We provide theoretical results that guarantee monotonic non-decreasing improvement in both the collective and individual objectives and ensure fairness. Empirical results in sequential social dilemma environments demonstrate that our approach outperforms baselines in terms of social welfare, while maintaining fairness.

---

## 论文详细总结（自动生成）

## 论文中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在混合动机（mixed-motive）的多智能体强化学习（MARL）中，智能体需要平衡个体利益与集体目标，但现有方法（如奖励重塑、礼物机制）虽然促进了合作，却**忽视了基于任务定义外在奖励的公平性**。例如，在Cleanup任务中，一些智能体专门清理废物而得不到苹果奖励，即使通过礼物补偿，其任务奖励仍然不公平。
- **研究动机**：现有方法如内在动机、不平等厌恶等侧重集体回报的最大化，未明确处理个体与集体目标冲突时的公平性问题。本文旨在同时提升集体表现并保证公平性，以α-公平性（α-fairness）为评估准则。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：提出**FCGrad（Fair and Conflict-aware Gradient Adjustment）**，一种冲突感知的梯度调整方法。它动态检测个体梯度（g_ind）与集体梯度（g_col）之间的冲突（内积为负），在冲突发生时，将**具有较低期望回报的目标的梯度投影到另一个目标的法平面上**，从而在不干扰另一目标的前提下提升该目标。无冲突时则简单加权。
- **关键技术细节**：
  - 定义个体回报V_ind和集体回报V_col（平均回报）。
  - 计算梯度g_ind和g_col。
  - 若⟨g_ind, g_col⟩ ≥ 0（无冲突），使用加权和：g = (1−β)g_ind + βg_col。
  - 若冲突（内积<0）：
    - 当V_col ≥ V_ind（个体处于不公平不利地位）时，g = g_ind − (⟨g_col, g_ind⟩/∥g_col∥²) g_col（投影个体梯度到集体梯度法平面）。
    - 当V_col < V_ind时，g = g_col − (⟨g_ind, g_col⟩/∥g_ind∥²) g_ind。
- **理论保证**：
  - **定理3.1**：在L-光滑假设下，FCGrad更新保证V_ind和V_col均单调非减。
  - **定理3.2**：在步长满足Robbins–Monro条件且冲突反复出现的假设下，V_ind与V_col的差距收敛到0，从而各智能体个体回报趋于相等，实现公平。
- **实用算法**：在IPPO（独立PPO）基础上实现，每个智能体训练两个价值网络（个体和集体），共享编码器，使用GAE估计优势，然后应用FCGrad合并策略梯度。

### 3. 实验设计：使用了哪些数据集/场景，它的 benchmark 是什么，对比了哪些方法

- **环境与设置**：
  - **Unfair Coins**：修改版，绿色硬币出现概率15/16，红色1/16，制造不对称，迫使绿智能体让渡硬币实现公平。
  - **Cleanup**：4个智能体，苹果收集与废物清理的时序社会困境，固定生成位置（部分智能体靠近废物区）。
  - **Harvest**：4个智能体，可持续收割的时序困境，也引入不对称生成位置。
- **Benchmark**：使用α-公平性指标（α=0为平均回报Mean，α=1为几何平均GeoMean，α→∞为最小回报Min）以及Gini系数和Jain's index。
- **对比方法**：共6种基线：
  - Col（集体回报优化）、Ind（个体回报优化）、IA（不平等厌恶奖励重塑）、Weighted（加权梯度，无冲突处理）、PCGrad（梯度投影冲突解决）、AgA（利他梯度调整）。

### 4. 资源与算力（文中说明情况）

- **硬件**：本地服务器，AMD EPYC 7713 64核CPU，**五张NVIDIA RTX 6000 Ada GPU**。
- **训练时长**：每个运行2-8小时。
- **并行环境**：每个rollout使用64-256个并行环境（具体依任务而定）。
- **说明**：文中明确提供了上述信息（见附录C）。

### 5. 实验数量与充分性

- **实验数量**：
  - 三个主要环境（Unfair Coins, Cleanup, Harvest），每个环境使用**4个随机种子**。
  - 额外进行了**β超参数消融实验**（Harvest环境，见Fig.5）。
  - 补充了**Gini系数和Jain's index**公平性指标（Table 1）。
- **充分性评价**：
  - 覆盖了不同难度和类型的混合动机任务，包括不对称和时序困境。
  - 对比了6种代表性基线（包括无冲突处理、奖励重塑、梯度投影、集体/个体优化等），比较全面。
  - 结果显示FCGrad在多种α-公平性指标上优于或持平于基线，且公平性指标更优。
  - 实验设计客观、公平，种子和标准差已报告（图中包含误差带）。

### 6. 论文的主要结论与发现

- FCGrad在**所有环境**的α-公平性（特别是几何平均和最小回报）上显著优于基线。
- 与集体优化方法相比，FCGrad能在大幅提升公平性的同时保持相当的平均回报。
- 个体回报分布更均衡：例如在Unfair Coins中，绿智能体和红智能体收敛到几乎相同的回报。
- 理论证明保证了单调改进和公平收敛，并得到了实验支持。

### 7. 优点：方法或实验设计上的亮点

- **理论贡献**：第一个在混合动机MARL中同时保证单调改进（个体与集体）和公平收敛的方法。
- **方法简洁高效**：仅需计算梯度投影，计算开销低（相比AgA需要Hessian），易于集成到现有策略梯度算法（如IPPO）。
- **关注外在奖励公平**：强调使用任务定义的外在奖励衡量公平，更符合实际参与感，避免内在奖励的模糊性。
- **实验设计合理**：修改标准环境引入不对称性以突出公平挑战；使用多种α-公平性指标全面评估合作与公平；包含消融和额外公平性指标。

### 8. 不足与局限

- **理论假设脆弱**：定理3.2需要“冲突反复出现”条件，在实际训练中可能不成立（尤其当β较大时非冲突步骤增多），作者在局限中也承认了这一点。
- **超参数敏感**：β（不冲突时的加权系数）对合作需求较高的任务（如Cleanup、Harvest）影响较大，需要手动调整（0.7-0.8）。
- **可扩展性未验证**：仅在4智能体环境中测试，扩展到更多智能体或复杂通信场景的效果未知。
- **实验环境有限**：仅使用三个修改版环境，未在更多标准SSD或真实应用（如交通控制）中验证。
- **偏差风险**：采用IPPO作为基础算法，可能不适用于需要集中训练或参数共享的其他MARL范式。

（完）
