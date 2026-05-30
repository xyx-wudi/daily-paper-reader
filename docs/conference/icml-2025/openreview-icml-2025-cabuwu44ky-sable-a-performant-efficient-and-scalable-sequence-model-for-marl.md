---
title: "Sable: a Performant, Efficient and Scalable Sequence Model for MARL"
title_zh: "Sable: 面向MARL的高性能高效可扩展序列模型"
authors: "Omayma Mahjoub, Sasha Abramowitz, Ruan John de Kock, Wiem Khlifi, Simon Verster Du Toit, Jemma Daniel, Louay Ben Nessir, Louise Beyers, Juan Claude Formanek, Liam Clark, Arnu Pretorius"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=CAbuWU44ky"
tags: ["query:marl"]
score: 9.0
evidence: 面向MARL的高性能、高效、可扩展序列模型
tldr: MARL在处理大规模复杂问题时需兼顾性能、内存效率和可扩展性。本文提出Sable，将Retentive Network的保留机制应用于多智能体观测序列处理，实现高效长时序推理。在六个环境上的实验表明Sable显著超越现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 742, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1241, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1774, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1746, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1716, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 472, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 516, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 534, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 481, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 549, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 533, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 878, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 876, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1735, \"height\": 2211, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cabuwu44ky/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1733, \"height\": 1302, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1612, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 521, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 238, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 238, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1778, \"height\": 1264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 1260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 1248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1777, \"height\": 1260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1779, \"height\": 1235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 582, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 578, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 709, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 633, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 700, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1061, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 976, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 817, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 867, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cabuwu44ky/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 980, \"height\": 284, \"label\": \"Table\"}]"
motivation: 现有MARL算法在大规模问题中性能、内存与可扩展性不足。
method: 采用Retentive Network的保留机制处理多智能体观测序列，实现长上下文记忆。
result: 在六个多样环境中显著超过现有最先进方法。
conclusion: 序列建模方法可有效提升MARL的规模化和性能。
---

## Abstract
As multi-agent reinforcement learning (MARL) progresses towards solving larger and more complex problems, it becomes increasingly important that algorithms exhibit the key properties of (1) strong performance, (2) memory efficiency, and (3) scalability. In this work, we introduce Sable, a performant, memory-efficient, and scalable sequence modelling approach to MARL. Sable works by adapting the retention mechanism in Retentive Networks (Sun et al., 2023) to achieve computationally efficient processing of multi-agent observations with long context memory for temporal reasoning. Through extensive evaluations across six diverse environments, we demonstrate how **Sable is able to significantly outperform existing state-of-the-art methods in a large number of diverse tasks (34 out of 45 tested)**. Furthermore, Sable maintains performance as we scale the number of agents, handling environments with more than a thousand agents while exhibiting a linear increase in memory usage. Finally, we conduct ablation studies to isolate the source of Sable's performance gains and confirm its efficient computational memory usage. **All experimental data, hyperparameters, and code for a frozen version of Sable used in this paper are available on our website:** https://sites.google.com/view/sable-marl. **An improved and maintained version of Sable is available in Mava:** https://github.com/instadeepai/Mava.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当多智能体强化学习（MARL）处理更大规模、更复杂的问题时，算法需要同时满足**高性能**、**内存高效**和**可扩展性**三个关键属性。现有方法通常只能兼顾其中一两个：
  - **独立学习（IL）**：内存高效但不具备高性能和可扩展性（因非平稳性导致性能差）。
  - **集中训练分散执行（CTDE）**：性能较好、内存高效，但集中训练成本高，且大规模部署时协调能力有限。
  - **集中学习（CL）**：性能强（如基于Transformer的MAT），但内存占用高、无法扩展到大量智能体。
- **整体含义**：论文旨在开发一种同时具备三个属性的集中式MARL算法，通过引入改进的保留机制（Retention）替代注意力机制，实现高效的长序列建模，从而在性能、内存和可扩展性上取得突破。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将MARL建模为序列模型问题，采用**RetNet（Retentive Network）** 中的保留机制，替代MAT中的自注意力，以线性复杂度的循环/分块计算处理多智能体观测序列，保留长程时间依赖。
- **关键技术细节**：
  - **架构**：提出**编码器-解码器RetNet**，编码器处理所有智能体当前时刻观测（并行），解码器自回归地生成动作（循环）。
  - **保留机制适配RL**：
    - 引入**交叉保留（cross-retention）**：解码器使用来自编码器的key/value进行交叉注意力。
    - **可重置隐状态**：在episode结束时将隐状态重置为零，防止信息跨episode流动。
    - **衰减矩阵改进**：对同一时间步内所有智能体使用相同的衰减系数；利用分块掩码实现编码器内完全自保留（跨智能体）；在episode终止处将衰减矩阵清零。
  - **训练与执行**：
    - 训练：使用分块表示（chunkwise）并行处理完整轨迹，并结合PPO目标函数优化。
    - 执行：编码器使用分块表示，解码器使用循环表示；隐状态在episode结束时重置。
  - **可扩展性策略**：
    - 大量智能体：使用单时间步序列，分块应用于智能体维度。
    - 长轨迹：沿时间轴对智能体-时间步扁平序列进行分块，确保同一时间步的所有智能体在同一块内。

