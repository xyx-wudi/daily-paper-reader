---
title: Regret Lower Bounds for Decentralized Multi-Agent Stochastic Shortest Path Problems
title_zh: 分散式多智能体随机最短路径问题的遗憾下界
authors: "Utkarsh U. Chavan, Prashant Trivedi, Nandyala Hemachandra"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=lDh9wSb9nP"
tags: ["query:marl"]
score: 9.0
evidence: 分散式多智能体随机最短路径下界
tldr: 该论文研究分散式多智能体随机最短路径问题的遗憾下界。针对分散式控制场景，利用线性函数近似和对称性论证，推导出算法性能的严格下界。这项工作填补了多智能体RL在分散式设置下的理论空白，为未来算法设计提供了基准。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ldh9wsb9np/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 496, \"label\": \"Table\"}]"
motivation: 多智能体系统在分散式协调中理论分析不足，尤其SSP问题尚未被充分研究。
method: 通过对称性论证和线性函数近似，对Dec-MASSPs进行理论分析。
result: 推导出分散式多智能体SSP的遗憾下界，为算法性能提供了理论界限。
conclusion: 该工作推进了分散式多智能体强化学习的理论基础。
---

## Abstract
Multi-agent systems (MAS) are central to applications such as swarm robotics and traffic routing, where agents must coordinate in a decentralized manner to achieve a common objective. Stochastic Shortest Path (SSP) problems provide a natural framework for modeling decentralized control in such settings. While the problem of learning in SSP has been extensively studied in single-agent settings, the decentralized multi-agent variant remains largely unexplored. In this work, we take a step towards addressing that gap.  We study decentralized multi-agent SSPs (Dec-MASSPs) under linear function approximation, where the transition dynamics and costs are represented using linear models. Applying novel symmetry-based arguments, we identify the structure of optimal policies. Our main contribution is the first regret lower bound for this setting based on the construction of hard-to-learn instances  for any number of agents, $n$. Our regret lower bound of $\Omega(\sqrt{K})$, over $K$ episodes, highlights the inherent learning difficulty in Dec-MASSPs. These insights clarify the learning complexity of decentralized control and can further guide the design of efficient learning algorithms in multi-agent systems.

---

## 论文详细总结（自动生成）

# 论文总结：分散式多智能体随机最短路径问题的遗憾下界

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多智能体系统（如群机器人、交通路由）中，智能体需要以分散方式协调实现共同目标。随机最短路径（SSP）问题为这种分散式控制提供了自然建模框架。单智能体SSP的学习问题已被广泛研究，但分散式多智能体变种（Dec-MASSP）几乎未被探索。该论文旨在填补这一理论空白。
- **核心问题**：在具有线性函数近似的Dec-MASSP中，学习算法的性能极限（即遗憾下界）是什么？
- **整体含义**：论文通过构造困难实例，首次给出了分散式MASSP在线性函数近似下的遗憾下界 Ω(√K)（K为回合数），匹配已存在的上界，揭示了分散式环境下学习的内在难度，为设计高效算法提供了理论基准。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：通过构造一系列“难以学习”的MASSP实例，利用信息论和对称性论证推导任何算法的遗憾下界。
- **关键技术细节**：
  - **实例构造**：考虑两个节点（初始节点 s 和目标节点 g），n个智能体。状态空间大小为 2^n，动作空间指数级。使用线性函数近似建模转移概率（Assumption 1）和成本（统一成本为1，到达目标后为零）。
  - **特征设计**：设计新颖的特征映射 ϕ(s′|s,a)（式(3)和(4)），确保转移概率的合法性，并使最优策略易于解析。
  - **对称性和单调性**：基于每个节点上智能体数量对状态空间进行划分（类型 r），证明最优价值函数仅依赖于类型，且严格单调递增（Theorem 1）。最优策略为在所有非目标状态下选择与参数 θ 符号一致的联合动作 a^θ。
  - **遗憾下界推导**（Theorem 2）：
    1. 利用递归分解将遗憾表示为智能体在非目标状态下选择错误动作的次数之和。
    2. 引入截断过程和处理KL散度：利用非负性和对称性，将KL散度上界绑定为 O(∆²·E[N⁻])（Lemma 7），其中 ∆ 为参数扰动幅度。
    3. 选择特定 ∆ = (d-1)√δ / (2^{n+5} √(K V₁^*))，结合Pinsker不等式得到平均遗憾下界，从而存在一个困难实例满足下界。
