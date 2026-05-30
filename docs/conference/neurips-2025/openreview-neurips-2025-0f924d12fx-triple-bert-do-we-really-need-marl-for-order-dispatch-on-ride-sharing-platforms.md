---
title: "Triple-BERT: Do We Really Need MARL for Order Dispatch on Ride-Sharing Platforms?"
title_zh: Triple-BERT：共享出行平台订单调度真的需要多智能体强化学习吗？
authors: "Zijian Zhao, Sen Li"
date: 2025-05-08
pdf: "https://openreview.net/pdf?id=0F924d12FX"
tags: ["query:marl"]
score: 6.0
evidence: 讨论集中式训练分布式执行（CTDE）的多智能体强化学习在共享出行调度中的应用
tldr: 该论文探讨共享出行平台的订单调度问题，指出尽管MARL常用于该任务，但独立MARL和CTDE方法均有不足。为此提出Triple-BERT模型，该模型不依赖于MARL框架却能更好地捕获全局信息并避免维度灾难。实验表明Triple-BERT在效率上优于现有CTDE-MARL方法，引发对MARL必要性的思考。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 740, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 962, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1306, \"height\": 1084, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1308, \"height\": 2190, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0f924d12fx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1307, \"height\": 1416, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0f924d12fx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0f924d12fx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 994, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0f924d12fx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 342, \"label\": \"Table\"}]"
motivation: 现有MARL方法在共享出行调度中面临独立方法缺乏全局信息、CTDE方法维度灾难的问题。
method: 提出Triple-BERT模型，通过三流BERT结构处理订单、司机和上下文信息，避免传统MARL的复杂性。
result: Triple-BERT在真实数据集上优于CTDE-MARL基线，同时计算效率更高。
conclusion: 对于某些集中式任务，精心设计的非MARL模型可能比传统MARL方法更有效。
---

## Abstract
On-demand ride-sharing platforms, such as Uber and Lyft, face the intricate real-time challenge of bundling and matching passengers—each with distinct origins and destinations—to available vehicles, all while navigating significant system uncertainties. Due to the extensive observation space arising from the large number of drivers and orders, order dispatching, though fundamentally a centralized task, is often addressed using Multi-Agent Reinforcement Learning (MARL). However, independent MARL methods fail to capture global information and exhibit poor cooperation among workers, while Centralized Training Decentralized Execution (CTDE) MARL methods suffer from the curse of dimensionality. To overcome these challenges, we propose Triple-BERT, a centralized method designed specifically for large-scale order dispatching on ride-sharing platforms. Built on TD3, our approach addresses the vast action space through an action decomposition strategy that breaks down the joint action probability into individual driver action probabilities. To handle the extensive observation space, we introduce a novel BERT-based network, where parameter reuse mitigates parameter growth as the number of drivers and orders increases, and the attention mechanism effectively captures the complex relationships among the large pool of driver and orders. We validate our method  using a real-world ride-hailing dataset from Manhattan. Triple-BERT achieves approximately an 11.95\% improvement over current state-of-the-art methods, with a 4.26\% increase in served orders and a 22.25\% reduction in pickup times. Our code, trained model parameters, and processed data are publicly available at the anonymous repository https://anonymous.4open.science/r/Triple-BERT .

---

## 论文详细总结（自动生成）

# 1. 论文的核心问题与整体含义（研究动机和背景）

- 论文聚焦于共享出行平台（如 Uber、Lyft）的**实时订单调度**问题，即动态地将具有不同起终点的乘客与可用车辆进行匹配，同时应对需求波动、交通状况、司机可用性等系统不确定性。
- 核心挑战在于**大规模观测空间**（大量司机和订单）和**大规模动作空间**（组合爆炸：n=1000 司机、m=10 订单时动作空间可达约 10^30），使得传统强化学习方法难以应用。
- 现有方法多采用多智能体强化学习（MARL）：**独立 MARL**（如 IDDQN）计算高效但缺乏全局信息，合作性差；**集中式训练分布式执行（CTDE）** 方法（如 QMIX）面临维度灾难，收敛慢且次优。
- 论文提出**集中式单智能体强化学习（SARL）** 框架 Triple-BERT，旨在充分利用全局信息、避免 MARL 的弊端，同时处理大规模动作与观测空间。

# 2. 论文提出的方法论

## 核心思想
- 将订单调度视为**集中式决策问题**，利用 BERT 的自注意力机制捕获司机与订单间的复杂关系，通过参数复用避免参数爆炸。
- 采用 **TD3** 作为强化学习基础算法，并针对离散动作和大动作空间进行改造。

## 关键技术细节
1. **动作分解**：
   - 将联合动作概率分解为每个司机选择每个订单的独立概率，通过 Logit 模型计算概率矩阵 \(P_t\)。
   - 使用改进的 QK-Attention（正归一化）计算司机-订单对的效用，降低计算复杂度（从乘法变为加法）。
   - 推理时通过整数线性规划（ILP）最大化联合概率的对数和，选择全局最优匹配；训练时引入噪声以实现探索。

2. **网络架构（图 2）**：
   - **编码器**：司机状态（含非序列信息和车载订单序列，后者用双向 LSTM 提取）+ 订单状态（MLP），输出统一维度特征。
   - **Actor 子网络**：一个 BERT（无位置编码）处理所有司机和订单的嵌入序列，输出特征后经 QK-Attention 得到效用矩阵。
   - **Critic 子网络**：两个独立的 BERT + MLP，输入 Actor BERT 的输出与动作组合，输出两个 Q 值（遵循 TD3 双 critic 设计）。

