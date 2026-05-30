---
title: Sequential Multi-Agent Dynamic Algorithm Configuration
title_zh: 序列化多智能体动态算法配置
authors: "Chen Lu, Ke Xue, Lei Yuan, Yao Wang, Yaoyuan Wang, Fu Sheng, Chao Qian"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=27aIOGfkAV"
tags: ["query:marl"]
score: 6.0
evidence: 多智能体强化学习用于动态算法配置
tldr: 针对复杂算法中多个超参数存在内在依赖关系的问题，提出基于多智能体强化学习的动态配置方法。利用MARL建模参数间依赖，实现序列化调整。实验表明优于静态配置和独立配置方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-27aiogfkav/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1314, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-27aiogfkav/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1387, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-27aiogfkav/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1388, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-27aiogfkav/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1298, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-27aiogfkav/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1371, \"height\": 1208, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 927, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1493, \"height\": 973, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 978, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1071, \"height\": 1124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-27aiogfkav/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1431, \"height\": 171, \"label\": \"Table\"}]"
motivation: 现有动态算法配置方法未考虑多参数之间的依赖关系。
method: 将参数配置视为多智能体序列决策问题，使用MARL学习依赖关系。
result: 在多种算法配置任务上，性能优于基线方法。
conclusion: MARL为复杂算法配置提供新思路。
---

