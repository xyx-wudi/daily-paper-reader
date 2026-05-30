---
title: "MACS: Multi-Agent Reinforcement Learning for Optimization of Crystal Structures"
title_zh: MACS：面向晶体结构优化的多智能体强化学习
authors: "Elena Zamaraeva, Christopher Collins, George R Darling, Matthew Stephen Dyer, Bei Peng, Rahul Savani, Dmytro Antypov, Vladimir Gusev, Judith Clymo, Paul G. Spirakis, Matthew Rosseinsky"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=XwMDUND6iO"
tags: ["query:marl"]
score: 8.0
evidence: 合作多智能体强化学习在晶体结构优化中的应用
tldr: 该论文提出MACS方法，将晶体结构几何优化问题建模为部分可观察马尔可夫博弈，其中每个原子作为智能体协作调整位置。通过在多组分晶体材料上训练，MACS能够成功优化训练组分以及更大尺寸和未见组分的结构，展示了MARL在材料设计中的应用潜力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1378, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 716, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1306, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 720, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1304, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1309, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1414, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1309, \"height\": 1061, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1313, \"height\": 2148, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 719, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1411, \"height\": 2119, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1410, \"height\": 1252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1408, \"height\": 2118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xwmdund6io/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1407, \"height\": 1255, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 1035, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1402, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 974, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 508, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 956, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 990, \"height\": 939, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1234, \"height\": 925, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 921, \"height\": 885, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 667, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 799, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xwmdund6io/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 692, \"height\": 983, \"label\": \"Table\"}]"
motivation: 晶体结构几何优化是计算化学和材料设计中的常见任务，现有方法效率有待提高。
method: 将几何优化视为部分可观察马尔可夫博弈，原子作为智能体，通过多智能体强化学习联合优化位置。
result: 在多种晶体组成上训练的MACS能够成功优化训练组分及未见的大尺寸和不同组分的结构。
conclusion: 多智能体强化学习为周期性晶体结构优化提供了一种新颖有效的学习范式。
---

## Abstract
Geometry optimization of atomic structures is a common and crucial task in computational chemistry and materials design. Following the learning to optimize paradigm, we propose a new multi-agent reinforcement learning method called Multi-Agent Crystal Structure optimization (MACS) to address the problem of periodic crystal structure optimization. MACS treats geometry optimization as a partially observable Markov game in which atoms are agents that adjust their positions to collectively discover a stable configuration. We train MACS across various compositions of reported crystalline materials to obtain a policy that successfully optimizes structures from the training compositions as well as structures of larger sizes and unseen compositions, confirming its excellent scalability and zero-shot transferability. We benchmark our approach against a broad range of state-of-the-art optimization methods and demonstrate that MACS optimizes periodic crystal structures significantly faster, with fewer energy calculations, and the lowest failure rate.

---

## 论文详细总结（自动生成）

# 论文总结：MACS — 面向晶体结构优化的多智能体强化学习

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在计算化学和材料设计中，晶体结构的几何优化是一项关键且频繁的任务。现有优化方法（如 BFGS、FIRE、共轭梯度等）在优化大型结构时要么需要大量步数，要么每一步的计算代价高昂，成为晶体结构预测等应用中效率的瓶颈。
- **核心问题**：如何利用“学习优化”范式，设计一种能够更快、更高效地将周期性晶体结构优化到局部能量最小值的方法。
- **整体含义**：论文提出将几何优化建模为多智能体协调问题，每个原子作为一个智能体，通过多智能体强化学习（MARL）学习分散策略，从而集体发现稳定构型。这项工作首次将 MARL 应用于周期性晶体结构优化，展示了其在材料设计中的潜力。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将晶体结构优化视为一个部分可观察马尔可夫博弈（POMG），其中原子作为智能体，每个智能体仅能观察到局部环境（自身及最近邻的信息），通过独立同时行动来调整位置，最大化个体奖励，最终使所有原子上的力低于阈值（0.05 eV/Å），达到局部能量最小值。
- **关键技术细节**：
  - **观测空间**：每个智能体观测包括自身特征（共价半径、缩放因子、梯度向量、对数梯度范数、上一步位移和梯度变化）以及 k=12 个最近邻的对应特征和相对位置。观测向量长度为 204。
  - **动作空间**：动作是 3 维位移向量，范围 [-1,1]，通过一个依赖于梯度范数的缩放因子 \(c_t^i = \min(\|g_t^i\|, c_{\max})\) 映射到实际位移，以避免过大步长。
  - **奖励函数**：个体奖励为当前步与下一步梯度范数对数之差 \(R_t^i = \log(\|g_t^i\|) - \log(\|g_t^{i+1}\|)\)，鼓励快速降低原子力。折扣因子 γ=0.995。
  - **算法**：采用独立 Soft Actor-Critic（SAC），每个原子独立学习策略，但共享策略网络和 Q 网络。使用两层的 MLP 和 ReLU 激活。训练使用经验回放缓冲区（容量 1000 万）和熵正则化。
  - **能量/力计算**：使用预训练的机器学习原子间势 CHGNet 提供快速准确的能量和梯度估计。

## 3. 实验设计：数据集、场景、基准、对比方法