3. **两阶段训练策略**：
   - **阶段一（预训练）**：使用 IDDQN 训练编码器，让特征提取器学习通用表征。此时将问题视为独立多智能体，记录每个司机的经验，利用大规模样本（多个司机共享经验）避免样本稀缺。
   - **阶段二（集中式微调）**：固定编码器，使用改进的 TD3 训练整个网络，并采用策略梯度形式更新 actor（公式 7），利用 ILP 选择动作。

4. **正归一化 QK-Attention**（公式 3）：对订单侧输出做 Softplus 后 L2 归一化，消除参数冗余（\(f\) 和 \(g\) 的尺度歧义），保证解唯一。

# 3. 实验设计

- **数据集**：纽约曼哈顿黄色出租车真实行程数据（NYC TLC Trip Record Data）。训练时段为 2024 年 7 月 17 日 19:00-19:30（3726 个有效订单），测试时段包括 14:00-14:30、17:00-17:30、20:00-20:30、21:00-21:30、22:00-22:30（订单数 2850～4910）。
- **场景**：模拟 1000 名司机，每辆车容量 3，每 episode 时长 30 分钟（30 个时间步）。使用 OSRM 模拟器计算 TSP 路径和时间。
- **对比基准**（表 1）：
  - 独立 MARL：DeepPool（IDDQN）、BMG-Q（IDDQN + GAT）
  - CTDE：HIVES（QMIX）、Enders et al.（MASAC）
  - 集中式 MARL：CEVD（VD 变体）
  - 额外基线：贪心方法（就近分配）
- **度量指标**：累积奖励、服务率（Served Orders）、交付时间、绕路时间、接单时间（Pickup Time）、确认时间。

# 4. 资源与算力

- **训练硬件**：单台 Windows 11 工作站，Intel i7-14700KF CPU，NVIDIA RTX 4080 GPU（显存 16 GB）。
- **GPU 占用**：Triple-BERT 占用约 8.03 GB（表 1）。
- **训练时长**：论文未明确给出具体训练时间，但提到 1000 episodes 需要约一整天（Appendix F.1），暗示数据稀缺问题。
- **模型大小**：16M 参数（与 HIVES 相当，但大于其他方法）。

# 5. 实验数量与充分性

- **主要实验**：在训练集上每 10 episodes 评估一次，绘制训练曲线（图 3）；在 5 个不同时段测试集上重复 3 次，取平均值与标准差（图 6、表 3）。
- **消融实验**：
  - 移除阶段一预训练（w/o stage 1）
  - 移除 QK-Attention 正归一化（w/o normalization）
  - 比较三种噪声类型（高斯、均匀、BSC，图 4）
- **充分性评估**：
  - 实验覆盖了多种对比方法（5 个基线）、多个时段（5 个）、多次重复（3 次），统计上较为充分。
  - 消融实验验证了核心组件（预训练、归一化）的必要性，噪声对比验证了方法的鲁棒性。
  - 测试集时段多样（不同订单量），有助于评估泛化能力。
  - **公平性**：所有对比方法在同一模拟器和同一数据集上测试，超参数公开，代码和模型权重已开放，可复现。但论文未报告方法间的超参数调优细节（如各基线是否达到其原文最佳配置），存在一定偏向风险。

# 6. 论文的主要结论与发现

1. Triple-BERT 在累积奖励上相比最优基线（CEVD）提升约 11.95%，服务率提升 4.26%，接单时间降低 22.25%。
2. 集中式 SARL 方法在共享出行调度中完全可行且优于现有 MARL 方法，表明**精心设计的集中式方法可以避免 MARL 的复杂性**。
3. 两阶段训练策略（先 MARL 预训练再集中式微调）有效缓解了集中式训练中样本稀缺问题。
4. 正归一化 QK-Attention 对模型收敛至关重要，缺乏它会导致性能大幅下降（低至 Greedy 水平）。
5. 该方法在高订单量场景下优势更明显（合作收益更大）。

# 7. 优点

- **创新性**：首次将集中式 SARL 成功应用于大规模订单调度，挑战了 MARL 在此类任务中的必要性。
- **网络设计高效**：BERT 自注意力捕获全局关系，参数复用避免维度爆炸，QK-Attention 降复杂度，均实用且优雅。
- **工程细节扎实**：两阶段训练解决样本不足；正归一化消除参数冗余；ILP 保证全局最优匹配。
- **实验充分开放**：代码、模型、数据均开源，可复现；消融实验覆盖主要设计选择；多种噪声测试鲁棒性。

# 8. 不足与局限

- **理论近似**：策略梯度公式（式 7）假设 \(z(x)\) 弹性为常数，实际未必成立，可能造成次优解（论文自身承认）。
- **实验场景受限**：仅测试了曼哈顿 30 分钟窗口的出租车数据，未涉及更长时段（如全日）、更多城市、或不同服务平台（如外卖、快递），泛化性存疑。
- **算力/时间未详细报告**：未给出完整训练时间，样本稀缺问题限制了实验规模（1000 episodes 已需一天）。
- **MARL 基线可能未达到最优**：对比方法中的超参数可能未经充分调优（尤其 HIVES、CEVD 等需集中训练的方法在数据量上可能吃亏），存在不公平比较风险。
- **未讨论在线部署**：论文未提及实际部署时的延迟、扩展性、实时性限制。
- **伦理关注**：论文仅简短提及公平性问题（Appendix F.2），未设计具体约束或实验验证算法是否导致歧视。

（完）