## Abstract
The performance of an algorithm often critically depends on its hyperparameter configuration. Dynamic algorithm configuration (DAC) is a recent trend in automated machine learning, which can dynamically adjust the algorithm’s configuration during the execution process and relieve users from tedious trial-and-error tuning tasks. Recently, multi-agent reinforcement learning (MARL) approaches have improved the configuration of multiple heterogeneous hyperparameters, making various parameter configurations for complex algorithms possible. However, many complex algorithms have inherent inter-dependencies among multiple parameters (e.g., determining the operator type first and then the operator's parameter), which are, however, not considered in previous approaches, thus leading to sub-optimal results. In this paper, we propose the sequential multi-agent DAC (Seq-MADAC) framework to address this issue by considering the inherent inter-dependencies of multiple parameters. Specifically, we propose a sequential advantage decomposition network, which can leverage action-order information through sequential advantage decomposition. Experiments from synthetic functions to the configuration of multi-objective optimization algorithms demonstrate Seq-MADAC's superior performance over state-of-the-art MARL methods and show strong generalization across problem classes. Seq-MADAC establishes a new paradigm for the widespread dependency-aware automated algorithm configuration. Our code is available at https://github.com/lamda-bbo/seq-madac.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：动态算法配置 (Dynamic Algorithm Configuration, DAC) 旨在根据运行状态自动调整超参数，但现有方法大多独立地处理多个超参数，忽略了它们之间存在的**固有依赖关系**（例如，先确定算子类型，再配置该算子的参数）。这种忽略导致配置策略次优，且易陷入组合爆炸。
- **整体含义**：论文提出**序列化多智能体动态算法配置 (Seq-MADAC)** 框架，利用多智能体强化学习的序列决策能力显式建模参数间的依赖关系，从而更高效、更鲁棒地配置复杂算法的多个异构超参数，并提升泛化能力。

## 2. 论文提出的方法论

- **核心思想**：将 DAC 问题建模为**上下文序列化多智能体马尔可夫决策过程 (Contextual Sequential MMDP)**，其中智能体按预设顺序依次选择动作（配置参数），当前智能体可以看到之前智能体已选的动作，从而利用参数依赖。
- **关键技术**：
  - **序列化优势分解网络 (Sequential Advantage Decomposition Network, SADN)**：将全局优势函数分解为各智能体顺序的优势函数之和（基于多智能体优势分解引理）。
  - **更新方式**：每个智能体维护一个优势网络，独立训练，通过梯度反向传播隐式学习；全局优势函数使用一步TD误差（GAE λ=0）更新。
  - **理论保证**：满足**个体全局最大值 (Individual Global Max, IGM) 原理**，确保序列化的贪婪选择等价于全局最优联合动作，避免组合爆炸。
- **算法流程**：在每个时间步，智能体 1 根据当前状态选择动作→智能体 2 根据状态+动作1选择动作→……→联合动作执行→环境返回全局奖励→更新各优势网络。

## 3. 实验设计

- **合成测试环境**：
  - **Sigmoid**（原始，无依赖）、**Seq-Sigmoid**（引入前后参数依赖）、**Seq-Sigmoid-Mask**（屏蔽部分状态，增加随机性）、**Seq-Sigmoid-Robust(n)**（引入随机智能体模拟学习失败）。
  - 维度：5/10 个超参数。
- **真实复杂算法**：
  - **MOEA/D**（多目标进化算法），配置权重、邻域大小、算子类型、算子参数四个异构超参数。
  - Benchmark：DTLZ2、DTLZ4、WFG4–WFG9 等 8 个问题，每个问题设置 6、9、12 维。
- **对比方法**：
  - 序列化方法：ACE、SAQL、MAPPOar（将先前动作加入状态）。
  - 通用MARL：VDN、QMIX（价值分解）、MAPPO、HAPPO、HASAC（策略梯度）。
  - 静态基线：原始 MOEA/D 默认配置。
- **评价指标**：合成任务用奖励值，MOEA/D 用反转世代距离 (IGD，越小越好)。

## 4. 资源与算力

- 论文在附录 D 中声明“所有实验对计算资源要求不高”，但**未明确说明 GPU 型号、数量、具体训练时长**（仅给出了相对训练时间比较，如 SADN 在 10D Seq-Sigmoid 上约 4h28'，在 MOEA/D 上约 14h56'，均在一台机器上运行）。
- 可以认为实验在常规 CPU/GPU 机器上即可复现，无特殊算力需求。

## 5. 实验数量与充分性

- **数量**：涵盖 4 类合成任务（含不同维度和噪声设置）、8 个 MOEA/D 问题（3 个维度，共 24 个实例）、正确/逆序对比、跨维度泛化测试（额外 1 组），以及鲁棒性测试等。每组实验平均 6–10 次独立运行。
- **充分性**：实验设计较为全面，既验证了基本性能，也测试了鲁棒性、顺序重要性、泛化能力。使用统计检验（Wilcoxon 秩和检验）确保显著性。对比方法覆盖主流 MARL 及序列化方法，基线合理。
- **客观公平**：论文声明使用了相同超参数设置（如隐藏层大小、学习率等）进行公平比较，且代码已开源。但部分基线（如 MAPPOar）是简单扩展，可能未充分调优。

## 6. 论文的主要结论与发现

1. **顺序信息显著提升性能**：在含依赖的合成任务上，利用正确顺序的 SADN 优于所有非序列化方法，且比 ACE、SAQL 等序列化方法收敛更快、最终性能更好。
2. **鲁棒性强**：在 Seq-Sigmoid-Robust 中引入随机智能体时，SADN 仍然保持稳定，而 ACE 和 SAQL 性能明显下降。
3. **在真实 MOEA/D 上超越 SOTA**：SADN 在大多数训练和测试问题上 IGD 最小，平均排名第一；仅在少数测试问题上偶尔低于基线，可能由于泛化不足。
4. **跨问题泛化能力**：SADN 在未见过的测试问题上仍能获得较好结果，且在不同维度间迁移时表现稳定。
5. **顺序的重要性验证**：使用逆序训练时性能普遍下降，说明正确捕捉参数依赖至关重要。

## 7. 优点

- **方法论创新**：首次将参数依赖显式建模为序列化多智能体决策问题，并提出对应优势分解网络，理论上有 IGM 保证。
- **实用性强**：适用于实际复杂算法（如 MOEA/D）的多参数配置，可缓解手动调参负担。
- **实验完整性好**：在合成和真实场景下进行了多维度、多噪声、多基线的比较，消融实验（正确顺序 vs 逆序）直接验证了核心假设。
- **代码开源**，可复现。

## 8. 不足与局限

- **超参数顺序预设**：模型需要预先给定参数配置顺序（通常根据代码执行顺序设定），若顺序不准确可能导致性能下降。论文未提供自动学习顺序的方法。
- **跨维度泛化仍存挑战**：虽然实验显示一定泛化能力，但跨维度迁移性能仍有差距，论文承认这是未来方向。
- **计算效率分析不完整**：仅对比了训练时间，未分析推理阶段的计算开销及扩展到大场景时的瓶颈。
- **随机性大的场景表现不稳定**：在 WFG8 等高难度问题上，所有方法均表现不佳，说明 DAC 本身仍受限于目标算法的强随机性。
- **缺少对更广泛算法（如深度学习调参、组合优化）的验证**：实验仅覆盖进化算法，其他领域的适用性待验证。

（完）
