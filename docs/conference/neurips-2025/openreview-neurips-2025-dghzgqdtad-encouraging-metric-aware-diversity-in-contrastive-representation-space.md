---
title: Encouraging metric-aware diversity in contrastive representation space
title_zh: 在对比表示空间中鼓励度量感知的多样性
authors: "Tianxu Li, Kun Zhu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=DghZGQDTaD"
tags: ["query:marl"]
score: 9.0
evidence: 合作多智能体强化学习，多样性探索
tldr: 在合作多智能体强化学习中，共享参数的智能体容易学习相似行为，导致探索不足。本文提出Wasserstein对比多样性（WCD）方法，通过最大化轨迹分布的Wasserstein距离来促进智能体多样性。在对比表示空间中进行度量感知的多样性探索，实验证明WCD能显著提高探索效率和最终合作策略的质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1074, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1189, \"height\": 769, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1185, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1288, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1337, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 900, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1286, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dghzgqdtad/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1293, \"height\": 293, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 606, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1458, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 949, \"height\": 128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1250, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1351, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 653, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1058, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1459, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 950, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dghzgqdtad/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 418, \"label\": \"Table\"}]"
motivation: 共享参数的多智能体易产生同质化行为，阻碍探索和最优策略学习。
method: 提出WCD方法，最大化智能体轨迹分布间的Wasserstein距离以增强多样性。
result: 在多个合作任务上，WCD比现有多样性方法取得更好的探索和合作性能。
conclusion: 度量感知的多样性探索是提升合作多智能体学习的关键。
---

## Abstract
In cooperative Multi-Agent Reinforcement Learning (MARL), agents that share policy network parameters often learn similar behaviors, which hinders effective exploration and can lead to suboptimal cooperative policies. Recent advances have attempted to promote multi-agent diversity by leveraging the Wasserstein distance to increase policy differences. However, these methods cannot effectively encourage diverse policies due to ineffective Wasserstein distance caused by the policy similarity. To address this limitation, we propose Wasserstein Contrastive Diversity (WCD) exploration, a novel approach that promotes multi-agent diversity by maximizing the Wasserstein distance between the trajectory distributions of different agents in a latent representation space. To make the Wasserstein distance meaningful, we propose a novel next-step prediction method based on Contrastive Predictive Coding (CPC) to learn distinguishable trajectory representations. Additionally, we introduce an optimized kernel-based method to compute the Wasserstein distance more efficiently. Since the Wasserstein distance is inherently defined for two distributions, we extend it to support multiple agents, enabling diverse policy learning. Empirical evaluations across a variety of challenging multi-agent tasks demonstrate that WCD outperforms existing state-of-the-art methods, delivering superior performance and enhanced exploration.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **研究背景**：在合作多智能体强化学习（MARL）中，为了降低参数量和训练成本，常用参数共享（parameter sharing）让所有智能体使用同一策略网络。但这会导致智能体学习相似的同质化行为，阻碍有效探索，最终得到次优的合作策略。
- **现存方法不足**：近期一些方法通过最大化策略间的 Wasserstein 距离来促进多样性，但由于共享参数导致的初始策略高度相似，Wasserstein 距离会趋近于零，无法提供有效的多样性激励。基于互信息（KL 散度）的方法虽然能区分轨迹，但 KL 散度是度量无关的（metric-agnostic），微小差异即可最大化，不足以激励大幅度的探索。
- **本文目标**：提出 Wasserstein Contrastive Diversity (WCD) 方法，在潜表示空间中最大化不同智能体轨迹分布之间的 Wasserstein 距离，从而获得度量感知（metric-aware）的多样性激励，促进更充分的探索。

---

## 2. 方法论

- **核心思想**：通过学习**可区分的轨迹表示**，使初始相似的策略在表示空间中产生可分离的分布，然后在该空间中最大化 Wasserstein 距离作为内在奖励，推动智能体学习多样化策略。
- **关键技术细节**：

  - **轨迹表示学习**：采用对比预测编码（CPC）进行下一步预测。将智能体每一步的观测-动作对（\(x_t^a = (o_t^a, u_t^a)\)）通过非线性编码器 \(g_{\theta_e}\) 映射为嵌入 \(z_t^a\)，再经自回归模型（GRU）聚合历史得到轨迹表示 \(c_t^a\)。通过最小化 InfoNCE 损失，使当前轨迹表示与自身下一步嵌入相近，与其它智能体的下一步嵌入相远，从而学到区分性强的表示。
  - **Wasserstein 距离计算**：使用光滑 Wasserstein 距离的对偶形式，并用核方法优化对偶函数（高斯核 + 随机特征映射），大幅降低计算成本。对偶向量 \(\lambda_\mu, \lambda_\nu\) 通过随机梯度下降更新。
  - **多智能体扩展**：对于多于两个智能体，每个智能体的内在奖励设为与其最近邻智能体轨迹表示分布之间的 Wasserstein 距离：\(r_w = \min_{a'\neq a} W(p_{\pi^a}, p_{\pi^{a'}})\)。
  - **与 QMIX 集成**：额外引入一个内在效用网络 \(Q_w^a\)，输入为原始 Q 值 \(Q^a\) 和轨迹表示 \(c_t^a\)，通过 TD 损失最大化内在奖励。总损失为 \(L_{total} = L_{TD} + \alpha L_{wTD}\)，作为正则项与原 QMIX 损失联合优化。还提供了与 MAPPO 的集成方式（直接对奖励进行 shaping）。
