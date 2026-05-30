---
title: "Solving Continuous Mean Field Games: Deep Reinforcement Learning for Non-Stationary Dynamics"
title_zh: 求解连续平均场博弈：面向非平稳动力学的深度强化学习
authors: "Lorenzo Magnino, Kai Shao, Zida Wu, Jiacheng Shen, Mathieu Lauriere"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Jw5TFF3HkH"
tags: ["query:marl"]
score: 7.0
evidence: 大规模多智能体系统中非平稳连续平均场博弈的深度强化学习
tldr: 平均场博弈(MFGs)为大规模多智能体系统建模提供强大框架，但现有方法局限于有限空间或平稳模型。本文提出一种深度强化学习算法，基于虚拟博弈方法，利用DRL进行最佳响应计算，并采用条件归一化流学习时变种群分布，从而解决非平稳连续MFGs。实验表明算法在连续空间上有效收敛且优于先前方法，拓展了平均场博弈的实践应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1410, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 544, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1104, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1316, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1189, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1316, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1220, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1214, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1412, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1408, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 857, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1429, \"height\": 1354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jw5tff3hkh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1430, \"height\": 1353, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jw5tff3hkh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1336, \"height\": 348, \"label\": \"Table\"}]"
motivation: 现有用于平均场博弈的RL方法局限于有限空间或平稳模型，无法处理现实问题。
method: 结合虚拟博弈、深度强化学习和条件归一化流，学习时变种群分布。
result: 在连续非平稳MFG基准上，所提算法显著优于现有方法，收敛稳定。
conclusion: 本文首次将深度RL扩展到非平稳连续平均场博弈，拓展了应用范围。
---

## Abstract
Mean field games (MFGs) have emerged as a powerful framework for modeling interactions in large-scale multi-agent systems. Despite recent advancements in reinforcement learning (RL) for MFGs, existing methods are typically limited to finite spaces or stationary models, hindering their applicability to real-world problems. This paper introduces a novel deep reinforcement learning (DRL) algorithm specifically designed for non-stationary continuous MFGs. The proposed approach builds upon a Fictitious Play (FP) methodology, leveraging DRL for best-response computation and supervised learning for average policy representation. Furthermore, it learns a representation of the time-dependent population distribution using a Conditional Normalizing Flow. To validate the effectiveness of our method, we evaluate it on three different examples of increasing complexity. By addressing critical limitations in scalability and density approximation, this work represents a significant advancement in applying DRL techniques to complex MFG problems, bringing the field closer to real-world multi-agent systems.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

大规模多智能体系统中，智能体之间的策略交互使得学习变得极具挑战性。当智能体数量增多，联合策略空间急剧膨胀，传统多智能体强化学习（MARL）方法计算上难以处理。**平均场博弈（Mean Field Games, MFGs）** 通过建模一个代表性智能体与演化群体分布之间的交互，为近似此类大规模系统提供了原则性框架。尽管近年来在MFGs的强化学习（RL）方面取得了进展，现有方法通常局限于**有限状态/动作空间**或**平稳（stationary）模型**，无法处理现实世界中常见的连续状态-动作空间和非平稳（time-dependent）动力学。本文旨在解决这一关键空白，提出首个能够学习非平稳连续MFGs纳什均衡策略和群体分布的深度强化学习算法。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 2.1 核心思想
本文提出的**Density-Enhanced Deep-Average Fictitious Play（DEDA-FP）**，基于**虚拟博弈（Fictitious Play, FP）** 框架，通过深度强化学习（DRL）计算最佳响应，利用监督学习近似平均策略，并采用**条件归一化流（Conditional Normalizing Flow, CNF）** 学习时变群体分布。该方法首次实现了对连续空间非平稳MFGs的完整求解（同时获得均衡策略和均衡分布）。

### 2.2 关键技术细节

- **动力学与奖励**：考虑一般性的非平稳动力学：\(x_{t+1} \sim P_t(\cdot | x_t, a_t, \mu_t)\)，其中\(\mu_t\)为t时刻群体分布。奖励函数\(r(x,a,\mu)\)可能依赖于局部密度（如拥塞惩罚）。
- **纳什均衡定义**：寻找策略\(\pi^*\)和分布\(\mu^*\)，使得\(\pi^*\)在\(\mu^*\)下是最优反应，且\(\mu^*\)由\(\pi^*\)生成。
- **虚拟博弈迭代**：每轮迭代k中，计算当前平均分布\(\bar{G}_{k-1}\)下的最佳响应策略\(\pi^*_k\)；然后通过监督学习更新平均策略网络\(\bar{\pi}_k\)（使其逼近所有历史最佳响应的平均）；再通过CNF学习平均分布\(\bar{G}_k\)（由\(\bar{\pi}_k\)生成）。
- **条件归一化流（CNF）**：采用神经样条流（Neural Spline Flow）结合自回归层，以时间t为条件，实现从简单基分布到目标分布的变换，同时支持采样和密度估计。

### 2.3 算法流程（文字说明）

1. **初始化**：随机初始化策略网络\(\pi_{\theta_0^*}\)和平均策略网络\(\bar{\pi}_{\bar{\theta}_0}\)；收集初始状态-动作对存入监督学习缓冲区\(M_{SL}\)。
2. **对k=1到K迭代**：
   - 使用DRL（SAC或PPO）计算针对前一轮平均分布\(\bar{G}_{k-1}\)的最佳响应\(\pi^*_k\)。
   - 收集\(\pi^*_k\)的轨迹样本存入\(M_{SL}\)。
   - 通过极大似然估计（最小化负对数似然）训练平均策略网络\(\bar{\pi}_{\bar{\theta}_k}\)。
   - 通过CNF训练平均分布\(\bar{G}_k\)，使其逼近由\(\bar{\pi}_k\)生成的真实分布。
