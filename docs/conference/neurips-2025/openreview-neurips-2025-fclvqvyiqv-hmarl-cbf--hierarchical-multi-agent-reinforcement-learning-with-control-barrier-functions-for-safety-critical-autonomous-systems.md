---
title: HMARL-CBF – Hierarchical Multi-Agent Reinforcement Learning with Control Barrier Functions for Safety-Critical Autonomous Systems
title_zh: HMARL-CBF：基于控制屏障函数的安全关键自主系统分层多智能体强化学习
authors: "H M Sabbir Ahmad, Ehsan Sabouni, Alexander Wasilkoff, Param Budhraja, Zijian Guo, Songyuan Zhang, Chuchu Fan, Christos Cassandras, Wenchao Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fcLVqvyiqV"
tags: ["query:marl"]
score: 9.0
evidence: 协作多智能体强化学习与安全保障
tldr: 针对多智能体安全关键系统，提出一种基于控制障碍函数的分层多智能体强化学习方法。上层学习联合协作行为，下层保证个体安全。实验表明该方法在保证安全的同时有效完成协作任务，为安全关键自主系统提供了可行的分层学习框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1017, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1126, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1157, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 541, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 987, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 911, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fclvqvyiqv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1288, \"height\": 266, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fclvqvyiqv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fclvqvyiqv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 544, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fclvqvyiqv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fclvqvyiqv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1383, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fclvqvyiqv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fclvqvyiqv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 825, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fclvqvyiqv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 199, \"label\": \"Table\"}]"
motivation: 多智能体安全关键系统中，每个智能体需始终满足安全要求并协作完成任务。
method: 提出分层MARL框架，上层通过RL学习联合协作策略，下层使用控制屏障函数保证个体安全。
result: 在安全关键自主系统任务中，方法实现了安全与协作的有效平衡。
conclusion: 分层安全MARC框架是安全关键多智能体系统中一种有效范式。
---

## Abstract
We address the problem of safe policy learning in multi-agent safety-critical autonomous systems.
In such systems, it is necessary for each agent to meet the safety requirements at all times while also cooperating with other agents to accomplish the task. Toward this end, we propose a safe Hierarchical Multi-Agent Reinforcement Learning (HMARL) approach based on Control Barrier Functions (CBFs). Our proposed hierarchical approach decomposes the overall reinforcement learning problem into two levels –- learning joint cooperative behavior at the higher level and learning safe individual behavior at the lower or agent
level conditioned on the high-level policy. Specifically, we propose a skill-based HMARL-CBF algorithm in which the higher-level problem involves learning a joint policy over the skills for all the agents and the lower-level problem involves
learning policies to execute the skills safely with CBFs. We validate our approach on challenging environment scenarios whereby a large number of agents have to safely navigate through conflicting road networks. Compared with existing state-of-the-art methods, our approach significantly improves the safety achieving near perfect (within $5\%$) success/safety rate while also improving performance across all the environments.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

多智能体安全关键系统（如自动驾驶、无人机群、机器人协作）要求每个智能体在协作完成任务的同时，**在每一时刻都满足安全约束**。然而，现有基于约束马尔可夫决策过程（CMDP）的方法只保证平均或统计意义上的安全（轨迹期望），缺乏点态时间保证。此外，传统分层多智能体强化学习（HMARL）虽能降低样本复杂度，但未专门处理安全。本文提出 **HMARL-CBF**，将控制屏障函数（CBF）与分层 MARL 结合，在训练和部署中均能提供硬安全保证（forward invariance），同时实现高效协作。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于技能的分层框架。上层（high-level）学习智能体间的联合技能选择策略（π_H），下层（low-level）为每个技能学习一个安全执行策略，该策略通过 CBF 约束保证点态安全。
- **关键技术细节**：
  - **高层策略**：建模为多智能体半马尔可夫决策过程（MSMDP）。使用 CTDE 范式，可采用 MAPPO（on-policy）或 QMIX（off-policy）优化。高层决策“技能”（skill）作为时间扩展动作，技能的选择基于联合观测。
  - **低层策略**：对每个技能，通过一个参数化 QP（二次规划）生成控制动作。QP 的约束包括：
    - **CBF 约束**：确保与其它智能体及环境的碰撞安全（如圆形安全区域、道路边界）。
    - **CLF 约束**：驱动系统收敛到技能终止状态（如目标速度、航向）。
    - 目标函数为控制代价与松弛变量加权和，参数 ϕ 通过可微 QP 层端到端学习。
  - **联合训练**：高层和低层策略交替更新（算法 1）。低层奖励可引入高层优势项以对齐任务目标。
