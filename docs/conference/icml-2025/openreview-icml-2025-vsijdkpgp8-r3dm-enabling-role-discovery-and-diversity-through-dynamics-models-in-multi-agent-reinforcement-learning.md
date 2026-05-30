---
title: "R3DM: Enabling Role Discovery and Diversity Through Dynamics Models in Multi-agent Reinforcement Learning"
title_zh: R3DM：通过动力学模型实现多智能体强化学习中的角色发现与多样性
authors: "Harsh Goel, Mohammad Omama, Behdad Chalaki, Vaishnav Tadiparthi, Ehsan Moradi Pari, Sandeep P. Chinchali"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VSIjdKPGp8"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体强化学习算法用于角色发现
tldr: 现有角色发现方法仅从过去经验定义角色，忽略其对未来轨迹的影响。提出R3DM框架，通过动力学模型让角色塑造智能体未来行为，提升复杂任务中的协作效率。实验证明该方法在多个MARL基准测试中取得更好性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1660, \"height\": 1411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1688, \"height\": 386, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1115, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 929, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1867, \"height\": 662, \"label\": \"Table\"}]"
motivation: 现有角色方法忽略了角色对智能体未来行为的塑造作用，限制协调效果。
method: 提出基于动力学模型的角色发现框架，使角色主动影响智能体未来轨迹。
result: 在多个MARL基准任务中表现优异，提升协作效率。
conclusion: 通过动力学模型实现前瞻性角色发现，有效增强多智能体协作。
---

## Abstract
Multi-agent reinforcement learning (MARL) has achieved significant progress in large-scale traffic control, autonomous vehicles, and robotics. Drawing inspiration from biological systems where roles naturally emerge to enable coordination, role-based MARL methods have been proposed to enhance cooperation learning for complex tasks. However, existing methods exclusively derive roles from an agent's past experience during training, neglecting their influence on its future trajectories. This paper introduces a key insight: an agent’s role should shape its future behavior to enable effective coordination. Hence, we propose Role Discovery and Diversity through Dynamics Models (R3DM), a novel role-based MARL framework that learns emergent roles by maximizing the mutual information between agents' roles, observed trajectories, and expected future behaviors. R3DM optimizes the proposed objective through contrastive learning on past trajectories to first derive intermediate roles that shape intrinsic rewards to promote diversity in future behaviors across different roles through a learned dynamics model. Benchmarking on SMAC and SMACv2 environments demonstrates that R3DM outperforms state-of-the-art MARL approaches, improving multi-agent coordination to increase win rates by up to 20%. The code is available at https://github.com/UTAustin-SwarmLab/R3DM.

---

## 论文详细总结（自动生成）

# 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的基于角色的多智能体强化学习（MARL）方法仅从智能体的历史经验（过去的观测-动作轨迹）中推导角色，忽略了角色对智能体未来行为的影响。这种仅限于过去的角色定义方式限制了智能体之间的有效协调，例如在消防场景中，两个无人机因初始观测相似而采用相同角色，导致冗余行动（都飞向同一火源），而不是分散处理两处火灾。
- **整体含义**：论文提出一个关键见解——智能体的角色应当塑造其未来行为，从而实现更有效的协作。为此，R3DM（Role Discovery and Diversity through Dynamics Models）通过最大化智能体角色、观测轨迹和期望未来行为之间的互信息，使角色能够主动影响未来轨迹，促进涌现出互补且多样化的角色，提升多智能体协同任务（如星际争霸微操）的整体性能。

# 2. 论文提出的方法论

- **核心思想**：提出一个基于互信息（MI）的信息论目标，连接角色、历史轨迹和未来轨迹。该目标被分解为两个部分：（1）通过对比学习从历史观测-动作历史中学习中间角色嵌入；（2）通过动力学模型（基于DreamerV3的RSSM）产生内在奖励，鼓励角色引导的未来行为多样性。
- **关键技术细节**：
    - **角色嵌入学习**：利用ACORM的对比学习框架，将智能体轨迹嵌入聚类为|M|个角色簇，通过正负样本对比优化角色嵌入，使其区分不同行为模式。
    - **内在奖励**：由两部分组成：
        - **策略内在奖励**：鼓励角色对策略的影响，通过KL散度计算角色条件Q值与角色无关平均Q值之间的差异。
        - **动力学内在奖励**：通过角色条件RSSM（DreamerV3）和角色无关RSSM的预测差异，衡量角色对未来观测的预测影响。具体公式为解码器和对数似然项之差。
    - **最终学习目标**：结合任务奖励和内在奖励（权重α），使用QMIX框架进行集中式训练，保持CTDE范式。
