---
title: "Causality Meets Locality: Provably Generalizable and Scalable Policy Learning for Networked Systems"
title_zh: 因果遇见局部：面向网络系统可泛化可扩展的策略学习
authors: "Hao Liang, Shuqing Shi, Yudi Zhang, Biwei Huang, Yali Du"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dfcQFL89OM"
tags: ["query:marl"]
score: 7.0
evidence: 每个智能体学习稀疏局部因果掩码，实现在网络系统中的去中心化执行
tldr: 针对大规模网络系统中强化学习智能体面临规模大和环境迁移的挑战，本文提出GSAC框架，通过因果表示学习使每个智能体识别最小局部邻域变量，得到紧凑表示，从而在去中心化执行中保持可扩展性和领域泛化。理论证明局部因果掩码的指数级紧致性，实验验证其在交通、电力等系统中的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 450, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1407, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1214, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1397, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1328, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1357, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1409, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1408, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dfcqfl89om/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1408, \"height\": 442, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dfcqfl89om/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 2260, \"label\": \"Table\"}]"
motivation: 大规模网络系统中，多智能体策略学习面临规模扩展和跨域泛化的双重挑战。
method: 提出GSAC框架，结合因果表示学习与元Actor-Critic，每个智能体学习稀疏局部因果掩码。
result: 在多个网络系统基准任务上，GSAC实现了卓越的泛化性能和扩展性。
conclusion: 本文为大规模网络系统的去中心化策略学习提供了可理论保证的解决方案。
---

## Abstract
Large‑scale networked systems, such as traffic, power, and wireless grids, challenge reinforcement‑learning agents with both scale and environment shifts. To address these challenges, we propose \texttt{GSAC} (\textbf{G}eneralizable and \textbf{S}calable \textbf{A}ctor‑\textbf{C}ritic), a framework that couples  causal representation learning with meta actor‑critic learning to achieve both scalability and domain generalization. Each agent first learns a sparse local causal mask that provably identifies the minimal neighborhood variables influencing its dynamics, yielding exponentially tight approximately compact representations (ACRs) of state and domain factors. These ACRs bound the error of truncating value functions to $\kappa$-hop neighborhoods, enabling efficient learning on graphs. A meta actor‑critic then trains a shared policy across multiple source domains while conditioning on the compact domain factors; at test time, a few trajectories suffice to estimate the new domain factor and deploy the adapted policy. We establish finite‑sample guarantees on causal recovery, actor-critic convergence, and adaptation gap, and show that \texttt{GSAC} adapts rapidly and significantly outperforms learning-from-scratch and conventional adaptation baselines.

---

## 论文详细总结（自动生成）

# 论文详细总结：Causality Meets Locality: Provably Generalizable and Scalable Policy Learning for Networked Systems

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大规模网络系统（如交通网络、电力网格、无线通信系统）中的多智能体强化学习（MARL）面临两大根本挑战：
  - **可扩展性**：全局状态-动作空间随智能体数量指数增长，传统RL算法计算不可行。
  - **泛化性**：实际网络系统常发生环境迁移（如信道变化、流量波动），算法需能快速适应新环境。
- **核心问题**：能否设计一个 **可证明可泛化且可扩展** 的MARL算法，用于大规模网络系统？
- **整体含义**：本文通过融合**因果表示学习**与**元Actor-Critic学习**，提出GSAC框架，首次在带网络结构的MARL中同时实现：
  - 每个智能体仅依赖于其局部邻域的紧凑状态表示（ACR），实现**去中心化可扩展执行**。
  - 借助因果掩码和域因子条件化策略，实现**跨域快速适应**（少量轨迹即可部署）。
  - 提供严格的有限样本保证（因果恢复、收敛、适应差距）。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- **因果结构识别**：每个智能体从轨迹数据中学习**稀疏局部因果掩码**，标识哪些邻域变量真正影响自身动态和奖励。
- **近似紧凑表示（ACR）**：利用因果掩码递归提取**最小必要状态子集**（s◦），将价值函数和策略的输入维度大幅降低，且近似误差随截断半径κ指数衰减。
- **元Actor-Critic**：在多个源域上训练**域因子条件化的共享策略**，测试时仅需少量轨迹估计新域因子，即可部署未经微调的策略。

### 关键技术细节
1. **局部过渡模型**（公式1）：每个智能体的下一状态仅依赖于其邻居状态和自身动作：
   \[
   P(s_i(t+1) \mid s_{\mathcal{N}_i}(t), a_i(t))
   \]
2. **因果掩码学习**（公式6）：定义每个状态维度的生成函数含二元掩码 \(c_{\cdot\to\cdot}\)，指示结构依赖。在标准忠实性假设下，这些掩码可被唯一识别（Theorem 1）。
3. **价值ACR（Definition 1）**：递归定义κ跳邻域内直接影响奖励的状态分量，形成紧凑集\(s^\circ_{\mathcal{N}_i^\kappa}\)。近似误差不超过 \(2\bar{r}/(1-\gamma)\cdot \gamma^{\kappa+1}\)（Proposition 1）。
4. **策略ACR（Algorithm 3）**：使用有限步递归提取影响未来奖励的局部状态子集，策略仅依赖于这些分量。
5. **域因子ACR（Definition 5 & 7）**：类似地压缩域因子 \(\omega\) 到最小相关子集。
6. **元Actor-Critic流程（Algorithm 1）**：
   - Phase 1：因果发现与域因子估计（每个源域）。
   - Phase 2：构造ACR。
   - Phase 3：元训练：抽样源域、使用ACR输入执行内循环TD学习（Critic）、外循环策略梯度更新（Actor）。
   - Phase 4：新域适应：收集少数轨迹估计\(\hat{\omega}\)，直接部署策略。
