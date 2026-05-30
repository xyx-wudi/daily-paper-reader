---
title: Learning Mean Field Control on Sparse Graphs
title_zh: 稀疏图上的平均场控制学习
authors: "Christian Fabian, Kai Cui, Heinz Koeppl"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Y34a82DptF"
tags: ["query:marl"]
score: 9.0
evidence: 稀疏图上的平均场控制用于MARL
tldr: 针对稀疏大规模智能体网络在MARL中的计算与理论挑战，提出基于局部弱收敛的平均场控制模型，覆盖幂律网络等稀疏图。设计可扩展学习算法，在合成示例上验证有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-y34a82dptf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1750, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y34a82dptf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y34a82dptf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y34a82dptf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 226, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-y34a82dptf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y34a82dptf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1759, \"height\": 648, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y34a82dptf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1752, \"height\": 326, \"label\": \"Table\"}]"
motivation: 现有平均场方法仅适用于密集或中等稀疏网络，无法处理实际稀疏图。
method: 基于局部弱收敛提出适用于稀疏图（如幂律网络）的平均场控制模型及可扩展算法。
result: 在多种合成稀疏图示例上验证了模型和算法的有效性。
conclusion: 将平均场MARL扩展至更现实的稀疏图场景，具备理论保证。
---

## Abstract
Large agent networks are abundant in applications and nature and pose difficult challenges in the field of multi-agent reinforcement learning (MARL) due to their computational and theoretical complexity. While graphon mean field games and their extensions provide efficient learning algorithms for dense and moderately sparse agent networks, the case of realistic sparser graphs remains largely unsolved. Thus, we propose a novel mean field control model inspired by local weak convergence to include sparse graphs such as power law networks with coefficients above two. Besides a theoretical analysis, we design scalable learning algorithms which apply to the challenging class of graph sequences with finite first moment. We compare our model and algorithms for various examples on synthetic and real world networks with mean field algorithms based on Lp graphons and graphexes. As it turns out, our approach outperforms existing methods in many examples and on various networks due to the special design aiming at an important, but so far hard to solve class of MARL problems.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：多智能体强化学习（MARL）在大规模智能体系统中面临计算和理论复杂性。平均场博弈（MFG）和平均场控制（MFC）通过将同质智能体群体抽象为概率分布来降低复杂度，但传统方法假设智能体不可区分，忽略了网络结构。  
- **已有进展**：图论平均场博弈（GMFG）及基于 Lp 图论和 graphex 的扩展（LPGMFG、GXMFG）可以处理密集或中等稀疏的网络，但这些方法要求网络的平均度趋于无穷，无法覆盖实际中更稀疏的拓扑结构（如幂律度分布系数 γ>2 的网络，其期望度有限但方差发散）。  
- **核心问题**：如何为这类**稀疏图（如幂律网络）** 上的大规模智能体系统设计可扩展且理论保证的 MARL 方法？  
- **整体含义**：本文首次将平均场控制模型推广到稀疏图场景，为处理互联网、共著网络、生物网络等真实稀疏图上的合作多智能体问题提供了理论框架和实用算法。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

#### 核心思想
- 利用**局部弱收敛（Local Weak Convergence）** 作为图序列收敛的理论工具，建立适用于稀疏图的平均场控制模型——**局部弱平均场控制（LWMFC）**。局部弱收敛可以描述有限期望度、方差可发散的网络（如配置模型、优先连接模型、Chung-Lu 图），而 Lp 图论和 graphex 都无法覆盖这一范围。

#### 关键技术细节
1. **有限系统与极限系统**  
   - 有限系统：给定图 \(G_N\)，智能体按度分类（度 k 的智能体共享策略 \(\pi^k\)），系统状态为每个度 k 的经验平均场 \(\mu_t^{N,k}\)。每个智能体根据自身的度、状态及其邻居的度-状态分布做出动作。  
   - 极限系统：当 \(N \to \infty\) 时，假设图序列局部弱收敛，证明了经验平均场收敛到极限平均场（Theorem 3.1），目标函数也收敛（Proposition 3.3），并给出有限策略集中最优策略在足够大有限系统中仍保持最优的推论（Corollary 3.4）。

2. **复杂性分析与两系统近似**  
   - Lemma 4.1 说明在极限系统中，完全计算 t-hop 邻域分布的计算复杂度在度较大时呈指数增长，不可行。  
   - 提出**两系统近似**：引入阈值 \(k^*\)，将智能体分为低度（\(k \le k^*\)）和高度（\(k > k^*\)）。对高度智能体，假设它们观察到的邻域状态分布为统一近似 \(\hat{G}_t^\infty\)，基于 Heuristic 1（邻节点度分布按度加权）计算；对低度智能体，假设其邻域从 \(\hat{G}_t^\infty\) 中按多项分布采样。由此得到闭合的近似演化方程。  
   - 此外，在附录 B 中给出了更精确的**扩展近似（LWMFC*）**，但计算复杂度过高，仅用于部分对比。

3. **学习算法**  
   - **LWMFC 策略梯度（Algorithm 1）**：将极限 MFC 系统建模为单智能体 MDP，其中“动作”是每个度的策略 \(\pi_t\)，状态是低度和高度平均场的组合。使用 PPO 学习高层策略 \(\hat{\pi}\) 来输出 \(\pi_t\)。  
   - **LWMFMARL 策略梯度（Algorithm 2）**：不依赖模型知识，直接在实际网络上交互，将真实网络的经验平均场作为状态，用同样的策略梯度方法进行学习。该方法避免了两系统近似的误差，且具有单智能体 RL 的理论保证。