- **公式或算法流程（文字说明）**：算法基于ACORM和QMIX，每轮训练中先获取智能体轨迹和角色嵌入，定期使用K-means聚类并更新对比学习损失；同时利用DreamerV3模型计算内在奖励，修改Q-learning目标（公式10）进行参数更新。

# 3. 实验设计

- **使用数据集/场景**：SMAC（星际争霸多智能体挑战）和SMACv2两个基准环境。SMAC中选取6个困难/超困难场景（如5m vs 6m, MMM2, 3s5z vs 3s6z, 27m vs 30m, 6h vs 8z, Corridor）；SMACv2引入随机初始化条件，选取5vs5和10vs11的多种族场景（protoss, terran, zerg）。
- **benchmark**：与五个SOTA基线对比——QMIX、ACORM、CIA、GoMARL、CDS、EMC。其中ACORM是直接对比的基于对比学习的角色方法。
- **对比方法**：包括角色对比学习（ACORM、CIA）、分组机制（GoMARL）、多样性内在奖励（CDS、EMC）以及基础QMIX。

# 4. 资源与算力

- 论文未明确说明使用的GPU型号、数量及训练时长。仅在实现细节中提到了使用SMAC版本SC 2.4.10，但算力资源细节缺失。

# 5. 实验数量与充分性

- **实验数量**：在SMAC上进行了6个场景的实验，在SMACv2上进行了6个场景的实验（每个场景5个随机种子），并包含定性分析（TSNE可视化）和消融实验（想象步数、角色数量、对比学习的影响）。
- **充分性**：实验覆盖了多个难度级别和随机性场景，与多个SOTA方法对比，统计了均值和标准差（5种子），消融实验验证了关键组件（内在奖励、对比学习、角色数量、想象步数）。总体较充分，但SMACv2上的10vs11环境所有方法表现仍有限，说明算法仍有改进空间。实验较为公平，所有基线在相同种子和超参数下运行。

# 6. 论文的主要结论与发现

- R3DM在SMAC和SMACv2的大部分场景中显著优于所有基线，最终胜率提升最高达20%，尤其在超困难场景（如3s5z vs 3s6z、Corridor）中表现突出。
- 定性可视化显示R3DM学习到的角色能产生未来行为分化（如一名追猎者引诱敌方狂热者，其余分队攻击），而ACORM的角色则趋向同质化。
- 消融实验表明：内在奖励（尤其是动力学内在奖励）是性能提升的主要驱动；对比学习进一步通过清晰的角色表示增强效果；角色数量适中（3个）最优；想象步数过大会因累积误差导致性能下降。
- 在SMACv2的随机性环境下，R3DM表现出更好的泛化能力和样本效率。

# 7. 优点

- **方法新颖性**：首次将角色与未来轨迹联系起来，通过动力学模型提供前瞻性内在奖励，超越了仅基于历史经验的角色发现。
- **理论扎实**：从互信息下界推导出可优化的两部分目标，并给出严格的定理证明（Theorem 4.1-4.3）。
- **实验全面**：在两个基准、多样场景、多个基线上验证，消融实验覆盖关键设计选择。
- **可重复性**：提供开源代码，实现细节详尽（网络结构、超参数表）。
- **性能提升显著**：在困难场景中最高提升20%胜率，展示出更强的协调能力。

# 8. 不足与局限

- **角色数量需预定义**：|M|作为超参数需手动设定，未能动态自适应推导，可能不适用于未知任务。
- **世界模型局限性**：动力学模型仅基于局部观测-动作历史，忽略其他智能体动作的影响，未来可引入更复杂的联合动力学。
- **算力信息缺失**：未报告具体GPU型号、数量和训练耗时，影响可复现性。
- **SMACv2高难度场景仍欠优**：在10vs11场景中所有方法胜率均较低，说明算法在面对极端随机性时仍有局限，泛化能力有待提升。
- **实验的充分性**：虽然场景较多，但仅在SMAC系列环境下测试，未在机器人控制、交通等现实场景验证，可能存在领域偏差。

（完）
