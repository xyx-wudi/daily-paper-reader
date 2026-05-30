---
title: Heterogeneity in Multi-Agent Reinforcement Learning
title_zh: 多智能体强化学习中的异质性
authors: "Tianyi Hu, Zhiqiang Pu, Yuan Wang, Tenghai Qiu, Min Chen, Xin Yu"
date: 2025-05-12
pdf: "https://openreview.net/pdf?id=v7nDKBVRPy"
tags: ["query:marl"]
score: 8.0
evidence: 系统研究多智能体强化学习中的异质性并提出动态参数共享算法
tldr: 多智能体强化学习中异质性对策略多样性和环境交互至关重要，但缺乏严格定义。本文首次系统定义、量化并利用异质性：划分五种异质性类型并给出数学定义；提出异质性距离量化方法；设计基于异质性的动态参数共享算法，在多个MARL基准上取得性能提升，为异质性研究建立了理论基础和实用工具。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 641, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1281, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 710, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 711, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1013, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1012, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 998, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v7ndkbvrpy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 826, \"height\": 347, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7ndkbvrpy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 527, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7ndkbvrpy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1327, \"height\": 121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v7ndkbvrpy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1553, \"height\": 323, \"label\": \"Table\"}]"
motivation: MARL领域对异质性缺乏严格定义和深入理解，阻碍了对其有效利用。
method: 提出异质性的五种分类、量化距离和基于异质性的动态参数共享算法。
result: 在多个标准MARL任务上，所提算法优于固定参数共享和非共享方法。
conclusion: 本文为MARL异质性的研究建立了理论基础和实用工具。
---

## Abstract
*Heterogeneity* is a fundamental property in multi-agent reinforcement learning (MARL), which is closely related not only to the functional differences of agents, but also to policy diversity and environmental interactions. However, the MARL field currently lacks a rigorous definition and deeper understanding of heterogeneity. This paper systematically discusses heterogeneity in MARL from the perspectives of *definition*, *quantification*, and *utilization*.
First, based on an agent-level modeling of MARL, we categorize heterogeneity into five types and provide mathematical definitions.
Second, we define the concept of heterogeneity distance and propose a practical quantification method.
Third, we design a heterogeneity-based multi-agent dynamic parameter sharing algorithm as an example of the application of our methodology.
Case studies demonstrate that our method can effectively identify and quantify various types of agent heterogeneity. Experimental results show that the proposed algorithm, compared to other parameter sharing baselines, has better interpretability and stronger adaptability.
The proposed methodology will help the MARL community gain a more comprehensive and profound understanding of heterogeneity, and further promote the development of practical algorithms.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

多智能体强化学习（MARL）中，异质性（heterogeneity）是一个基础但尚未被严格定义和深入理解的性质。异质性不仅体现在智能体的功能差异上，还与策略多样性和环境交互密切相关。当前研究多聚焦于特定类型的异质性（如功能差异或策略多样性），缺乏对异质性的系统分类、数学定义和量化手段，也难以有效利用异质性提升协作性能。本文旨在填补这一空白，从**定义、量化和利用**三个层面系统研究MARL中的异质性，为后续算法设计奠定理论基础。

### 论文提出的方法论

#### 1. 异质性的分类与定义（基于POMG建模）
- 采用部分可观测马尔可夫博弈（POMG）作为基本模型，以智能体级视角定义五类异质性：
  - **观测异质性**：智能体观察全局信息的方式不同（观测空间或观测函数差异）。
  - **响应转移异质性**：智能体局部状态转移受全局环境和动作影响的方式不同（状态空间或局部转移函数差异）。
  - **效应转移异质性**：智能体的状态和动作对全局状态转移的影响不同（动作空间、状态空间或全局转移函数差异）。
  - **目标异质性**：智能体奖励函数不同。
  - **策略异质性**：智能体基于观测的决策不同（观测空间、动作空间或策略函数差异）。
- 每种异质性均给出否定同质条件的数学定义（定义1-5）。

#### 2. 异质性的量化：异质性距离
- 提出**异质性距离**概念，通过累积核心函数在输入空间上的分布差异来量化异质性程度（公式3）。
- 实际计算采用基于表示学习的方法：利用条件变分自编码器（CVAE）学习分布的潜在表示，用Wasserstein距离度量分布差异，并通过蒙特卡洛采样和GPU并行化高效计算。
- 针对模型可知（model-based）和模型未知（model-free）两种情况分别推导ELBO损失。
- 进一步提出**元转移模型**（Meta-Transition），量化智能体与环境的综合异质性（元转移异质性距离）。