7. **理论保证**：
   - 因果恢复样本复杂度：\(O(d_i \cdot d_{\max} \log(d_i n/\delta)/\lambda^2)\)（Proposition 4）。
   - 域因子估计误差：\(O(\sqrt{D_\Omega \log(nT_e/\delta)/T_e})\)（Proposition 5）。
   - Critic收敛误差：含截断项、域因子估计项等（Theorem 2）。
   - Actor收敛：梯度范数边界含 \(O(1/\sqrt{K} + \rho^{\kappa+1} + 1/\sqrt{T_e} + 1/\sqrt{M})\)（Theorem 3）。
   - 适应差距：\(O(L_{\omega'} C_\omega \sqrt{\log(n/\delta)/T_a})\)（Theorem 4）。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **基准（Benchmark）**：
  - **无线通信**：n个用户位于2D网格，每个用户维护队列，选择AP传输，碰撞导致失败。域因子为包到达概率 \(p_i\)。
  - **交通控制**：n个路口信号灯，目标是最大化吞吐量（或最小化队列长度）。域因子为车辆到达率。
- **网格大小**：3×3（16智能体）、4×4（25）、5×5（36），影响邻域稀疏性和规模。
- **源域与目标域**：M=3个源域，域因子ω∈{0.2,0.5,0.8}；目标域ω=0.65（可变化）。
- **对比方法**：
  - **GSAC（本文）**：域因子条件化策略，测试时估计ω直接部署。
  - **SAC-MTL**：多任务学习，使用one-hot编码域ID，不显式建模ω。
  - **SAC-FT**：单一策略（无域条件），在目标域微调。
  - **SAC-LFS**：从头学习，无元训练。
- **评估指标**：平均累积奖励（适应阶段前30个episode的曲线）。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。
- 仅提到实验在“两个标准基准”上运行，未披露计算集群或硬件详情。

## 5. 实验数量与充分性

- **实验组数**：
  - 无线通信：3种网格尺寸 × 3种目标域参数（0.6,0.65,0.7）→ 9组适应对比图。
  - 交通控制：同样3种网格尺寸 × 3种目标域参数 → 9组适应对比图。
  - 另外提供了训练曲线（图6）。
  - 未做消融实验（如ACR vs 无ACR）或在其他基准上验证。
- **充分性分析**：
  - **优点**：覆盖了不同网络规模和域迁移场景，对比了三种有代表性的基线。
  - **不足**：
    - **未报告误差棒或置信区间**（论文承认因计算预算限制未提供），单次或少数几次运行的结果难以判断统计显著性。
    - **仅表格化/全观测环境**（论文也指出这是当前局限），未在连续动作空间或部分可观测设置下验证。
    - **未在真实大规模网络数据集上测试**（如实际交通数据），仅限于模拟。
    - **缺少ACR有效性消融**：未对比使用完整邻域 vs ACR的效果，仅理论分析。
    - **适应阶段轨迹数量固定为20**，未研究不同\(T_e\)/\(T_a\)的影响。

## 6. 论文的主要结论与发现

- GSAC在**所有网格尺寸和域目标设置**下，适应阶段前30个episode的平均奖励**均高于**SAC-MTL、SAC-FT和SAC-LFS，表明快速适应能力。
- 随网格增大（智能体增多），基线性能下降明显，而GSAC保持较高水平，体现**可扩展性**。
- 理论结果首次为**网络化MARL中的因果结构识别**提供了样本复杂度保证，并建立了**元Actor-Critic的收敛与适应边界**。
- ACR框架能显著减小输入维度，且近似误差受截断半径控制，为可扩展学习提供理论支撑。

## 7. 优点

- **理论创新**：首次将因果表示学习与网络MARL的局部性结合，给出因果掩码恢复的有限样本保证，以及元策略梯度收敛和适应差距的严格界。
- **可扩展设计**：ACR从因果角度大幅压缩状态/域因子维度，使学习复杂度与邻域大小而非全局规模相关。
- **适应高效**：仅需少量轨迹估计域因子即可部署，无需微调策略参数。
- **实验设计覆盖多尺度**：不同网格大小和目标域参数，验证了鲁棒性。
- **代码与算法细节完整**：附录提供完整伪代码、证明和实验设置。

## 8. 不足与局限

- **实验统计不充分**：未报告多次运行的均值和方差，无法判断性能的稳定性。
- **环境假设较强**：需要离散/表格化状态、全观测、局部因果性假设（忠实性、Lipschitz等），实际连续或部分观测系统可能不满足。
- **因果发现前提**：要求因果掩码可识别，需要数据满足忠实性和足够样本量，在复杂非线性系统中可能不成立。
- **计算资源未公开**：难以复现或评估方法的实际训练成本。
- **仅两个模拟基准**：缺乏真实大规模网络数据或更复杂场景（如异构智能体、随机拓扑）的验证。
- **ACR构造依赖离线预计算**：Phase 1和2需要预处理，虽然是一次性，但新域仍需重新估计域因子，可能影响在线适应性。
- **未讨论部分可观测问题**：限制了在传感器噪声或隐藏状态下的应用。

（完）
