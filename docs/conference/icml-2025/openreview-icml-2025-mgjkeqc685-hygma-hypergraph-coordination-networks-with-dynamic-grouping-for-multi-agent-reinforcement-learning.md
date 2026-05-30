---
title: "HYGMA: Hypergraph Coordination Networks with Dynamic Grouping for Multi-Agent Reinforcement Learning"
title_zh: HYGMA：基于超图协调网络与动态分组的合作多智能体强化学习
authors: "Chiqiang Liu, Dazi Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=mgJkeqc685"
tags: ["query:marl"]
score: 9.0
evidence: 基于超图协调的动态分组合作多智能体强化学习
tldr: 合作多智能体强化学习中智能体关系组织与信息交换困难，本文提出HYGMA框架，通过动态谱聚类构建超图结构，并借助注意力机制增强智能体间高阶关系建模。该方法允许智能体自适应分组，提升大规模合作任务中的协调效率，实验显示其在多个基准上显著优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mgjkeqc685/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mgjkeqc685/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1763, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mgjkeqc685/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mgjkeqc685/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mgjkeqc685/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 847, \"height\": 428, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 1497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 817, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 978, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 911, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 902, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1207, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mgjkeqc685/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 963, \"height\": 199, \"label\": \"Table\"}]"
motivation: 现有方法难以动态组织智能体关系，缺乏高效信息交换。
method: 动态谱聚类构建超图结构，结合注意力机制实现自适应分组与高阶关系建模。
result: 在多个合作任务上超越现有方法，提升了协调效率和可扩展性。
conclusion: 为动态协调的多智能体系统提供了有效框架。
---

## Abstract
Cooperative multi-agent reinforcement learning faces significant challenges in effectively organizing agent relationships and facilitating information exchange, particularly when agents need to adapt their coordination patterns dynamically. This paper presents a novel framework that integrates dynamic spectral clustering with hypergraph neural networks to enable adaptive group formation and efficient information processing in multi-agent systems. The proposed framework dynamically constructs and updates hypergraph structures through spectral clustering on agents' state histories, enabling higher-order relationships to emerge naturally from agent interactions. The hypergraph structure is enhanced with attention mechanisms for selective information processing, providing an expressive and efficient way to model complex agent relationships. This architecture can be implemented in both value-based and policy-based paradigms through a unified objective combining task performance with structural regularization. Extensive experiments on challenging cooperative tasks demonstrate that our method significantly outperforms state-of-the-art approaches in both sample efficiency and final performance. The code is available at: https://github.com/mysteryelder/HYGMA.

---

## 论文详细总结（自动生成）

# 论文总结：HYGMA——基于超图协调网络与动态分组的合作多智能体强化学习

## 1. 核心问题与整体含义（研究动机和背景）
合作多智能体强化学习（MARL）面临两大挑战：如何有效组织智能体之间的动态关系，以及如何在智能体之间高效交换信息。现有方法（如值分解方法VDN、QMIX、QTRAN等）通常假设固定的智能体关系结构（如求和/取最大操作），无法捕捉动态协调模式；图神经网络方法虽能建模成对交互，但局限于二元连接，无法自然表达多智能体间的高阶群体协作。针对这一不足，本文提出**HYGMA**框架，通过**动态谱聚类**自适应发现智能体协调分组，并利用**超图神经网络**（Hypergraph Neural Networks）直接建模高阶关系，从而提升协调效率与样本效率。

## 2. 方法论：核心思想、关键技术细节与算法流程
### 核心思想
- 将多智能体协调问题建模为基于超图的动态分组与信息处理过程。
- 采用**两阶段架构**：第一阶段通过谱聚类对智能体状态历史进行动态分组，第二阶段利用注意力增强的超图卷积网络（HGCN）在组内进行特征传播。

### 关键技术细节
- **动态谱聚类分组**：
  - 输入：智能体状态历史矩阵 \(H_t \in \mathbb{R}^{b \times l \times d}\)。
  - 构建相似矩阵 \(W\)（基于k近邻的欧氏距离），求解归一化割（Normalized Cut）的谱松弛问题，选择k个最小特征值对应的特征向量进行聚类。
  - 最优分组数 \(k^*\) 通过轮廓系数（Silhouette Score）自动确定。
  - 分组更新采用稳定性阈值 \(\delta\)：仅当分组变化比例 \(\eta > \delta\) 时才更新，保证收敛性（定理3.2证明有限时间收敛）。
- **超图注意力卷积网络**：
  - 每个组对应一个超边，组内所有智能体节点由该超边连接，超边权重由组内凝聚度（轮廓系数）决定。
  - 节点特征更新公式：\[
    h_i^{(l+1)} = \sigma\left( \sum_{e \in \mathcal{E}_i} \alpha_{ie} \cdot D^{-1/2} H W B^{-1} H^T D^{-1/2} h_i^{(l)} P^{(l)} \right)
    \]
    其中 \(\alpha_{ie}\) 为注意力系数，通过LeakyReLU计算。
  - 注意力机制使智能体能自适应加权不同超边信息，生成个性化表示。
- **统一学习目标**：\[
    \mathcal{L}_{\text{total}} = \mathcal{L}_{\text{task}} + \lambda_1 \mathcal{L}_{\text{group}} + \lambda_2 \mathcal{L}_{\text{att}}
    \]
  - \(\mathcal{L}_{\text{group}}\)：最小化组内距离、最大化组间距离。
  - \(\mathcal{L}_{\text{att}}\)：熵正则化，鼓励注意力选择性。
