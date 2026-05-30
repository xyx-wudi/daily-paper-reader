---
title: "Oryx: a Scalable Sequence Model for Many-Agent Coordination in Offline MARL"
title_zh: Oryx：面向大规模多智能体离线协调的可扩展序列模型
authors: "Juan Claude Formanek, Omayma Mahjoub, Louay Ben Nessir, Sasha Abramowitz, Ruan John de Kock, Wiem Khlifi, Daniel Rajaonarivonivelomanantsoa, Simon Verster Du Toit, Arnol Manuel Fokam, Siddarth Singh, Ulrich Armel Mbou Sob, Felix Chalumeau, Arnu Pretorius"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=XzXGqoUNUa"
tags: ["query:marl"]
score: 9.0
evidence: 离线合作多智能体强化学习与序列模型
tldr: 针对离线多智能体强化学习中的多智能体多步协调难题，提出Oryx算法。将保留架构Sable与隐式约束Q学习结合，设计离线自回归策略更新方案。在SMAC、RWARE和Multi-Agent MuJoCo等基准上验证，有效处理复杂协调任务并保持时间一致性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1364, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 265, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1182, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 1357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1326, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 425, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1302, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1360, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 732, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xzxgqounua/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 732, \"height\": 459, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 741, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1170, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 656, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 636, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1167, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 865, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 642, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 709, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1317, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1026, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 707, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1452, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1451, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 702, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 795, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 700, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 703, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 719, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xzxgqounua/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 741, \"height\": 419, \"label\": \"Table\"}]"
motivation: 离线MARL中实现多智能体多步协调面临挑战。
method: 采用基于保留架构的序列模型结合隐式约束Q学习，实现离线自回归策略更新。
result: 在多种离散和连续控制基准上，协调性能显著优于已有离线MARL方法。
conclusion: 序列建模为离线MARL协调提供了有效方案。
---

## Abstract
A key challenge in offline multi-agent reinforcement learning (MARL) is achieving effective many-agent multi-step coordination in complex environments. In this work, we propose Oryx, a novel algorithm for offline cooperative MARL to directly address this challenge. Oryx adapts the recently proposed retention-based architecture Sable and combines it with a sequential form of implicit constraint Q-learning (ICQ), to develop a novel offline autoregressive policy update scheme. This allows Oryx to solve complex coordination challenges while maintaining temporal coherence over long trajectories. We evaluate Oryx across a diverse set of benchmarks from prior works—SMAC, RWARE, and Multi-Agent MuJoCo—covering tasks of both discrete and continuous control, varying in scale and difficulty. Oryx achieves state-of-the-art performance on more than 80% of the 65 tested datasets, outperforming prior offline MARL methods and demonstrating robust generalisation across domains with many agents and long horizons. Finally, we introduce new datasets to push the limits of many-agent coordination in offline MARL, and demonstrate Oryx's superior ability to scale effectively in such settings.

---

## 论文详细总结（自动生成）

# 论文总结：Oryx: a Scalable Sequence Model for Many-Agent Coordination in Offline MARL

## 1. 核心问题与整体含义（研究动机和背景）

离线多智能体强化学习（Offline MARL）的目标是从预先收集的静态数据集中训练多智能体策略，而无需与环境交互。这在安全关键或成本高昂的真实场景（如自动物流、交通管理）中具有重要意义。然而，离线MARL面临两个主要挑战：（1）**外推误差**：智能体可能选择超出数据集分布的动作，且随着智能体数量增加，联合动作空间呈指数增长，误差累积加剧；（2）**协调失败**：智能体无法与环境主动交互，只能依赖数据集中的历史行为（往往来自次优策略），导致策略不兼容。现有方法多在小规模智能体场景下验证，难以扩展到大量智能体且需要长期时间依赖的任务。

**整体含义**：本文旨在同时解决外推误差和协调失败两大挑战，提出一种可扩展的序列模型Oryx，使离线MARL能够在复杂、多智能体、长周期场景中实现有效协调，从而推动离线MARL向真实大规模部署前进。

## 2. 方法论

### 核心思想
Oryx将**保留机制序列模型Sable**与**隐式约束Q学习（ICQ）**相结合，设计了一种**离线自回归策略更新方案**。通过顺序更新各智能体策略，并基于反事实优势估计进行约束优化，同时缓解外推误差和协调失败。

### 关键技术细节
- **网络架构**：基于Sable的保留区块（Retention Blocks）进行高效序列建模。采用双解码器结构，同时输出策略分布和Q值。编码器处理观测序列，解码器输出每个智能体的动作对数概率和Q值估计。
- **自回归ICQ损失**：利用多智能体优势分解定理（Kuba et al., 2021），将联合策略优化分解为顺序更新。每个智能体i_j的更新目标为：
  \[
  \pi_{i_j}^* = \arg\max_{\pi_{i_j}} \mathbb{E}_{\tau, a_{i_1:j} \sim B} \left[ -\frac{1}{Z_{i_1:j}(\tau)} \log(\pi_{i_j}(a_{i_j} | \tau, a_{i_1:j-1})) \exp\left( \frac{A_{i_1:j}(\tau, a_{i_1:j})}{\alpha} \right) \right]
  \]
  其中\(Z_{i_1:j}\)是归一化函数，\(\alpha\)是温度参数。
- **Critic更新**：采用序列SARSA风格更新，目标值从数据集采样，使用隐式重要性权重。
- **反事实基线**：使用反事实优势估计降低方差，使方差上界与智能体数量无关。
- **顺序执行**：在每一步，智能体按随机排列顺序依次选择动作，后序智能体可观测前序智能体的动作，从而促进协调。