- **理论保证**：根据定理 5.1，CBF 约束的满足保证前向不变性，从而确保整个轨迹的点态安全。

### 3. 实验设计：数据集/场景、基准与对比方法

- **场景**（共 8 种）：
  - **METADRIVE 模拟器**：5 种复杂交通环境（Merging、Intersection、Roundabout、Bottleneck、Tollgate），部分观测，agent 数量最多 45。
  - **Lidar 环境套件**：Target、Spread、Target-Bicycle（含自行车动力学），同样部分观测，agent 数量可扩展。
- **对比基线**：
  - 经典 MARL：CoPo、IPPO、MFPO。
  - 安全 MARL：MAPPO-Lagrangian、MACPO（基于 CMDP）。
  - 最新方法：DGPPO、InforMARL（固定/调度的惩罚）。
- **评价指标**：成功率（↑）、成功加权的平均时间和能量消耗（↓）。

### 4. 资源与算力

论文在附录 A.1.4 说明：使用一台配备单块 **NVIDIA RTX A5000 GPU** 和 **32 个 CPU 核心** 的桌面计算机。主要计算开销来自数据收集，训练收敛较快（≤ 300k 迭代）。未报告确切训练总时长，但指出基准方法需 2000+ 小时个体驾驶经验，而本文方法不增加额外样本复杂度。

### 5. 实验数量与充分性

- **主实验**：在 5 个 METADRIVE 环境下，每个环境使用 5 个不同随机种子，每种子运行 5 个测试回合（共 25 次），报告均值和标准差。对比了 4 种基线（含 3 种安全相关基线）。
- **消融实验**（表 2、表 3）：
  - 去掉分层结构（扁平策略）
  - 随机高层策略
  - 随机丢弃 CBF 约束
  - 用 LQR 代替 CBF 低层
  - 固定低层参数
- **泛化实验**（表 4-8）：
  - 改变车道宽度
  - 技能迁移（从一个环境训练低层到另一个环境训练高层）
  - 改变智能体密度/数量
  - 在 Lidar 环境套件上对比 DGPPO 等（图 7-8）
- **充分性评价**：实验覆盖多类场景、多种变化，消融验证了每个设计组件的必要性，泛化实验说明可靠性。对比基线包括当时 SOTA，统计指标合理，实验充分且客观。

### 6. 论文的主要结论与发现

- HMARL-CBF 在所有测试环境中达到近乎 **100% 的成功率（≥ 95%）**，远优于基线（多数 < 50%）；
- 同时显著降低了平均时间和能量消耗，表明不仅保证了安全，还优化了协作效率；
- 分层结构加速收敛（≤ 300k 迭代 vs 基线 1M 迭代）；
- 消融实验证实：CBF 提供的点态安全约束不可或缺，分层结构、技能学习、参数化 QP 均对最终性能有重要贡献；
- 技能迁移实验表明低层技能可跨环境泛化。

### 7. 优点

- **理论保证**：首次在 HMARL 中引入 CBF 提供点态安全的全轨迹正不变性，区别于 CMDP 的期望安全；
- **可扩展性**：采用 CTDE 和参数共享，智能体数量增加时仍可高效训练；
- **兼容性**：上层可选用多种 MARL 算法（on-policy / off-policy），下层 QP 求解快速适合实时控制；
- **实验全面**：在多障碍、多交通场景及多种设置下验证，消融和泛化丰富；
- **技能可解释性**：技能（巡航、加速、让行、换道）直观，便于人类理解与安全验证。

### 8. 不足与局限

- **模型依赖**：CBF 约束依赖系统动力学模型（文中采用了近似模型），虽然提及可用鲁棒 CBF 处理不确定性，但未在真实物理系统上验证；
- **技能预定义**：技能集合需人工设计，未实现自主技能发现（作者在将来工作中提及）；
- **通信/感知限制**：未考虑 agent 间通信延迟或感知遮挡对 CBF 约束的影响（部分场景中依赖 lidar 半径内其他 agent 状态）；
- **计算开销**：虽然 QP 求解快，但高维状态或极大数据量下，端到端可微 QP 层可能成为瓶颈；
- **环境局限性**：主要验证在模拟交通场景，真实自动驾驶等复杂场景的应用有待进一步验证。

（完）
