---
title: Robust and Diverse Multi-Agent Learning via Rational Policy Gradient
title_zh: 通过理性策略梯度实现鲁棒且多样的多智能体学习
authors: "Niklas Lauffer, Ameesh Shah, Micah Carroll, Sanjit A. Seshia, Stuart Russell, Michael D Dennis"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ipEqdzO2IT"
tags: ["query:marl"]
score: 9.0
evidence: 面向合作多智能体学习的理性保持优化
tldr: 针对合作多智能体学习中对抗优化导致代理自我破坏的问题，提出了理性保持策略优化（RPO）。RPO通过确保代理保持理性（即策略相对于某些合作伙伴策略最优）来避免自我破坏。该方法在合作场景中成功增强了鲁棒性和多样性，扩展了对抗优化的适用范围。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1424, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 479, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 726, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1419, \"height\": 1753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1426, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 447, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 597, \"height\": 207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1386, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 305, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1437, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 987, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 856, \"height\": 209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 658, \"height\": 172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 989, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 987, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 986, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ipeqdzo2it/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 988, \"height\": 371, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 950, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1380, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 659, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 809, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ipeqdzo2it/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 667, \"height\": 226, \"label\": \"Table\"}]"
motivation: 对抗优化在合作多智能体设置中会导致代理自我破坏，限制了其应用。
method: 提出理性保持策略优化（RPO），确保代理的策略相对于某些合作伙伴策略是最优的。
result: RPO避免了自我破坏，并提升了合作场景中策略的鲁棒性和多样性。
conclusion: 为合作多智能体学习中的对抗优化提供了有效且实用的方法。
---

