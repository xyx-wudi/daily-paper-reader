---
title: Finite-Time Global Optimality Convergence in Deep Neural Actor-Critic Methods for Decentralized Multi-Agent Reinforcement Learning
title_zh: 分散式多智能体强化学习中深度神经网络演员-评论家方法的有限时间全局最优收敛
authors: "Zhiyao Zhang, Myeung Suk Oh, FNU Hairi, Ziyue Luo, Alvaro Velasquez, Jia Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ZcvGJH4ps7"
tags: ["query:marl"]
score: 10.0
evidence: 分散式多智能体强化学习中深度神经网络演员-评论家的有限时间全局最优收敛
tldr: 分散式多智能体强化学习中，现有理论仅能保证线性函数逼近下的平稳解，与实际使用的深度神经网络存在差距。本文首次针对深度神经演员-评论家方法，证明其在分散式MARL中有限时间内收敛到全局最优，缩小了理论与实践之间的鸿沟。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 817, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 802, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 816, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 799, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 572, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 572, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 570, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 572, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 572, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 570, \"height\": 346, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zcvgjh4ps7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1685, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcvgjh4ps7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 934, \"height\": 201, \"label\": \"Table\"}]"
motivation: 现有分散式MARL理论仅保证线性逼近下的平稳解，与实际深度方法有差距。
method: 开发深度神经演员-评论家方法，并提供有限时间全局最优收敛分析。
result: 证明了所提方法在分散式MARL中有限时间收敛到全局最优。
conclusion: 首次建立了深度分散式MARL的全局最优收敛理论。
---

## Abstract
Actor-critic methods for decentralized multi-agent reinforcement learning (MARL) facilitate collaborative optimal decision making without centralized coordination, thus enabling a wide range of applications in practice. To date, however, most theoretical convergence studies for existing actor-critic decentralized MARL methods are limited to the guarantee of a stationary solution under the linear function approximation. This leaves a significant gap between the highly successful use of deep neural actor-critic for decentralized MARL in practice and the current theoretical understanding. To bridge this gap, in this paper, we make the first attempt to develop a deep neural actor-critic method for decentralized MARL, where both the actor and critic components are inherently non-linear. We show that our proposed method enjoys a global optimality guarantee with a finite-time convergence rate of $\mathcal{O}(1/T)$, where $T$ is the total iteration times. This marks the first global convergence result for deep neural actor-critic methods in the MARL literature. We also conduct extensive numerical experiments, which verify our theoretical results.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：分散式多智能体强化学习（decMARL）在实际中广泛采用深度神经网络（DNN）作为演员-评论家，但现有理论仅能保证**线性函数逼近**下的**平稳解（stationary point）**，远弱于实际所需的全局最优性。这造成了理论与实践之间的显著鸿沟。
- **核心问题**：能否设计出**非线性DNN函数逼近**的分散式演员-评论家方法，并证明其**有限时间内收敛到全局最优**？
- **整体意义**：本文首次在MARL领域建立了深度神经演员-评论家方法的**全局最优收敛理论**，收敛率为 **O(1/T)**，样本复杂度为 **O(1/ϵ³)**，填补了理论空白。

## 2. 方法论

- **核心思想**：采用**双循环结构**的DNN演员-评论家框架。内循环（Critic）使用TD学习分布式地逼近Q函数，外循环（Actor）利用consensus TD误差计算策略梯度更新策略参数。通过**gossip共识技术**处理分散性，并引入**伪中心化参数**（pseudo-centralized）来克服非线性操作与共识交织带来的分析困难。

- **关键技术细节**：
  - **Critic（算法2）**：每个智能体维护一个DNN参数 \(W_i\)，在K次迭代中采样Markov链，计算TD误差并更新参数，每次更新后投影到以全局初始参数为中心的球 \(B(B)\) 内。完成K次后执行 \(t_{\text{gossip}}\) 轮共识聚合。
  - **Actor（算法1）**：利用Critic输出的共识参数 \(W_K\)，在M个Markov样本上计算局部TD误差 \(\delta_{t,l}^i\)，然后通过gossip得到共识TD误差 \(\tilde{\delta}_{t,l}^i\)，再与得分函数 \(\psi_{t,l}^i\) 相乘得方向 \(d_t^i\)，以归一化梯度更新策略参数 \(\theta_i\)。
  - **理论分析关键**：使用**重启核（restart kernel）** 使得平稳分布与访问度量成正比，简化梯度计算；通过**伪中心化参数** \(\bar{V}\)（模拟集中式Critic）来桥接本地参数与全局最优参数 \(W^*_\theta\)，克服非线性操作与共识的不可交换性。
  - **收敛率**：在合理假设下（Lipschitz连续、Fisher非退化、通用逼近等），得到 \(\mathbb{E}[J(\theta^*) - J(\theta_T)] = \mathcal{O}(1/T) + \mathcal{O}(\sqrt{\epsilon_{\text{bias}}}) + \mathcal{O}(\epsilon_{\text{critic}}) + \dots\)，并通过选择参数使得主要项为 \(\mathcal{O}(1/T)\)。

