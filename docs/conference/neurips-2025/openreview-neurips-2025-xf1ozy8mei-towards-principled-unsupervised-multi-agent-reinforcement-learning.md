---
title: Towards Principled Unsupervised Multi-Agent Reinforcement Learning
title_zh: 走向有原则的无监督多智能体强化学习
authors: "Riccardo Zamboni, Mirco Mutti, Marcello Restelli"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=XF1OzY8mEI"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体强化学习，无监督预训练
tldr: 本文针对多智能体强化学习中的无监督预训练问题，提出了一个理论基础框架。通过将单智能体状态熵最大化方法扩展到多智能体场景，解决了多智能体环境下无监督学习的理论挑战。实验表明该方法能有效预训练策略，加速下游任务学习，为多智能体无监督强化学习提供了新方向。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xf1ozy8mei/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 585, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xf1ozy8mei/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xf1ozy8mei/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xf1ozy8mei/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 1297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xf1ozy8mei/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 420, \"label\": \"Figure\"}]"
motivation: 现有无监督强化学习主要针对单智能体，缺乏对多智能体环境下的理论理解和方法。
method: 将状态熵最大化扩展到多智能体设置，探索多种问题形式化并分析理论性质。
result: 提出并验证了多智能体无监督预训练的有效性，为后续任务提供良好初始化。
conclusion: 为多智能体无监督强化学习奠定了理论和实践基础。
---

## Abstract
In reinforcement learning, we typically refer to *unsupervised* pre-training when we aim to pre-train a policy without a priori access to the task specification, i.e., rewards, to be later employed for efficient learning of downstream tasks. In single-agent settings, the problem has been extensively studied and mostly understood. A popular approach casts the unsupervised objective as maximizing the *entropy* of the state distribution induced by the agent's policy, from which principles and methods follow. In contrast, little is known about state entropy maximization in multi-agent settings, which are ubiquitous in the real world. What are the pros and cons of alternative problem formulations in this setting? How hard is the problem in theory, how can we solve it in practice? In this paper, we address these questions by first characterizing those alternative formulations and highlighting how the problem, even when tractable in theory, is non-trivial in practice. Then, we present a scalable, decentralized, trust-region policy search algorithm to address the problem in practical settings. Finally, we provide numerical validations to both corroborate the theoretical findings and pave the way for unsupervised multi-agent reinforcement learning via state entropy maximization in challenging domains, showing that optimizing for a specific objective, namely *mixture entropy*, provides an excellent trade-off between tractability and performances.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多智能体强化学习（MARL）在协调、规划等领域取得进展，但现有工作多集中于“从零开始”学习，缺乏对先验知识的利用。单智能体无监督预训练（如状态熵最大化）已被证明能有效提升下游任务学习效率，但在多智能体环境下尚缺乏理论理解和方法支持。
- **核心问题**：如何将状态熵最大化原则性地推广到多智能体场景？不同目标函数（联合熵、边际熵、混合熵）有何理论差异和实际表现？能否设计可扩展的算法进行预训练？预训练对下游稀疏奖励任务有何影响？
- **整体含义**：本文首次为多智能体无监督预训练提供了理论基础，形式化了多智能体状态熵最大化问题，分析了不同目标函数的性质，并提出了一种实际可用的算法，为后续研究奠定了基石。

#### 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将单智能体状态熵最大化（通过凸MDP框架）扩展到多智能体环境，定义为凸马尔可夫博弈（cMG）中的熵最大化。区分了三种目标函数：
  - **联合熵（Joint）**：最大化智能体联合状态分布的熵，鼓励协同探索，但状态空间随智能体数量指数增长。
  - **边际熵（Disjoint）**：每个智能体独立最大化自身状态熵，忽略其他智能体影响，不利于协同。
  - **混合熵（Mixture）**：定义所有智能体边际状态分布的平均分布，再求其熵。在智能体状态空间相同（假设3.1）时，该目标能鼓励智能体覆盖不同区域（聚类行为），且理论性质优于前两者。
- **关键技术细节**：
  - 理论分析：给出三种目标之间的性能上界（引理4.1），以及有限试次下近似误差的集中不等式（定理4.2），证明混合熵的误差随智能体数量增加而减小。
  - 无限试次情形：证明独立策略梯度（PG）在集中信息策略下收敛到全局最优（事实4.1，理论推至定理B.6）。
  - 有限试次情形（更实际）：指出无限试次优化可能导致有限试次下性能差，因此直接优化有限试次目标。
