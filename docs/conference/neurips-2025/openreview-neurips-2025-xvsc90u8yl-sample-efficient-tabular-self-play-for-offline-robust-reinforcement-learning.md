---
title: Sample-Efficient Tabular Self-Play for Offline Robust Reinforcement Learning
title_zh: 面向离线鲁棒强化学习的样本高效表格自博弈
authors: "Na Li, Zewu Zheng, Wei Ni, Hangguan Shan, Wenjie Zhang, Xinyu Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xVsC90U8yl"
tags: ["query:marl"]
score: 9.0
evidence: 离线多智能体强化学习中的鲁棒双人零和马尔可夫博弈
tldr: 在离线环境下，多智能体强化学习需应对环境不确定性。本文聚焦离线鲁棒双人零和马尔可夫博弈（RTZMGs），提出基于模型的RTZ-VI-LCB算法，结合乐观鲁棒值迭代和数据驱动的伯恩斯坦惩罚项，在部分覆盖下建立了近乎最优的样本复杂度保证，为离线鲁棒马尔可夫博弈提供了首个有限样本保证算法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xvsc90u8yl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 412, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xvsc90u8yl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1173, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xvsc90u8yl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 834, \"height\": 147, \"label\": \"Table\"}]"
motivation: 离线MARL中，环境不确定性要求策略鲁棒，但现有方法缺乏样本复杂度保证。
method: 提出RTZ-VI-LCB算法，采用乐观鲁棒值迭代和伯恩斯坦惩罚项处理分布偏移。
result: 在部分覆盖条件下，算法达到近乎最优的样本复杂度，理论证明完备。
conclusion: 本文为离线鲁棒马尔可夫博弈提供了首个具有有限样本保证的算法。
---

## Abstract
Multi-agent reinforcement learning (MARL), as a thriving field, explores how multiple agents independently make decisions in a shared dynamic environment. Due to environmental uncertainties, policies in MARL must remain robust to tackle the sim-to-real gap. We focus on robust two-player zero-sum Markov games (TZMGs) in offline settings, specifically on tabular robust TZMGs (RTZMGs). We propose a model-based algorithm (*RTZ-VI-LCB*) for offline RTZMGs, which is optimistic robust value iteration combined with a data-driven Bernstein-style penalty term for robust value estimation. By accounting for distribution shifts in the historical dataset, the proposed algorithm establishes near-optimal sample complexity guarantees under partial coverage and environmental uncertainty. An information-theoretic lower bound is developed to confirm the tightness of our algorithm's sample complexity, which is optimal regarding both state and action spaces. To the best of our knowledge, RTZ-VI-LCB is the first to attain this optimality, sets a new benchmark for offline RTZMGs, and is validated experimentally.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究领域**：离线多智能体强化学习（Offline MARL），聚焦鲁棒双人零和马尔可夫博弈（Robust Two-Player Zero-Sum Markov Games, RTZMGs）。
- **核心挑战**：
  - 环境不确定性（sim-to-real 差距）导致标准 MARL 算法易失效；
  - 历史数据仅提供部分且有限的状态-动作空间覆盖（partial coverage）；
  - 现有算法（如 P2M2PO）样本复杂度高（$eO(C_r H^5 S^2 AB / \varepsilon^2)$），且在状态数 S 和动作数 {A,B} 上未达到最优，且未考虑不确定性水平的影响。
- **整体意义**：首次在离线 RTZMGs 中实现关于状态空间 S 和动作空间 {A,B} 的**最优样本复杂度**，并给出匹配的信息论下界，为离线鲁棒多智能体强化学习建立了新基准。

## 2. 方法论

**核心思想**：模型驱动的乐观鲁棒值迭代，结合数据驱动的伯恩斯坦（Bernstein）惩罚项，以同时应对分布偏移和不确定性。

**关键技术细节**：

1. **两阶段子采样（Algorithm 1）**：
   - 将数据集分为 $D_m$ 和 $D_a$，基于 $D_a$ 计算裁剪计数 $N_t(s)$ 用于限制统计依赖性，生成独立同分布近似的子数据集 $D_0$。

2. **经验名义 MDP 的构建**：
   - 通过经验频率估计转移核 $\hat{P}^0$ 和奖励 $\hat{r}_h$，得到替代名义模型。

3. **乐观鲁棒 Q 值更新（公式 15）**：
   - 对最大化玩家：$\hat{Q}^+_h(s,a,b) = \min\left\{ \hat{r}_h + \inf_{P\in U_{\sigma^+}(\hat{P}^0)} P\hat{V}^+_{h+1} + \beta_h(\cdot), H \right\}$；
   - 对最小化玩家：$\hat{Q}^-_h(s,a,b) = \max\left\{ \hat{r}_h + \sup_{P\in U_{\sigma^-}(\hat{P}^0)} P\hat{V}^-_{h+1} - \beta_h(\cdot), 0 \right\}$。

4. **鲁棒贝尔曼算子的对偶求解**：
   - 利用 TV 距离下的强对偶性，将 inf/sup 转化为关于 $\alpha$ 的优化问题，避免直接在高维概率单纯形上优化。