- **算法流程**：论文未提出新算法，而是证明下界；上界算法来自文献[23]（MACCM）。

## 3. 实验设计

- **实验设置**：论文为纯理论工作，未进行任何数值实验或仿真验证。
- **数据集/场景**：无。
- **Benchmark与对比方法**：文中表1对比了相关工作的上、下界结果，包括单智能体SSP（[18][7][14]）和多智能体SSP（[23]），但均为理论比较，无实验验证。

## 4. 资源与算力

- **资源使用**：文中未提及任何算力资源（GPU型号、数量、训练时长等），因为不涉及计算实验。

## 5. 实验数量与充分性

- **实验数量**：无实验。
- **充分性**：作为理论论文，其贡献主要在于数学证明和推导。证明过程完整，依赖严格假设（线性函数近似、统一成本、特定特征设计等），但缺乏在真实或模拟环境中的验证。实验覆盖不适用，但理论论证本身是充分的。

## 6. 主要结论与发现

- **主要结论**：对于任意分散式学习算法π，存在一个线性的MASSP实例（满足假设条件），使得在K个回合后，期望遗憾满足：
  \[
  \mathbb{E}_{\theta,\pi}[R(K)] \geq \frac{d \cdot \sqrt{\delta} \cdot \sqrt{K \cdot B^*/n}}{2^{n+9}} = \Omega(\sqrt{K})
  \]
  其中 d 为特征维度，δ∈(2/5,1/2)，B^* 为SSP直径，n 为智能体数量。
- **发现**：
  - 下界与K是平方根关系，匹配已存在的上界（[23]），表明该上界在K上是最优的。
  - 下界随智能体数量n指数衰减，反映问题内在难度随智能体数增加而增大（更多近优策略）。
  - 结果恢复单智能体（n=1）时的下界（与[14]一致）。
- **最优策略结构**：对于构建的困难实例，最优策略是选择与θ符号一致的联合动作，且最优价值函数仅依赖于当前位于初始节点的智能体数量，并严格单调递增。

## 7. 优点

- **理论首创性**：首次建立了分散式多智能体SSP在线性函数近似下的遗憾下界，填补了该领域的理论空白。
- **构造精巧**：设计的困难实例具有指数级状态-动作空间，但通过对称性论证和类型划分，使得最优策略和价值函数可解析处理，为分析提供了可行性。
- **方法论创新**：克服了多个挑战，包括：
  - 设计合法线性特征以构造转移概率。
  - 利用状态类型归纳证明最优价值和策略的结构。
  - 通过非负性、对称性和截断技巧有效界定了KL散度，解决了指数项求和困难。
- **匹配已有上界**：下界与[23]的上界在K上匹配（至多对数因子），表明在回合维度上已紧。
- **泛化性**：结果对任意数量的智能体n均成立，且不依赖特定通信协议，适用范围广。

## 8. 不足与局限

- **假设较强**：
  - 需要线性函数近似（线性混合SSP），且成本统一为1（目标状态为零），这是为了简化分析。实际多智能体环境可能不满足这些条件。
  - 实例构造基于两个节点（初始节点和目标节点），虽可推广至更多节点，但证明依赖于特定结构。
- **理论而非实证**：作为纯理论工作，缺乏在仿真或真实数据集上的实验验证，无法直观展现下界的紧致性或算法在实际中的表现。
- **指数衰减的解释**：下界随n指数衰减，论文解释为n增大时近优策略增多使学习更困难，但该衰减可能源于实例构造的特殊性，而非普遍性质。更通用的下界可能具有不同标度。
- **未考虑通信影响**：论文不限制通信协议，但下界推导未明确量化通信程度对学习复杂度的影响。实际中，通信可降低难度，而下界可能因此上移。
- **复杂性未充分揭示**：下界仅与K和d有关，未体现与状态空间大小（2^n）直接明显的依赖（通过B^*间接体现），可能低估了维度灾难的影响。

（完）
