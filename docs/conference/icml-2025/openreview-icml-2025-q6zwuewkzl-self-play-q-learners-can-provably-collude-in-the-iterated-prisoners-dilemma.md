---
title: "Self-Play $Q$-Learners Can Provably Collude in the Iterated Prisoner's Dilemma"
title_zh: 自对弈Q学习者在囚徒困境中可证明共谋
authors: "Quentin Bertrand, Juan Agustin Duque, Emilio Calvano, Gauthier Gidel"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=q6zwUeWkZL"
tags: ["query:marl"]
score: 9.0
evidence: 分析多智能体Q学习中的合作行为
tldr: 针对简单机器学习智能体在社会困境中涌现合作行为这一现象，为自对弈多智能体Q学习者在迭代囚徒困境中的合作行为提供了理论基础。刻画了智能体可证明学习到合作性帕夫洛夫策略而非总是背叛策略的广泛条件，并通过实验验证了理论结果在深度学习算法中的鲁棒性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-q6zwuewkzl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 488, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-q6zwuewkzl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-q6zwuewkzl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1774, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-q6zwuewkzl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1781, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-q6zwuewkzl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 839, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-q6zwuewkzl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 950, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-q6zwuewkzl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 1261, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-q6zwuewkzl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-q6zwuewkzl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 877, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-q6zwuewkzl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 716, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-q6zwuewkzl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 564, \"height\": 839, \"label\": \"Table\"}]"
motivation: 理解简单机器学习智能体为何在囚徒困境中涌现合作行为。
method: 理论分析自对弈多智能体Q学习者的收敛特性，刻画合作条件。
result: 证明了在广泛条件下智能体学习到合作性的帕夫洛夫策略。
conclusion: 为多智能体强化学习中的合作行为提供了理论支撑。
---

## Abstract
A growing body of computational studies shows that simple machine learning agents converge to cooperative behaviors in social dilemmas, such as collusive price-setting in oligopoly markets, raising questions about what drives this outcome. In this work, we provide theoretical foundations for this phenomenon in the context of self-play multi-agent Q-learners in the iterated prisoner’s dilemma. We characterize broad conditions under which such agents provably learn the cooperative Pavlov (win-stay, lose-shift) policy rather than the Pareto-dominated “always defect” policy. We validate our theoretical results through additional experiments, demonstrating their robustness across a broader class of deep learning algorithms.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：在算法定价广泛应用的背景下，多家竞争企业利用机器学习算法自动定价可能引发隐性合谋（tacit collusion），导致价格升高、损害消费者利益。先前模拟研究已表明，简单的Q-learning等算法能够在重复博弈中学习到维持高价的“合谋性”行为，但缺乏严格的理论解释。
- **核心问题**：本文旨在为自对弈（self-play）多智能体Q学习者在迭代囚徒困境（Iterated Prisoner’s Dilemma）中为何能够从“总是背叛”策略转变为合作性策略（尤其是帕夫洛夫/Pavlov策略）提供理论基础。
- **整体含义**：揭示了简单学习算法通过自对弈和乐观初始化可以证明收敛到合作均衡，为理解算法合谋现象提供理论支撑，对反垄断监管具有重要启示。

## 2. 方法论
### 核心思想
- 采用标准随机化（非平均化）的ϵ-贪婪Q-learning（带一步记忆），在自对弈场景下分析其动态。
- 展示算法在乐观初始化下逐步从“总是背叛”（Always Defect）过渡到“输-换”（Lose-Shift），最终收敛至合作性帕夫洛夫（Pavlov）策略（即Win-Stay, Lose-Shift）。

### 关键技术细节
- **算法流程**：Algorithm 1（多智能体自对弈Q学习）和Algorithm 2（ϵ-贪婪策略）。每次迭代，两个Agent根据同一Q表ϵ-贪婪选择动作，更新对应状态-动作对的Q值。
- **固定点分析**：在带记忆的多智能体Bellman方程中，存在多个固定点策略：总是背叛、帕夫洛夫、冷酷触发（Grim Trigger）。帕夫洛夫策略需要折扣因子γ > (r_DC - r_CC)/(r_CC - r_DD)且ϵ足够小才能存在。
- **收敛证明**：
  - **无探索情形（ϵ=0）**：定理3.2证明乐观初始化（满足假设3.1）下，算法依次经历三个线性收敛阶段，最终稳定在帕夫洛夫策略。
  - **有探索情形（ϵ>0）**：定理3.3证明对于任意δ>0，在足够小的学习率α和ϵ下，以概率1-δ算法在O(1/α)步内收敛到帕夫洛夫或输-换合作策略。核心技巧是控制非贪婪动作出现次数（引理3.4），保证Q值偏离有限。
