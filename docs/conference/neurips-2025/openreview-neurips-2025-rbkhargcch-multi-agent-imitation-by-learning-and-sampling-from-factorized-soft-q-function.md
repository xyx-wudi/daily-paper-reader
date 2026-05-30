---
title: Multi-Agent Imitation by Learning and Sampling from Factorized Soft Q-Function
title_zh: 通过学习和采样分解软Q函数实现多智能体模仿
authors: "Yi-Chen Li, Zhongxiang Ling, Tao Jiang, Fuxiang Zhang, Pengyuan Wang, Lei Yuan, Zongzhang Zhang, Yang Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=RbkHARGCcH"
tags: ["query:marl"]
score: 9.0
evidence: 基于分解软Q函数的多智能体模仿学习
tldr: 该工作针对多智能体模仿学习中的行为克隆累积误差和对抗模仿学习不稳定性问题，提出了MAFIS方法，通过引入分解软Q函数和价值分解框架，在离线和在线设置下均能鲁棒学习专家策略。实验表明MAFIS有效缓解了上述挑战，为多智能体模仿学习提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 677, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1409, \"height\": 1959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 661, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 662, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 808, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1428, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1430, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rbkhargcch/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1430, \"height\": 356, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbkhargcch/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1394, \"height\": 792, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbkhargcch/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1357, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rbkhargcch/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 583, \"height\": 343, \"label\": \"Table\"}]"
motivation: 现有MAIL方法面临累积误差或训练不稳定，需要更鲁棒的方法。
method: 基于单智能体IQ-Learn框架，引入分解软Q函数和价值分解实现多智能体模仿。
result: MAFIS在标准多智能体环境中优于BC和AIL基线。
conclusion: 因子化软Q函数有效解决多智能体模仿学习的核心难题。
---

## Abstract
Learning from multi-agent expert demonstrations, known as Multi-Agent Imitation Learning (MAIL), provides a promising approach to sequential decision-making. However, existing MAIL methods including Behavior Cloning (BC) and Adversarial Imitation Learning (AIL) face significant challenges: BC suffers from the compounding error issue, while the very nature of adversarial optimization makes AIL prone to instability. In this work, we propose \textbf{M}ulti-\textbf{A}gent imitation by learning and sampling from \textbf{F}actor\textbf{I}zed \textbf{S}oft Q-function (MAFIS), a novel method that addresses these limitations for both online and offline MAIL settings. Built upon the single-agent IQ-Learn framework, MAFIS introduces the value decomposition network to factorize the imitation objective at agent level, thus enabling scalable training for multi-agent systems. Moreover, we observe that the soft Q-function implicitly defines the optimal policy as an energy-based model, from which we can sample actions via stochastic gradient Langevin dynamics. This allows us to estimate the gradient of the factorized optimization objective for continuous control tasks, avoiding the adversarial optimization between the soft Q-function and the policy required by prior work. By doing so, we obtain a tractable and \emph{non-adversarial} objective for both discrete and continuous multi-agent control. Experiments on common benchmarks including the discrete control tasks StarCraft Multi-Agent Challenge v2 (SMACv2), Gold Miner, and Multi Particle Environments (MPE), as well as the continuous control task Multi-Agent MuJoCo (MaMuJoCo), demonstrate that MAFIS achieves superior performance compared with baselines. Our code is available at https://github.com/LAMDA-RL/MAFIS.

---

## 论文详细总结（自动生成）

# 论文总结：Multi-Agent Imitation by Learning and Sampling from Factorized Soft Q-Function

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：多智能体模仿学习（Multi-Agent Imitation Learning, MAIL）旨在从专家演示中学习策略，但现有方法存在严重缺陷。
- **现有方法局限**：
  - **行为克隆（BC）**：容易产生累积误差（compounding error），即模型在遇到未训练的状态时，小误差随时间积累。
  - **对抗性模仿学习（AIL）**：如MA-GAIL，基于对抗优化，训练不稳定，对超参数敏感。
