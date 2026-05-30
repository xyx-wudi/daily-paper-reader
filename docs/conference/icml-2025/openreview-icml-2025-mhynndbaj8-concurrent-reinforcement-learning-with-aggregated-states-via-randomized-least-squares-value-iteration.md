---
title: Concurrent Reinforcement Learning with Aggregated States via  Randomized Least Squares Value Iteration
title_zh: 基于随机最小二乘值迭代的聚合状态并发强化学习
authors: "Yan Chen, Qinxun Bai, Yiteng Zhang, Maria Dimakopoulou, Shi Dong, Qi Sun, Zhengyuan Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=MhYnnDBAJ8"
tags: ["query:marl"]
score: 8.0
evidence: 多智能体并发探索的理论研究
tldr: 在复杂环境中多智能体如何高效探索是挑战。本文将随机最小二乘值迭代扩展到并发学习框架，在聚合状态表示下建立多项式后悔界。理论证明随机化有助于多智能体协作探索，为分布式多智能体强化学习提供理论基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mhynndbaj8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 775, \"height\": 1025, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mhynndbaj8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 445, \"label\": \"Table\"}]"
motivation: 单智能体随机化探索有效，但多智能体并发探索的理论未知。
method: 将随机最小二乘值迭代扩展到并发多智能体学习，使用聚合状态表示。
result: 给出多项式遗憾上界，证明随机化可促进多智能体探索。
conclusion: 随机化价值函数是提升多智能体系统探索效率的有效工具。
---

## Abstract
Designing learning agents that explore efficiently in a complex environment has been widely recognized as a fundamental challenge in reinforcement learning. While a number of works have demonstrated the effectiveness of  techniques based on randomized value functions on a single agent, it remains unclear, from a theoretical point of view, whether injecting randomization can help a society of agents concurently explore an environment. The theoretical results established in this work tender an affirmative answer to this question. We adapt the concurrent learning framework to randomized least-squares value iteration (RLSVI) with aggregated state representation. 
We demonstrate polynomial worst-case regret bounds in both finite- and infinite-horizon environments.
In both setups the per-agent regret decreases at an optimal rate of $\Theta\left(\frac{1}{\sqrt{N}}\right)$, highlighting the advantage of concurent learning. Our algorithm exhibits significantly lower space complexity compared to Russo (2019) and Agrawal et. al (2021). We reduce the space complexity by a factor of $K$ while incurring only a $\sqrt{K}$ increase in the worst-case regret bound, compared to Russo (2019) and Agrawal et. al (2021). Interestingly, our algorithm improves the worst-case regret bound of Russo (2019) by a factor of $H^{1/2}$, matching the improvement in Agrawal et. al (2021). However, this result is achieved through a fundamentally different algorithmic enhancement and proof technique. Additionally, we conduct numerical experiments to demonstrate our theoretical findings.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：单智能体中的随机化探索（如随机最小二乘值迭代 RLSVI）已被证明有效，然而在多智能体并发学习场景下，随机化是否能帮助一群智能体协同高效地探索复杂环境，在理论上尚不明确。
- **核心问题**：本文首次从理论角度证明，在聚合状态表示下，并发运行 RLSVI 算法的智能体群体能够实现多项式级的后悔界，且每个智能体的平均后悔以最优速率 \(\Theta(1/\sqrt{N})\) 下降，凸显了并发学习的优势。
- **背景**：现有并发学习理论主要集中在模型基算法（如 PSRL），模型无关算法缺乏理论分析；同时，高空间复杂度（存储所有历史轨迹）在实际大规模多智能体系统中不可行。本文填补了模型无关并发 RL 的理论空白，并兼顾了计算可行性。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将随机最小二乘值迭代（RLSVI）扩展到并发多智能体框架，利用聚合状态表示降低统计复杂度，仅存储上一轮（或上一伪回合）的交互数据以降低空间复杂度，并通过加权平均实现智能体间的信息共享。
- **技术细节**：
  - **聚合状态表示**：将状态-动作空间划分为 \(\Gamma\) 个聚合状态，每个聚合状态的值函数近似所有原始状态的 Q 值，容许 \( \epsilon \)-误差。
  - **算法流程**（有限视野，仅存储最后一次回合）：
    1. 初始化：所有聚合状态值设为 H，随机采样初始回合。
    2. 每轮 \((k)\)：每个智能体从上一轮数据计算经验转移和奖励，并添加高斯噪声（\(\mathcal{N}(0,\sigma^2)\)）扰动奖励，构造扰动 MDP。
    3. 每个智能体通过最小化正则化损失函数（包含 temporal difference 误差和正则项）求解聚合状态的 Q 值，并取 min(H) 作为截断值。
    4. 回合结束后，所有智能体基于访问次数加权平均各自 Q 值，更新全局 Q 函数。
  - **正则化损失函数**：包含偏差项 \(\xi\)、上一轮 Q 值（带权重 \(1-\alpha\)）和当前经验 + 随机噪声项（带权重 \(\alpha\)），其中 \(\alpha_n = 1/(1+n)\)。
  - **空间复杂度**：存储所有历史数据时为 \(O(KHN)\)，仅存储上一回合为 \(O(HN)\)（有限视野）或 \(O(TN)\)（无限视野）。