### 3. 实验设计：数据集/场景、基准、对比方法

- **环境与场景**：6个多样化环境，共45个任务。
  - **RWARE**（机器人仓库，稀疏奖励）
  - **LBF**（基于等级觅食）
  - **MABrax**（连续控制机器人）
  - **SMAX**（星际争霸多智能体挑战，JAX版）
  - **Connector**（网格路径连接）
  - **MPE**（多智能体粒子环境）
  - 另外在**LBF**和**Neom**（新提出的可扩展环境）上进行智能体数量扩展测试。
- **基准与对比方法**：
  - 主要对比：**MAT**（当前SOTA序列模型）、**MAPPO**、**IPPO**、**QMIX**、**MASAC**、**HASAC**。
  - 对比方法均使用JAX实现，基于Mava库。
- **实验协议**：
  - 每个任务进行**10个独立试验**，每个试验训练2000万环境步，122个均匀间隔的评估点。
  - 评估指标：平均episode回报、概率改进分数（Agarwal et al., 2021）。
  - 超参数使用**TPE贝叶斯优化**（Optuna）每个任务调优40次。

### 4. 资源与算力

- **硬件**：实验使用多种GPU：NVIDIA Quadro RTX 4000 (8GB)、Tesla V100 (32GB)、A100 (80GB)，以及TPU v4-8和v3-8设备。
- **训练时长**：文中未明确给出每个任务的具体训练时长，但提到使用128或64个向量化环境并行收集数据。
- **代码开源**：提供冻结版Sable代码、超参数和复现脚本；改进版已在Mava库中维护。

### 5. 实验数量与充分性

- **实验数量**：
  - 主实验：6个环境共**45个任务**（每个任务10次独立运行），提供近**450条学习曲线**。
  - 消融实验：在RWARE和SMAX上进行了**两组消融**：实现细节（RMSNorm、SwiGLU、记忆）和分块大小。
  - 可扩展性实验：在LBF（32/64/128智能体）和Neom（32/512/1024智能体）上比较内存与性能。
- **充分性评估**：
  - 使用标准评估协议（Gorsane et al., 2022），报告均值、置信区间、概率改进分数、性能剖面等。
  - 对比方法均经过单独超参数调优，使用相同调优预算（每个任务40次Trial），确保公平。
  - 消融实验表明Sable的性能增益主要来自**时序记忆**而非仅架构改进。
  - **客观与公平**：实验设计规范，涵盖多种奖励类型（稀疏/密集）、动作空间（离散/连续）、智能体数量（2-1024）。但存在以下局限性：连续控制场景中SAC-based方法更强，Sable在此类任务上未达最优；调优计算成本高但已公开。

### 6. 论文的主要结论与发现

- **性能**：Sable在45个任务中**34个任务上显著超过当前SOTA**（包括MAT），尤其在离散动作、稀疏奖励场景下优势明显。
- **内存效率**：Sable内存消耗与IPPO相当（线性增长），而MAT在1024智能体时超出80GB显存限制。
- **可扩展性**：Sable可稳定处理高达**1024个智能体**，保持约40-50%智能体到达目标位置，而MAT在1024智能体时无法运行。
- **消融结论**：Sable的性能提升主要来源于**时序记忆能力**（而非仅架构差异如RMSNorm/SwiGLU），且分块训练在不牺牲性能前提下显著降低内存。

### 7. 优点

- **方法创新**：首次将RetNet保留机制成功应用于在线RL控制策略，提出可重置隐状态和交叉保留，解决了RL中episode边界与智能体间信息流动问题。
- **全面基准测试**：提供近乎双倍于之前基准工作的任务量（45个），覆盖多个JAX环境，结果可复现。
- **实用性强**：代码开源并集成于Mava框架，便于社区使用；提供冻结版和持续维护版。
- **实验严谨**：使用标准评估协议、多次独立试验、概率改进统计、超参数调优，确保结果统计显著性和公平性。

### 8. 不足与局限

- **连续控制场景较弱**：在MABrax（连续控制）上不如SAC-based方法（HASAC、MASAC），尽管在MPE连续任务上表现最佳。
- **调优开销**：每个任务调优40次Trial，计算资源消耗较大；虽已开源，但复现成本较高。
- **环境限制**：标准环境（如SMAX、MPE）的观测空间随智能体数量增长，不利于纯扩展性测试；新环境Neom较为简单（1D模式匹配），可能无法完全反映真实复杂多智能体系统的挑战。
- **超参数敏感性**：保留机制的衰减系数κ、分块大小等需要手动选择，文中未提供自动调整策略。
- **理论分析匮乏**：尽管基于HAML框架（有收敛保证），但未深入证明Sable在特定条件下的最优性或样本效率上界。

（完）