### 3. 实验设计：数据集、场景、benchmark 和对比方法

- **问题（场景）**：共四个经典问题  
  1. **SIS**（易感-感染-易感）流行病模型，状态 {S, I}，动作 {保护, 不保护}。  
  2. **SIR**（易感-感染-恢复）扩展模型，增加恢复态 R。  
  3. **图着色（Color）**：5 种颜色分布在圆环上，智能体可左移/右移/停留，目标接近目标分布并避免邻居颜色相邻。  
  4. **谣言传播（Rumor）**：状态 {I（无知）, A（知晓）}，知晓者可选择传播或不传播。

- **数据集（网络）**：  
  - **真实网络**：8 个来自 KONECT 数据库的社交网络/通信网络（CAIDA, Cities, Digg Friends, Enron, Flixster, Slashdot, Yahoo, YouTube），节点规模从 1.4 万到 320 万。  
  - **合成网络**：使用 Chung-Lu 模型生成不同大小（N=167, 406, 860, 1598）的稀疏图。

- **Benchmark 与对比方法**：  
  - 动力学准确性对比：**LPGMFG**（基于 Lp 图论的平均场）、**GXMFG**（基于 graphex 的平均场）、**LWMFC**（本文两系统近似）、**LWMFC***（本文扩展近似，仅在部分问题中计算）。  
  - 学习性能对比：**IPPO**（独立 PPO，一种常见的可扩展 MARL 算法），以及本文的 **LWMFC** 和 **LWMFMARL**。

### 4. 资源与算力

- 文中明确提到：使用了约 **80,000 个 CPU 核时**，每次训练通常在 **96 个并行 CPU 核**上运行约一天。  
- **未提及使用 GPU**（所有实验均在 CPU 上进行）。  
- 硬件环境：Lichtenberg 高性能计算集群（TU Darmstadt）。

### 5. 实验数量与充分性

- **动力学准确性实验**（Table 1）：在 8 个真实网络 × 4 个问题 = 32 组（但 Color 和 Rumor 下 LWMFC* 因计算复杂未做，实际 24 组有完整数据），每组 50 次试验，报告平均总变差 ∆μ 及其标准差。  
- **学习性能实验**（Table 2）：在 4 种不同大小的合成 CL 图上，对 4 个问题训练 24h，比较 LWMFC、LWMFMARL 与 IPPO 的最终目标函数值。  
- **训练曲线可视化**（Fig.2-4）：展示了代表性网络上的 MF 演化及学习曲线。  
- **充分性评价**：  
  - 实验覆盖了多种稀疏图（真实和合成）、多种经典问题（流行病、组合优化、信息传播），与现有最强基线（LPGMFG/GXMFG/IPPO）对比，数据全面。  
  - 对近似精度进行了消融（LWMFC vs LWMFC*），分析了计算复杂性与精度的权衡。  
  - 公平性：学习算法采用相同的 PPO 超参数和训练时长；但 IPPO 使用的是官方 MARLlib 实现，可能存在实现差异。总体而言实验设计客观、充分。

### 6. 论文的主要结论与发现

- **模型表现**：LWMFC 的动力学近似在所有真实网络和问题上的平均总变差（∆μ）显著低于 LPGMFG 和 GXMFG，表明针对稀疏图的建模更准确。扩展近似 LWMFC* 在小部分问题中可进一步提升精度，但计算代价过高。  
- **学习性能**：在较大图（860 和 1598 节点）上，LWMFC 和 LWMFMARL 均优于 IPPO；在较小图上表现与 IPPO 相当或稍弱。LWMFC 由于基于模型可能略差，但 LWMFMARL 直接与环境交互，通常获得更好结果。  
- **理论优势**：证明了有限系统经验 MF 向极限系统收敛（Theorem 3.1），提供了收敛性保证和最优策略的有限近似推论。

### 7. 优点

- **理论贡献**：首次将局部弱收敛应用于平均场控制，严格证明了收敛性，为稀疏图上的 MARL 提供了数学基础。  
- **实践价值**：覆盖了 Lp 图论和 graphex 无法处理的幂律网络（γ>2），使平均场方法能应用于大量现实稀疏网络。  
- **算法可扩展性**：两系统近似将无限维度问题简化为有限维 MDP，学习算法可在单智能体 RL 框架下高效训练。LWMFMARL 无需模型知识，可直接在真实网络上学习。  
- **实验充分**：在多种真实和合成网络上与多个基线对比，结果统计详尽，并分析了近似误差。

### 8. 不足与局限

- **理论假设限制**：要求图序列在概率意义下局部弱收敛，某些现实网络可能不严格满足；Heuristic 1（邻节点度分布按度加权）是一种近似，在非 CL 图上可能偏差。  
- **近似误差**：两系统近似忽略了高度节点邻域的内部结构，且统一简化假设可能导致动力学偏移（Table 1 中 ∆μ 虽小但非零）。  
- **实验覆盖不足**：  
  - 未在更大规模的稀疏图上测试学习算法（最大 1598 节点合成图，真实网络仅用于动力学验证而非学习）。  
  - 学习算法只对比了 IPPO，未与更先进的分布式 MARL 方法（如 QMIX、MAPPO）比较（但 IPPO 的可扩展性适用于大规模场景）。  
  - 所有实验均使用离散状态和动作空间，连续场景未涉及。  
- **计算资源**：仅使用 CPU，训练时间较长（24h），未探索 GPU 加速可能。  
- **可复现性**：代码未公开（文中未提供），仅描述了参数设置（附录 C），但超参数细节有限，可能影响复现。

（完）