## Abstract
Adversarial optimization algorithms that explicitly search for flaws in agents' policies have been successfully applied to finding robust and diverse policies in the context of multi-agent learning. However, the success of adversarial optimization has been largely limited to zero-sum settings because its naive application in cooperative settings leads to a critical failure mode: agents are irrationally incentivized to *self-sabotage*, blocking the completion of tasks and halting further learning. To address this, we introduce *Rationality-preserving Policy Optimization (RPO)*, a formalism for adversarial optimization that avoids self-sabotage by ensuring agents remain *rational*—that is, their policies are optimal with respect to some possible partner policy. To solve RPO, we develop *Rational Policy Gradient (RPG)*, which trains agents to maximize their own reward in a modified version of the original game in which we use *opponent shaping* techniques to optimize the adversarial objective. RPG enables us to extend a variety of existing adversarial optimization algorithms that, no longer subject to the limitations of self-sabotage, can find adversarial examples, improve robustness and adaptability, and learn diverse policies. We empirically validate that our approach achieves strong performance in several popular cooperative and general-sum environments. Our project page can be found at https://rational-policy-gradient.github.io.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：对抗优化算法（如自博弈、对抗训练）在零和博弈中能有效提升策略的鲁棒性和多样性，但在合作或一般和博弈（general-sum）中，直接应用会导致智能体出现**自我破坏（self-sabotage）** 行为——即智能体为了最小化队友的奖励而故意采取非理性策略（如拒绝合作、主动破坏任务），从而阻碍学习。
- **研究动机**：扩展对抗优化的适用范围，使其也能在合作场景中发挥作用，同时避免自我破坏问题。
- **整体含义**：提出一种称为“理性保持策略优化”（Rationality-preserving Policy Optimization, RPO）的形式化框架，通过强制策略对某些可能的伙伴策略是最优响应（即保持理性），从而解决自我破坏问题。基于RPO，进一步开发了“理性策略梯度”（Rational Policy Gradient, RPG）算法，实现多种对抗优化算法的合作场景迁移，显著提升策略的鲁棒性和多样性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：
  - **自我破坏的原因**：在合作博弈中，若直接让一个智能体（Adversary）最小化另一个智能体（Victim）的奖励，该智能体可以通过采取非理性动作（如不合作、故意破坏）来轻松降低对方得分，但这无法提供有意义的对抗信号，也不利于策略改进。
  - **RPO 定义**：对于每个智能体 \(i\)，其对抗优化目标为 \(O_i(\pi_1,\dots,\pi_m)\)。RPO 添加约束：要求 \(\pi_i\) 是某个可能伙伴策略 \(\pi'_{-i}\) 的最优响应，即 \(\exists \pi'_{-i} \in \Pi_{-i} \quad \text{s.t.} \quad \pi_i \in \text{BR}(\pi'_{-i})\)。这保证了智能体的行为始终是理性的（即不会故意牺牲自身收益）。
- **关键技术——理性策略梯度（RPG）**：
  - 引入两类智能体：**基础智能体（Base Agent）** 和**操控者（Manipulator）**。每个基础智能体 \(i\) 都有一个对应的操控者 \(\pi_{-i}^M\)。
  - **基础智能体**的目标是最大化自己在与操控者互动时的收益（即作为对操控者策略的最优响应），从而隐式满足 RPO 约束。
  - **操控者**的目标是优化原始的对抗目标 \(O_i\)，但只能通过影响基础智能体的学习过程（即通过**对手塑形（Opponent Shaping）** 技术）间接实现。操控者需要计算**高阶梯度**：先模拟基础智能体一步更新后的参数，再通过该更新对操控者参数进行梯度下降。
  - **梯度更新示意**：
    - 基础智能体：\(\theta_i' \leftarrow \theta_i + \nabla_{\theta_i} U(\theta_i, \theta_{-i}^M)\)
    - 操控者：\(\theta_{-i}^M \leftarrow \theta_{-i}^M + \nabla_{\theta_{-i}^M} O_i(\theta_1', \dots, \theta_m')\)
  - 使用 **Loaded DiCE** 技术来近似无偏的高阶梯度。
  - 引入**伙伴对打正则化（Partner-play Regularization）**：在基础智能体训练时加入少量与最终评估伙伴的互动样本，防止分布偏移。
- **衍生算法**：基于 RPG 扩展了五种对抗优化算法：
  - **AP-RPG**（Adversarial Policy）：寻找固定策略的理性对抗样本。
  - **AT-RPG**（Adversarial Training）：同时训练受害者和对抗者，提升鲁棒性。
  - **PAIRED-RPG**：利用遗憾（regret）进行鲁棒训练。
  - **PAIRED-Attack-RPG**：寻找最大化遗憾的对抗策略。
  - **XPD-RPG**（Cross-Play Diversity）：学习多样且不兼容的策略组，避免自我破坏。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **实验场景（四个主要环境）**：
  - **矩阵游戏**：包含零和、合作、混合动机的支付矩阵（如Figure 2、8等）。
  - **Overcooked**：经典合作烹饪游戏，使用了 `cramped_room`、`forced_coordination`、`counter_circuit`、`coordination_ring` 等布局。
  - **STORM**：修改后的版本，智能体收集红色或绿色硬币，在互动时若颜色相同则获得奖励。实验中还使用了“无观察队友位置”和“可故意破坏”的变体。
  - **Hanabi**：简化版（3色3级和4色4级），经典不完全信息合作游戏。
- **对比方法**：
  - **Self-Play (SP)**：智能体与自身副本对练。
  - **Adversarial Policy (AP)** 和 **Adversarial Training (AT)**：原始对抗算法。
  - **PAIRED**：原始遗憾驱动算法。
  - **XPD baseline**：与 LIPO 和 ADVERSITY 类似的交叉对打多样性基线。
  - **CoMeDi**：先前尝试解决自我破坏的最先进方法。
- **评估指标**：自对打分数、交叉对打分数、对抗攻击后的分数等。

## 4. 资源与算力

- 论文在 **Section E.3** 中明确说明：
  - 实验在单 GPU 上运行（混合使用 A4000 和 A6000）。
  - 使用本地 SLURM 集群，分配 32 个 CPU 核心和 50 GB RAM。
  - 每个实验种子运行时间从几分钟到最多 24 小时不等。
  - 未报告总 GPU 小时数或整体实验消耗。

## 5. 实验数量与充分性

- **实验组数**：论文在四个环境中进行了大量实验，每种算法至少运行 5 个随机种子（见图 5 交叉对打网格），并在每个设置中报告均值、置信区间等。
- **消融/分析实验**：包括对不同 lookahead 步数的分析（矩阵游戏）、不同 partner-play 系数的调参、对 CoMeDi 自我破坏的展示（Figure 18）等。
- **充分性评价**：实验设计较为充分，涵盖了多种环境（简单矩阵、复杂网格、不完全信息卡牌）、多种任务（对抗搜索、鲁棒性、多样性）。对比方法包括了当前主流基线，并明确指出了基线失败的情况。但部分分析仅基于少数种子或特定设置（如矩阵游戏），大规模统计稳定性可进一步验证。总体而言，实验是客观且公平的。

## 6. 论文的主要结论与发现

- **Claim 1**：XPD-RPG 能够学习到**有意义的多样策略**，即一组在自对打得分高、交叉对打得分低的策略，且交叉对打得分不会降为零（避免自我破坏）。相比之下，CoMeDi 和 XPD baseline 会在交叉对打中通过故意破坏（如挡住盘子台）来降低得分，反映出虚假的多样性。
- **Claim 2**：XPD-RPG 训练的智能体**对不同的伙伴策略具有更强的鲁棒性**。在 Overcooked 和 Hanabi 的交叉对打网格中，XPD-RPG 智能体与多种不同策略的伙伴配合时均获得较高奖励，而 SP 或 XPD 智能体则容易崩溃。
- **Claim 3**：AP-RPG 和 PAIRED-A-RPG 可以**找到非平凡的理性对抗样本**，而不依赖于自我破坏。例如在 overcooked 中，AP-RPG 发现受害者假设顺时针绕行，而对抗者采用逆时针策略导致冲突。
- **Claim 4**：RPG 算法**完全消除了自我破坏行为**，在所有测试环境中均保持理性。

## 7. 优点

- **方法创新**：首次将对手塑形（opponent shaping）应用于对抗训练，解决了长期存在的自我破坏问题，并为合作场景中的对抗优化提供了一个通用框架。
- **统一框架**：RPO/RPG 可扩展多种现有算法（AP、AT、PAIRED、XPD），适用范围广。
- **实验设计全面**：覆盖了从简单矩阵到复杂部分可观测环境的多个 benchmark，并提供了丰富的可视化和交互式演示（项目页面）。
- **结果强有力**：在鲁棒性、多样性、对抗搜索三个任务上都显著优于现有基线，且避免了虚假的自我破坏行为。
- **公开代码和项目页面**：便于复现和继续研究。

## 8. 不足与局限

- **计算开销**：RPG 依赖于高阶梯度和若干次 lookahead 步骤，训练速度比普通 RL 慢（约 3 倍于 XPD，而 XPD 本身已是 SP 的 2 倍）。虽为常数开销，但在大规模场景中仍可能成为瓶颈。
- **高方差**：高阶梯度估计来自样本，需要较大 batch size 来稳定训练；论文虽使用 Loaded DiCE 降低方差，但未与其他方差缩减技术深入比较。
- **收敛保证**：RPG 缺乏形式化的收敛证明，论文仅凭实验结果说明其有效性，理论分析不足。
- **实验覆盖**：虽然环境多样，但主要集中在 2 人博弈；多智能体（>2）场景下的效果未充分验证。此外，Hanabi 实验仅使用了简化版（3-4 色），与标准 5 色 5 级设置尚有差距。
- **与更复杂 RL 算法的兼容性**：当前使用简单的 actor-critic 而非 PPO，因为 PPO 的 clipping 会干扰高阶梯度。如何在更现代算法中集成 RPG 尚待探索。

（完）
