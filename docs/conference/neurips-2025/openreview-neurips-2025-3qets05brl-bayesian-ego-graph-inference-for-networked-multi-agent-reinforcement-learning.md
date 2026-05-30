---
title: Bayesian Ego-graph Inference for Networked Multi-Agent Reinforcement Learning
title_zh: 网络化多智能体强化学习的贝叶斯自我图推断
authors: "Wei Duan, Jie Lu, Junyu Xuan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3qeTs05bRL"
tags: ["query:marl"]
score: 9.0
evidence: 去中心化多智能体强化学习与图推理
tldr: 针对网络化多智能体强化学习中智能体需在局部可观测和受限通信下自主决策的问题，提出贝叶斯自我图推断方法。每个智能体基于局部邻居采样子图进行决策，采用去中心化Actor-Critic框架。实验证明在动态环境中优于静态邻域方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1425, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1424, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1359, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1441, \"height\": 804, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1406, \"height\": 1662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3qets05brl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1455, \"height\": 2043, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3qets05brl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1044, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3qets05brl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 1095, \"label\": \"Table\"}]"
motivation: 现有网络化MARL方法假设静态邻域，无法适应动态环境，而集中式框架依赖全局状态不实用。
method: 提出随机图策略，每个智能体基于局部物理邻域采样子图，配合贝叶斯去中心化Actor-Critic。
result: 在多种网络化MARL基准上，提高了适应性和性能。
conclusion: 动态图建模增强了去中心化多智能体系统的鲁棒性。
---

## Abstract
In networked multi-agent reinforcement learning (Networked-MARL), decentralized agents must act autonomously under local observability and constrained communication over fixed physical graphs. Existing methods often assume static neighborhoods, limiting adaptability to dynamic or heterogeneous environments. While centralized frameworks can learn dynamic graphs, their reliance on global state access and centralized infrastructure is impractical in real-world decentralized systems. We propose a stochastic graph-based policy for Networked-MARL, where each agent conditions its decision on a sampled subgraph over its local physical neighborhood. Building on this formulation, we introduce \textbf{BayesG}, a decentralized actor–critic framework that learns sparse, context-aware interaction structures via Bayesian variational inference. Each agent operates over an ego-graph and samples a latent communication mask to guide message passing and policy computation. The variational distribution is trained end-to-end alongside the policy using an evidence lower bound (ELBO) objective, enabling agents to jointly learn both interaction topology and decision-making strategies.
BayesG outperforms strong MARL baselines on large-scale traffic control tasks with up to 167 agents, demonstrating superior scalability, efficiency, and performance.

---

## 论文详细总结（自动生成）

## 论文中文结构化总结

### 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：网络化多智能体强化学习 (Networked-MARL) 中，智能体在固定物理通信图上局部可观测、受限通信条件下自主决策。
- **核心问题**：现有方法大多假设静态邻域结构（固定邻居），无法适应动态或异构环境；而集中式方法虽能学习动态图，但依赖全局状态和集中基础设施，在真实去中心化系统中不实用。
- **整体含义**：提出一种去中心化的贝叶斯自我图推断框架，使每个智能体能够基于局部观测自适应地选择任务相关的交互结构，实现在拓扑约束下的高效、稳定协调。

### 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：每个智能体维护一个局部自我图（ego-graph），通过贝叶斯变分推断学习一个**二元通信掩码**，从物理邻域中采样稀疏的子图，并在此子图上执行图条件策略。
- **关键技术细节**：
  - **随机图策略**：策略定义为先采样子图（从分布 ρ(·) 中采样），再基于图编码后的观测选择动作，即 π(ui, G_{Vi}|s_{Vi}) = ρ(G_{Vi}|s_{Vi}) · π̃(ui|f̃(s_{Vi}, G_{Vi}))。
  - **贝叶斯变分推断**：将掩码 Zi 视为潜在变量，用变异分布 q(Zi; φi) 近似后验 p(Zi|G_env, Di)，通过最小化 KL 散度等价于最大化证据下界 (ELBO)。
  - **ELBO目标**： L_ELBO = E_q[−L_{θ,φ} + log p(Zi) − log q(Zi)]，其中 L_{θ,φ} 是图条件策略损失， log p(Zi) 为伯努利先验， log q(Zi) 为掩码熵。
  - **重参数化**：使用 Gumbel-Softmax 实现离散掩码的梯度传播。
  - **联合优化**：结合策略学习与图结构学习，总损失为各智能体 ELBO 与标准 A2C 评论家损失之和。
  - **算法流程**（见附录 D 算法 1 和 2）: 每个时间步，智能体采样掩码，构建有效邻接矩阵，通过 GCN 进行条件编码，更新策略和评论家，收集轨迹批次后联合更新策略、评论家和变分参数。

