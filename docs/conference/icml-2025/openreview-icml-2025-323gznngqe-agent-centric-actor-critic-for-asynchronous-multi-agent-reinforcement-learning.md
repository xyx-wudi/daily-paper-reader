---
title: Agent-Centric Actor-Critic for Asynchronous Multi-Agent Reinforcement Learning
title_zh: 面向异步多智能体强化学习的智能体中心Actor-Critic
authors: "Whiyoung Jung, Sunghoon Hong, Deunsol Yoon, Kanghoon Lee, Woohyung Lim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=323GZNnGqe"
tags: ["query:marl"]
score: 9.0
evidence: 针对异步多智能体的集中训练与分散执行
tldr: 针对宏动作引入的异步性问题，提出ACAC算法，采用智能体中心编码器独立处理轨迹，并通过注意力机制聚合历史信息构建集中式评论家，无需填充即可管理异步性，提升CTDE框架下的协调性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 771, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 786, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 1198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 737, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1785, \"height\": 1161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 863, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1482, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1751, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1744, \"height\": 1735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1783, \"height\": 1157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1781, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1784, \"height\": 797, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-323gznngqe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1290, \"label\": \"Table\"}]"
motivation: 解决多智能体稀疏奖励环境中宏动作导致的异步性对CTDE的影响。
method: 提出智能体中心编码器和注意力聚合模块的Actor-Critic算法，无需填充处理异步问题。
result: 在稀疏奖励环境中有效提升协调性能。
conclusion: ACAC为异步MARL中的CTDE提供了有效解决方案。
---

## Abstract
Multi-Agent Reinforcement Learning (MARL) struggles with coordination in sparse reward environments. Macro-actions —sequences of actions executed as single decisions— facilitate long-term planning but introduce asynchrony, complicating Centralized Training with Decentralized Execution (CTDE). Existing CTDE methods use padding to handle asynchrony, risking misaligned asynchronous experiences and spurious correlations. We propose the Agent-Centric Actor-Critic (ACAC) algorithm to manage asynchrony without padding. ACAC uses agent-centric encoders for independent trajectory processing, with an attention-based aggregation module integrating these histories into a centralized critic for improved temporal abstractions. The proposed structure is trained via a PPO-based algorithm with a modified Generalized Advantage Estimation for asynchronous environments. Experiments show ACAC accelerates convergence and enhances performance over baselines in complex MARL tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机（背景）

- **现状与挑战**：多智能体强化学习（MARL）在**稀疏奖励**环境中面临协调困难，智能体难以将个体动作与全局回报关联，探索效率低。
- **宏动作的引入**：将一系列微动作组合为单个决策单元（宏动作），有助于长期规划和加速学习，但宏动作执行时长各异，导致智能体**异步**地完成动作、获取新观察，破坏了传统同步MARL的假设。
- **CTDE框架的困境**：集中训练与分散执行（CTDE）在异步场景下无法直接适用，因为联合观察在时间上不完整。现有方法使用**填充**（padding）——用最近一次观察填补缺失数据——但这会引入**虚假相关性**和**不准确的历史抽象**，使价值学习偏离正确轨迹。

## 2. 方法论：核心思想与关键技术

- **核心思想**：抛弃填充方式，改用**智能体中心编码器**独立处理每个智能体的轨迹，再通过**注意力聚合模块**将个体历史整合为集中式评论家的输入，从而实现无需填充的异步CTDE。
- **关键技术细节**：
  - **智能体中心编码器**：输入为宏观察 \(z^i_t\) 及其发生时刻 \(p^i_t\)（通过**正弦时间嵌入**编码），拼接后经MLP和GRU提取每个智能体的历史表征 \(h^i_t\)。仅在智能体收到新宏观察时才更新其隐藏状态。
  - **集中式评论家**：将各智能体最新的隐藏状态集合 \(\tilde{h}_t = \{h^1_t, \dots, h^N_t\}\) 送入**自注意力模块**和**平均池化**，最后通过MLP输出价值 \(V_\psi(\tilde{h}_t)\)。相比填充法，避免了过期或重复数据干扰。
  - **基于PPO的优化**：分散式执行器使用PPO裁剪损失，评论家使用价值函数MSE损失，并采用PopArt进行值归一化。
  - **改进的GAE**：针对异步环境，将λ折扣从微时间步尺度迁移到**宏时间步尺度**——未来TD误差按宏决策步数（而非实际时间步数）折扣。公式为：
    \[
    A^{\lambda,\text{macro}}_{l(k)} = \sum_{m=k}^{\infty} \lambda^{m-k} \gamma^{l(m)-l(k)} \delta_{l(m)}
    \]
    其中 \(l(k)\) 为第k次宏观察出现的微时间步。该设计更符合宏动作决策的语义。
- **算法流程**：多轮收集轨迹 → 计算异步GAE优势 → 集中式评论家更新 → 各智能体PPO策略更新 → 循环迭代。

