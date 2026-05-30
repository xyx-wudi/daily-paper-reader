---
title: Wolfpack Adversarial Attack for Robust Multi-Agent Reinforcement Learning
title_zh: 面向鲁棒多智能体强化学习的狼群对抗攻击
authors: "Sunwoo Lee, Jaebak Hwang, Yonghyeon Jo, Seungyul Han"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1Iny6XlON0"
tags: ["query:marl"]
score: 9.0
evidence: 聚焦于合作多智能体强化学习中的鲁棒性
tldr: 合作多智能体强化学习易受协调对抗攻击。本文受狼群狩猎策略启发，提出狼群对抗攻击框架，通过干扰初始代理及其辅助代理破坏合作。同时提出WALL防御框架，训练鲁棒策略促进系统协作。实验表明攻击极具破坏性，而WALL显著提升鲁棒性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1608, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 878, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 786, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 786, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 871, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1692, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 785, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 774, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 776, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1247, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1620, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1080, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1600, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1599, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1725, \"height\": 1035, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1724, \"height\": 1038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1335, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1334, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1743, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1743, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1616, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1732, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1iny6xlon0/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1053, \"height\": 631, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 755, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 867, \"height\": 469, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1668, \"height\": 1055, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1403, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1537, \"height\": 672, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 992, \"height\": 762, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1253, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1669, \"height\": 888, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1684, \"height\": 1054, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1685, \"height\": 1066, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1056, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1iny6xlon0/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1236, \"height\": 745, \"label\": \"Table\"}]"
motivation: 现有鲁棒方法难以抵御合作场景中的协调对抗攻击。
method: 提出狼群对抗攻击及基于合作训练的WALL防御框架。
result: 狼群攻击能有效破坏合作，WALL防御显著提升系统鲁棒性。
conclusion: 合作多智能体系统需针对性设计鲁棒机制，WALL提供有效方案。
---

## Abstract
Traditional robust methods in multi-agent reinforcement learning (MARL) often struggle against coordinated adversarial attacks in cooperative scenarios. To address this limitation, we propose the Wolfpack Adversarial Attack framework, inspired by wolf hunting strategies, which targets an initial agent and its assisting agents to disrupt cooperation. Additionally, we introduce the Wolfpack-Adversarial Learning for MARL (WALL) framework, which trains robust MARL policies to defend against the proposed Wolfpack attack by fostering system-wide collaboration. Experimental results underscore the devastating impact of the Wolfpack attack and the significant robustness improvements achieved by WALL. Our code is available at https://github.com/sunwoolee0504/WALL.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 论文的核心问题与整体含义
- **研究动机**：多智能体强化学习（MARL）在合作场景中，现有鲁棒方法（如随机攻击、EGA等）通常只攻击单个智能体，未能有效应对协调性对抗攻击。合作智能体间存在依赖关系，单一攻击可被其他智能体补偿。
- **背景**：集中训练分散执行（CTDE）框架（如VDN、QMIX、QPLEX）在部分可观测环境中有广泛应用，但在训练-部署不匹配时易出现性能下降。现有鲁棒方法（如RARL、ROMANCE、ERNIE）主要针对单智能体攻击，难以抵御同时攻击多个智能体的协调攻击。
- **论文目标**：提出一种新型协调攻击——狼群对抗攻击（Wolfpack Adversarial Attack），并设计对应的防御框架WALL，显著提升合作MARL的鲁棒性。

## 2. 论文提出的方法论
### 核心思想
- 受狼群狩猎策略启发：先攻击一个初始智能体，然后攻击那些响应并协助该初始智能体的“跟随智能体”组，从而破坏智能体间的协作。

### 关键技术细节
- **狼群攻击定义**：在LPA-Dec-POMDP框架下，定义攻击者π^WP_adv，在每个攻击时刻t，选择攻击代理集N_{t,attack}：
  - 初始攻击（t_init）：随机选一个智能体i，使˜a_i = argmin Q_tot(s_t, a_i, a_{-i})。
  - 跟随攻击（t_init+1 至 t_init+t_WP）：攻击选出的跟随组N_{follow-up}。
- **跟随组选择方法**：
  - 基于初始攻击后各智能体Q值变化程度。利用式(1)计算更新后的˜Q_j，然后用Softmax将Q_j和˜Q_j转化为分布，计算KL散度，选择散度最大的m个智能体作为跟随组（排除初始攻击者）。
- **关键攻击步骤选择**：
  - 定义∆Q^WP_t = Σ_{l=t}^{t+t_WP} ∆Q^tot_l，即狼群攻击造成的总Q值下降。
  - 使用Transformer规划器预测未来状态和观测，估计∆Q^WP_t，然后通过式(3)生成初始攻击概率P_{t,attack}（基于温度T的Softmax），选择关键步骤进行初始攻击。
- **WALL防御框架**：
  - 在狼群攻击者构造的LPA-Dec-POMDP ˜M上训练MARL策略，使用标准CTDE算法（QMIX、VDN、QPLEX）更新Q_tot，采用TD损失函数。算法伪代码见Algorithm 1。

### 公式与算法流程
- 攻击目标：˜a_i = argmin Q_tot(st, a_i, a_{-i})。
- 跟随组选择：N_{follow-up} = argmax Σ D_KL(Soft(Q_j) || Soft(˜Q_j))。
- 步骤概率：P_{t,attack} = Soft([∆Q^WP_t/T, ...]_1)。
- 训练：针对每个时间步，根据P选择t_init，执行初始攻击或跟随攻击，否则执行原动作，更新Q_tot和规划器。

