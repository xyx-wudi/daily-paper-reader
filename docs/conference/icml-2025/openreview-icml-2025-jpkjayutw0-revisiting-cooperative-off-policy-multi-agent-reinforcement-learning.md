---
title: Revisiting Cooperative Off-Policy Multi-Agent Reinforcement Learning
title_zh: 重新审视合作离线多智能体强化学习
authors: "Yueheng Li, Guangming Xie, Zongqing Lu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JPkJAyutW0"
tags: ["query:marl"]
score: 9.0
evidence: 合作离线多智能体强化学习中的Q目标估计问题
tldr: 合作多智能体强化学习在离线学习中面临联合Q函数的扩展误差问题，且随智能体数量增加而恶化。本文通过分析Q目标估计错误，提出包括退火多步提升在内的一系列技术，显著缓解了扩展误差，提升了可扩展性，并在多个合作任务上验证了方法的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 840, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1548, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1644, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1731, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1744, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 823, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1714, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1729, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1712, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1727, \"height\": 359, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jpkjayutw0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1247, \"height\": 878, \"label\": \"Table\"}]"
motivation: 离线MARL中联合Q函数因扩展误差导致可扩展性差，且该误差随智能体数量加剧。
method: 提出退火多步提升等技术，针对离策略MARL中的Q目标估计错误进行修正。
result: 所提技术有效缓解扩展误差，在多个合作任务上实现更好性能。
conclusion: 揭示了离策略MARL中的关键问题并提供了实用解决方案。
---

## Abstract
Cooperative Multi-Agent Reinforcement Learning (MARL) has become a critical tool for addressing complex real-world problems. 
However, off-policy MARL methods, which rely on joint Q-functions, face significant scalability challenges due to the exponentially growing joint action space.
In this work, we highlight a critical yet often overlooked issue: erroneous Q-target estimation, primarily caused by extrapolation error.
Our analysis reveals that this error becomes increasingly severe as the number of agents grows, leading to unique challenges in MARL due to its expansive joint action space and the decentralized execution paradigm.
To address these challenges, we propose a suite of techniques tailored for off-policy MARL, including annealed multi-step bootstrapping, averaged Q-targets, and restricted action representation. Experimental results demonstrate that these methods effectively mitigate erroneous estimations, yielding substantial performance improvements in challenging benchmarks such as SMAC, SMACv2, and Google Research Football.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **核心问题**：合作离线策略多智能体强化学习（off-policy MARL）中，联合Q函数的估计误差（特别是外推误差）随智能体数量指数级增长，导致可扩展性严重下降。尽管值分解方法（如VDN、QMIX）在一定程度上缓解了可扩展性问题，但随着智能体增加，性能仍然显著退化。
- **研究动机**：现有研究多关注目标逼近误差（TAE），即Q函数拟合目标的能力，而忽略了目标估计误差（TEE），即由外推误差引起的Q-target偏差。该偏差在MARL中因联合动作空间庞大且缺乏欧几里得相似性而尤为突出。
- **整体含义**：该工作揭示了离线策略MARL性能瓶颈的真正根源，并提供了实用解决方案，为提升大规模多智能体协作系统的性能开辟了新方向。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
通过降低对Q(s′, a′)的依赖、减少目标方差、限制联合动作空间的影响，来缓解目标估计误差（TEE），并利用单调性分解保证误差传递一致性（EPC）。

### 关键技术细节
#### (1) 退火多步自举 (Annealed Multi-Step Bootstrapping)
- **原理**：采用Peng's Q(λ) (PQL) 算子，用多步蒙特卡洛回报替代单步TD目标中的Q(s′, a′)，以减少对未训练价值网络的依赖。
- **公式**：\( \mathcal{N}^{\mu,\pi}_\lambda Q = (1-\lambda)\sum_{n=1}^\infty (\lambda T^\mu)^{(n-1)} T^\pi Q \)
- **误差传播**：命题4.1证明，每一步的TEE上界为 \( \beta \epsilon \)，其中 \( \beta = \frac{\gamma(1-\lambda)}{1-\gamma\lambda} \)，λ越大误差越小。
- **退火策略**：训练初期使用较大λ（如0.8）以降低误差，后期逐渐退火至较小λ*（如0.0或0.2），避免策略偏置。退火公式：\( \lambda_k = \lambda^* + \frac{1-\lambda^*}{1+\alpha k} \)，α=10/T。

#### (2) 平均TD目标 (Averaged TD Target)
- **原理**：集成M个独立的Q函数估计器（或个体效用网络），将它们的输出平均作为目标，使方差降低至1/M。
- **实现**：对于值分解方法，平均个体效用网络（而非混合网络），因为混合网络不依赖动作空间；损失函数为 \( L(\theta,\psi) = \sum_{j=1}^M \mathbb{E}_D[(Q(s,a;\theta_j,\psi)-y_{s,a})^2] \)，其中 \( y_{s,a} \) 使用平均Q函数计算PQL目标。
- **注意**：需保证单调性（EPC）才能将联合Q函数误差传递到个体效用。

#### (3) 受限动作表示 (Restricted Action Representation, RAR)
- **原理**：通过映射函数g将高维联合动作空间压缩至低维离散空间，减少外推误差。
- **应用**：
  - **对MADDPG**：g(a)映射为5个2类别的分类变量（共2^5=32种组合，原始54种），通过直通梯度训练。
  - **对QPLEX**：直接对权重λ_i(s,a)施加Sigmoid限制，使其∈[0,1]，抑制由罕见(state,action)对产生的异常大值。

