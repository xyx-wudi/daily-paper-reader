---
title: "Continuous Soft Actor-Critic: An Off-Policy Learning Method Robust to Time Discretization"
title_zh: 连续软演员-评论家：一种对时间离散化鲁棒的离策略学习方法
authors: "Huimin Han, Shaolin Ji"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Ey0mro4vJ6"
tags: ["query:marl"]
score: 8.0
evidence: 连续SAC算法的多智能体扩展
tldr: 该论文提出连续软演员-评论家算法（Continuous SAC），对时间离散化鲁棒，并扩展至多智能体场景。该MARL算法适用于竞争和合作环境，利用随机控制理论和鞅正交条件推导损失函数，建立了超参数随离散时间步长变化的缩放原则。为连续时间多智能体强化学习提供了新方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 896, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1003, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1160, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1154, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1207, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 778, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 778, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1210, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ey0mro4vj6/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 376, \"height\": 409, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1387, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 824, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1413, \"height\": 724, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1406, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 828, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 731, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 960, \"height\": 1108, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 960, \"height\": 850, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 578, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 561, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1143, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1143, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 558, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 561, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1368, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 559, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 561, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 414, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1334, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ey0mro4vj6/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1215, \"height\": 539, \"label\": \"Table\"}]"
motivation: 许多深度强化学习算法对时间离散化敏感，影响真实场景性能。
method: 提出连续时间离策略SAC算法，并扩展到多智能体场景，使用鞅正交条件推导损失函数。
result: 算法在时间离散化下表现稳健，并成功应用于多智能体环境。
conclusion: 为连续时间多智能体强化学习提供了鲁棒且可扩展的算法。
---

## Abstract
Many \textit{Deep Reinforcement Learning} (DRL) algorithms are sensitive to time discretization, which reduces their performance in real-world scenarios. We propose Continuous Soft Actor-Critic, an off-policy actor-critic DRL algorithm in continuous time and space. It is robust to environment time discretization. We also extend the framework to multi-agent scenarios. This \textit{Multi-Agent Reinforcement Learning} (MARL) algorithm is suitable for both competitive and cooperative settings. Policy evaluation employs stochastic control theory, with loss functions derived from martingale orthogonality conditions. We establish scaling principles for hyperparameters of the algorithm as the environment time discretization $\delta t$ changes ($\delta t \rightarrow 0$). We provide theoretical proofs for the relevant theorems. To validate the algorithm's effectiveness, we conduct comparative experiments between the proposed algorithm and other mainstream methods across multiple tasks in \textit{Virtual Multi-Agent System} (VMAS). Experimental results demonstrate that the proposed algorithm achieves robust performance across various environments with different time discretization parameter settings, outperforming other methods.

---

## 论文详细总结（自动生成）

# Continuous Soft Actor-Critic: 一种对时间离散化鲁棒的离策略学习方法

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：许多深度强化学习算法（如PPO、SAC、DDPG）在离散时间框架下开发，对时间离散化参数（时间步长δt）高度敏感。当δt趋于0时，这些算法的性能显著下降，甚至失效。论文研究以下问题：
  - 在随机环境中，当δt→0时，基于Q-learning的算法（如DQN、SAC）是否会崩溃？
  - 能否提出一种对时间离散化鲁棒的算法？
  - 当δt变化时，应如何调整超参数？
- **背景**：现有工作（Tallec等，2019）已证明在确定性环境中Q-learning在连续时间下不存在。但在随机环境中，类似问题尚未充分研究。同时，多智能体强化学习在连续时间设置下的研究较少。
- **整体含义**：论文提出连续软演员-评论家（CSAC）及其多智能体版本CMASAC，利用随机控制理论和鞅方法，使得算法对不同时间离散化步长具有鲁棒性，为连续时间强化学习提供实用框架。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将强化学习问题建模为随机最优控制问题，状态演化由随机微分方程（SDE）描述。
- 采用熵正则化的期望累积回报，政策（policy）最大化熵与回报之和。
- 证明在连续时间下，值函数满足鞅性质，传统均方时间差分误差（MSTDE）不适用，需使用鞅正交条件进行策略评估。
- 提出离策略学习算法，利用历史轨迹更新，并通过超参数缩放定律保证δt变化时稳定收敛。

### 关键技术细节
1. **策略评估（Policy Evaluation）**：
   - 传统MSTDE在连续时间随机环境下不为零，导致学习不收敛。
   - 基于鞅正交条件：对于值函数Jθ，需满足对任意测试函数ξt有  
     \[
     \mathbb{E}\left[\int_0^T \xi_t (dJ^\theta(t,X_t) + r dt - \lambda \ln\pi dt - \beta J^\theta dt)\right] = 0
     \]
   - 由此推导出损失函数，利用梯度下降最小化鞅差项。

2. **策略梯度（Policy Gradient）**：
   - 推导出连续时间策略梯度定理（Theorem 3），参数更新公式中包含鞅差项和熵正则项。
   - 采用重参数化采样，使离策略学习无偏。

3. **超参数缩放定律（Theorem 5）**：
   - 学习率需按α·δt缩放（β=1时离散参数轨迹收敛到连续轨迹）。
   - 折扣因子：γ = e^{-βδt}。
   - 温度参数λ和奖励r均需线性缩放：λ_{δt} = λ·δt，r_{δt} = r·δt。

4. **多智能体扩展**：
   - 基于中央训练分布式执行（CTDE）框架，两智能体交替更新，分别优化各自的值函数和策略。
   - 策略评估和梯度公式类似单智能体，但包含对方策略的期望。