## 3. 实验设计

- **场景与环境**：
  - **BoxPushing**：双智能体合作将大箱子推到目标区，6×6 / 8×8 / 10×10三种地图，稀疏奖励。
  - **Overcooked**：三智能体合作制作沙拉，7×7网格，三种地图（A、B、C），预定义宏动作。
  - **Overcooked-Rand**：随机化物体和智能体初始位置，增加不确定性。
  - **Overcooked-Large**：11×11网格、6个智能体、4套工具，极大规模异步场景。
- **对比基线**：
  - **宏动作基线**：Mac-NIACC（单一集中式评论家+填充）、Mac-IAICC（各智能体独立评论家+填充）、ACAC-Vanilla（与ACAC同架构但使用普通策略梯度而非PPO）。
  - **微动作基线**：MAPPO micro、ACAC micro（在原始同步微动作环境运行MAPPO和ACAC）。
- **评价指标**：**无折扣回报**（与基线论文不同，后者使用折扣回报），统计五次随机种子下的均值和标准误差。

## 4. 资源与算力

- 论文在附录G中明确说明：
  - **硬件**：AMD EPYC 7453 28-Core Processor + NVIDIA A10 GPU。
  - **训练时长**：Overcooked环境下约24～150小时；BoxPushing环境下约30分钟～2小时。
  - **未说明**：使用的GPU数量、是否多卡并行、训练总能耗等详细信息未提供。

## 5. 实验数量与充分性

- **主要实验组**（均为5个随机种子）：
  - 3种BoxPushing地图 × 5种方法 = 15条学习曲线。
  - 3种Overcooked地图 × 7种方法（含宏/微基线及ACAC变体） = 21条曲线。
  - 3种Overcooked-Rand地图 × 7种方法 = 21条曲线。
  - 6种Overcooked-Large地图 × 3种宏动作方法（ACAC、Mac-NIACC、Mac-IAICC） = 18条曲线。
  - 总计约75条训练曲线，涵盖不同难度和随机性。
- **消融实验**：
  - 填充影响（ACAC vs ACAC-Duplicate）在3个环境集合上展示。
  - GAE折扣方式（宏水平 vs 微水平）在3个环境集合上展示。
  - 时间嵌入与自注意力的消融（附录E.2）在Overcooked和Overcooked-Rand共6个地图上展示。
  - 裁剪比率ϵ的敏感性分析（附录E.2）在6个地图上展示。
- **充分性与公平性**：实验覆盖多种异步MARL基准，与当前主流宏动作方法直接对比，并采用统一超参数设置（尽量一致）。消融实验直接支撑核心设计选择。但缺乏连续动作空间实验、缺乏与其他异步MARL方法（如ASM-PPO）的直接对比，部分结果只报告了平均曲线而无boxplot或统计显著性检验。

## 6. 主要结论与发现

- ACAC在所有基准环境上均显著优于填充法基线，**收敛更快、最终回报更高**，尤其在**大规模异步场景（Overcooked-Large）**中表现突出，而基线几乎无法学习。
- 消除填充（ACAC-Duplicate对比）和宏水平GAE折扣两个设计均被消融实验验证为**关键因素**：填充导致次优解，微水平GAE显著降低性能。
- 基于PPO的损失函数（ACAC vs ACAC-Vanilla）进一步提升了训练稳定性与效率。
- 宏动作本身（对比微动作基线）对于稀疏奖励任务具有显著优势，但也必须配合合适的异步CTDE架构。

## 7. 优点

- **创新架构**：智能体中心编码器+注意力聚合机制，避免填充引入的噪声，同时保持集中式值函数的信息完整性。
- **理论适配**：提出宏水平GAE，从理论上解释了为何标准微时间步折扣不适应异步环境，并提供公式推导。
- **实验扎实**：涵盖从小到大的多尺度异步环境（2～6智能体、6×6～11×11网格），且包含随机化变体测试泛化能力。
- **代码开源**：提供完整实现代码，增强可复现性。
- **清晰图示**：通过流程图和对比图（如填充法与ACAC的信息流）直观展示方法差异。

## 8. 不足与局限

- **实验覆盖局限**：仅涵盖离散动作空间和预定义宏动作的场景，未评估**连续动作**或**学习宏动作**（技能发现）情况。论文本身也指出该方向是未来工作。
- **计算资源报告不完整**：只给出训练时长范围，未说明GPU使用数量、总能耗，不利于能耗对比。
- **缺乏统计显著性检验**：仅以均值和标准误曲线展示，未做t检验或置信区间分析，部分对比可能不显著。
- **对环境假设的依赖**：需要已知宏动作的定义及终止条件；若宏动作不可知或内部策略可学习，ACAC需扩展。
- **可扩展性疑虑**：注意力聚合模块在高智能体数（百级以上）时的计算复杂度未讨论；实验中最大仅6个智能体。

（完）