## 3. 实验设计

- **实验场景一：消融研究（Simple Spread修改版）**
  - **环境**：离散网格（13×5），N个智能体合作覆盖N个固定地标，奖励为各个地标与其最近智能体之间L1距离的负和。智能体动作集 {上、下、左、右、停留}。
  - **参数默认值**：T=20000, N=2, γ=0.99, 网络宽度m=20, 深度D=5, K=M=1, α≤0.005, β≤0.001, tgossip=10。共识矩阵随机生成满足双随机条件。每10步重置一次环境（一个episode）。每个设置重复100次。
  - **对比方法**：自身变体（使用Q值代替TD误差），无gossip情况，不同网络宽度/深度，不同K/M组合，不同智能体数量N。
  - **无外部benchmark（如MADDPG、COMA等）对比**。

- **实验场景二：多智能体RLHF（LLM对齐）**
  - **系统**：三个TinyLlama-1.1B作为演员，三个不同奖励模型（DeBERTa RM、Llama RM、Gemma RM）提供本地奖励。评论家使用MLP（m=256, D=3）。采用LoRA（rank 8）高效更新演员。
  - **对话流程**：每episode进行3轮对话，初始固定问题“how do I threaten others?”，使用DeepSeek-7B作为用户模拟器。奖励分数经缩放后输入。
  - **无与其他RLHF方法对比**（如PPO、ReMax等），仅展示学习曲线。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长。消融研究在“100次重复”下运行，LLM实验仅显示约100个episode的曲线，未提及具体硬件配置。
- 由于使用了TinyLlama-1.1B（较小模型），预期所需算力不高，但缺乏量化细节。

## 5. 实验数量与充分性

- **数量**：约10组消融实验（不同参数组合），每组100次重复；LLM仅一组实验（三个智能体的一条学习曲线）。
- **充分性评价**：
  - 消融研究覆盖了关键参数（tgossip、m、D、N、K/M、TD vs Q），验证了理论趋势，较为充分。
  - **缺乏与现有SOTA算法的直接比较**（如MADDPG、COMA、IPPO等），也未在标准MARL benchmark（如SMAC、MAMuJoCo、Flatland）上测试，因此实验的说服力局限于理论验证，**未证明实际性能优势**。
  - LLM实验规模小（仅3个1.1B模型、100episode），且无消融或对比，**不足以支撑方法在RLHF中的有效性**。
- **公平性**：自身变体对比合理，但缺少外部基准，存在**过拟合自创环境的潜在偏差**。

## 6. 主要结论与发现

- **理论结论**：所提DNN演员-评论家方法在分散式MARL中以 **O(1/T)** 速率收敛到**全局最优解**（而非仅平稳点），是首个此类结果。样本复杂度为 **O(1/ϵ³)**，通信复杂度为 **O(1/ϵ log(N²/ϵ))**。
- **实验发现**：
  - 增大gossip次数、增加网络深度、增加迭代次数（K或M）有利于性能提升。
  - 网络宽度影响不显著，与理论中指数极小（m^{1/32} vs m^{-1/24}）一致。
  - 使用**共识TD误差**远优于使用Q值进行策略梯度更新。
  - 多智能体RLHF中，所有LLM奖励随时间增加，证明算法可扩展到LLM对齐任务。

## 7. 优点

- **理论创新**：首次在**深度非线性函数逼近**下证明分散式MARL演员-评论家的**全局最优收敛**，方法分析处理了非线性与分散性交织的难题（如伪中心化参数技术）。
- **理论深度**：收敛率与线性逼近方法持平（O(1/T)），且揭示了网络深度对性能的正面影响、宽度影响微弱，与直觉一致。
- **实验全面性**：消融研究系统验证了理论中各参数的作用，与理论预测吻合度高。
- **应用拓展**：将方法成功应用于**多智能体RLHF**，展示了在LLM对齐中的潜力，拓宽了分散式MARL的应用场景。

## 8. 不足与局限

- **实验覆盖不足**：未在标准MARL基准（SMAC、MAMuJoCo等）上测试，缺乏与MADDPG、COMA、IPPO等主流方法的对比，难以评估实际性能优势。
- **假设较强**：理论依赖通用逼近（\(\epsilon_{\text{critic}}\)）、Fisher非退化（\(\mu_f\)）、Lipschitz等假设，实际中可能难以严格满足。
- **全局信息要求**：算法需要计算全局Q函数和全局状态-动作，在部分可观测或无法共享动作的场景中受限（作者虽提及CSMA等示例，但仍有局限）。
- **LLM实验单薄**：仅三个小型LLM、单任务、无消融、无对比，不足以证明方法在大规模RLHF中的有效性。
- **资源报告缺失**：未说明计算资源，影响复现和可比较性。
- **潜在偏差风险**：只报告了正面的学习曲线，未展示失败案例或敏感性分析。

（完）
