---
title: Robust Multi-Agent Reinforcement Learning with Stochastic Adversary
title_zh: 鲁棒多智能体强化学习与随机对手
authors: "Ziyuan Zhou, Guanjun Liu, Mengchu Zhou, Weiran Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bnhFueOeav"
tags: ["query:marl"]
score: 9.0
evidence: 带有随机对手的鲁棒多智能体强化学习
tldr: 多智能体强化学习模型在观测扰动下性能脆弱。现有对抗训练过拟合扰动且忽略主角策略先验。本文提出ATSA，在线训练随机对手，包含随机导演和生成器，引入主角策略先验，提升观测鲁棒性。实验证明其有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 775, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 849, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1736, \"height\": 967, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 691, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1248, \"height\": 1005, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1769, \"height\": 1759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 443, \"label\": \"Table\"}]"
motivation: MARL模型对观测扰动敏感，现有对抗训练方法缺乏策略先验。
method: 提出ATSA框架，在线训练随机对手，利用策略先验生成针对性扰动。
result: 在多个MARL环境上提升了对抗扰动下的鲁棒性。
conclusion: 在线随机对手训练能有效增强MARL模型的鲁棒性。
---

## Abstract
The performance of models trained by Multi-Agent Reinforcement Learning (MARL) is sensitive to perturbations in observations, lowering their trustworthiness in complex environments. Adversarial training is a valuable approach to enhance their performance robustness. However, existing methods often overfit to adversarial perturbations of observations and fail to incorporate prior information about the policy adopted by their protagonist agent, i.e., the primary one being trained. To address this important issue, this paper introduces Adversarial Training with Stochastic Adversary (ATSA), where the proposed adversary is trained online alongside the protagonist agent. The former consists of Stochastic Director (SDor) and SDor-guided generaTor (STor). SDor performs policy perturbations by minimizing the expected team reward of protagonists and maximizing the entropy of its policy, while STor generates adversarial perturbations of observations by following SDor's guidance. We prove that SDor's soft policy converges to a global optimum according to factorized maximum-entropy MARL and leads to the optimal adversary. This paper also introduces an SDor-STor loss function to quantify the difference between a) perturbations in the agent's policy and b) those advised by SDor. We evaluate our ATSA on StarCraft II tasks and autonomous driving scenarios, demonstrating that a) it is robust against diverse perturbations of observations while maintaining outstanding performance in perturbation-free environments, and b) it outperforms the state-of-the-art methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多智能体强化学习（MARL）模型对观测值（observation）的扰动非常敏感，导致其在复杂环境中的可信度下降。现有的对抗训练方法虽然能提升鲁棒性，但存在两个严重缺陷：一是过拟合于特定的对抗扰动，导致在无扰动或随机噪声环境中性能下降；二是未能充分利用主角智能体（protagonist agent）的策略先验信息。
- **整体含义**：论文旨在提出一种新的对抗训练框架——**ATSA（Adversarial Training with Stochastic Adversary）**，通过在线训练一个**随机对手（stochastic adversary）**，既能在观测扰动下保持鲁棒，又能在干净环境中维持优异性能，从而提升MARL模型的通用鲁棒性和实际应用价值。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将对抗训练转化为一个策略扰动问题，通过分解为两个子模块——**随机导演（Stochastic Director, SDor）** 和**SDor引导的生成器（SDor-guided generaTor, STor）**，并引入**最大熵原则**和**因子化最大熵MARL**理论，保证收敛到全局最优。同时设计**SDor-STor损失函数**以对齐策略扰动与观测扰动。
- **关键技术细节**：
  - **SDor**：在策略对抗性Dec-POMDP（PD-POMDP）中学习一个随机策略，目标是最小化主角的预期团队奖励并最大化自身策略熵，从而避免过拟合。其目标函数为：
    \[
    J(h^{jt}) = \mathbb{E}\left[ \sum_t \left( \hat{r}(s_t,\hat{a}_t) + \alpha H(h^{jt}(\cdot|\tau^a_t)) \right) \right]
    \]
  - **STor**：根据SDor给出的策略扰动建议，生成观测扰动，使得主角智能体的实际策略变化与SDor意图一致。其优化目标是最小化主角策略与SDor策略之间的KL散度：
    \[
    D_{KL}\left( \mathbb{E}_{\hat{o}_i \sim h^{\phi_i}_i} [\pi^{\phi_{ip}}_i(\cdot|\hat{o}_i,\tau^{ip}_t)],\; h^{\phi_i}_i(\cdot|o_i,\tau^{ip}_t) \right)
    \]
    实际中通过FGSM近似求解。
  - **SDor-STor损失函数**：使用交叉熵损失衡量主角实际策略与SDor建议策略之间的差异，并将其加入SDor的更新梯度中，增强两者一致性。
  - **理论保证**：证明在因子化最大熵MARL下，SDor的软策略迭代收敛到全局最优；联合STor能导出最优随机观测对手。