- **算法流程**（Algorithm 1）：
  1. 初始化经验回放池、超图结构。
  2. 每回合每步：若分组变化超过阈值则更新分组和超图；计算注意力系数和节点特征；智能体根据实现类型（值函数/策略）选择动作；执行动作，存储转移。
  3. 采样小批量，计算总损失，更新网络参数。
- **两种实现**：
  - 值函数实现（基于QMIX）：增强后的Q值 \(Q_i(\tau_i, a_i, h_i)\) 输入单调混合网络得到 \(Q_{\text{tot}}\)。
  - 策略实现（Actor-Critic）：策略网络和评论家网络均使用组感知特征。

## 3. 实验设计
### 使用的数据集/场景
- **基于值函数的实验**：StarCraft II Multi-Agent Challenge（SMAC）中的三个地图：
  - `3s_vs_5z`（Hard，不对称战斗）
  - `5m_vs_6m`（Hard，需精确战术协调）
  - `3s5z_vs_3s6z`（Super Hard，异构单位）
- **基于策略的实验**：
  - Predator-Prey（捕食者-猎物）：两种规模（10×10网格5智能体、20×20网格10智能体）。
  - Traffic Junction（交通路口）：两种复杂性（7×7网格5车、14×14网格10车）。
  - Google Research Football（GRF）：3个攻击智能体对内置AI防守。

### Benchmark 对比方法
- SMAC：Ft-QMIX、QPLEX、VAST、MAPPO、GoMARL、RIIT。
- Predator-Prey/Traffic Junction/GRF：MAGIC、CommNet、GA-Comm、I3CNet、TarMAC-IC3Net。

## 4. 资源与算力
论文中**未明确说明**具体使用的GPU型号、数量或训练时长。仅提到HYGMA约有36%的训练时间开销（相比于基线），但该开销通过更快的收敛得到补偿。附录C给出了HGCN参数量和计算开销百分比，但无硬件细节。

## 5. 实验数量与充分性
### 实验数量
- **SMAC**：3个地图，每个地图至少一种随机种子（论文中未明确种子数，但从图中错误条推测可能有多种子）。
- **Predator-Prey**：2个规模实验。
- **Traffic Junction**：2个场景实验。
- **GRF**：1个场景实验。
- **消融实验**：在5m_vs_6m上比较全方法、使用GCN替代HGCN、使用全体为一组，共3种变体。
- **分组分析**：在5m_vs_6m上展示组共现矩阵和演化时间线。

### 充分性与客观性
- 实验覆盖了多种合作任务类型（对称/不对称、同质/异构、稀疏奖励、随机性），基线全面（包含近期SOTA如GoMARL、MAGIC）。
- 每个结果均给出均值和标准差（或置信区间），并使用多次运行（如GRF中HYGMA有±0.7%的波动），统计严谨。
- 消融实验验证了超图结构和动态分组的必要性。
- 但也存在改进空间：未在更多环境（如物流、机器人编队）上测试；未与更多最新方法（如基于Transformer的方法）对比；GRF场景仅有一个配置，缺乏多样性。

## 6. 主要结论与发现
- HYGMA在SMAC所有三个地图上均达到最高或接近最高的胜率，且在困难异构场景（3s5z_vs_3s6z）中显著优于所有基线。
- 在Predator-Prey和Traffic Junction中，HYGMA的收敛速度更快（样本效率更高），且在大规模场景下优势更明显。
- 在GRF中，HYGMA的成功率与MAGIC相当（97.7% vs 98.2%），但步数更少（30.26 vs 34.30），说明策略更高效。
- 分组分析揭示了可解释的协调模式（核心战术单元、灵活支援单元、独立单元）。
- 消融实验证明性能提升主要来自超图结构，而非单纯信息增加；动态分组优于固定全体一组。
- 理论证明：谱聚类近似归一化割的最优解（\(O(\log k)\)近似比），分组更新收敛，且分组质量对值函数的影响有界（\(|\gamma\alpha\log k|\)）。

## 7. 优点
- **方法创新性**：首次将动态谱聚类与超图神经网络结合，自动发现高阶协调结构，无需预定义组数或角色。
- **理论扎实**：提供了聚类近似、收敛性、通信复杂度、值函数质量保证等多条定理，增强了可信度。
- **通用性**：同时支持值函数和策略梯度两种范式，适用面广。
- **效率设计**：分组更新仅在变化足够大时触发，降低计算开销；超图结构将通信复杂度从\(O(n^2)\)降至\(O(n^2/k)\)。
- **实验充分**：在多个公认复杂的基准上验证，与多种类型SOTA方法对比，结果全面；附带消融和分组可视化，洞察机制。
- **可复现**：提供GitHub代码链接。

## 8. 不足与局限
- **计算资源信息缺失**：未报告GPU型号、数量、训练时长，影响复现和效率比较。
- **实验环境有限**：SMAC仅3个地图且均为StarCraft领域；未在更广泛的MARL基准（如粒子世界、RODE、MAMuJoCo等）上测试，泛化性待验证。
- **超参数敏感性**：稳定性阈值δ、正则化系数λ₁、λ₂等需要手动调整，在不同任务上可能需重新调优。
- **扩展性分析不足**：虽理论上通信复杂度降低，但未给出实际大智能体数量（>20）的实验结果，分组数量上限和HGCN层数对性能的影响未深入探讨。
- **对比方法时效性**：2025年论文，比较的基线多为2023年及之前，最新方法（如基于Transformer或扩散模型的方法）未包含。
- **潜在偏差**：在Predator-Prey和Traffic Junction中，MAGIC的成功率有时更高（如99.9% vs 99.2%），HYGMA主要优势体现在收敛速度，需注意“样本效率”与“最终性能”的权衡。

（完）