- **算法流程**：伪代码见附录 Algorithm 1。主要步骤包括：收集轨迹、更新编码器（最小化 InfoNCE 损失）、更新对偶函数、计算 Wasserstein 距离内在奖励、联合训练策略。

---

## 3. 实验设计

- **数据集 / 场景**：
  - **Pac-Men**：4 个智能体的觅食游戏，需分散到不同房间收集豆子。
  - **SMAC**（StarCraft Multi-Agent Challenge，版本 SC2.4.10）：6 个场景——3s5z（简单）、2c_vs_64zg（困难）、7sz（困难）、6h_vs_8z（超难）、corridor（超难）、3s5z_vs_3s6z（超难）。
  - **SMACv2**：引入随机性的改进版，3 个场景——terran_5_vs_5、protoss_5_vs_5、zerg_5_vs_5。
  - **额外**：Google Research Football（3 个场景）、同质行为测试（4 个场景）、可扩展性测试（不同智能体数量）。
- **Benchmark 与对比方法**：
  - 包括价值分解方法（QMIX, QTRAN）、基于角色的多样性方法（RODE）、基于互信息的多样性方法（MAVEN, EOI, SCDS, PMIC, LIPO, FoX）、基于 Wasserstein 距离的多样性方法（MAPD, DiCo），以及 MAPPO。
  - 所有方法使用相同的超参数和网络架构，每个实验 5 个随机种子报告均值和标准差。

---

## 4. 资源与算力

- **硬件**：论文在附录 K 中说明所有实验运行在 **单张 NVIDIA GeForce RTX 4090 GPU** 上。
- **训练时长**：附录 J 表 9 显示，在 SMAC 三个超难场景中，QMIX 训练约 7–10 小时，WCD+QMIX 略多（约 7h–10h50m），额外开销不大。未报告总 GPU 小时数，但可推测总体计算量适中。

---

## 5. 实验数量与充分性

- **实验数量**：包含主要性能对比（Pac-Men + SMAC 6 场景 + SMACv2 3 场景 + GRF 3 场景）、同质行为测试（4 场景）、可扩展性测试（4 场景）、与 ε-greedy 对比（4 场景）、消融研究（多个变体，如图 6a）、不同核函数（线性 vs. 高斯）、不同内在奖励权重 α、不同成本函数（欧氏距离 vs. 余弦相似度）。总计约 20 余个不同设置。
- **充分性**：实验覆盖了简单到超难任务、随机性环境、不同类型动作（离散）、不同算法族（value-based 和 policy-based），并进行了充分的消融验证，证明了各组件（CPC 表示、自回归模型、最近邻 Wasserstein 等）的必要性。报告了标准差，结果可靠。
- **公平性**：与基线采用相同超参数和网络结构，随机种子一致，对比客观。

---

## 6. 主要结论与发现

- WCD 在所有测试任务中**显著优于**所有基线方法，尤其在超难场景和随机性强的 SMACv2 中提升明显。
- 通过最大化对比表示空间中的 Wasserstein 距离，WCD 能**持续提供有效的多样性激励**，而基于互信息的方法（如 EOI）因度量无关性导致激励快速收敛。
- 与 MAPD 等直接使用 Wasserstein 距离的方法相比，WCD 通过表示学习解决了初始策略相似导致的 Wasserstein 距离无效问题。
- WCD **不会阻碍必要的同质行为**（如集中火力），因为它本质是探索正则化，在环境奖励较高时会收敛到相同动作。
- 消融研究表明，表示学习（CPC）、自回归模型、最近邻 Wasserstein 内在奖励等组件都对性能有重要贡献。

---

## 7. 优点

- **方法创新性**：将对比表示学习与 Wasserstein 距离结合，解决参数共享导致的多样性不足问题，思路新颖且有效。
- **理论支撑**：在附录 B 中证明了轨迹表示的紧致性和 Wasserstein 距离的有界性，保证了训练的稳定性。
- **计算效率**：用核方法（随机特征映射）近似对偶函数，避免复杂神经网络参数化，降低多智能体场景中的计算开销。
- **广泛的实验验证**：在多种基准、多种难度、多种随机种子下进行了充分的比较和消融，结果可信。
- **简洁易集成**：可作为正则项与现有 MARL 算法（QMIX, MAPPO）结合，仅增加少量计算开销。

---

## 8. 不足与局限

- **成本函数选择**：默认使用欧氏距离作为 Wasserstein 距离的成本函数，论文在 Section 7 中指出选择最优成本函数仍是一个挑战，可能在不同任务中需要调整。
- **动作空间限制**：实验仅限于离散动作场景（SMAC, GRF），未在连续动作空间任务（如 Multi-Agent Particle Environment）上验证，但论文在附录 D 中给出了与 MAPPO 的集成方法，有潜在可扩展性。
- **超参数敏感性**：虽然进行了 α 权重消融，但未系统研究其他超参数（如 β、m 维度等）的影响，可能在不同任务中需手动调整。
- **可扩展性测试有限**：仅测试了最多 20 个智能体，更大规模（如百级）未涉及。
- **未与其他高级表示学习技术对比**：如无对比预测编码（SimCLR, BYOL）等其他对比学习变体。
- **代码与数据**：提供了代码，但未明确开源许可或详细部署指南，可能影响复现便捷性。

（完）