3. **返回**：最终策略\(\bar{\pi}_K\)和分布\(\bar{G}_K\)作为纳什均衡解。

### 2.4 收敛性理论（定理1）
在假设奖励和转移的Lipschitz连续性下，证明了算法的可剥削性（exploitability）收敛到由三种误差（最佳响应误差、平均策略近似误差、分布近似误差）之和限定的界限，即算法收敛到近似纳什均衡。

## 3. 实验设计

- **场景与数据集**：论文设计了三个复杂度递增的实验环境：
  1. **海滩酒吧问题（Beach Bar Problem）**：一维连续状态空间，奖励包含局部密度惩罚（拥塞避免）。对比了DEDA-FP与两个基准方法。
  2. **线性二次型（LQ）模型**：连续状态/动作空间，线性动力学、二次奖励。验证了方法在已知最优解可求环境下的有效性。
  3. **四房间探索（4-rooms Exploration）**：二维连续状态空间，含障碍墙，奖励含熵最大化项（密度惩罚）。重点测试算法在复杂环境下的密度建模和采样效率。
  此外，附录还包含一个**市场模型（Market Model）** 的额外实验。

- **Benchmark对比方法**：
  - **Algo. 1**：简单虚拟博弈方法（无平均策略学习，仅从行为缓冲区均匀采样）。
  - **Algo. 2**：学习平均策略，但仅用经验轨迹近似分布，无生成模型。
  - **DEDA-FP（Algo. 3）**：本文提出的完整方法。

- **评价指标**：近似可剥削性（exploitability），计算方式为最佳响应奖励与当前策略奖励之差。所有实验进行4次独立运行，报告均值和标准差。

## 4. 资源与算力

论文明确指出：使用**RTX4090 GPU（24 GB RAM）** 进行所有实验。训练过程中，DRL采用Stable Baselines库（SAC用于前两个例子，PPO用于四房间案例）。但**未明确报告每个实验的详细训练时长**（除了一次性采样5000条轨迹的时间比较：DEDA-FP约1.52秒，Algo.1约16.76秒，Algo.2约15.14秒）。总体计算资源消耗未量化，但属于中等规模。

## 5. 实验数量与充分性

- **实验组数**：共3个主要实验+1个附录实验（市场模型）。每个实验包含4次独立随机种子运行。
- **消融研究**：通过Algo.1、Algo.2与DEDA-FP的对比，间接体现了平均策略学习、密度建模等组件的贡献。未进行更细致的模块消融（如去掉CNF改用经验分布、不同DRL算法对比等）。
- **公平性**：所有算法使用相同的超参数设置（如学习率经初步扫描选定3e-4），但不能完全排除因针对特定环境调参导致的偏差。可剥削性计算基于近似方法，其准确性依赖于环境近似。
- **充分性**：尽管场景涵盖了一维、二维、线性/非线性、局部密度依赖等维度，但缺少高维状态空间（如d>3）或更复杂的非线性动力学验证，推广性仍需更多证据。

## 6. 主要结论与发现

1. DEDA-FP是首个能够求解连续空间非平稳MFGs的深度强化学习算法，同时输出纳什均衡策略和群体分布。
2. 在连续空间上，该方法能有效收敛，可剥削性随迭代次数下降。
3. 条件归一化流（CNF）提供了比经验分布更高效、更准确的密度近似，采样速度显著快于基准（10倍以上），且能直接计算局部密度，避免了卷积近似导致的偏差。
4. 在处理局部密度依赖（如拥塞、熵最大化）时，DEDA-FP显著优于只能依赖经验分布的方法。
5. 提供了理论误差传播分析（定理1），从理论上保证了算法的收敛性到近似纳什均衡。

## 7. 优点

- **创新性突出**：首次将深度RL扩展到非平稳连续MFGs，解决了长期存在的技术瓶颈。
- **方法论完整**：结合虚拟博弈、DRL、监督学习、生成模型，形成了一个端到端的求解框架。
- **实验设计合理**：从简单到复杂逐步验证，直观展示了方法在不同场景下的优势。
- **理论保障**：提供了误差传播定理，对算法收敛性给出了定性分析。
- **工程价值高**：CNF的引入不仅提升了精度，还大幅提高了采样效率，实际部署价值大。

## 8. 不足与局限

- **理论分析不充分**：定理1只给出了误差上界与积累误差的关系，但未提供严格收敛速率或最优性差距，且依赖于较多假设（Lipschitz连续性、均衡唯一性等）。
- **消融研究缺失**：未对DRL算法选择（SAC vs PPO）、CNF架构变体等进行消融，难以判断各部分具体贡献。
- **实验覆盖有限**：仅测试了低维（d=1,2）环境，未验证高维或更复杂动力学的可扩展性。
- **可剥削性近似存在风险**：由于模型自由设置，最佳响应值的计算本身依赖于近似，评价指标的可靠性有待提升。
- **计算成本未系统报告**：GPU内存、训练时间等资源消耗数据不完整，不利于复现和比较。
- **代码未开源**：论文声明“接受后开放代码”，目前无法独立复现结果。

（完）