## 3. 实验设计
### 使用的环境/场景
- **MPE（多智能体粒子环境）**：三个捕食者-猎物场景：PP 3/1（3捕食者1猎物）、PP 6/2、PP 9/3。
- **SMAC（星际争霸多智能体挑战）**：6个场景：2s3z、3m、3s vs 3z、8m、MMM、1c3s5z。

### Benchmark与对比方法
- **攻击基线**：Natural（无攻击）、Random Attack、EGA（进化生成攻击者）、Wolfpack Adversarial Attack（本文）。
- **鲁棒防御基线**：Vanilla QMIX、RANDOM（用随机攻击训练）、RARL、RAP、ROMANCE、ERNIE、WALL（本文）。
- 所有方法基于QMIX基线，额外在VDN和QPLEX上验证。

### 实验配置
- 训练3M timesteps，从预训练1M的Vanilla QMIX模型开始。
- 超参数搜索：跟随组数量m、狼群攻击次数K_WP、攻击持续时间t_WP、温度T。
- 报告最后100个episode的平均值，5个随机种子。

## 4. 资源与算力
- **硬件**：NVIDIA GeForce RTX 3090 GPU，AMD EPYC 7513 32-Core处理器，Ubuntu 20.04，PyTorch。
- **训练时间**（附录E.4）：
  - 8m环境下：Vanilla QMIX 6.5h；RANDOM 6.5h；RARL 11.17h；RAP 14.58h；ERNIE 16.5h；ROMANCE 16.58h；WALL 21.08h。
  - MMM环境下：Vanilla QMIX 7.5h；RANDOM 7.58h；RARL 15.83h；RAP 17.42h；ERNIE 20.92h；ROMANCE 18.75h；WALL 23.5h。
- 未明确总GPU数量和算力消耗细节，但可推断WALL比ROMANCE多约30%训练时间。

## 5. 实验数量与充分性
- **实验数量**：主要实验包括MPE三个场景和SMAC六个场景，每种场景下对比7种防御方法×4种攻击类型（Natural、Random、EGA、Wolfpack），共约7×4×9=252组主要结果（部分场景未列全）。另有消融实验：
  - 组件评估（默认、Init. agent(min)、Follow-up(L2)、Step(Random)、Agents & Step(Random)）在8m和MMM上。
  - 超参数消融：m、T、K_WP、t_WP。
  - 扩展到VDN和QPLEX算法（附录E.1）。
  - 通用鲁棒性实验（高斯噪声、参数偏移，附录E.5）。
- **充分性与公平性**：
  - 所有方法采用作者原始参数，训练种子相同。
  - 攻击测试时攻击步数统一。
  - 报告均值和标准差，曲线和表格齐全。
  - 提供了可视化分析（图8、图G.1-G.3）以解释结果。
  - 总体上实验设计系统、对比严谨、消融全面。

## 6. 论文的主要结论与发现
- **狼群攻击破坏性显著大于现有攻击**：在QMIX基线下，Wolfpack攻击使Vanilla QMIX在SMAC平均胜率从98.7%下降到39.4%（降幅59.3%），而EGA只降到69.6%（降幅29.1%），随机攻击只降到78.6%（降幅20.1%）。
- **WALL防御效果最佳**：在所有攻击类型下（包括Natural场景），WALL均取得最高平均胜率（SMAC平均93.4%），远超ROMANCE（59.1%）等基线。在MPE中同样最优。
- **可视化表明**：狼群攻击能有效破坏援助行为，而WALL训练出的策略能让非攻击智能体背身保护，抵御攻击。
- **消融验证**：跟随组选择方法优于简单L2距离选择；规划器步骤选择优于随机选择；适当数量的跟随组和攻击步数对鲁棒性关键。

## 7. 优点
- **攻击创新**：首次提出协调多智能体攻击策略，更符合真实对抗场景（如军事战术），且比现有单智能体攻击更具破坏力。
- **跟随组选择机制**：利用Q值变化和KL散度动态识别重要援助智能体，具有理论基础。
- **规划器步骤选择**：通过Transformer预测未来Q值下降，选择关键攻击时间，提升攻击有效性，同时降低计算成本（分离规划器和Q差Transformer）。
- **防御框架通用性**：WALL可集成到多种CTDE算法（QMIX、VDN、QPLEX），实验验证一致有效。
- **全面实验**：覆盖多个环境、多种攻击和防御基线、消融研究，提供开源代码，结果可复现。
- **可视化解释**：详细展示攻击前后智能体行为变化，增强方法可理解性。

## 8. 不足与局限
- **计算开销**：WALL训练时间比ROMANCE多约30%（因Transformer规划器），在实际大规模部署中可能受限。论文认为此开销值得，但未提供推理阶段的时间比较。
- **超参数依赖性**：需要调优m、K_WP、t_WP、T等参数，虽论文给出指导，但在新场景下仍需搜索。
- **攻击假设**：狼群攻击假设攻击者能完全观察全局状态并访问Q_tot，实际中攻击者能力可能受限。防御框架依赖这些假设，可能导致鲁棒性迁移性不明确。
- **实验覆盖有限**：仅评估了MPE和SMAC两类环境，未在连续控制、大规模或真实机器人场景验证。攻击类型仅考虑动作扰动，未探索状态/观测扰动。
- **随机性偏差风险**：初始攻击者随机选择可能引入方差，但论文通过多种子平均缓解。然而未讨论攻击者智能程度的泛化边界。
- **局限性原文承认**：Transformer额外开销，但指出其他基线无法达到同等性能。超参数调优必要但不过度敏感。

（完）