- **算法流程——信任区域纯探索算法（TRPE）**：
  1. 初始化联合策略参数。
  2. 每回合：用当前策略采集N条轨迹，计算每条轨迹的熵估计值（基于经验分布）。
  3. 每个智能体独立迭代：
     - 使用重要性采样（IS）构建代理目标函数（公式4）。
     - 在KL散度信任区域内进行梯度上升更新参数（直到约束被违反）。
  4. 输出最终联合策略。
  - 算法特点：完全分布式、离策略、适用于任意cMG中的有限试次目标，不限于熵函数。

#### 3. 实验设计

- **实验场景**：
  - **秘密房间（Env. i）**：两个智能体在10x10网格中，需协作踩下开关打开门才能探索另一房间，用于测试协调探索能力。状态空间离散。
  - **Reacher（Env. ii，MaMuJoCo）**：两个智能体控制两关节机械臂，每维状态离散化为10个bin，用于高维空间测试。
- **基准方法**：
  - 对比三种目标函数：联合熵、混合熵、边际熵（各自优化）。
  - 基线：均匀随机初始策略（Uniform）、零均值初始策略（Zero-Mean）、随机初始化。
- **对比方式**：
  - 比较不同目标优化后得到的策略的联合熵、混合熵（图2）。
  - 在下游稀疏奖励任务中，用MA-TRPO（多智能体TRPO）微调查询，比较不同初始策略的学习曲线和最终回报（图3）。
  - 零样本性能：直接部署预训练策略，比较回报。

#### 4. 资源与算力

- 文中未明确说明GPU型号、数量、训练时长等算力细节，仅提及实验运行在Apple M2芯片（8核CPU，8核GPU，16核神经引擎，8GB统一内存），最大执行时间24小时。未提及其他大规模计算资源。

#### 5. 实验数量与充分性

- **实验数量**：包含两个环境，每个环境不同的探索步数（T=50,100,150，Env. i；T=100，Env. ii）。每个实验报告4次运行的平均值和95%置信区间。补充材料中提供了更多实验结果（图4、图5）。
- **充分性**：实验覆盖了不同目标、不同探索效率、不同维度空间，且包含下游任务微调和零样本测试。但仅两个环境，且均为离散或离散化状态，缺乏连续大规模实验。此外，未对比其他无监督预训练方法（如ICM、RND）。整体充分性中等，基本支持核心结论，但泛化性验证有限。

#### 6. 主要结论与发现

- **理论方面**：混合熵目标在有限试次下的近似误差随智能体数量增加而减小，具有更好的集中性质；联合熵目标虽在无限试次下易于优化，但在有限试次下性能差。
- **实践方面**：
  - 混合熵优化能有效诱导智能体分散探索（聚类行为），在短探索步数下优于联合熵和边际熵。
  - 下游稀疏奖励任务中，混合熵预训练策略能显著加快学习速度，甚至实现零样本成功，而边际熵预训练有害，联合熵预训练方差大。
  - TRPE算法能有效优化有限试次目标。

#### 7. 优点

- **理论创新**：首次为多智能体无监督状态熵最大化提供形式化框架，分析了三种目标函数的性能边界和有限试次下的集中性质，指导了实际选择。
- **算法设计**：TRPE算法完全分布式，兼容信任区域优化，适用于任意凸马尔可夫博弈，具有独立贡献。
- **实验验证**：通过简单但挑战性的环境直观展示了不同目标的行为差异，并验证了预训练的有效性，包括零样本能力。
- **学术价值**：为后续多智能体无监督强化学习研究打下理论基础。

#### 8. 不足与局限

- **实验覆盖有限**：仅两个环境，且状态空间离散或离散化，缺乏连续域（如连续动作、高维图像输入）的验证。未在标准MARL基准（如SMAC、MPE全任务集）上测试。
- **算法可扩展性**：TRPE依赖蒙特卡洛估计和重要性采样，在高维、长轨迹场景下样本效率可能低；熵的插值估计仅适用于离散空间。
- **理论假设较强**：需要所有智能体状态空间相同（假设3.1），且无限试次收敛需要集中信息策略和强正则性假设（Assumption B.1-3），实际中不易满足。
- **对比方法不足**：未与现有基于内在奖励的多智能体探索方法（如CIM、EDE）比较，仅比较了不同目标本身。
- **计算资源细节缺失**：未报告完整训练时间、收敛所需样本量等资源消耗。

（完）
