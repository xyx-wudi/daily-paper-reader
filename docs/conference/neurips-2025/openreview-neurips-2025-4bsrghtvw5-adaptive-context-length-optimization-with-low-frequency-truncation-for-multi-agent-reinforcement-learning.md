---
title: Adaptive Context Length Optimization with Low-Frequency Truncation for Multi-Agent Reinforcement Learning
title_zh: 基于低频截断的自适应上下文长度优化在多智能体强化学习中的应用
authors: "Wenchang Duan, Yaoliang Yu, Jiwan He, Yi Shi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=4BsrGHtvW5"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体强化学习，自适应上下文长度
tldr: 针对多智能体强化学习中使用固定大上下文长度导致的探索低效和冗余问题，本文提出自适应上下文长度优化框架。设计中心智能体通过时间梯度分析动态调整上下文长度，并引入低频截断减少噪声。实验证明该方法在多种MARL任务中提升了探索效率和收敛速度。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1320, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1422, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 544, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4bsrghtvw5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 566, \"height\": 880, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 895, \"height\": 728, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 816, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1160, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1283, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1338, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1082, \"height\": 734, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1332, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4bsrghtvw5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1453, \"height\": 588, \"label\": \"Table\"}]"
motivation: 固定大上下文长度限制探索效率且包含冗余信息。
method: 设计中心智能体通过时间梯度分析动态优化上下文长度，结合低频截断。
result: 在多个MARL环境中，该方法提高了探索效率并加速收敛到全局最优。
conclusion: 自适应上下文长度是提升MARL性能的有效手段。
---

## Abstract
Recently, deep multi-agent reinforcement learning (MARL) has demonstrated promising performance for solving challenging tasks, such as long-term dependencies and non-Markovian environments. Its success is partly attributed to conditioning policies on large fixed context length. However, such large fixed context lengths may lead to limited exploration efficiency and redundant information. In this paper, we propose a novel MARL framework to obtain adaptive and effective contextual information. Specifically, we design a central agent that dynamically optimizes context length via temporal gradient analysis, enhancing exploration to facilitate convergence to global optima in MARL. Furthermore, to enhance the adaptive optimization capability of the context length, we present an efficient input representation for the central agent, which effectively filters redundant information. By leveraging a Fourier-based low-frequency truncation method, we extract global temporal trends across decentralized agents, providing an effective and efficient representation of the MARL environment. Extensive experiments demonstrate that the proposed method achieves state-of-the-art (SOTA) performance on long-term dependency tasks, including PettingZoo, MiniGrid, Google Research Football (GRF), and  StarCraft Multi-Agent Challenge v2 (SMACv2).

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在多智能体强化学习（MARL）中，处理长期依赖和非马尔可夫环境时，现有方法通常采用**固定的大上下文长度**，但这会导致探索效率低下和冗余信息累积，同时输入表示的高维度和泛化困难也亟待解决。
- **研究动机**：固定上下文长度难以适应动态变化的环境，容易陷入次优解；而现有的序列处理方法（如Transformer）虽能处理长序列，但存在预训练成本高、静态长度无法自适应等问题。因此，需要一种**自适应上下文长度优化机制**，并配合高效的输入表示，以平衡计算效率与决策质量。
- **整体含义**：本文首次系统性地解决MARL中上下文长度增加带来的双重挑战（计算开销与表示泛化），提出自适应上下文长度优化结合低频截断（ACL-LFT）框架，在多个复杂多智能体环境中取得SOTA性能。

## 2. 方法论

### 核心思想
- 引入一个**中央智能体**，通过时间梯度分析动态优化上下文长度，提升探索效率并加速收敛到全局最优。
- 利用**傅里叶变换**将历史观测从时域转换到频域，并采用**低频截断**（基于Littlewood-Paley理论的二进分割）提取全局时间趋势，过滤高频噪声，为中央智能体提供紧凑且有效的输入表示。

### 关键技术细节
1. **傅里叶低频截断模块**：
   - 对历史状态序列 \(s_t^{-1} = \{s_j\}_{j=0}^{t-1}\) 应用离散傅里叶变换（DFT），得到频域系数 \(S[k]\)。
   - 基于Littlewood-Paley理论，设计离散二进分割单位分解，通过低通窗函数 \(X[k]\) 保留低频分量（\(k \le 2^m\) 或 \(k \ge t - 2^m\)），同时用带通窗函数 \(\Phi_j[k]\) 分割高频带，形成近似单位分解（误差随 \(t\) 增大趋于零）。
   - 截断后得到表征全局趋势的低频信息 \(s_t^c\)。

2. **中央智能体自适应上下文长度选择**：
   - 状态：低频截断表示 \(s_t^c\)。
   - 动作空间 \(A_c = \{m_1, m_2, \dots, m_M\}\)，对应不同低频截断水平（即不同上下文长度）。
   - 奖励设计：通过多头注意力机制计算每个分散智能体的权重 \(\omega_t^i\)，将各自奖励加权聚合作为中央智能体的奖励 \(r_t^c = \sum_i \omega_t^i r_t^i\)。
   - 更新策略：使用优势估计（GAE）和梯度优化，公式为：
     \[
     \theta \leftarrow \theta + \zeta \nabla_\theta \log \pi(a_t^c | s_t^c) \delta_t^c, \quad \delta_t^c = r_t^c + \gamma V(s_{t+1}^c) - V(s_t^c)
     \]

