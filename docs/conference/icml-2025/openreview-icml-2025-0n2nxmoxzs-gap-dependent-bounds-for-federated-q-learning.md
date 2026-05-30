---
title: Gap-Dependent Bounds for Federated $Q$-Learning
title_zh: 联邦Q学习的间隙依赖界
authors: "Haochen Zhang, Zhong Zheng, Lingzhou Xue"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0n2nXmOxZS"
tags: ["query:marl"]
score: 4.0
evidence: 联邦Q学习与多智能体遗憾分析
tldr: 提出首个基于间隙的联邦Q学习遗憾与通信代价分析，利用MDP良性结构实现对数级遗憾界，并揭示多智能体加速模式。非典型MARL方法，但涉及多智能体学习理论。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0n2nxmoxzs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0n2nxmoxzs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0n2nxmoxzs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1242, \"height\": 832, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0n2nxmoxzs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1232, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0n2nxmoxzs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1240, \"height\": 843, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0n2nxmoxzs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1717, \"height\": 462, \"label\": \"Table\"}]"
motivation: 现有联邦强化学习方法仅关注最坏情况，未利用MDP结构。
method: 基于子优间隙的间隙依赖分析框架，优化探索与利用平衡。
result: 获得对数级遗憾界和更优的通信成本界，发现多智能体加速模式。
conclusion: 为联邦Q学习提供更精细的理论保证，揭示多智能体优势。
---

## Abstract
We present the first gap-dependent analysis of regret and communication cost for on-policy federated $Q$-Learning in tabular episodic finite-horizon Markov decision processes (MDPs). Existing FRL methods focus on worst-case scenarios, leading to $\sqrt{T}$-type regret bounds and communication cost bounds with a $\log T$ term scaling with the number of agents $M$, states $S$, and actions $A$, where $T$ is the average total number of steps per agent. In contrast, our novel framework leverages the benign structures of MDPs, such as a strictly positive suboptimality gap, to achieve a $\log T$-type regret bound and a refined communication cost bound that disentangles exploration and exploitation. Our gap-dependent regret bound reveals a distinct multi-agent speedup pattern, and our gap-dependent communication cost bound removes the dependence on $MSA$ from the $\log T$ term. Notably, our gap-dependent communication cost bound also yields a better global switching cost when $M=1$, removing $SA$ from the $\log T$ term.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义
- **研究动机**：现有联邦强化学习（FRL）方法仅针对最坏情况 MDP 进行分析，得到 $\sqrt{T}$ 型遗憾界和依赖 $MSA\log T$ 的通信成本界。然而实际中 MDP 常具有良性结构（如正次优性间隙 $\Delta_{\min}>0$），可以利用该结构显著改善理论保证。
- **整体含义**：本文首次在在线联邦 Q 学习中建立基于间隙的（gap-dependent）遗憾和通信成本上界，实现对数型遗憾并揭示多智能体加速模式；同时获得更紧的通信成本界，其 $\log T$ 项摆脱了对 $M$、$S$、$A$ 的依赖，并改进了单智能体切换成本。这回答了该领域的两个重要开放问题。

## 2. 方法论
- **核心思想**：利用 MDP 的最小非零次优性间隙 $\Delta_{\min}$，在联邦 Q 学习（FedQ-Hoeffding）中通过控制值函数估计误差和访问次数，实现探索与利用的分离分析，从而获得对数型遗憾界和更紧的通信成本界。
- **关键技术细节**：
  - **误差控制引理（Lemma 4.1）**：以高概率将总误差 $\sum (Q_k^h - Q^*_h)$ 的上界表示为依赖 $1/\Delta_{\min}$ 的对数项与依赖 $M,\sqrt{H}$ 的间隙无关项之和。
  - **访问次数集中性（Lemma 5.2）**：利用最优策略下的平稳访问概率 $P^*_{s,h}$ 与执行策略的偏差递归，证明对最优动作的访问次数与期望之差以高概率被 $O(\sqrt{RP^*\iota} + HC_{\min})$ 控制。
  - **多智能体同时增长引理（Lemma 5.3 & 5.4）**：当触发条件满足且访问数足够大时，所有智能体对最优动作的访问数同步获得 $1/(6H(H+1))$ 倍增长，从而去除 $M$ 和 $SA$ 对 $\log T$ 项的影响。
  - **算法流程**：回合制协议，服务器基于当前 Q 估计确定确定性策略并广播；代理按策略收集轨迹，当某个 $(s,a,h)$ 被单一代理访问达到触发阈值 $c_k^h(s,a)= \max\{1, \lfloor N_k^h(s,a)/(M H(H+1))\rfloor\}$ 时发送中断信号；服务器聚合后按两种情况更新 Q 值（初始化阶段用小学习率迭代，后期用均值更新），然后更新 V 和策略。
- **公式方面**：最终遗憾界为 $O\left(\frac{H^6SA\log(MSAT)}{\Delta_{\min}} + M\sqrt{H^7SA}\sqrt{\log(MSAT)} + M H^5 SA\right)$；通信轮次界为 $O\big(M H^3 SA \log(M H^2 \iota_0) + H^3 SA \log(\frac{H^5 SA}{\Delta_{\min}^2}) + H^3 S \log(\frac{M H^9 SA \iota_0}{\Delta_{\min}^2 C_{\text{st}}}) + H^2 \log(\frac{T}{HSA})\big)$。

