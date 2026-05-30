---
title: "HyperMARL: Adaptive Hypernetworks for Multi-Agent RL"
title_zh: HyperMARL：面向多智能体强化学习的自适应超网络
authors: "Kale-ab Tessera, Arrasy Rahman, Amos Storkey, Stefano V. Albrecht"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=56CgYnf9Dr"
tags: ["query:marl"]
score: 9.0
evidence: 使用超网络实现多智能体强化学习中的自适应合作
tldr: 该论文针对多智能体强化学习中参数共享导致行为多样性不足的问题，提出基于自适应超网络的方法。通过解耦智能体ID与观测，超网络生成个性化参数，在保持共享策略高效性的同时实现行为特化，无需额外目标或复杂度。实验验证了该方法在多种合作场景下的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 732, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1192, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 480, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1414, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 496, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1309, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1307, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 851, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1430, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 864, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 939, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1418, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1362, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 654, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1192, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1445, \"height\": 1116, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1444, \"height\": 1294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1400, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-56cgynf9dr/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 861, \"height\": 739, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 932, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 664, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1594, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1458, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1490, \"height\": 1714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1344, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1453, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 1552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 871, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 474, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 846, \"height\": 895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 545, \"height\": 671, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 655, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 872, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1007, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1175, \"height\": 1360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 689, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 725, \"height\": 1544, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 729, \"height\": 1543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 702, \"height\": 1541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1422, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 702, \"height\": 1549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1218, \"height\": 812, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1459, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-56cgynf9dr/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1710, \"height\": 443, \"label\": \"Table\"}]"
motivation: 参数共享抑制了多智能体行为多样性，现有解决方案增加了复杂性或限制了适应性。
method: 提出自适应超网络，通过为每个智能体生成个性化参数，在共享策略框架下实现行为特化与混合。
result: 在多个合作任务中，HyperMARL在保持参数共享效率的同时实现了更丰富的自适应合作行为。
conclusion: 超网络提供了一种简洁有效的途径来兼顾多智能体系统的共享效率和行为多样性。
---

## Abstract
Adaptive cooperation in multi-agent reinforcement learning (MARL) requires policies to express homogeneous, specialised, or mixed behaviours, yet achieving this adaptivity remains a critical challenge. While parameter sharing (PS) is standard for efficient learning, it notoriously suppresses the behavioural diversity required for specialisation. This failure is largely due to cross-agent gradient interference, a problem we find is surprisingly exacerbated by the common practice of *coupling agent IDs with observations*. Existing remedies typically add complexity through altered objectives, manual preset diversity levels, or sequential updates -- raising a fundamental question: *can shared policies adapt without these intricacies?* We propose a solution built on a key insight: an agent-conditioned hypernetwork can generate agent-specific parameters and *decouple* observation- and agent-conditioned gradients, directly countering the interference from coupling agent IDs with observations. Our resulting method, **HyperMARL**, avoids the complexities of prior work and empirically reduces policy gradient variance. Across diverse MARL benchmarks (22 scenarios, up to 30 agents), HyperMARL achieves performance competitive with six key baselines while preserving behavioural diversity comparable to non-parameter sharing methods, establishing it as a versatile and principled approach for adaptive MARL. The code is publicly available at https://github.com/KaleabTessera/HyperMARL.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多智能体强化学习（MARL）中，参数共享（Parameter Sharing, PS）虽能提升样本效率，但严重抑制了行为多样性，导致无法学习特化策略。现有解决方法（如修改目标函数、预设多样性水平、顺序更新等）增加了复杂性或限制了灵活性。
- **研究动机**：作者发现，**将智能体ID与观测耦合**是加剧跨智能体梯度干扰的关键原因。这一发现激发了设计一种既能保持共享策略效率、又能自适应产生特化或同质行为的方法。
- **整体含义**：提出**HyperMARL**——基于智能体条件超网络的架构，通过**解耦观测条件梯度与智能体条件梯度**，在不增加额外复杂性的前提下，实现自适应合作。该方法在22个场景、最多30个智能体的基准测试中，与六种基线竞争，同时保持了与非参数共享方法相当的行为多样性。

---

## 2. 论文提出的方法论

### 核心思想
- 使用**智能体条件超网络（agent-conditioned hypernetwork）**为每个智能体动态生成策略和评论家的参数。
- 通过解耦梯度，直接缓解因ID与观测耦合导致的梯度干扰。
- 无需修改标准RL目标、无需预设多样性水平、无需顺序更新。

### 关键技术细节
- **线性超网络**：对于独热编码的智能体ID，生成参数为 \( \theta_i = 1_i \cdot W + b \)，每个智能体对应权重矩阵的一行。
- **MLP超网络**：使用隐层和非线性，输入为**可学习的智能体嵌入**。嵌入正交初始化，并与超网络端到端优化。
- **梯度解耦**：公式（4）展示了策略梯度分解为**智能体条件雅可比（确定性）**与**观测条件项（随机期望）**，先平均每个智能体的噪声再应用确定性变换，从而降低方差；而FuPS+ID中二者纠缠，导致梯度干扰。
- **初始化**：超网络初始化使生成参数的尺度匹配标准初始化方案（如正交初始化），促进稳定训练。
- **算法流程**（附录F.1）：每轮迭代，超网络为每个智能体生成参数；与环境交互收集轨迹；计算标准RL损失（如PPO）更新超网络和嵌入。

---

## 3. 实验设计

