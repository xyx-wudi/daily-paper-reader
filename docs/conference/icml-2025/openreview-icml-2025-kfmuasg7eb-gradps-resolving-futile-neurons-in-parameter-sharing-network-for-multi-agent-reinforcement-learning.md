---
title: "GradPS: Resolving Futile Neurons in Parameter Sharing Network for Multi-Agent Reinforcement Learning"
title_zh: GradPS：解决多智能体强化学习参数共享网络中的无效神经元
authors: "Haoyuan Qin, Zhengzhu Liu, Chenxing Lin, Chennan Ma, Songzhu Mei, Siqi Shen, Cheng Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=KFMuaSG7eB"
tags: ["query:marl"]
score: 9.0
evidence: 解决MARL参数共享网络中的无效神经元
tldr: 参数共享在多智能体强化学习中广泛使用，但导致策略同质化限制性能。本文发现梯度冲突产生无效神经元，阻碍学习。提出GradPS方法，为每个无效神经元动态创建多个克隆，分配低梯度冲突的智能体组，提升学习效率与多样性。实验验证其有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 775, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 838, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 831, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 834, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 839, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1749, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1721, \"height\": 1331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1706, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1716, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1723, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1726, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1694, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1686, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1734, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1297, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1717, \"height\": 885, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1721, \"height\": 1781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1353, \"height\": 1036, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1353, \"height\": 1038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1303, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1710, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kfmuasg7eb/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1710, \"height\": 457, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1552, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1672, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1674, \"height\": 663, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 382, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 382, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 405, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 383, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1735, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1278, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1474, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kfmuasg7eb/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1430, \"height\": 320, \"label\": \"Table\"}]"
motivation: 参数共享导致策略同质化，梯度冲突造成无效神经元。
method: 动态为每个无效神经元创建多个克隆，将低梯度冲突的智能体分配到各克隆。
result: 在多个MARL任务上提升了学习效率与策略多样性。
conclusion: 处理梯度冲突可有效解决参数共享中的神经元失效问题。
---