- **训练数据集**：6 种不同组成（Y₂O₃、Cu₂₈S₁₆、SrTiO₃、Ca₃Ti₂O₇、K₃Fe₅F₁₅、Ca₃Al₂Si₃O₁₂），原子数 5-80，含 2-4 种元素。训练时随机生成 ~40 个原子的结构。
- **测试数据集**：每种训练组成生成 3 个测试集（各 300 个结构），大小分别为 K、1.5K、2K 原子（K≈40）。另选 3 种未见过的组成（从 SrTiO₃ 衍生出 Sr₂TiO₄、Sr₃Ti₂O₇、Sr₄Ti₃O₁₀），同样生成不同尺寸的测试集。
- **场景**：随机初始结构优化，最多 1000 步，成功条件为所有原子力 < 0.05 eV/Å。
- **基准方法**：BFGS、BFGS+线搜索、FIRE、FIRE+BFGS 混合、MDMin、共轭梯度（CG），均来自 ASE 或 SciPy。对比指标：平均步数 (N_mean)、平均时间 (T_mean)、平均能量计算次数 (C_mean)、失败率 (PF)。

## 4. 资源与算力

- **训练硬件**：Linux 集群节点，配备两个 20 核 Intel Xeon Gold 6138 CPU（2.00 GHz），384 GB 内存。未使用 GPU。
- **训练方式**：40 个并发环境同时运行，总训练步数约 80,000 步，训练耗时约 343,800 秒（约 95.5 小时）。
- **测试硬件**：同一节点的单个 CPU 核心，其余核心空闲，确保公平对比。
- **论文未明确说明 GPU 型号或数量**（实际未使用 GPU），也未报告消融实验的额外算力开销。

## 5. 实验数量与充分性

- **实验规模**：共包含 6 种训练组成 × 3 种大小 + 3 种未见组成 × 2 种大小 = 24 个测试集，每个测试集 300 个结构，总计 7200 个优化任务。对比 6 种基线方法，每个方法在所有测试集上运行。
- **消融实验**：针对观测空间（6 种特征设计）、奖励函数（3 种变形）、动作设计（2 种）、最近邻数量（3 个值）、超参数（g_max、c_max、目标熵、学习率等）进行了系统性消融和调优。
- **充分性**：实验覆盖多种化学组成、尺寸变化、未见组成，且评估指标全面（时间、步数、能量计算次数、失败率、能量分布、原子间距分析）。提供了标准误差，并报告了不同随机种子的策略稳定性。实验设计客观、公平，基线均使用标准实现。
- **公平性**：所有方法在同一硬件、相同初始结构下测试，能量计算均使用 CHGNet 以保证一致性。训练时间未计入对比，但讨论了实际使用中可忽略。

## 6. 论文的主要结论与发现

- **效率优势**：MACS 在所有测试集上平均比最强基线（BFGSLS）快 34%，能量计算次数少 28%，失败率最低（0.36%，与 BFGSLS 持平，远低于其他基线）。
- **可扩展性与零样本迁移**：在更大尺寸的结构和未见的组成上，MACS 仍优于所有基线，证明了其良好的泛化能力。
- **能量分布一致**：MACS 和基线得到的局部能量最小值分布相似，未引入虚假低能构型，优化结果是物理合理的。
- **消融结果**：观测中的力相关特征和历史特征对性能至关重要；缩放因子的动作设计显著提升样本效率；奖励函数的影响较小。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次将周期晶体结构优化建模为多智能体协调问题，利用 MARL 的分散决策能力。
- **观测设计**：使用最近邻的化学与几何信息，结合历史位移和梯度变化，使智能体获得充分的局部上下文。
- **动作缩放**：基于梯度范数的自适应步长机制稳定训练并加速收敛。
- **算法选择**：独立 SAC 结合经验回放和熵正则化，适合高维连续动作空间。
- **实验详尽**：大规模、多样化的测试集和基线对比，消融实验系统，结果统计可靠。
- **零样本迁移**：策略可泛化到未见过组成和更大尺寸的结构，实用性强。

## 8. 不足与局限

- **特征表示有限**：当前唯一区分原子种类的特征是共价半径，未来可引入更丰富的原子描述符。
- **历史依赖不足**：仅使用上一步信息，未利用更长时间序列，未来可考虑循环神经网络。
- **单位胞优化缺失**：当前仅优化原子位置，未优化单位胞参数（晶格常数和形状），限制了完全自由度的优化。
- **能量计算依赖 CHGNet**：CHGNet 作为机器学习势可能存在误差，文中仅用其进行训练和测试，未验证在更精确（如 DFT）下的表现，也未测试噪声或不同势的影响。
- **训练开销**：训练耗时约 95.5 小时（仅 CPU），虽然实际使用中可忽略，但相比传统方法仍需额外训练资源。
- **组成复杂性**：在最复杂的组成 Ca₃Al₂Si₃O₁₂ 上，MACS 略逊于 BFGS（但针对性训练后可超越），表明对高多样性组成可能需要更长的训练或采样策略。
- **实验局限性**：未测试极大规模（>200 原子）或极端化学环境的结构，未见对多相/无序材料的验证。

（完）