- **研究动机**：需要一种既能避免累积误差、又能避免对抗优化不稳定的多智能体模仿学习方法，同时支持离线和在线设置，以及离散和连续控制任务。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：基于单智能体IQ-Learn框架，将软Q函数（soft Q-function）分解为各智能体Q函数的加权和，从而将模仿目标分解到智能体层面，实现可扩展训练；利用能量基模型（EBM）和随机梯度Langevin动力学（SGLD）从软Q函数中采样动作，避免对抗优化。

- **关键技术细节**：
  - **软Q函数分解**：联合软Q函数 \(Q_{\text{tot}}(\tau, a)\) 表示为每个智能体Q函数 \(Q_i(\tau_i, a_i)\) 的加权和：  
    \[
    Q_{\text{tot}}(\tau, a) = \sum_{i=1}^n k_i(s) Q_i(\tau_i, a_i)
    \]  
    其中 \(k_i(s)\) 是混合网络（Mixing Network），确保 \(k_i(s) > 0\)。
  - **非对抗性目标**：通过分解，将原对抗目标转化为可直接优化的非对抗目标（Proposition 4.1）。对于离散动作空间，可直接计算 \(\log Z_{\tau_i}\)；对于连续动作空间，通过SGLD采样来估计梯度（Proposition 4.2）。
  - **能量基策略采样**：最优策略可表示为能量基模型：  
    \[
    \pi_{Q_i}(a_i|\tau_i) \propto \exp\left(\frac{1}{\alpha} k_i(s) Q_i(\tau_i, a_i)\right)
    \]  
    使用SGLD迭代更新采样：  
    \[
    a_{i,k+1} \leftarrow a_{i,k} + \frac{\epsilon^2}{2\alpha} \nabla_{a_{i,k}} k_i(s) Q_i(\tau_i, a_{i,k}) + \epsilon \omega
    \]  
    其中 \(\omega \sim \mathcal{N}(0, \sigma^2)\)。
  - **去中心化执行**：在推理时，每个智能体使用仅依赖局部观测-动作历史的策略 \(\tilde{\pi}_{Q_i}(a|\tau)\)，即去掉全局状态依赖的 \(k_i(s)\)，仅使用 \(Q_i(\tau_i, a_i)\) 进行指数归一化，并选择最高Q值的动作执行。

- **算法流程（伪代码概述）**：
  1. 初始化联合Q函数 \(Q_{\text{tot}}\)、专家演示数据集 \(D_E\)、总训练步数 \(T\)。
  2. （在线）清空回放缓冲区 \(B\)。
  3. （连续控制）设置Langevin步数 \(K\)、步长 \(\epsilon\)、采样数 \(N\)。
  4. 对于每一步 \(t=1\) 到 \(T\)：
     - （在线）与环境交互采样，存储到缓冲区。
     - 若离散控制，则按式(7)更新 \(Q_{\text{tot}}\)。
     - 若连续控制，则按式(8)更新 \(Q_{\text{tot}}\)（通过SGLD采样估计梯度）。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集/场景**：
  - **离散控制任务**：
    - StarCraft Multi-Agent Challenge v2 (SMACv2)：包括 terran_5_vs_5、protoss_5_vs_5、zerg_5_vs_5、terran_10_vs_11、protoss_10_vs_11、zerg_10_vs_11。
    - Multi Particle Environments (MPE)：simple_spread、simple_reference、simple_speaker_listener。
    - Gold Miner：GoldMiner_Easy、GoldMiner_Medium、GoldMiner_Hard。
  - **连续控制任务**：
    - Multi-Agent MuJoCo (MaMuJoCo)：Ant(2x4)、HalfCheetah(2x3)、Walker2d(2x3)。

- **基准**：与以下方法对比：
  - BC（Behavior Cloning）：离线监督学习方法。
  - MA-GAIL（Multi-Agent Generative Adversarial Imitation Learning）：在线对抗模仿学习。
  - MIFQ（Multi-Agent Inverse Factorized soft Q-learning）：最新基于IQ-Learn的离线可分解方法（仅适用于离散控制）。
  - 专家（Expert）：使用真实奖励训练的策略，作为性能上界。