### 算法流程（以AEQMIX为例）
1. 初始化M个个体Q网络和一个混合超网络。
2. 对每个episode，收集轨迹到回放缓冲区。
3. 从缓冲区采样批数据，对每个转移使用平均个体效用(argmax)选择联合动作a′。
4. 用平均Q函数计算Q′(s′, a′)，再结合PQL目标计算y_{s,a}。
5. 通过损失函数(9)更新参数，每d步更新目标网络和退火λ。

## 3. 实验设计：数据集/场景、benchmark、对比方法

### 场景与Benchmark
- **SMAC**（StarCraft Multi-Agent Challenge）：包括4张经典地图（2s3z, 2c_vs_64zg, MMM2, 27m_vs_30m），含Easy、Hard、Super Hard等级。
- **SMACv2**：改进版，含更多随机性（随机生成单位和初始位置），共15张地图（按种族分为zerg/protoss/terran，每种族5种规模：5v5, 10v10, 20v20, 10v11, 20v23）。
- **GRF**（Google Research Football）：5张场景（3_vs_1_with_keeper, counterattack_easy/hard, run_pass_and_shoot_with_keeper, corner）。

### 对比方法
- **基线**：QMIX, VDN, QPLEX, FACMAC, MADDPG（均为2018-2021年主流离线策略方法）。
- **本文方法**：AEQMIX, AEFACMAC, AEMADDPG-RAR, AEQPLEX-RAR, AEVDN。
- **额外对照**：MAPPO、MAA2C（在线策略方法），以及不同超参数设置（λ, M, 隐藏层大小）。

## 4. 资源与算力
论文中未明确说明所使用的GPU型号、数量、训练时长。仅在附录D.1给出超参数表（如批次大小、缓冲区大小等）。未提供完整的硬件配置细节。

## 5. 实验数量与充分性
- **实验数量**：
  - 主实验：SMAC（4张图×2种方法对比）、SMACv2（15张图×2种方法对比）、GRF（5张图×2种方法对比）。
  - 消融实验：λ不同取值（0.0,0.2,0.4,0.6,0.8）、集成规模M（1,2,4,8）、网络隐藏层大小（64,128,256）、悲观目标策略对比（REDQ式最小化）、混合网络数量M等。
  - 其他：TEE/TAE测量、外推比例分析、λ对QPLEX的影响等。
- **充分性与客观性**：
  - 覆盖了3个主流基准（SMAC、SMACv2、GRF），共24个场景，涵盖不同难度和规模。
  - 消融实验深入探讨了每个技术组件的作用，且对比了退火vs固定λ、集成大小、悲观目标等合理对照。
  - 所有结果均绘制均值曲线，部分给出标准差（如Fig.4显示λ均值/标准差/最大值），显示了统计可靠性。
  - 但未报告多次运行的具体种子数量和置信区间，仅展示单次运行曲线，可能引入随机性偏差。

## 6. 主要结论与发现
- **结论1**：离线策略MARL性能下降的根本原因是目标估计误差（TEE），主要由外推误差引起，且随智能体数量加剧。
- **结论2**：单调性值分解（如QMIX）满足误差传播一致性（EPC），使联合Q函数误差能传递到个体效用，从而允许通过修正联合误差来自我纠正。
- **结论3**：提出的三种技术（退火多步自举、平均目标、受限动作表示）可显著降低TEE，在SMACv2等大规模任务中实现了超过QMIX baseline 20-40个百分点的胜率提升。
- **结论4**：单纯增大网络参数（如隐藏层从64到256）反而因外推误差恶化而降低性能，说明提升并非来自模型容量而是更准确的目标估计。

## 7. 优点
- **问题洞察新颖**：首次系统性地将外推误差与TEE引入离线策略MARL分析，突破了以往只关注TAE的局限。
- **方法通用且实用**：三种技术可即插即用地集成到现有离线策略方法（值基、策略基、分解、非分解）中，无需大幅修改原有架构。
- **理论支撑扎实**：提供了误差传播上界（Proposition 4.1）和EPC概念的形式化定义（Definition 3.1与Proposition 3.2），保证了方法的合理性。
- **实验设计全面**：覆盖多领域、多规模任务，并进行了细致的消融（λ、M、RAR、悲观策略等），结论可信。

## 8. 不足与局限
- **硬件资源未报告**：缺少GPU型号、训练时长、总计算量等详细信息，不利于他人复现或评估计算成本。
- **统计可靠性不足**：未提供多次运行的均值/标准差或箱线图，仅展示单次曲线，可能导致对性能可重复性的质疑。
- **应用限制**：
  - 退火策略和λ*需要针对不同任务调参（如表1中SMAC、SMACv2、GRF的λ和λ*均不同），增加了调参成本。
  - RAR技术（如Sigmoid限制λ）仅针对特定结构（QPLEX、MADDPG），能否泛化到其他因子化方法（如QTRAN、FOP）未验证。
  - 仅测试了离散动作空间的任务（SMAC、GRF），未在连续动作空间（如mujoco多智能体）上验证。
- **理论假设的局限性**：平均目标假设误差i.i.d.，但实际中由于模型偏差可能非独立；退火策略的理论保证仅针对固定行为策略μ，动态策略下需要进一步分析。
- **与SOTA在线策略方法的比较缺失**：未与当前最强的在线策略方法（如MAPPO、HAPPO）在完全相同的实验设置下进行系统对比（Fig.1仅有初步对比，缺乏关键任务上的定量数字）。

（完）
