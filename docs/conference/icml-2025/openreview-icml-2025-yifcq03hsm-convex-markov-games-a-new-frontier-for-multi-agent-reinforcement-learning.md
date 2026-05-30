---
title: "Convex Markov Games: A New Frontier for Multi-Agent Reinforcement Learning"
title_zh: 凸马尔可夫博弈：多智能体强化学习的新前沿
authors: "Ian Gemp, Andreas Alexander Haupt, Luke Marris, Siqi Liu, Georgios Piliouras"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yIfCq03hsM"
tags: ["query:marl"]
score: 10.0
evidence: 凸马尔可夫博弈用于多智能体强化学习
tldr: 针对马尔可夫博弈无法表达非加性偏好的问题，提出凸马尔可夫博弈类，支持一般凸偏好。证明无限时域下纯策略纳什均衡存在，并给出基于可剥削性上界的梯度下降近似算法。实验展示在公平性、多样性等场景中的新解。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1296, \"height\": 162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 270, \"height\": 151, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 871, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 646, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 783, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 819, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1166, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 381, \"height\": 151, \"label\": \"Table\"}]"
motivation: 现有马尔可夫博弈无法处理多样性和公平性等非加性偏好。
method: 定义凸马尔可夫博弈类，允许凸偏好，证明均衡存在性并设计可剥削性上界梯度优化。
result: 在重复博弈、公平性协作和机器人仓库安全等场景中取得创新解。
conclusion: 凸马尔可夫博弈扩展了MARL建模能力，理论基础扎实且实用。
---

## Abstract
Behavioral diversity, expert imitation, fairness, safety goals and others give rise to preferences in sequential decision making domains that do not decompose additively across time. We introduce the class of convex Markov games that allow general convex preferences over occupancy measures. Despite infinite time horizon and strictly higher generality than Markov games, pure strategy Nash equilibria exist. Furthermore, equilibria can be approximated empirically by performing gradient descent on an upper bound of exploitability. Our experiments reveal novel solutions to classic repeated normal-form games, find fair solutions in a repeated asymmetric coordination game, and prioritize safe long-term behavior in a robot warehouse environment. In the prisoner's dilemma, our algorithm leverages transient imitation to find a policy profile that deviates from observed human play only slightly, yet achieves higher per-player utility while also being three orders of magnitude less exploitable.

---

## 论文详细总结（自动生成）

# 论文总结：Convex Markov Games

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在多智能体强化学习（MARL）中，许多重要目标（如行为多样性、人类模仿、公平性、安全性等）所对应的偏好无法表示为每步奖励的简单加和（即非加性偏好）。传统马尔可夫博弈（Markov Game, MG）模型仅支持线性目标，无法处理这类复杂偏好。
- **研究动机**：单智能体领域已推广至凸马尔可夫决策过程（cMDP），支持凸偏好（如熵、风险等）。但在多智能体领域，缺乏对应的形式化框架与均衡存在性证明。本文旨在填补这一空白。
- **整体含义**：引入“凸马尔可夫博弈”（convex Markov Game, cMG）类，允许每个智能体的效用函数是其占优测度（occupancy measure）的连续凹函数，从而统一建模多样性、模仿、公平、安全等偏好。理论上证明了纯策略纳什均衡的存在性，并给出了可计算的近似均衡算法，为多智能体序列决策的复杂偏好建模提供了新基础。

## 2. 论文提出的方法论