- **理论基础**：推导出有限视野下最坏情况后悔界 \(\tilde{O}(\epsilon KHN + KH^{5/2}\Gamma\sqrt{N})\)（仅存一回合）和 \(\tilde{O}(\epsilon\sqrt{K}HN + H^{5/2}\Gamma\sqrt{KN})\)（存全部历史）；无限视野下类似，其中 \(\tau\) 代替 H。

### 3. 实验设计：数据集 / 场景、基准方法、对比方法

- **数据集/环境**：使用合成的 MDP 环境：
  - 有限视野：\((S,A,K,H)\) 分别为 (5,5,20,30)、(10,10,25,40)、(20,20,30,50)。
  - 无限视野：\(T=300\)，\((S,A)\) 分别为 (5,5)、(20,20)、(30,30)，折现因子 \(\eta=0.99\)。
  - 转移概率从 Dirichlet 分布抽样，奖励在 [0,1] 上均匀分布且确定。
- **基准方法**：未与具体算法进行实验对比，而是与理论下界（\(1/\sqrt{N}\) 趋势）和先前工作（Russo 2019, Agrawal 2021）的理论界比较。
- **对比方法**：仅在理论表格（Table 1）中列出了 Russo(2019)、Agrawal(2021) 等方法的 regret 界和空间复杂度，但实验中未实现这些方法进行对比。

### 4. 资源与算力

- 文中**未明确提及**实验所用的计算资源（GPU 型号、数量、训练时长等）。
- 仅说明代码开源（GitHub 链接），但未提供算力细节。

### 5. 实验数量与充分性

- **实验数量**：
  - 有限视野：3 种规模，每种规模测试 N 从 1 到 50（共 10 个数值），每个 N 采样 500 个随机 MDP。
  - 无限视野：3 种规模，同样测试 10 个 N 值，每个 MDP 采样 50 次几何分段，取最坏 regret。
- **充分性评价**：实验覆盖了不同状态-动作空间规模和不同智能体数量，并验证了 \(1/\sqrt{N}\) 趋势，与理论吻合。但**缺乏与现有算法（如单智能体 RLSVI 变体、UCB 方法等）的对比实验**，无法体现算法在实际中的相对优势。此外，未进行消融研究（如分析存储历史长度、聚合粒度、噪声强度等的影响）。因此实验虽足以证明理论趋势，但公平性和完整性有限。

### 6. 论文的主要结论与发现

- 并发运行 RLSVI 算法在聚合状态表示下，能够实现最坏情况后悔界与 \(\sqrt{N}\) 成正比（总后悔）或 \(1/\sqrt{N}\) 成正比（每个智能体）。
- 仅存储上一回合数据可以将空间复杂度降低 \(K\) 倍，而代价仅为后悔界增加 \(\sqrt{K}\) 因子，具有良好实践性。
- 算法在有限视野下改进了 Russo(2019) 的后悔界至少 \(H^{1/2}\) 因子，与 Agrawal(2021) 相当但方法不同。
- 数值实验验证了每个智能体平均后悔随 N 增加以 \(1/\sqrt{N}\) 速率下降的理论预测。

### 7. 优点

- **理论贡献突出**：首次为模型无关并发 RL（RLSVI）提供严格的最坏情况后悔界分析。
- **实际可行性**：通过仅存储最近一次回合的数据，大幅降低空间复杂度和计算开销，适合大规模多智能体系统。
- **统一分析框架**：同时覆盖有限视野和无限视野（利用几何分布伪回合），并将折现因子视为算法参数而非目标函数组成部分，符合实际用法。
- **聚合状态表示**：允许在状态-动作空间很大时有效控制统计复杂度，并处理近似误差。

### 8. 不足与局限

- **实验对比不足**：未与现有方法（如蒙特卡洛树搜索、UCB 类算法、其他并发算法如 Taiga et al. 2022）进行直接数值比较，无法评测算法在实际性能上的提升。
- **依赖强假设**：假设环境为弱通信 MDP，且最优策略的奖励平均时间有界（Assumption 6），限制了算法在一般环境中的适用性。
- **忽略通信开销**：算法假设智能体可以完美共享数据，未讨论实际分布式系统中的通信延迟、隐私等问题。
- **缺少消融和灵敏度分析**：未探讨聚合粒度 \(\Gamma\)、噪声方差 \(\beta\) 等超参数对性能的影响。
- **实验环境为合成 MDP**：缺乏真实世界或高维连续控制任务的验证，结果推广性存疑。
- **理论界限可能不紧**：仅给出上界，未证明匹配的下界。

（完）