5. **算法流程**（文字说明）：
   - 初始化网络参数θ, φ，目标网络。
   - 与环境交互收集轨迹，存入经验回放池。
   - 每步更新：采样批次→计算鞅差δM→计算梯度Δθ, Δφ→按缩放后的学习率更新参数→调整温度λ→软更新目标网络。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **实验环境**：
  - 使用VMAS（Vectorized Multi-Agent Simulator）模拟器中的多任务。
  - 主要任务：
    - **Navigation**（导航）：智能体需导航到目标，同时避免碰撞。
    - **Sampling**（采样）：智能体在三维高斯分布场中收集样本。
    - **Balance**（平衡）：智能体合作搬运球体至目标点。
- **Benchmark与对比方法**：
  - 对比算法：MAPPO、MASAC、MADDPG、IQL、QMIX。
  - 额外对比：TEST（CMASAC的无缩放版本，即不使用超参数缩放）。
- **评估指标**：
  - 归一化得分，包括中位数、IQM（四分位均值）、均值、最优差距（Optimality Gap），并给出95%置信区间。
  - 使用性能曲线（Performance Profile）和聚合得分图。

## 4. 资源与算力

- **硬件信息**：
  - CPU：Intel Xeon Silver 4314 (2.40GHz, 16物理核心)
  - GPU：NVIDIA RTX 4090 (24GB VRAM)
- **资源消耗**：
  - 每个独立实验运行平均消耗约1.5GB CPU RAM和2.2GB GPU VRAM。
- **训练时长**：文中未明确给出具体训练时长，仅说明使用不同数量的帧（如3×10^5帧、6×10^5帧、3×10^6帧等）。未提及其他具体时间开销。

## 5. 实验数量与充分性

- **实验组数**：
  - 主要实验在Navigation和Sampling任务上进行，包含多种δt设置（0.1和0.01）。
  - 随机种子：多数实验使用3个种子（{0,1,2}），部分扩大至4或5个种子。
  - 消融实验：对比CMASAC与TEST（无缩放版本）和MASAC，以分离鞅正交条件和超参数缩放的效果。
  - 额外在Balance任务上测试。
  - 单智能体线性二次型问题实验中对比了CSAC与Q-learning方法。
- **充分性**：
  - 实验覆盖了不同时间步长、不同超参数设置（折扣因子0.9 vs 0.99）、不同帧数量。
  - 提供了梯度分析（Tables 6,7）说明缩小δt导致梯度消失，以及缩放策略的有效性。
  - 使用了统计工具（marl-eval）计算置信区间，确保结果可靠性。
  - **公平性**：对比算法使用BenchMARL默认超参数，作者指出可能未针对CSAC优化，但用于鲁棒性验证合理。
- **客观性评价**：实验较为充分，但仅在VMAS模拟器上测试，未涉及真实物理环境或离散动作空间任务，存在一定局限。

## 6. 论文的主要结论与发现

- 传统离散时间DRL算法（如MASAC、MADDPG、IQL）在δt减小时性能显著下降，而CMASAC保持稳定。
- 提出的鞅正交条件策略评估方法在连续时间随机环境中有效，优于基于MSTDE的方法。
- 超参数缩放定律（学习率、折扣因子、温度、奖励）是保证算法在不同δt下收敛的关键。
- 离策略学习框架在连续时间下可行，通过重参数化避免偏差。
- 多智能体CMASAC在合作与竞争场景下均表现出鲁棒性，在δt=0.01时优于其他方法。
- 单智能体线性二次型实验中，CSAC在行为策略与目标策略差异较大时仍稳定，而Q-learning方法崩溃。

## 7. 优点：方法或实验设计上的亮点

- **理论严谨性**：将随机控制理论与强化学习深度融合，给出鞅正交条件作为策略评估的新范式，并严格证明策略梯度定理。
- **实用离策略算法**：解决了Jia和Zhou（2022,2023）中仅有on-policy或存在偏差的问题，实现高效的离线学习。
- **超参数缩放定律**：首次在随机连续时间MDP中推导出随δt变化的缩放原则，具有实用指导意义。
- **多智能体扩展**：先驱性地提出有限智能体连续时间actor-critic算法，并给出实验实现。
- **实验统计严谨**：使用95%置信区间、IQM等指标以及性能曲线，结果可视化清晰。
- **消融分析**：通过TEST变体（无缩放）和MASAC对比，分离了两种关键贡献（鞅条件和缩放）。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖有限**：
  - 仅使用VMAS环境中的3个任务（Navigation, Sampling, Balance），未在更多标准MARL基准（如SMAC、Multi-agent Particle Environment）上测试。
  - 未涉及真实物理机器人实验，仅仿真。
  - 随机种子数偏少（多数组3个），虽然补充了5个种子的结果，但统计稳定性仍有提升空间。
- **偏差风险**：
  - 对比算法的超参数采用BenchMARL默认值，可能导致对比不利；作者也承认CSAC的性能可能未达到最优。
  - 单智能体实验中，仅线性和二次问题，未能体现更复杂场景。
- **应用限制**：
  - 算法假设连续状态和动作空间，不适用于离散空间问题。
  - 多智能体框架目前仅实现两智能体，虽声称可扩展至有限个，但未验证。
  - 计算资源需求较高（GPU 24GB），可能限制在资源受限设备上的应用。
- **理论假设较强**：
  - 需满足值函数光滑性、多项式增长等条件，在实际神经网络近似中可能不完全满足。
  - 鞅性质仅通过梯度下降近似保持，严格性在深度学习中难以保证。

（完）