- **核心思想**：将传统马尔可夫博弈中的线性奖励函数替换为关于智能体占优测度的任意连续凹函数。每个智能体的目标是在给定对手策略下，选择占优测度最大化其效用。问题在占优测度空间中是凸的（线性约束 + 凹目标），但在策略空间中往往非凸。
- **关键技术细节**：
  - **定义**：cMG 由六元组 ⟨S, A, P, u, γ, μ₀⟩ 表示，其中 u_i(μ_i, π_{-i}) 对 μ_i 连续且凹，对 π_{-i} 连续。
  - **均衡存在性**：
    - 混合策略纳什均衡存在性由经典 Glicksberg 定理得出（策略空间紧致，效用连续）。
    - 纯策略纳什均衡存在性需要更复杂的拓扑论证：由于最佳响应集在策略空间中可能非凸（见图1b），不满足 Kakutani 不动点定理的凸性假设。本文借助 Kosowsky (2023) 的结论，证明最佳响应集是“可收缩的”（contractible），进而由 Debreu (1952) 的定理得到纯策略 NE 的存在。
  - **均衡计算**：
    - 定义 exploitability ϵ = max_i ϵ_i，其中 ϵ_i 为智能体 i 单方面偏离的最大增益。
    - 直接最小化 exploitability 需要求解 n 个凸规划，代价高。本文推导一个可微的上界：通过引入熵正则化（温度 τ），得到损失函数 L_τ(π) = Σ_i || Π_{T U_i}(∇_i^τ μ_i) ||²，其中 Π_{T U_i} 是投影到可行占优测度切空间的算子，∇_i^τ μ_i 是熵正则化后的梯度。
    - 定理2（低温近似均衡 = 近似NE）：ϵ_i ≤ τ log(|S||A_i|) + √2 ||Π_{T U_i}(∇_i^τ μ_i)||。因此最小化 L_τ 可得到 exploitability 的上界。
  - **算法流程**（算法1：PGL）：
    1. 初始化策略 π 和温度调度 τ_t。
    2. 对 t=0,…,T：用 Adam 等优化器更新 π 以最小化 L_τ_t(π)。
    3. 输出 π。
    - 温度 τ 按计划退火（如指数衰减或基于损失的自适应），模仿同伦延续方法（homotopy methods）。

## 3. 实验设计

- **使用的域/场景**（共7个）：
  1. **多智能体路径规划**（网格世界）：两智能体需通过瓶颈门到达共同目标。
  2. **迭代囚徒困境（IPD）**：两玩家每次选择合作或背叛。
  3. **迭代公共品游戏（IPGG）**：三玩家选择贡献全部或不贡献。
  4. **El Farol 酒吧问题**：三玩家决定是否去酒吧（少于3人则不拥挤）。
  5. **巴赫-斯特拉文斯基协调博弈**：两玩家偏好不同演出但需协调。
  6. **合成安全域**：图1中的两状态两动作博弈，安全区域由凸损失定义。
  7. **机器人仓库安全网格世界**：两机器人取放包裹，可在中心危险区选择快或慢动作，安全目标限制快动作比例在10%以下。
- **基准方法**：
  - **min ϵ**：直接最小化 exploitability（使用 CVXPYLAYERS 自动微分凸优化）。
  - **Sim（同时梯度下降）**：所有智能体同时梯度下降，评估策略平均值。
  - **RR（轮流梯度下降）**：智能体轮流更新。
  - **SGAMESOLVER**：用于马尔可夫博弈的同伦法包（不直接支持cMG，但可用于对比线性偏好情形）。
- **对比指标**：exploitability（越低越好）、策略形态、效用、安全违反等。

## 4. 资源与算力

- 论文明确提到：
  - “除路径搜索外，所有实验均在单个CPU上运行，耗时约一分钟；使用 CVXOPT 报告准确 exploitability 会增加约10倍运行时间。”
  - 路径搜索使用了1个GPU（未指定型号、显存或训练时长）。
- 未提及大规模分布式训练或详细硬件配置。

## 5. 实验数量与充分性