5. **Bernstein 惩罚项**（公式 18）：
   - $\beta_h(s,a,b,\hat{V}) = \min\left\{ \max\left\{ \sqrt{\frac{C_n \log(KH/\delta)}{N_h(s,a,b)} \mathrm{Var}_{\hat{P}^0_{h,s,a,b}}(\hat{V})},\; \frac{2C_n H \log(KH/\delta)}{N_h(s,a,b)} \right\}, H \right\}$，用于捕获方差结构。

6. **策略估计**：
   - 在每个时间步 h 和状态 s，通过求解零和矩阵博弈（使用 `ComputNash` 函数）得到近似 Nash 均衡策略 $(\mu^+_h(s), \nu^+_h(s))$ 和 $(\mu^-_h(s), \nu^-_h(s))$。

7. **多智能体扩展**：
   - 推广至多玩家一般和马尔可夫博弈（Multi-RTZ-VI-LCB），通过类似过程获得 $\tilde{O}(C_r^\star H^4 S \sum A_i / \varepsilon^2 \cdot f(\{\sigma_i\}, H))$ 的样本复杂度，打破“多智能体诅咒”。

## 3. 实验设计

- **数据集/场景**：随机生成的转移核（tabular setting），参数设置 $S=50,\ A=B=2,\ H=100$，初始分布 $\varrho$ 均匀。每个实验在 100 个不同随机种子上平均。
- **Baseline 对比**：仅与**无惩罚项的鲁棒值迭代（RTZ-VI）** 进行比较。在理论表格中与现有最优算法 **P2M2PO**[5] 进行了样本复杂度对比，但实验部分未实现该算法。
- **评估指标**：
  - 不同状态下的值函数差距 $|\hat{V}^{+}_1(s) - \hat{V}^{-}_1(s)|$；
  - 不同样本量 K 下的总体值函数差距；
  - log-log 图验证复杂度依赖关系。
- **结果**：RTZ-VI-LCB 在所有状态下一致优于 RTZ-VI；线性拟合斜率 ≈ -0.4877，与理论预测接近。

## 4. 资源与算力

- **硬件**：单张 NVIDIA RTX 4090 24GB GPU。
- **软件**：PyTorch 2.0.0。
- **训练时长**：文中未明确说明单次实验或总训练时长。

## 5. 实验数量与充分性

- **实验数量**：
  - 展示三个主要图表（图1a、1b、1c），分别对应状态维度、样本量维度和对数尺度的性能依赖。
  - 附录A中还包含一个小表格，列出不同样本量下的 Gap 值。
- **充分性评价**：
  - **正面**：平均100个种子，误差棒合理，验证了理论趋势；对数图拟合验证了复杂度阶数。
  - **不足**：
    - **对比基线不充分**：仅与自身的消融变体（RTZ-VI）对比，未与现有离线鲁棒 MARL 算法（如 P2M2PO）进行实验对比（仅在理论表格中对比）。
    - **实验环境单一**：仅限于表格型随机转移核，未扩展至更复杂环境（如图像、高维状态空间）。
    - **计算资源说明不完整**：未给出每次实验的耗时或总计算量。

## 6. 主要结论与发现

- **样本复杂度最优性**：RTZ-VI-LCB 在状态 S 和动作 {A,B} 上达到最优样本复杂度 $eO(C_r^\star H^4 S(A+B)/\varepsilon^2 \cdot f(\sigma^+,\sigma^-,H))$，匹配信息论下界。
- **不确定性水平的影响**：当 $\min\{\sigma^+,\sigma^-\} \lesssim 1/H$ 时，复杂度与非鲁棒情况相同；当不确定性更大时，复杂度依赖因子 $1/\min\{\sigma^+,\sigma^-\}$。
- **首次突破**：第一个在离线 RTZMGs 中同时实现最优性并处理部分覆盖的算法。
- **扩展性**：多玩家一般和博弈中同样取得最优复杂度，打破多智能体诅咒。

## 7. 优点

- **理论创新强**：提出“鲁棒单边裁剪集中性”（Robust Unilateral Clipped Concentrability）新度量，更紧地量化分布偏移；同时给出匹配的上下界证明。
- **算法设计巧妙**：两阶段子采样+伯恩斯坦惩罚的设计有效解耦统计依赖，并精确捕获方差。
- **计算可行**：通过强对偶将鲁棒贝尔曼算子转化为一维优化，避免了高维穷举。
- **实验验证理论**：对数图斜率与理论预测一致，增强了结果可信度。

## 8. 不足与局限

- **实验验证较弱**：
  - 未在更复杂或大规模环境中评估（如图像、连续控制、大规模多智能体场景）。
  - 未与现有离线鲁棒 MARL 算法（如 P2M2PO、Double Pessimism）进行实验对比。
- **假设限制**：
  - 假设奖励确定且属于 [0,1]；
  - 仅考虑 TV 距离下的不确定性集合，实际中可能使用 KL 或 Wasserstein 距离。
  - 需要较强的分覆盖率假设 C_r^\star 存在且有限，且无法从数据中估算。
- **计算资源未详细报告**：缺少训练时间或内存消耗的量化分析。
- **扩展的充分性**：Multi-RTZ-VI-LCB 仅有理论分析，无对应实验验证。
- **实际应用距离**：算法基于表格型环境，直接扩展到高维连续状态空间需要函数近似，文中未讨论实际应用中的工程挑战。

（完）
