---
title: Cross-environment Cooperation Enables Zero-shot Multi-agent Coordination
title_zh: 跨环境合作实现零样本多智能体协调
authors: "Kunal Jha, Wilka Carvalho, Yancheng Liang, Simon Shaolei Du, Max Kleiman-Weiner, Natasha Jaques"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zBBYsVGKuB"
tags: ["query:marl"]
score: 9.0
evidence: 通过跨环境合作实现零样本多智能体协调
tldr: 针对零样本协调问题，现有方法局限于单一任务导致泛化不足。本文提出跨环境合作（CEC）范式，通过在分布化环境中与单个搭档训练，使智能体学会通用合作技能。实验表明，CEC在大量未见过的搭档和任务上显著优于基线，推动了零样本协调的泛化能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 813, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 528, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 180, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 726, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 863, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 776, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 849, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1505, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 888, \"height\": 1209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 863, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1782, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 854, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 850, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 847, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 848, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 816, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1772, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 814, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 474, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 473, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1765, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 449, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1724, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1730, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 851, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 853, \"height\": 323, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1709, \"height\": 1404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1578, \"height\": 778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1246, \"height\": 911, \"label\": \"Table\"}]"
motivation: 现有零样本协调方法局限于单一任务，无法泛化到新任务。
method: 提出跨环境合作范式，在分布化的环境中训练，学习通用合作技能。
result: 在大量未见过的搭档和任务上超越基线，实现高效零样本协调。
conclusion: 跨环境训练是提升多智能体协调泛化能力的有效途径。
---

## Abstract
Zero-shot coordination (ZSC), the ability to adapt to a new partner in a cooperative task, is a critical component of human-compatible AI. While prior work has focused on training agents to cooperate on a single task, these specialized models do not generalize to new tasks, even if they are highly similar. Here, we study how reinforcement learning on a **distribution of environments with a single partner** enables learning general cooperative skills that support ZSC with **many new partners on many new problems**. We introduce *two* Jax-based, procedural generators that create billions of solvable coordination challenges. We develop a new paradigm called **Cross-Environment Cooperation (CEC)**, and show that it outperforms competitive baselines quantitatively and qualitatively when collaborating with real people. Our findings suggest that learning to collaborate across many unique scenarios encourages agents to develop general norms, which prove effective for collaboration with different partners. Together, our results suggest a new route toward designing generalist cooperative agents capable of interacting with humans without requiring human data.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有零样本协调（Zero-shot Coordination, ZSC）方法主要使用**种群训练（PBT）**在单一任务上训练，与多样伙伴合作。但这些智能体无法泛化到新任务——即使任务高度相似。这限制了在家庭机器人、自动驾驶等真实场景中的应用。
- **背景**：
  - 人类擅长在新环境和与不同伙伴合作，通过共享意图、角色分工等认知机制。
  - 当前RL方法将ZSC局限于单一环境，需针对每个新环境重新训练。
  - 作者假设：**在多样化环境中训练（即使只用单个固定伙伴），能学到更通用的合作技能，支持与任意伙伴在新任务上零样本协调**。
- **整体含义**：提出**跨环境合作（Cross-Environment Cooperation, CEC）**范式，挑战“自对弈对合作游戏无效”的传统观点，开辟无需人类数据即可实现通用合作AI的新方向。

## 2. 方法论

- **核心思想**：用**环境多样性**替代**伙伴多样性**。训练单一策略在大量过程化生成的不同环境中进行自对弈（Self-Play, SP），从而迫使智能体学习任务结构而非固定策略。
- **关键技术细节**：
  - **目标函数**：\( J(\pi_C) = \mathbb{E}_{m_i \sim \mathcal{M}} [S(\pi_C, \pi_C, m_i)] \)，其中\(\pi_C\)是合作者策略，\(m_i\)从任务分布\(\mathcal{M}\)采样，\(S\)是总回报。**只有一个策略，无伙伴种群**。
  - **环境生成器**：
    1. **Dual Destination Game**（玩具环境）：5×5网格，两智能体需移动到不同目标格子。程序化随机初始和目标位置，生成无数变体。
    2. **Overcooked**（大型环境）：基于JaxMARL，从5个原始布局（图4）提取墙结构，随机放置物品（锅、洋葱盘、盘子、目标），并旋转网格。可生成**1.16×10¹⁷**个可解布局。实现速度达**1000万步/分钟**（单GPU）。
  - **训练算法**：使用**IPPO**（独立PPO）进行训练，网络含LSTM（支持元学习）。训练步数**30亿步**。
  - **变体**：CEC-Finetune（CEC-FT）——在CEC预训练后在单个原始布局上微调1亿步。

## 3. 实验设计

- **场景与数据集**：
  - **Dual Destination Game**：固定任务（图2a）与程序化生成任务（图2b）。
  - **Overcooked**：5个原始布局（Asymmetric Advantages, Coordination Ring, Counter Circuit, Cramped Room, Forced Coordination） + 100个程序化生成的新布局（均未在训练中出现）。