- **实验组数**：共7个不同域，每个域有若干子实验（创造力、模仿、公平、安全）。例如：IPD和IPGG中有两个子设置（创造力和模仿）。安全合成域和机器人仓库单独测试。巴赫-斯塔文斯基重复了10次随机初始化。
- **消融/参数研究**：论文提供了超参数表（学习率、退火类型），并在图3中比较了不同方法在3个迭代NFG上的收敛曲线。但未进行系统的超参数扫描或对不同初始化的敏感性分析。
- **公平性**：对比了4种基线方法，但min ϵ在大多数域中因数值不稳定而失败（图3中用星标表示失败）。未与 model-free MARL 算法（如 MADDPG、Q-learning）比较，但对于cMG这类需要转移概率的设定，model-based 方法是合理的。整体实验量适中，展示了概念验证，但缺乏大规模复杂环境的验证，充分性一般。

## 6. 论文的主要结论与发现

- **理论贡献**：cMG 模型中纯策略纳什均衡存在（即使最佳响应集不凸）。定理1是主要理论结果。
- **算法贡献**：提出可微的 exploitability 上界损失 L_τ，通过梯度下降加温度退火可有效逼近均衡。
- **实验发现**：
  - PGL 在多个迭代博弈中收敛到低 exploitability（图3），优于或可与 RR 和 Sim 媲美。
  - 创造力设置：PGL 发现非平凡策略，如 IPD 中类似“以牙还牙”（tit-for-tat）的对称策略（表2），IPGG 中条件贡献策略（表3），而基线方法收敛到静态子博弈完美均衡（全部背叛/零贡献）。
  - 模仿设置：使用 KL 散度正则化逼近人类数据，得到的策略与人类策略相似但 exploitability 低三个数量级（表4）。
  - 公平性：在巴赫-斯特拉文斯基博弈中，通过二次惩罚实现均衡状态下的公平访问。
  - 安全性：在机器人仓库域中，安全损失有效降低了快动作在危险区的频率（从69%降至42%）。合成安全域达到精确 NE（ϵ=0）。
- **总体结论**：cMG 是一个通用框架，可用于求解多样性、模仿、公平、安全等目标下的均衡，理论完备且实用。

## 7. 优点

- **理论深度**：打破了传统博弈论中凸性假设的依赖，证明了纯策略 NE 在更一般条件（非凸最佳响应集）下的存在性，利用拓扑收缩性给出新证明。
- **方法创新**：将占优测度空间的凸性与策略空间的简单约束结合，设计出可微的 exploitability 损失函数，并引入温度退火机制引导均衡选择。
- **统一框架**：用同一套形式化和算法处理多种非加性偏好（熵、KL散度、二次惩罚、非光滑损失），展示了广泛适用性。
- **代码开源**（基于 JAX）：算法可复现（附录提供伪代码和超参）。
- **对人类行为的启发**：在 IPD 中，通过模仿人类但降低 exploitability 找到了更优策略，体现了学习“容错”均衡的实际价值。

## 8. 不足与局限

- **实验覆盖范围有限**：所有域都是小型网格世界或迭代博弈（状态空间 ≤4 个，动作 ≤3 个），未验证在复杂连续空间或大规模 MARL 基准（如 SMAC、MuJoCo 多智能体）上的可扩展性。
- **算法依赖模型**：PGL 需要已知转移概率 P 来计算占优测度及投影矩阵，不能直接用于 model-free 环境。论文承认 model-free 和无偏估计投影矩阵是未来挑战。
- **收敛保证缺失**：算法1无理论收敛保证，尽管实践中表现良好，但可能收敛到局部极小或非均衡点。
- **对比基线不全面**：未与专门求解 cMDP 的多智能体扩展方法（如基于值函数的变体）或近期 model-based MARL 方法比较。min ϵ 在多数设置中失败，使得比较不够公平（基线有效数量有限）。
- **计算开销**：精确 exploitability 计算需要求解 n 个凸规划（使用 CVXOPT），显著增加运行时间（约10倍）。实际中只用 L_τ 近似，但近似程度仅通过理论界保证。
- **可转移性**：由于占优测度的定义依赖无限时域 γ 折扣，对于有限时域或非折扣问题需要额外适配。

（完）