## Abstract
Parameter-sharing (PS) techniques have been widely adopted in cooperative Multi-Agent Reinforcement Learning (MARL). In PS, all the agents share a policy network with identical parameters, which enjoys good sample efficiency. However, PS could lead to homogeneous policies that limit MARL performance. We tackle this problem from the angle of gradient conflict among agents. We find that the existence of futile neurons whose update is canceled out by gradient conflicts among agents leads to poor learning efficiency and diversity. To address this deficiency, we propose GradPS, a gradient-based PS method. It dynamically creates multiple clones for each futile neuron. For each clone, a group of agents with low gradient-conflict shares the neuron's parameters.
Our method can enjoy good sample efficiency by sharing the gradients among agents of the same clone neuron. Moreover, it can encourage diverse behaviors through independently updating an exclusive clone neuron. Through extensive experiments, we show that GradPS can learn diverse policies with promising performance. The source code for GradPS is available in \url{https://github.com/xmu-rl-3dv/GradPS}.

---

## 论文详细总结（自动生成）

# GradPS：解决多智能体强化学习参数共享网络中的无效神经元 — 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **参数共享（PS）** 在多智能体强化学习（MARL）中广泛使用，能够提升样本效率，但会导致智能体策略趋同，限制表达能力。
- 现有PS方法（全共享、组共享、部分共享、掩码共享）仍无法有效解决策略同质化问题，主要原因在于 **梯度冲突（gradient conflict）**。
- 本文首次从 **神经元粒度** 分析梯度冲突，发现存在 **无效神经元（futile neuron）**——不同智能体对该神经元的梯度方向相反而相互抵消，导致更新几乎为零，损害学习效率和网络表达能力。
- 动机：通过解决无效神经元，在保持PS样本效率的同时，提高策略多样性。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 基于梯度冲突动态划分智能体组，为每个无效神经元创建多个克隆副本，每个副本由一组低冲突的智能体共享，从而避免梯度抵消，实现独立更新。

### 关键技术细节
- **定义**：
  - **神经元梯度**：一个目标网络更新周期内，智能体i对神经元n的累积梯度 \(\phi_i^T\)。
  - **神经元梯度冲突（NGC）**：两智能体梯度符号不同导致的抵消量 \(C_{ij}^T = \sum_T (|\phi_i^T| + |\phi_j^T| - |\phi_i^T + \phi_j^T|)\)。
  - **神经元梯度效率（NGE）**：\(e_n = \frac{1}{T}\sum_t (|\sum_i \phi_i^t| / \sum_i |\phi_i^t|)\)。
  - **无效神经元**：若 \(e_n < \alpha\)（如 \(\alpha=0.2\)），则该神经元为无效神经元。
- **分组（Conflict-based Grouping）**：
  - 基于最近T个更新周期的梯度冲突矩阵，使用高斯核函数转化为相似度矩阵，再执行谱聚类，将智能体分为K组，组内冲突最小。
- **神经元克隆（Group-based Neuron Clone）**：
  - 对每个无效神经元，将其输入权重和偏置复制K份。每个克隆仅由对应组的智能体共享。
  - 前向传播时，各克隆的输出相加后经过激活函数，输入下一层。
  - 更新时各克隆独立进行，避免梯度冲突。
- **恢复机制（Group Parameter Sharing Restoring）**：
  - 当克隆神经元间的参数方差变小时，以概率 \(\rho \times\) 当前无效神经元比例，选择方差最小的组进行恢复。
  - 用独立SGD优化器，添加正则化损失 \(L_{reg} = \sum_j (|W_j^{in} - \overline{W}^{in}| + |b_j^{in} - \overline{b}^{in}|)\)，逐步将克隆参数拉向平均值，最终合并为共享神经元。

## 3. 实验设计
- **基准环境**：
  - **SMAC（StarCraft Multi-Agent Challenge）**：包括同质和异质场景（如2c_vs_64zg、27m_vs_30m、3s5z_vs_3s6z、5m_vs_6m、MMM2、1c3s8z_vs_1c3s9z等）。
  - **Predator-Prey（捕食者-猎物）**：一个自定义网格世界，包含“隐藏属性”——部分捕食者捕获野兔与捕获鹿获得相同奖励，共3种大小（small/medium/large）。
- **对比方法**：
  - Full PS (FuPS)、Full PS + ID (FuPS+id)、Selective PS (SePS)、Structured Network Pruning (SNP)、Kaleidoscope、No PS (NoPS)。
  - 基础算法为QMIX，也测试了QPLEX、DMIX、RMIX作为agent网络。
- **评价指标**：SMAC用测试胜率（Test Win Rate），Predator-Prey用累计回报（Return）；同时监控无效神经元比例。

## 4. 资源与算力
- **文中说明**：实验在“一个配备多块NVIDIA GeForce RTX 3090 GPU的集群上”进行。
- **未具体说明**：未给出GPU数量、单次训练时长、总GPU时长等精确数字；但附录中提供了各方法的墙钟训练时间对比（单位小时），表明GradPS训练时间仅略高于FuPS，远低于SePS和NoPS。

## 5. 实验数量与充分性
- **实验组数**：SMAC上6个场景 + Predator-Prey 3个场景 = 9个主要实验；此外还有：
  - **消融实验**：超参数（\(T, K, \rho, \alpha\)）敏感性分析（图13）。
  - **跨算法验证**：使用QPLEX、DMIX、RMIX作为基础算法测试（图12）。
  - **网络宽度和深度分析**（附录）：不同神经元数量、不同层数下的冲突差异。
  - **与休眠神经元（DoNe）对比**（附录）：在矩阵游戏中比较无效神经元与休眠神经元的区别。
- **随机种子**：每个实验至少5个随机种子，报告95%置信区间。
- **充分性评价**：实验覆盖了同质/异质、对称/非对称奖励、不同规模等场景，消融全面，对比方法齐全，结果客观可信。但缺少如Google Research Football、Multi-Agent MuJoCo等更多样化的基准，存在一定局限性。

## 6. 论文的主要结论与发现
- 梯度冲突是PS网络中普遍存在的问题，导致大量无效神经元出现（可达40%~70%）。
- 无效神经元会进一步阻碍网络表达能力，导致MSE损失停滞。
- GradPS通过动态克隆 + 低冲突分组，显著减少无效神经元比例，提升胜率/回报。
- 在Predator-Prey中，GradPS能够通过梯度冲突自动识别具有隐藏属性的智能体，学习出多样化策略（如部分智能体专注于捕兔）。
- GradPS适用于多种价值分解方法（QMIX、QPLEX、DMIX、RMIX），具有良好迁移性。
- GradPS在计算时间上接近标准PS，参数增加幅度可控（总参数量最多增加约20%）。

## 7. 优点
- **问题新颖**：首次从神经元粒度定义梯度冲突及无效神经元，并将其与策略同质化关联。
- **方法有效**：简单但高效，仅需累积梯度并执行谱聚类，额外计算开销小。
- **动态性**：分组和恢复机制可随训练进程自适应调整，避免永久性结构改动。
- **可解释性**：梯度冲突矩阵能揭示智能体的固有角色/隐藏属性，有助于分析多智能体行为。
- **兼容性**：可以即插即用于任何基于PS的MARL算法（如VDN、QMIX等）。

## 8. 不足与局限
- **超参数敏感**：阈频α、分组数K、恢复概率ρ、累积周期T等需要手动调整，缺乏自适应选择机制。
- **参数开销**：虽然不大，但在极大规模智能体（如数百个）下克隆数量可能线性增长，需考虑可扩展性。
- **基准覆盖有限**：仅在SMAC和自定义Predator-Prey上测试，缺乏在SMACv2、GRF、MAMuJoCo等现代复杂环境上的验证。
- **理论分析薄弱**：未从优化角度严格证明梯度冲突与无效神经元之间的因果性，也未分析分组后梯度估计的方差变化。
- **工程实现细节**：梯度累积和克隆操作需改造网络结构，可能对某些现有框架不够友好。

（完）