- **数据集/场景**：22个场景，涵盖5种环境：
  - **Dispersion（VMAS）**：4智能体，离散动作，需要特化行为。
  - **Navigation（VMAS）**：2/4/8智能体，连续动作，包含同质、异质、混合目标配置。
  - **MAMuJoCo**：2–17智能体，连续控制，异质任务（如Humanoid, Walker2d, HalfCheetah, Ant）。
  - **SMAX（JaxMARL）**：2–20智能体，离散动作，同质行为任务（SMACv1/v2地图）。
  - **Blind-Particle Spread（BPS）**：15–30智能体，离散动作，异质角色推断。
- **对比方法**：NoPS（无参数共享）、FuPS+ID（完全共享+ID）、DiCo（预设多样性）、HAPPO（顺序更新）、Kaleidoscope（可学习掩码+多样性损失）、SePS（选择性参数共享，预训练聚类）。
- **算法基础**：主要使用IPPO/MAPPO，部分对比使用A2C（SePS）和MATD3（Kaleidoscope）。
- **评估指标**：使用IQM（Interquartile Mean）和95% bootstrap置信区间，遵循统计最佳实践。

---

## 4. 资源与算力

- 附录J表25详细列出：
  - **Specialisation/Synchronisation & Dispersion**：8核AMD EPYC 7H12 CPU，每实验2–6小时，总计约250小时。
  - **Navigation**：8核CPU + NVIDIA RTX A4500，每实验4–10小时，总计约320小时。
  - **MAMuJoCo**：8核CPU + NVIDIA RTX A4500，每实验8–24小时（因场景和算法不同），总计约1680小时。
  - **SMAX**：8核CPU + NVIDIA RTX A4500，每实验2–5小时，总计约160小时。
- **总结**：论文明确报告了每类实验的计算资源和运行时长，但未说明GPU具体卡数（推测单卡）。

---

## 5. 实验数量与充分性

- **实验数量**：共22个场景，每个场景至少5个随机种子（Dispersion 10个种子）。具体：
  - Specialisation Game：2/4/8/16智能体，10种子。
  - Dispersion：4智能体，10种子，20M时间步。
  - Navigation：2/4/8智能体，三种目标配置，共5×3=15组实验，5种子。
  - MAMuJoCo：4个任务（Humanoid-17x1, Walker2d-2x3, HalfCheetah-2x3, Ant-4x2），5种子。
  - SMAX：4个地图（2s3z, 3s5z, SMACv2 10/20单位），5种子。
  - BPS：4个变体（15-30智能体），5种子。
  - 消融实验：梯度解耦、初始化缩放、嵌入分析等。
- **充分性与公平性**：
  - 遵循各基线原始代码和超参数，环境使用标准版。
  - 使用IQM和置信区间，避免点估计偏差。
  - 对DiCo在n>2时进行了超参数搜索，但注意到预设多样性可能不适合所有规模。
  - 性能对比广泛，但部分场景（如SMAX）HyperMARL与FuPS最终性能相近，无明显优势；FuPS在简单地图初期收敛更快。

---

## 6. 论文的主要结论与发现

1. **梯度解耦是特化的关键**：HyperMARL通过超网络解耦观测和智能体条件梯度，有效降低了策略梯度方差，在需要特化的任务（如Dispersion）中达到NoPS水平，而FuPS+ID始终失败。
2. **自适应行为**：在Navigation中，HyperMARL在三种目标配置下均表现稳健，尤其在8智能体场景中优势明显；在SMAX中与FuPS持平，证明其无特化偏向，可适应同质任务。
3. **智能体嵌入自适应**：在同目标任务中，嵌入余弦距离收缩（更相似）；在不同目标任务中保持正交，说明嵌入自动反映任务需求。
4. **消融验证**：梯度解耦（w/o GD）在Humanoid和Dispersion中均导致性能下降；初始化缩放（w/o RF）在复杂任务中重要，在简单任务中影响较小。
5. **可扩展性**：MLP超网络参数随智能体数近乎常数（仅需嵌入维度增长），适合大规模MARL。

---

## 7. 优点

- **方法简洁**：不修改RL目标、不依赖预设多样性或顺序更新，仅通过架构设计实现自适应。
- **理论洞察**：明确识别出ID与观测耦合是梯度干扰的放大器，并提出梯度解耦的机制解释（公式4）。
- **实验全面**：覆盖22个场景、多种行为类型与规模，使用统计规范（IQM, CI）。
- **开源代码**：便于复现与后续研究。
- **通用性**：兼容连续/离散动作、前馈/循环架构（GRU），可与多种RL算法（PPO, A2C, MATD3）结合。

---

## 8. 不足与局限

- **参数开销**：超网络生成所有智能体参数，参数总量多于FuPS（尤其MLP变体），但随智能体数增加近似常数；论文提及可通过分块（chunking）或低秩近似缓解。
- **初始化敏感性**：复杂任务（Humanoid）对初始化缩放较敏感，需精心设置。
- **部分场景性能平局**：在SMAX中，HyperMARL与FuPS最终相当，但FuPS初期收敛更快；在Ant-v2中略低于NoPS/FuPS（CI重叠）。
- **超参数依赖**：智能体嵌入维度是重要超参数，可能需针对任务多样性调整；DiCo基线在n>2时需额外搜索，但HyperMARL也可能需要类似调参。
- **环境覆盖有限**：未在动态变化或大规模混合行为（如异构动作空间）场景中测试；未与最新角色分配或多样性方法（如ROMA, RODE, CDAS）直接对比（因其未公开实现或不适用于on-policy）。
- **理论分析**：仅给出梯度方差定性解释，未提供严格的理论保证或收敛性分析。

（完）