- **实验设置**：
  - 离散任务收集100条专家轨迹，连续任务收集20条专家轨迹。
  - 在线学习：每个任务在5个随机种子下运行，展示学习曲线。
  - 离线学习：每个任务在5个随机种子下训练3×10^6步，最终检查点评估10个轨迹的平均回报。

## 4. 资源与算力

- **硬件**：论文附录C.2明确列出：
  - NVIDIA RTX 4090 × 8
  - 12th Gen Intel(R) Core(TM) i9-12900K
- **软件**：Python 3.7, PyTorch 1.12.1, Gym 0.21.0, MuJoCo-py 2.1.2.14
- **训练时长**：未明确给出每个实验的具体运行时间，但提到离线学习每个种子训练3×10^6步。考虑到硬件配置，可以推测实验是可重复的，但缺乏具体耗时细节。

## 5. 实验数量与充分性

- **实验数量**：
  - 共12个任务（6个SMACv2、3个MPE、3个Gold Miner、3个MaMuJoCo），分成在线和离线两组实验。
  - 每个任务使用5个随机种子，每个种子在离线时评估10个轨迹。
  - 消融实验：对超参数（采样数N、熵权重α、Langevin步数K、噪声标准差σ、步长ε）进行敏感性分析，每个参数设定下也使用5个种子。
- **充分性与公平性**：
  - 覆盖了离散和连续控制，涵盖多个流行benchmark，对比了包括MIFQ（最新）在内的三个基线。
  - 使用相同的专家演示数据，确保公平比较。
  - 实验设计客观，展示了学习曲线和离线结果表格，误差棒通过阴影或表格标准差显示。
  - 消融实验较全面，涵盖关键超参数。
  - 但连续控制任务中，仅使用MaMuJoCo三个任务，可能不够全面；此外未在更复杂场景（如大规模智能体或高维动作空间）中验证。

## 6. 主要结论与发现

- **主要结论**：MAFIS在大多数任务上显著优于BC、MA-GAIL和MIFQ（离散任务），同时在连续控制任务中也优于BC和MA-GAIL（MIFQ不适用于连续）。在在线和离线设置下均表现稳定。
- **关键发现**：
  - 分解软Q函数可实现去中心化执行，并避免对抗训练的不稳定性。
  - 使用SGLD从能量基策略采样可有效处理连续动作空间，而直接对抗更新（如Adversarial Update）会失败。
  - 超参数敏感性分析表明：采样数N越大性能越好，但计算开销也大；熵权重α过大（如1.5）会导致性能下降；Langevin步数K和步长ε需适中。

## 7. 优点

- **方法创新**：
  - 首次将IQ-Learn框架成功扩展到多智能体，并解决连续控制难题，无需对抗优化。
  - 利用价值分解网络实现可扩展训练和去中心化执行。
  - 将最优策略视为能量基模型，通过SGLD采样避免了logsumexp在连续空间的不可计算性。
- **实验充分**：
  - 覆盖离散和连续两大领域，多个benchmark，对比了最相关的基线。
  - 进行了详细的消融实验，验证了关键超参数的影响。
- **稳定性**：非对抗目标有效提升了训练稳定性，从对抗更新失败的对比图中可见MAFIS明显更优。
- **开源代码**：提供了GitHub仓库，便于复现。

## 8. 不足与局限

- **性能差距**：MAFIS在连续控制任务上仍落后于专家演示，尤其是在HalfCheetah(2x3)上，离线性能远低于专家（2446 vs 9187），在线也只提升到3114。
- **实验覆盖有限**：
  - 连续任务仅使用MaMuJoCo的三个简单场景（2个智能体，动作维度4或3），未在更复杂场景（如多智能体高维动作、大规模智能体）中验证。
  - 未与更多最新的MAIL方法对比（如基于Transformer或扩散模型的方法）。
- **资源消耗**：SGLD采样需要多次迭代（K=25）和多个样本（N=20），可能增加训练计算成本，但论文未报告实际运行时间。
- **局限性总结**：作者在论文中指出“在连续控制任务上仍落后于专家”，并计划未来工作改进模仿效率和复杂动作空间的处理。此外，分解方法依赖于混合网络，可能对不完全可观察环境中的全局状态近似引入偏差。

（完）
