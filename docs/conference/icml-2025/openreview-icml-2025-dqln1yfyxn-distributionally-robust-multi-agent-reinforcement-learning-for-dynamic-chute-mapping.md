---
title: Distributionally Robust Multi-Agent Reinforcement Learning for Dynamic Chute Mapping
title_zh: 用于动态滑坡映射的分布鲁棒多智能体强化学习
authors: "Guangyi Liu, Suzan Iloglu, Michael Caldara, Joseph W Durham, Michael M. Zavlanos"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DqlN1yFyxN"
tags: ["query:marl"]
score: 9.0
evidence: 直接使用多智能体强化学习框架
tldr: 亚马逊仓库的动态滑坡映射问题因包裹投递率不确定而具有挑战性。本文提出分布鲁棒多智能体强化学习框架，使用群体分布鲁棒优化学习策略，使其在平均情况和各子群体上均表现良好。实验证明该方法能有效减少包裹回流，提高系统鲁棒性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 849, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 848, \"height\": 186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 851, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 848, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1747, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1749, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1400, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1306, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dqln1yfyxn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1299, \"height\": 643, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dqln1yfyxn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dqln1yfyxn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dqln1yfyxn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dqln1yfyxn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dqln1yfyxn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 491, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dqln1yfyxn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1776, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dqln1yfyxn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1651, \"height\": 894, \"label\": \"Table\"}]"
motivation: 动态滑坡映射中投递率不确定导致包裹回流增加，传统方法难以应对。
method: 提出分布鲁棒多智能体强化学习框架，结合群体分布鲁棒优化学习抗干扰映射策略。
result: 在亚马逊仓库场景下，所提方法显著降低了包裹回流率，提升了系统鲁棒性。
conclusion: 分布鲁棒优化能有效增强多智能体强化学习在动态环境下的稳定性和性能。
---

## Abstract
In Amazon robotic warehouses, the destination-to-chute mapping problem is crucial for efficient package sorting. Often, however, this problem is complicated by uncertain and dynamic package induction rates, which can lead to increased package recirculation. To tackle this challenge, we introduce a Distributionally Robust Multi-Agent Reinforcement Learning (DRMARL) framework that learns a destination-to-chute mapping policy that is resilient to adversarial variations in induction rates. Specifically, DRMARL relies on group distributionally robust optimization (DRO) to learn a policy that performs well not only on average but also on each individual subpopulation of induction rates within the group that capture, for example, different seasonality or operation modes of the system. This approach is then combined with a novel contextual bandit-based estimator of the worst-case induction distribution for each state-action pair, significantly reducing the cost of exploration and thereby increasing the learning efficiency and scalability of our framework. Extensive simulations demonstrate that DRMARL achieves robust chute mapping in the presence of varying induction distributions, reducing package recirculation by an average of 80% in the simulation scenario.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

亚马逊机器人分拣仓库中的“目的地-溜槽映射”问题需要动态分配有限数量的溜槽给不同目的地，以最小化包裹再循环。然而，包裹投递率（induction rate）具有很强的时空不确定性，包括季节性波动、年度增长等。传统的多智能体强化学习（MARL）策略在训练分布与部署分布一致时性能良好，但面对投递分布偏移时性能显著下降（例如训练于第1年数据，测试于第2-4年数据，再循环率相对退化）。为此，论文提出一种**分布鲁棒多智能体强化学习（DRMARL）框架**，旨在学习对投递率变化具有鲁棒性的溜槽映射策略。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想

- 利用**群体分布鲁棒优化（Group DRO）**：将历史数据划分为多个“群体”（每个群体代表一种典型的投递分布模式，如不同星期、不同年份），构建一个由这些群体概率组合构成的模糊集。优化目标是最小化**最差情况群体**下的损失（或最大化最差情况回报），从而保证策略在所有群体上表现良好。

### 关键技术细节