3. **时空解耦训练结构**：
   - 中央智能体独立训练，专注于时间信息优化。
   - 分散智能体联合训练，利用最优上下文 \(s_t^{-opt}\) 和当前状态 \(s_t\) 进行策略更新，避免联合优化带来的参数空间过大问题。

### 理论证明
- 定理1：在非平稳环境下，自适应上下文长度相比固定长度的长期累积奖励差异下界为 \(\Omega(T) - O(T^\alpha) = \Omega(T)\)（当T足够大时），证明自适应策略具有长期优势。

## 3. 实验设计

### 实验环境/场景
- **PettingZoo**: `Sample Spread`（4个智能体覆盖3个地标，避免碰撞）
- **MiniGrid Soccer Game**: 15×15网格足球游戏（3队各3个智能体，需射门得分）
- **Google Research Football (GRF)**: `Academy 3 vs 1 with Keeper`（3攻1守+守门员）、`Academy Counterattack-Hard`（4攻快攻）
- **StarCraft Multi-Agent Challenge v2 (SMACv2)**: `3s5z_vs_3s6z`、`5m_vs_6m`、`corridor`

### Benchmark 与对比方法
- **序列处理方法基线**：Transformer、Token Statistics Transformer (ToST)、AMAGO、Mamba
- **固定长度方法**：不同固定上下文长度（8、16、32、64步）
- **基础MARL算法**：MAPPO、QMIX、QPLEX（用于SMACv2验证）
- **消融实验**：去除自适应上下文长度（NO-ACL）、去除低频截断（NO-LFT）、同时去除两者（Raw）

### 实验规模
- 每个实验平均5个随机种子，结果以均值±标准差呈现。
- 总计在4个主要环境（以及SMACv2中3个任务）上进行性能对比、固定长度对比、消融实验、案例分析、无跨智能体历史信息消融等，实验组数超过10组。

## 4. 资源与算力

- 文中说明（附录C.2）：所有实验使用**NVIDIA A100 GPU**，最长单次训练约**一个月**。
- 未详细说明使用的GPU数量及总计算量，仅提及硬件类型和最大耗时。无具体FLOPs或能耗数据。

## 5. 实验数量与充分性

- **充分性评价**：实验覆盖了多种类型环境（合作、竞争、稀疏奖励、密集奖励），对比了多种先进序列处理方法，进行了消融研究、案例分析、跨智能体历史信息消融等，验证了各组件贡献及自适应长度的长期优势。
- **客观性与公平性**：所有方法采用相同的网络架构和训练框架，确保公平对比；结果报告了标准差（5个种子），并进行了统计显著性检验（误差线）。固定长度与自适应长度的对比也考虑了不同步长配置。
- **潜在不足**：未在真实机器人或物理环境中验证；仅在仿真环境中测试。

## 6. 主要结论与发现

- 提出的ACL-LFT框架在所有测试环境中均**显著优于**现有的序列处理方法（Transformer、ToST、AMAGO、Mamba）以及各种固定长度方法。
- 自适应上下文长度在动态环境中表现出长期优势，理论证明和实验均支持这一结论。
- 低频截断有效过滤高频噪声，提取全局趋势，提升了中央智能体的输入质量和整体性能。
- 消融实验表明，自适应上下文长度和低频截断**缺一不可**，二者协同作用带来性能提升。
- 在无跨智能体历史信息共享的情况下，ACL-LFT依然优于其他时序建模方法，证明其性能改进来源于自身机制而非隐式信息共享，且保持部分可观测性。

## 7. 优点

- **系统性**：首次同时解决MARL中上下文长度增加带来的两大挑战（计算效率和表示问题）。
- **创新性**：将傅里叶低频截断与二进分割应用于上下文表示，结合中央智能体自适应选择，设计了基于注意力的加权奖励机制。
- **理论保障**：提供了自适应长度优于固定长度的理论下界证明。
- **实验全面**：覆盖多种类型环境，对比多种最新基线，消融实验设计合理，结果稳定且有统计意义。
- **可重复性**：代码已开源（GitHub链接在摘要中提供），超参数详尽附录。

## 8. 不足与局限

- **计算资源要求高**：单次训练最长需一月，可能限制实际部署和复现，且未提供小规模或轻量级版本。
- **环境范围有限**：实验全部在仿真环境中进行，未在真实多智能体系统（如无人机群、机器人团队）中验证，其泛化性和鲁棒性有待进一步检验。
- **超参数敏感**：中央智能体动作空间（截断级别集合）需针对每个环境手动设计（如表8所示），依赖先验知识，缺乏自动搜索机制。
- **理论假设较强**：定理证明假设观测噪声高斯、局部线性可近似、策略满足Lipschitz连续性等，实际中这些假设可能不严格成立。
- **未探讨隐私/公平性**：未讨论多智能体系统中可能存在的隐私泄露或公平性问题。

（完）
