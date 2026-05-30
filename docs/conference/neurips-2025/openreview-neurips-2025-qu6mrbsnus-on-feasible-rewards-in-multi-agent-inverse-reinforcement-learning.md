---
title: On Feasible Rewards in Multi-Agent Inverse Reinforcement Learning
title_zh: 多智能体逆向强化学习中的可行奖励
authors: "Till Freihaut, Giorgia Ramponi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=qu6mRbSnUs"
tags: ["query:marl"]
score: 8.0
evidence: 马尔可夫博弈中可行奖励集合的表征
tldr: 针对多智能体逆向强化学习中的奖励函数恢复问题，该论文在马尔可夫博弈中刻画了可行奖励集合，识别出所有能够理性化给定均衡的奖励函数。通过引入熵正则化的马尔可夫博弈，确保唯一均衡同时保留战略激励，并提供了样本复杂度分析。这项工作为MAIRL奠定了理论基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qu6mrbsnus/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1033, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qu6mrbsnus/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1345, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qu6mrbsnus/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1302, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qu6mrbsnus/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1423, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qu6mrbsnus/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1398, \"height\": 338, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qu6mrbsnus/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 1933, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qu6mrbsnus/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 756, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qu6mrbsnus/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 760, \"height\": 289, \"label\": \"Table\"}]"
motivation: 基于均衡的观测具有歧义性，单个均衡对应多种奖励结构，影响多智能体系统的性质。
method: 引入熵正则化马尔可夫博弈，确保唯一均衡，并给出样本复杂度分析。
result: 完整刻画了可行奖励集合，并推导了学习误差对策略性能的影响。
conclusion: 为多智能体逆向强化学习提供了坚实的理论基础和实用见解。
---

## Abstract
Multi-agent inverse reinforcement learning (MAIRL) aims to recover agent reward functions from expert demonstrations. We characterize the feasible reward set in Markov games, identifying all reward functions that rationalize a given equilibrium. However, equilibrium-based observations are often ambiguous: a single Nash equilibrium can correspond to many reward structures, potentially changing the game's nature in multi-agent systems. We address this by introducing entropy-regularized Markov games, which yield a unique equilibrium while preserving strategic incentives. For this setting, we provide a sample complexity analysis detailing how errors affect learned policy performance. Our work establishes theoretical foundations and practical insights for MAIRL.

---

## 论文详细总结（自动生成）

# 多智能体逆向强化学习中的可行奖励：论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **多智能体逆向强化学习（MAIRL）** 旨在从专家演示中恢复智能体的奖励函数。相比单智能体IRL，多智能体场景由于智能体间的策略依赖性和纳什均衡（NE）的多样性，问题更加复杂。
- **核心歧义性**：一个给定的纳什均衡可能对应无数种奖励结构，甚至可能改变博弈的性质（例如将协调博弈变为反协调博弈），导致恢复的奖励函数缺乏意义。
- **研究目标**：刻画马尔可夫博弈中的可行奖励集合，解决均衡选择问题，并分析奖励可辨识性及样本复杂度，为MAIRL奠定理论基础。

## 2. 方法论：核心思想、关键技术细节、算法与公式

- **可行奖励集定义（单均衡观测）**：  
  - 定义3.1：对于给定的MAIRL问题 \((G, \pi^{\text{Nash}})\)，可行奖励集 \(R(G, \pi^{\text{Nash}})\) 包含所有在该奖励下 \(\pi^{\text{Nash}}\) 仍为纳什均衡的奖励函数。
  - 局限性（命题3.4）：仅观测一个均衡会导致可行集过大，恢复的奖励可能引入新的均衡，导致在原始博弈中的纳什间隙达到 \((1-\gamma)^{-1}\) 量级。