1. **分布鲁棒贝尔曼算子**（Lemma 3.2）：
   - 定义：$\tilde{\mathcal{T}}_G(\tilde{Q})(s,a) = \inf_{g\in G} \mathbb{E}_{X\sim P_g}[r(s,a;X)] + \gamma \max_{a'}\tilde{Q}(s',a')$。
   - 该算子是压缩映射，保证Q-learning收敛到唯一不动点。

2. **基于上下文老虎机（Contextual Bandit）的最坏情况奖励估计器**：
   - 状态-动作对 $(s,a)$ 作为上下文，臂为各个群体 $g \in G$，目标是用Q网络 $Q_{\text{CB}}(s,a,g;\psi)$ 预测每个群体的期望奖励，从而在线找出最坏情况群体 $g' = \arg\min_g Q_{\text{CB}}(s,a,g)$。
   - 训练过程（Algorithm 1）使用现有MARL策略探索，收集数据更新CB网络。复杂度从 $O(m)$ 降为 $O(1)$。

3. **DRMARL训练流程**（Algorithm 2）：
   - 初始化策略网络 $\tilde{Q}$ 和重放缓冲区。
   - 每步：用 $\epsilon$-贪心选择动作，用预训练的CB估计最坏群体 $g'$，执行动作并观察奖励、下一状态，存储经验；采样小批量更新 $\tilde{Q}$ 的损失函数（使用最坏奖励和下一个状态的最大Q值）。
   - 损失函数：$\tilde{L}(\theta) = \mathbb{E}_{s,a,r,s'}[(\tilde{Q}(s,a;\theta) - \mathbb{E}_{X\sim P_{g'}}[r] - \gamma \max_{a'}\bar{\tilde{Q}}(s',a';\bar{\theta}))^2]$。

## 3. 实验设计

### 数据集/场景
- **简化仿真**：10个溜槽、1个再循环溜槽、20个目的地；5小时一天，步长30分钟；投递分布为9个不同均值的高斯分布（群体 $G=9$）。
- **大规模仿真**：187个溜槽、1个再循环溜槽、120个目的地；11小时一天，步长5分钟；使用来自4年历史数据构造的21个分布群体（基于周次），每个群体用样本平均近似估计为多项分布。

### 基准方法
- **MARL**：标准MARL（训练于Year4数据）。
- **DRMARL (random)**：随机选择群体。
- **DRMARL (exhaustive)**：穷举最坏群体（计算量大，理论最优鲁棒）。
- **DRMARL (with $Q_{\text{CB}}$)**：本文提出的CB方法。
- **MARL (group-specific)**：每组单独训练和测试（每组最优性能，作为上界）。
- **三种鲁棒RL基线**：对抗智能体、对抗环境、鲁棒MDP（基于最坏奖励函数）。

### 评估指标
- 再循环率、吞吐量、再循环数量、条件风险价值（CVaR@5%）、最坏情况再循环量。

## 4. 资源与算力

- 论文未明确指定使用的GPU型号和数量，但提到**训练主要在CPU上进行**，因为环境仿真计算量大。
- 大规模实验中，DRMARL with exhaustive search 需要约**924小时**（64 vCPUs, Intel Xeon Scalable 4th gen, 128GB RAM），而CB方法显著减少了耗时。
- 简化实验中，CB方法收敛时间约300秒，穷举超过2900秒。

## 5. 实验数量与充分性

- **简化环境**：9组群体 × 每个组100次运行，共900次测试（表1数据来自9组均值±标准差）。
- **大规模环境**：21组群体 × 每个组5次实验（表2和表7给出详细数据）。
- **消融实验**：变化溜槽数量（图13）和目的地数量（图14），评估DRMARL在不同系统规模下的相对改善。
- **分布外测试**（图7）：测试策略在模糊集外分布下的泛化能力（Wasserstein距离818 vs 组内平均543）。
- **鲁棒方法对比**（表3）：比较DRMARL与三种基线，使用CVaR、最坏情况再循环等。
- **CB估计精度**（图8、图11）：验证CB的预测误差小于1%再循环率，近似贝尔曼算子误差<0.57%。

**充分性评价**：实验覆盖了多种场景、多种对比方法、关键消融和鲁棒性测试，数据统计量（均值、标准差）完整，结果客观公平。尤其是大规模环境使用了真实仓库布局参数，具有较高实际意义。

## 6. 主要结论与发现

- **DRMARL在所有群体上平均降低再循环率80%**，提升吞吐量5.62%。
- **DRMARL (with $Q_{\text{CB}}$) 性能接近穷举搜索**（再循环率0.56% vs 0.55%），且训练时间从>2900秒减少到<300秒（简化环境），从约924小时大幅缩短（大规模环境）。
- **DRMARL在模糊集外分布上也表现良好**，优于标准MARL。
- 相比其他鲁棒RL方法，DRMARL在CVaR、最坏情况再循环上全面占优，因其显式优化最坏分布。
- CB估计器能够高效准确地识别最坏情况群体，且误差很小。

## 7. 优点

1. **方法创新性**：首次将群体DRO与MARL结合，并引入上下文老虎机进行高效最坏情况估计，解决了分布鲁棒强化学习的计算瓶颈。
2. **理论扎实**：证明了分布鲁棒贝尔曼算子的压缩性质，保证了收敛性；利用线性规划对偶性将无限维DRO问题简化为有限维。
3. **计算效率**：CB方法将最坏情况识别的复杂度从 $O(m)$ 降为 $O(1)$，使得大规模实际部署可行。
4. **鲁棒性强**：不仅对训练集内分布有效，对分布外也泛化良好；在多种消融条件下保持优势。
5. **消融全面**：探讨了溜槽数量、目的地数量等系统参数变化的影响，证明了方法的稳健性。
6. **实际意义**：直接应用于亚马逊仓库的溜槽分配，可显著降低能耗、提高效率，具有工业价值。

## 8. 不足与局限

1. **近似贝尔曼算子上界**：在大规模环境中，由于转移概率也依赖投递分布，实际使用的算子 $\tilde{U}_R$ 是真实鲁棒算子的上界（误差<0.57%），但理论最优性未被严格保证。
2. **在极端场景下保守性**：当仅剩50%目的地活跃时，MARL表现超过DRMARL，因为DRMARL的策略为可能不存在的未来目的地保留溜槽，显得过于谨慎。
3. **假设历史群体能覆盖未来**：该方法假设未来分布可表示为历史群体的凸组合，但若出现全新模式（如突发事件），则无法保证鲁棒。
4. **未在真实仓库部署验证**：实验均在仿真中进行，真实环境中的噪声、机器人拥堵、传感器误差等未被充分建模。
5. **算力需求仍较高**：虽然CB比穷举高效，但DRMARL训练仍需数十到数百小时，对于更复杂环境可能需要更多资源。
6. **可解释性**：基于深度Q网络的方法缺乏对策略决策机理的直观解释，实际运营中调试困难。

（完）