## 3. 实验设计

- **数据集/场景**：
  - **StarCraft Multi-Agent Challenge (SMAC)**：三个地图（3m、3s_3z、8m），用于评估离散动作空间下的胜率。
  - **Connected and Autonomous Vehicles (CAV) 环境**：模拟高速公路匝道汇入场景，包含3辆自动驾驶车和1-4辆人类驾驶车，评估累积奖励和碰撞率。
- **Benchmark方法**：分为三类：
  - **无对抗/随机噪声基线**：NoAdv、RN。
  - **现有对抗训练方法**：FGSM、ATLA、PAAD。
  - **鲁棒学习方法**：PR、PR-REP、ERNIE、RAP、ROMANCE-p/s。
- **对比方式**：所有方法均基于VDN和QMIX两种基础MARL算法实现，并在多种对手（FGSM、ATLA、PAAD、ATSA等）下测试，计算平均胜率/奖励和碰撞率。
- **扰动设置**：ℓ∞范数，SMAC中扰动上界分别为0.25（3m, 3s_3z）和0.1（8m），CAV中为0.05。

## 4. 资源与算力

- 论文**未明确说明**所使用的GPU型号、数量或训练时长。仅在实验设置中提及使用了RMSprop优化器，学习率0.0005，目标网络每200 episode更新一次，其余算力细节缺失。

## 5. 实验数量与充分性

- **实验数量**：在两个基准环境（SMAC和CAV）上进行了大量实验。SMAC中涵盖了3个地图，CAV中1个场景。每个环境分别使用VDN和QMIX作为基础算法，总共产生 **12种训练方法 × 6种攻击方法** 的对比矩阵（见Table 1和Table 2）。此外还进行了：
  - **消融实验**：在3m和3s_3z上移除SDor-STor损失函数（κ=0），对比胜率变化（Fig. 2）。
  - **超参数敏感性分析**：在8m上测试α接近0时的效果（Fig. 4）。
  - **不同扰动范围泛化测试**：在3m上对扰动大小从0到0.25进行步长0.05的测试（Fig. 5）。
  - **连续动作空间拓展实验**：在MPE环境中使用MADDPG和FACMAC进行初步测试（Table 5）。
- **充分性与客观性**：
  - **充分**：涵盖了多种攻击类型、多种基础算法、多种评估指标，并进行了统计显著性检验（Wilcoxon秩和检验，p<0.05标记*）。
  - **公平**：所有基线方法均基于相同的VDN/QMIX实现，对手训练过程统一。但注意，部分强基线（如PAAD、ROMANCE）在其原始论文中可能有不同的训练细节，论文声称进行了恰当复现（见附录H.2）。
  - **潜在偏差**：CAV场景仅测试了单一配置，可能不足以全面反映鲁棒性；连续动作空间实验仅作初步展示，未与所有连续域方法对比。

## 6. 论文的主要结论与发现

- ATSA在SMAC和CAV中均取得了最高的平均胜率/奖励和最低的碰撞率，显著优于11种基线方法（42个统计显著优势）。
- 现有方法（NoAdv、RN、FGSM、PAAD等）存在过拟合或平衡不佳问题，而ATSA通过随机对手和SDor-STor损失函数，在干净环境和各种对抗扰动下均保持稳定高性能。
- 消融实验证明SDor-STor损失函数对于维持SDor与STor一致性至关重要，移除后胜率下降。
- 攻击性能分析表明，ATSA训练出的对手能有效暴露其他模型的弱点，但并非总是最强攻击（因其随机性），但能提供更全面的鲁棒性评估视角。

## 7. 优点

- **理论严谨**：给出了SDor软策略迭代收敛到全局最优的证明，并证明了最优随机对手的存在性。
- **创新性强**：提出“随机导演+生成器”架构，首次将最大熵思想引入MARL对抗训练，并通过新损失函数桥接策略扰动与观测扰动。
- **鲁棒性全面**：在多种攻击方式和扰动范围内均表现优异，且不牺牲干净环境性能。
- **实验设计完整**：覆盖离散和连续动作空间（初步）、多种消融、泛化测试，并采用统计检验。

## 8. 不足与局限

- **算力资源未报告**：无法评估方法在大规模场景下的计算开销。
- **连续动作空间表现有限**：在MPE连续控制任务中（特别是FACMAC）并未超越所有基线，论文自身承认需要进一步改进（如复合扰动生成困难）。
- **实验场景有限**：CAV仅包含单一场景，SMAC仅三个中等规模地图，未在大规模或更复杂环境（如SMAC超大规模地图）中验证。
- **对手假设**：方法假设主角策略为确定性离散策略，对随机策略或连续策略的适用性需拓展。
- **超参数敏感**：温度参数α和损失权重κ需根据环境调参，论文未给出通用选择规则。
- **未考虑对手之间的协同**：当前对手独立生成扰动，未考虑多智能体对手间的联合优化。

（完）