- **公式示例**：Q-learning更新公式 \( Q(s_t, a_t^1) \leftarrow Q(s_t, a_t^1) + \alpha [ r_{a_t^1,a_t^2} + \gamma \max_{a'} Q((a_t^1,a_t^2), a') - Q(s_t, a_t^1) ] \)。

### 核心假设
- 自对弈假设：两个Agent使用相同的Q表。
- 乐观初始化：初始Q值足够大，使得初始策略为总是背叛，但部分Q值满足不等式。
- 折扣因子γ足够大，探索率ϵ足够小。

## 3. 实验设计
- **场景与基准**：在模拟的迭代囚徒困境中进行实验，使用简化的奖励参数化（表3，参数g=1.8, γ=0.6）。与理论结果一致，未设定外部基准方法对比，主要验证理论预测（不同α、ϵ、初始化的影响）。
- **对比方法**：无明确对比其他强化学习算法，重点在于自对偶Q-learning本身在不同参数下的表现，以及扩展到深度Q-learning的演示。
- **实验内容**：
  - **标准Q-learning**：图1-3展示ϵ=0和ϵ>0时Q值差随迭代的演变；图2展示不同初始化假设对收敛的影响；图4展示不同α和ϵ下100次运行的合作成功率热力图；图6展示不同合作激励g的影响。
  - **深度Q-learning**：图5使用两层ReLU网络在自对弈训练下，计算不同状态下选择合作的经验概率，演示从总是背叛到帕夫洛夫策略的转变。

## 4. 资源与算力
- 论文附录E.2明确说明：深度Q-learning实验共进行5个种子（runs），每个run在单张RTX8000 GPU上训练约3小时。其他标准Q-learning实验未提及具体算力需求，通常可在CPU上快速完成。

## 5. 实验数量与充分性
- **标准Q-learning**：进行了多组参数扫描（α, ϵ, g, 初始化），图4基于100次独立重复给出统计成功率，总体实验数量充足，覆盖理论预测的主要条件。
- **深度Q-learning**：仅5个种子的演示性实验，展示了定性一致性，但未进行严格的大规模统计或消融研究。
- **客观性与公平性**：实验设计较为客观，参数选择基于理论条件，未选择对算法有利的特定参数。但缺乏与基线方法（如无记忆Q-learning、其他多智能体算法）的对比，部分削弱充分性。

## 6. 主要结论与发现
- 证明了在自对弈且乐观初始化条件下，ϵ-贪婪Q-learning（带一步记忆）可以从“总是背叛”策略收敛到合作性的帕夫洛夫策略。
- 收敛需要折扣因子足够大、探索率ϵ和学习率α足够小。无探索时收敛是确定性的；有探索时以高概率收敛。
- 深度Q-learning在类似设定下也表现出从总是背叛到帕夫洛夫策略的转变，证实理论结果在更复杂模型中的鲁棒性。

## 7. 优点
- **理论新颖性**：首次在标准随机（非平均化）多智能体Q-learning中提供严格的合作收敛证明，考虑了带记忆的真实更新过程，而非简化连续动态。
- **覆盖随机探索**：同时处理了ϵ>0的随机情形，通过概率下界和偏差控制实现了高概率收敛分析，技术贡献显著。
- **跨算法验证**：虽然深度Q学习实验仅演示性，但展示了理论洞察对更先进算法具有启发性。

## 8. 不足与局限
- **自对弈假设**：这是理论证明的核心假设，但实际多智能体系统中智能体可能使用不同策略，放松该假设的分析非常困难，论文仅提到经验上“大部分时间”仍可合作。
- **初始化依赖**：收敛依赖于“乐观”初始化（假设3.1），在实际应用中（如随机初始化神经网络）可能难以自动满足，论文提出用均匀随机策略预训练来近似，但未证明等价。
- **游戏单一性**：分析局限于迭代囚徒困境，未扩展到更一般的博弈（如伯川德竞争、公共物品博弈），结论的泛化性有限。
- **深度Q学习实验不充分**：仅5个种子、单个参数设置，缺乏对超参数敏感性的系统分析，也未与理论条件（如γ、ϵ）定量关联。
- **缺乏基线对比**：未与其他多智能体强化学习算法（如独立Q学习、对手建模方法）横向比较，难以评估该方法的相对优劣。

（完）