### 算法流程（文字说明）
1. 初始化策略网络和Q网络参数。
2. 从离线数据集中采样小批量轨迹。
3. 随机生成智能体顺序排列。
4. 对每个智能体（j=1..n）：
   - 更新Critic：最小化时序差分误差（目标值使用ICQ算子）。
   - 计算反事实优势。
   - 更新策略：最小化加权负对数似然（权重为优势指数）。
5. 重复直至收敛。

## 3. 实验设计

### 数据集与场景
- **SMAC**（StarCraft Multi-Agent Challenge）：9个场景，43个数据集，涵盖不同难度和质量等级（Good/Medium/Poor/Medium Replay/Expert/Mixed）。数据集来源包括OMIGA、OG-MARL、CFCQL等。
- **RWARE**（仓库机器人环境）：Tiny（11×11）和Small（11×20）布局，智能体数量2/4/6，共6个数据集。来源为AlberDICE。
- **Multi-Agent MuJoCo**（连续控制）：2x3 HalfCheetah、6x1 HalfCheetah、2x4 Ant、3x1 Hopper，共16个数据集。来源包括OMAR、OMIGA、ComaDICE等。
- **Connector**（新引入的大规模场景）：网格环境，智能体数量从3到50，共7种配置（20M在线数据采样至1M）。
- **T-Maze**（消融验证环境）：两智能体协调任务，包含replay和expert两种数据集。

### 对比方法
- 基线：MAICQ, I-ICQ, MADT, IQL-CQL, CFCQL, ComaDICE, DoF, MACQL, OMAR, OMIGA, AlberDICE等十余种。
- 消融：Oryx去除自回归动作/去除记忆/去除ICQ。
- 架构对比：MAT+ICQ（用Oryx相同的ICQ损失但替换Sable为MAT）。

## 4. 资源与算力

论文中未详细列出GPU型号、数量及训练时长。仅在附录C.4中提及“所有Connector实验分布在NVIDIA A100 GPU（40GB和80GB VRAM）上”。未说明具体数量、训练轮次时长或总计算量。因此，算力细节不够透明。

## 5. 实验数量与充分性

### 实验数量
- **主基准测试**：共65个数据集（SMAC 43个 + MAMuJoCo 16个 + RWARE 6个）。
- **大规模扩展**：Connector上7个智能体规模（3~50），每种设置3~10个随机种子。
- **消融实验**：T-Maze上5组（Oryx本身 + 4个消融变体），以及MAT+ICQ与Oryx在SMAC和RWARE上的对比。
- **每个实验**：通常重复10个随机种子，每次评估320个episode。

### 充分性与公平性
- 覆盖了离散和连续控制、多种难度、不同智能体数量，场景多样性高。
- 使用了标准化协议（OG-MARL提供的代码和数据），确保复现性。
- 统计显著性检验：使用双样本异方差t检验（95%置信区间），标明哪些算法与最优无显著差异。
- 消融实验完整，验证了每个核心组件的必要性。
- **潜在不足**：部分基线结果来自原始论文，可能因超参数调优差异导致不公平；Connector数据集仅与MAICQ对比，缺乏更多强基线。

**总体评价**：实验比较充分，设计较为客观，但可进一步涵盖更多最新离线MARL方法（如OMIGA在Connector上未测试）。

## 6. 主要结论与发现

1. **Oryx在65个数据集中超过80%达到或超越最新水平**，尤其在SMAC（79%）、MAMuJoCo（14/16）、RWARE（全部6个）上表现优异。
2. **大规模扩展能力强**：在Connector场景中，当智能体数量从23增至50时，Oryx保持接近专家性能，而MAICQ性能急剧下降（降至25%以下）。
3. **核心组件缺一不可**：消融实验显示，去除自回归动作、记忆或ICQ损失均导致T-Maze任务完全失败。
4. **Sable架构优于MAT**：在相同ICQ损失下，Oryx（基于Sable）在所有聚合指标（中位数、IQM、均值、最优性差距）上均优于MAT+ICQ。

## 7. 优点

- **方法创新**：首次将自回归序列模型与ICQ结合用于离线MARL，同时解决外推误差和协调失败。
- **理论支撑**：利用优势分解定理推导顺序更新，使用反事实基线降低方差。
- **实验广度**：涵盖65个数据集、多种环境类型和规模，消融实验设计严谨。
- **代码与数据开源**：所有Connector新数据集和代码公开，促进社区复现和进一步研究。
- **实际应用潜力**：展示了在50智能体级别的大规模协调能力，向真实场景迈进一步。

## 8. 不足与局限

- **算力资源未透明**：未提供GPU数量、训练时间等关键资源消耗信息，影响可复现性和能耗评估。
- **Connector基线不足**：仅与MAICQ对比，缺乏与ComaDICE、CFCQL等其他先进离线MARL方法的比较，削弱了结论的说服力。
- **超参数敏感性**：SMAC实验中ICQ策略温度需根据数据集质量手动调整（0.1~0.9），未提供自动化方案，可能限制泛化性。
- **只测试三/四个环境类型**：虽然场景多样，但均为模拟环境，真实工业系统（如复杂物流、交通）未验证。
- **未讨论计算效率**：尽管Sable设计高效，但Oryx在训练和推理时的具体时间/内存成本未与基线对比。
- **未考虑离线到在线微调**：作者将其列为未来工作，但该方法在离线设定外可能还需额外工程。
- **潜在偏差风险**：部分基线结果引用自原始论文，实验条件可能不完全一致，存在系统性偏差。

（完）