### 3. 实验设计：数据集/场景、Benchmark、对比方法

- **场景**：五个自适应交通信号控制 (ATSC) 基准，基于 SUMO 微观交通模拟器。
  - **中等规模**：ATSC_Grid (5×5 网格，25个智能体)、Monaco (真实28个交叉口)。
  - **大规模**：NewYork33 (33个信号灯)、NewYork51 (51个)、NewYork167 (167个)，源自曼哈顿真实路网。
- **Benchmark**：负的停止车辆数（归一化）作为奖励。
- **对比方法**：六种多智能体演员-评论家基线，基于统一 A2C 骨干：
  - **非通信型**：IA2C、ConseNet、FPrint、LToS。
  - **通信型**：CommNet、NeurComm。
- **实现统一**：所有方法均使用相同架构（MLP/GCN 编码器、LSTM 时序处理）和训练设置。

### 4. 资源与算力

- 论文未明确说明使用的 GPU 型号、数量及具体训练时长。
- 仅提及“每个实验平均5个随机种子”，但未提供计算资源细节。

### 5. 实验数量与充分性

- **覆盖范围**：5个 ATSC 场景 × 6个基线 + 1个所提方法 = 约35组主要对比实验。
- **消融实验**：2组（掩码策略对比、输入特征对比），在 Monaco 和 NewYork51 上进行。
- **案例研究**：在 ATSC_Grid 上展示动态图适应性和可解释性（图4、图11）。
- **充分性**：实验覆盖中等和大型网络，使用5个随机种子并报告均值±标准差；训练曲线和损失分解均有跟踪。对比方法均为强基线且实现公平。消融研究验证了各组件的贡献。整体实验设计客观、充分。

### 6. 主要结论与发现

- BayesG 在所有场景下优于所有基线，尤其在大型网络（NewYork167）上，收敛更快、最终收益更高。
- 学习到的通信掩码具有可解释性：能够动态关注拥堵区域的上游交叉口，实现方向性、任务驱动的协作。
- 消融表明：学习到的掩码远优于随机掩码或无掩码；结合状态、轨迹、策略三种特征的掩码性能最佳。
- 训练损失分析显示，方法在策略优化与图结构探索之间达到平衡，收敛稳定。

### 7. 优点

- **去中心化**：每个智能体仅依赖局部观测，无需全局状态或集中训练。
- **自适应图学习**：通过贝叶斯变分推断，智能体可端到端学习上下文相关的稀疏交互结构，适应动态环境。
- **不确定性建模**：掩码作为潜在变量，自然刻画了交互的不确定性，避免过早确定性的图剪枝。
- **可扩展性**：在多达167个智能体的真实交通网络中仍保持高性能。
- **可解释性**：学习到的掩码可直观显示通信优先级，与实际交通常识一致。

### 8. 不足与局限

- **固定物理拓扑**：方法假设环境图静态且给定，不适用于拓扑变化的任务（如移动机器人编队）。
- **局部观测限制**：智能体仅基于自我图推理，难以捕获需要长程全局上下文的依赖。
- **超参数敏感**：Gumbel-Softmax 温度、稀疏先验 λ 等需仔细调节，否则可能导致过度剪枝或协作不足。
- **计算开销**：与无通信方法相比，由于变分采样和 GNN 计算，训练成本略有增加（但实际仍高效）。
- **实验覆盖**：仅在交通信号控制领域验证，未在更通用的 MARL 基准（如 SMAC、MPE）上测试；论文解释为问题设定不兼容（需物理约束图），但这限制了方法的通用性证明。
- **公平性**：未讨论在非理想通信条件（丢包、时延）下的鲁棒性。

（完）