- **基准方法**：
  - **IPPO**（自对弈，单任务）
  - **FCP**（Fictitious Co-Play，种群方法）
  - **E3T**（Efficient End-to-End Training，当前SOTA单任务方法）
  - 以及它们的变体（如IPPO⁻、FCP⁻等，用于人类实验中的新布局泛化测试）
- **评估指标**：
  - **AI-AI交叉游戏（Cross-Play, XP）**：与不同随机种子训练的同伴合作时的奖励。
  - **跨算法合作（Ad-hoc Teamplay）**：不同算法配对，构建收益矩阵，进行经验博弈论分析（复制动力学梯度）。
  - **人类实验**：80名参与者（Prolific平台），在Counter Circuit和Coordination Ring上与6种AI合作，每轮后填写Likert量表（7个主观指标：适应性、一致性、类人性、阻碍感、挫折感、享受度、协调度）。

## 4. 资源与算力

- **训练硬件**：使用**单个GPU**（未明确型号，但基于Jax框架，推测为NVIDIA V100/A100级别）。
- **速度**：Overcooked环境可达**1000万步/分钟**。
- **总训练步数**：每个方法训练**30亿步**（3 billion steps），以确保比较公平。
- **人类实验**：通过NiceWebRL在线部署，80人共约30分钟/人。
- **备注**：论文未具体说明GPU型号、数量、显存大小及训练总耗时。

## 5. 实验数量与充分性

- **实验组数**：
  - 玩具环境：全观测、部分观测（3×3视野）、多任务变体共3组实验。
  - Overcooked：
    - AI-AI XP：在5个原始布局和100个程序化布局上，每种方法6个种子，生成大量交叉游戏配对。
    - 跨算法矩阵（5种算法 × 5种算法 = 25种配对）。
    - 消融实验：CEC-FT、CEC+E3T（图16）。
    - 学习曲线分析（图7）。
  - 人类实验：2个布局 × 6种算法（但实际测试5种，因为IPPO和FCP用新布局版本），每个布局40人，约240轮游戏+问卷。
- **充分性**：
  - **充分**：覆盖多种环境、多种伙伴、主观与客观指标，使用统计检验（t-test）。
  - **公平**：统一训练步数、相同网络架构（LSTM）、统一超参数（表2）。但CEC与单任务方法相比，测试环境（5个原始布局）是CEC训练中未见过的，而单任务方法在该布局上训练过，存在一定不公平；作者通过CEC-FT弥补。
- **不足**：CEC训练未收敛（图7显示仍在提升），可能低估CEC上限；人类实验仅两个布局，样本量80，且参与者限于英语使用者（WEIRD偏差）。

## 6. 主要结论与发现

1. **环境多样性优于伙伴多样性**：在AI-AI XP中，CEC显著超越FCP和E3T（图6）；在跨算法博弈论分析中，复制动力学梯度指向CEC或CEC-FT（图8），表明CEC具有更强鲁棒性。
2. **单任务方法完全无法泛化到新环境**：IPPO、FCP、E3T在100个程序化布局上得分为0（图6），因为它们学习的是低级序列而非任务结构。
3. **CEC在人类评估中主观更优**：尽管奖励低于E3T，但人类对CEC的7项主观评分均最高（图9底部），CEC-FT显著优于E3T（p<0.01）。
4. **CEC学会避免碰撞**：与人类合作时碰撞次数最低（图11），体现了学习到的通用规范（如让路）。
5. **微调CEC（CEC-FT）可提升单布局性能**，但损失对全新布局的泛化（图6左 vs 右）。
6. **结合环境与伙伴多样性未提升性能**：CEC+E3T反而更差（图16），可能因噪声过多需更大模型和更长训练。

## 7. 优点

- **概念创新**：用环境多样性替代昂贵的伙伴种群训练，简化训练流程且更可扩展。
- **工程高效**：基于Jax的生成器实现超高吞吐，使大规模实验成为可能。
- **全面评估**：同时进行AI-AI（含博弈论分析）和人类实验（含主观问卷），揭示奖励之外的重要维度（如适应性、碰撞避免）。
- **可复现性**：开源代码和环境，便于后续研究。
- **理论贡献**：证明自对弈在多样化环境下可学习通用合作技能，挑战了以往认为自对弈对合作游戏不足的观点。

## 8. 不足与局限

- **训练未收敛**：图7显示CEC在30亿步后仍在提升，可能当前结果未达最优，存在性能上限不明的问题。
- **人类实验偏差**：仅使用英语母语者（WEIRD样本），可能受文化影响（如游戏经验、合作习惯），缺乏跨文化验证。
- **环境单一**：仅测试了Overcooked作为大规模环境，能否推广到其他合作游戏（如Hanabi、机器人任务）未知。
- **CEC+环境+伙伴多样性组合失败**：未找到有效整合两种多样性的方法，需进一步研究。
- **微观行为分析有限**：论文定性提到CEC更均匀访问状态（图24-26），但缺乏定量度量（如熵、角色灵活性等）。
- **奖励与主观评分不一致**：CEC奖励低于E3T但主观更佳，表明简单奖励优化可能不是衡量合作的最佳指标，但论文未深入探讨这一权衡。

（完）