## 3. 实验设计
- **使用的场景**：合成表格型 MDP（episodic, tabular），奖励 $r_h(s,a)$ 和转移概率 $P_h(\cdot|s,a)$ 均匀随机生成。
- **Benchmark**：以单智能体版本的 UCB-Hoeffding（Jin et al., 2018）作为对比基线。
- **对比方法**：
  - 遗憾实验：FedQ-Hoeffding（M=10） vs UCB-Hoeffding（M=1）。
  - 通信成本实验：仅展示 FedQ-Hoeffding 在不同 M、S、A 下的通信轮次表现，未与其他 FRL 算法（如 FedQ-Advantage、Fed-UCBVI）进行实验比较。
- **参数设置**：
  - 遗憾实验：$(H,S,A)=(2,2,2)$ 和 $(5,3,2)$，每代理生成 $10^7$ 个 episode，共 $10^8$ 个 episode。
  - 通信成本实验：固定 $(H,S,A)=(2,2,2)$ 变化 $M\in\{2,4,6,8\}$；固定 $(H,A,M)=(2,2,2)$ 变化 $S\in\{2,4,6,8\}$；固定 $(H,S,M)=(2,2,2)$ 变化 $A\in\{2,4,6,8\}$，每代理生成 $10^7$ 个 episode，只分析 $5\times 10^5$ 个 episode 后的通信成本。

## 4. 资源与算力
- 文中未明确给出 GPU 型号、数量或总训练时长。
- 硬件描述：服务器 Intel Xeon E5-2650v4（2.2GHz），100 核；每项复制（trial）限制为单核 50GB RAM。
- 算力方面仅提及“所有实验在该服务器上运行”，未提供具体时间。

## 5. 实验数量与充分性
- **遗憾实验**：两组 MDP 参数，每组收集 10 条样本路径（共 20 次 runs），展示中位数与 10%-90% 百分位区间。结果支持对数型遗憾和 $1/M$ 加速模式，但未与其他 FRL 算法（如 FedQ-Advantage）对比，也未进行消融研究（如不同 $\Delta_{\min}$ 或不同触发阈值）。
- **通信成本实验**：针对 M、S、A 各取 4 个水平，绘制通信轮次 vs $\log(\text{episodes})$ 的拟合线，斜率相近表明 $\log T$ 项系数与 M、S、A 无关。实验数量较少（每种水平仅一条曲线，无误差条），但作为理论验证仍具说服力。
- **充分性评价**：作为理论论文，实验主要验证理论趋势，数量可接受；但缺乏在真实或复杂环境下的验证，也未进行与其他 SOTA FRL 算法的性能比较，公平性评估不够全面。

## 6. 主要结论与发现
- 证明了 FedQ-Hoeffding（以及 FedQ-Bernstein）在正间隙 MDP 上可实现对数型遗憾，优于最坏情况的 $\sqrt{T}$ 型界。
- 发现了多智能体加速模式：平均每 episode 遗憾的降低率为 $\tilde{O}(1/M)$，优于最坏情况下的 $\tilde{O}(1/\sqrt{M})$。
- 首次获得间隙依赖的通信成本上界，其 $\log T$ 项不依赖于 $M$、$S$、$A$，从而显著降低了大规模智能体-状态-动作空间下的通信开销。
- 单智能体情形下，得到改进的全局切换成本上界，消除了对 $SA$ 的依赖。
- 实验验证了遗憾的对数增长趋势，以及通信成本中 $\log T$ 项系数与 $M,S,A$ 无关的结论。

## 7. 优点
- **理论贡献突出**：首次在在线 FRL 中建立间隙依赖的遗憾和通信成本界，解决两个开放问题。
- **分析技术新颖**：开发了适用于变策略联邦学习的访问次数集中性工具，包括误差递归、多智能体同时增长引理、状态-wise 同时增长引理等，对后续间隙依赖分析具有独立价值。
- **比最坏情况界更紧**：当间隙 $\Delta_{\min}$ 固定且 $T$ 充分大时，遗憾从 $\sqrt{T}$ 降至 $\log T$，通信成本从 $O(MSA\log T)$ 降至仅 $O(\log T)$（主项），理论改进显著。
- **实验初步支持理论**：合成 MDP 上的结果清晰展示了对数型遗憾和通信成本主项与 M、S、A 无关的趋势。

## 8. 不足与局限
- **实验局限**：所有实验在合成 MDP 上进行，缺乏真实应用场景（如机器人、游戏）的验证；未与其他 FRL 算法（如 FedQ-Advantage、Fed-UCBVI、Byzan-UCBVI）进行实验比较，无法体现实际性能优势。
- **公平性与覆盖面**：仅测试了两种 MDP 参数（$S,A$ 很小），缺乏若干组不同规模、不同间隙分布的对比实验；未设计消融研究（如不同触发阈值、不同学习率的影响），无法证明方法对超参数的鲁棒性。
- **可扩展性限制**：间隙依赖分析依赖正 $\Delta_{\min}$，当间隙非常小（接近 0）时，界退化为最坏情况；实际 MDP 中可能难以确保严格正间隙。
- **算法范围**：分析仅针对 FedQ-Hoeffding 和 FedQ-Bernstein，未涵盖其他联邦 Q 学习变体（如基于优势函数的 FedQ-Advantage）。
- **计算资源未充分报告**：未提供训练时间或 GPU 使用情况，降低了可复现性和可比较性。

（完）