- **基于熵正则化的唯一均衡（QRE）**：  
  - 引入熵正则化马尔可夫博弈（带参数 \(\lambda\)），其均衡为唯一的**分位数反应均衡（Quantal Response Equilibrium, QRE）**，消除了均衡选择问题。
  - 引理3.6（可行奖励显式表征）：对于两玩家情形，可行奖励可由值函数 \(V\) 和 \(|B|-1\) 个自由函数显式表示：
    \[
    R(s,a,b) = \frac{1}{\nu^*(b|s)}\Bigl( \lambda\log\mu^*(a|s) + V(s) - \gamma\sum_{s',b'}\nu^*(b'|s)P(s'|s,a,b')V(s') - \sum_{b'\neq b}\nu^*(b'|s)R(s,a,b') \Bigr).
    \]
  - 定理3.7（误差传播）：真实奖励与估计奖励的差受限于策略对数误差、转移模型误差和对手策略的总变差。

- **样本复杂度分析**：  
  - 假设访问生成模型（均匀采样），采用经验估计器（式(12)-(14)）。  
  - 定理3.9：在假设3.8（最小动作概率 \(\Delta_{\min}>0\)）下，均匀采样算法达到最优准则的样本复杂度为
    \[
    \tilde{O}\left( \frac{\gamma^2 R_{\max}^2 |S||A||B|}{(1-\gamma)^4 \varepsilon^2 \Delta_{\min}^4} \right).
    \]
  - 该复杂度与动作空间乘积 \(|A||B|\) 线性相关，与多智能体强化学习中学习NE的下界一致。

- **奖励可辨识性**：  
  - 平均奖励可辨识（定理4.1）：若存在两个不同对手策略诱导不同转移矩阵，且满足秩条件（式(3)），则可恢复平均奖励 \(R^\nu(s,a)\) 至多一个常数。  
  - 线性可分奖励下的可辨识性（命题4.3）：若 \(R(s,a,b)=R_A(s,a)+R_B(s,b)\)，且对手策略不同，则在特定归一化下可恢复完整奖赏（秩条件需满足）。

## 3. 实验设计

- **场景与环境**：
  - 使用**3×3 Grid World**（与Hu and Wellman, 2003类似），两个智能体有不同的目标位置，转移概率在部分状态上随机化。
  - 对比**均匀采样 MAIRL 算法**（采用Max Gap方法从可行集中选取奖励）与**行为克隆（BC）**。
- **评估指标**：
  - **纳什间隙（Nash Gap）**：定义3.2，度量恢复策略在真实博弈中的可剥削性。
- **数据集**：
  - 无外部数据集。专家策略通过**NashQ-Learning**在确定性环境中训练得到。
- **实验结果**：
  - 图2表明单NE观测导致可行奖励集产生大量新均衡，平均纳什间隙大。
  - 图3显示QRE观测可避免新纯均衡出现，且恢复奖励与真实奖励相关性高（Pearson & Spearman）。
  - 图4对比了不同转移概率（p=1.0,0.5,0.0）下均匀采样MAIRL与BC的纳什间隙：BC在原始环境较好，但环境变化后MAIRL更优。
  - 图5展示了障碍物环境下BC失败（智能体1无法到达目标），而MAIRL仍能传递奖励。

## 4. 资源与算力

- 论文**未明确提及**使用的GPU型号、数量或训练时长。
- 实验为小规模Grid World（状态数少，动作数2），推测基于CPU完成，算力需求很低。

## 5. 实验数量与充分性

- **实验数量**：主要理论论文，实验为辅助验证。具体组数：
  - 单NE观测实验（图2）：重复10000次统计平均新均衡数和纳什间隙。
  - QRE观测实验（图3）：类似重复10000次，统计频率和相关指标。
  - 转移学习实验（图4）：三个转移概率场景，每个场景随样本量变化画曲线（未指明重复次数，但应有多次运行以显示趋势）。
  - 障碍物实验（图5）：定性示例，展示路径。
- **充分性评估**：
  - 实验**针对性地支持了理论结论**，例如单NE的歧义性、QRE的优越性、MAIRL优于BC在转移场景。
  - 但**覆盖面有限**：仅一种Grid World环境，动作集小，未在复杂博弈（如大规模随机博弈）上验证。
  - 公平性：对比方法BC是直接克隆专家动作，未与其他MAIRL算法（如MA-GAIL）比较，因后者不直接解决奖励恢复问题。

## 6. 主要结论与发现

1. **单均衡观测不足**：仅观测一个NE会导致可行奖励集过大，恢复的奖励可能引入新均衡，使策略在原始博弈中高度可剥削（纳什间隙达\((1-\gamma)^{-1}\)量级）。
2. **熵正则化带来唯一均衡**：引入QRE后，可行奖励集更紧凑，奖励恢复与真实奖励的相关性显著提高。
3. **误差传播与样本复杂度**：给出了奖励误差关于转移估计、策略估计和对手策略估计的显式上界，并推导出均匀采样算法达到\(\varepsilon\)-最优准则所需的样本复杂度（与\((1-\gamma)^{-4}\)、\(|S||A||B|\)、\(\Delta_{\min}^{-4}\)相关）。
4. **可辨识性条件**：
   - 多智能体一般情况只能恢复**平均奖励**（至多一个常数）。
   - 若奖励**线性可分**，且满足特定秩条件，则可完整恢复（至多一个常数）。

## 7. 优点

- **理论贡献扎实**：首次系统定义并分析了MAIRL的可行奖励集，揭示了均衡歧义性的根本困难。
- **引入QRE解决均衡选择**：提供了实用方向，且QRE本身具有行为合理性（有限理性）。
- **完整的误差传播与样本复杂度分析**：为后续算法设计提供了理论基准。
- **可辨识性分析**：明确了多智能体场景下奖励恢复的固有难度和可行条件，区分了平均奖励和具体奖赏的识别。
- **实验设计巧妙**：用简单博弈直观展示了理论结论（单NE vs QRE、MAIRL vs BC）。

## 8. 不足与局限

- **生成模型假设**：均匀采样所有状态-动作-智能体三元组，在实际应用中（尤其状态空间大时）不可行。论文在结论中承认需要探索离线或主动探索设置。
- **样本复杂度依赖乘积动作空间**：多智能体下指数增长（\(|A||B|\)），限制了扩展性。
- **实验范围狭窄**：仅使用3×3 Grid World，动作集小；未在更复杂的多智能体博弈（如随机博弈、大规模博弈）上验证。结果的可泛化性有待证实。
- **缺乏与其他MAIRL算法的定量对比**：只对比了BC，未与现有的MAIRL方法（如GAIL的多智能体变体）比较奖励恢复质量或策略性能。
- **理论假设较强**：如\(\Delta_{\min}>0\)（动作概率有正下界）、大量均匀采样等，在实际中可能不成立。
- **线性可分奖励假设较苛刻**：现实奖励往往耦合，难以直接分解。

（完）