#### 3. 异质性的利用：HetDPS动态参数共享算法
- 核心思想：根据异质性距离矩阵对智能体进行亲和传播（Affinity Propagation）聚类，动态调整参数共享结构。
- 周期性量化异质性，并根据聚类结果进行网络拆分或合并（匈牙利算法匹配），无需任务特定超参数。
- 算法流程（伪代码见附录I）：初始化 → 环境交互收集样本 → 定期计算异质性距离 → 聚类 → 更新参数共享分配。

### 实验设计

- **基准环境**：
  - **粒子多智能体扩散**（Particle-based Multi-agent Spreading）：四个任务（15a_3c, 30a_3c, 15a_5c, 30a_5c），不同智能体数量和颜色分布。
  - **星际争霸多智能体挑战**（SMAC）：四个任务（3s5z, 3s5z_vs_3s6z, MMM, MMM2）。
- **对比方法**：NPS（无参数共享）、FPS（全参数共享）、FPS+id、Kaleidoscope、SePS、AdaPS、MADPS，以及本文提出的HetDPS。
- **评估指标**：奖励曲线、训练速度（归一化于FPS）、异质性距离矩阵可视化。

### 资源与算力

论文未明确说明具体使用的GPU型号、数量和训练时长。仅在**表3**中提供了各方法的归一化训练速度（以FPS为1.000），HetDPS为0.712x，表明效率略低于FPS但高于AdaPS和MADPS。未提供绝对时间或硬件配置，因此无法精确评估算力消耗。

### 实验数量与充分性

- 共包含两个环境、8个任务，每个任务展示了奖励曲线（2个随机种子的均值±标准差）。
- 针对粒子环境设计了6个案例场景（图3）验证量化方法的有效性。
- 分析了训练过程中异质性距离的变化（图4）。
- 对比了8种方法，覆盖了主流参数共享策略。
- **不足**：未进行消融实验（如不同聚类算法、量化周期的影响）、未在更大规模环境（如多机器人控制）上测试，实验充分性中等偏上但可进一步扩展。

### 论文的主要结论与发现

1. 提出的异质性五分类和数学定义能够系统涵盖MARL中各类智能体差异。
2. 基于表示学习的异质性距离量化方法在模型可知和未知情形下均能准确识别不同类型的异质性，且与环境学习算法无关。
3. HetDPS算法在大多数任务上取得最优或可比性能，具有更好的可解释性（异质性距离矩阵直观展示分组依据）和适应性（无需手动设置分组数量）。
4. 在SMAC中，简单任务（如3s5z、MMM）智能体倾向于同质化以提高效率；困难任务（如3s5z_vs_3s6z、MMM2）异质性更符合原始类型，揭示了环境对异质性的影响。
5. 策略多样性本质上是策略异质性的表现，其根源在于环境异质性导致的分工。

### 优点

- **理论系统性**：首次给出MARL中异质性的完整分类和数学定义，为后续研究提供统一框架。
- **量化实用性**：异质性距离计算结合表示学习和采样，适用于复杂实际场景，且可并行化。
- **算法可解释性**：HetDPS基于异质性距离进行动态参数共享，避免黑箱超参数，分组逻辑清晰。
- **性能与效率平衡**：在提升性能的同时，训练速度损失较小（归一化速度0.712x）。

### 不足与局限

- **计算复杂度**：异质性距离矩阵计算为O(N²)，当智能体数量极大时可能成为瓶颈。
- **适用条件**：要求智能体相关变量为向量；若涉及多模态输入（如图像+文本），需额外处理（如padding），会增加实现难度。
- **模型未知情形下的严格性**：模型无关方法无法严格保证“异质性距离为0当且仅当智能体同质”，但实践中距离足够小。
- **实验覆盖**：未在复杂异构环境（如不同物理结构的机器人）中验证，且缺乏消融实验验证各组件（如聚类方法、量化频率）的贡献。
- **资源报告缺失**：未提供具体算力配置，影响可重复性评估。

（完）
