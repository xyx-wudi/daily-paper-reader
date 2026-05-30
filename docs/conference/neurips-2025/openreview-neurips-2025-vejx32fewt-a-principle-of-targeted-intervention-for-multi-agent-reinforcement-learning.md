---
title: A Principle of Targeted Intervention for Multi-Agent Reinforcement Learning
title_zh: 多智能体强化学习中的目标干预原则
authors: "Anjie Liu, Jianhong Wang, Samuel Kaski, Jun Wang, Mengyue Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Vejx32FeWt"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体影响图用于MARL交互范式分析
tldr: 该论文运用多智能体影响图（MAIDs）作为图形化框架，来分析和可视化合作多智能体强化学习中的交互范式。通过引入MARL交互范式的概念，并设计目标干预原则，为人类指导大规模MARL提供了易用的研究工具。该方法有助于理解自组织和全局引导机制，推动MARL的可控性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1382, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1425, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 898, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 1337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 1338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 1853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 1882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 724, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1447, \"height\": 1472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1446, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vejx32fewt/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 1771, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1412, \"height\": 1456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1191, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1079, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1079, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 834, \"height\": 1005, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 687, \"height\": 882, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1094, \"height\": 1050, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 907, \"height\": 841, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vejx32fewt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 907, \"height\": 881, \"label\": \"Table\"}]"
motivation: 大规模MARL中人类全局指导不切实际，缺乏系统性的交互范式分析工具。
method: 采用多智能体影响图（MAIDs）建模并设计交互范式，提出目标干预原则。
result: 提出了目标干预原则，便于分析和设计MARL的交互机制。
conclusion: MAIDs框架为MARL交互研究提供了新的理论视角和实用工具。
---

## Abstract
Steering cooperative multi-agent reinforcement learning (MARL) towards desired outcomes is challenging, particularly when the global guidance from a human on the whole multi-agent system is impractical in a large-scale MARL. On the other hand, designing external mechanisms (e.g., intrinsic rewards and human feedback) to coordinate agents mostly relies on empirical studies, lacking a easy-to-use research tool. In this work, we employ multi-agent influence diagrams (MAIDs) as a graphical framework to address the above issues. First, we introduce the concept of MARL interaction paradigms (orthogonal to MARL learning paradigms), using MAIDs to analyze and visualize both unguided self-organization and global guidance mechanisms in MARL. Then, we design a new MARL interaction paradigm, referred to as the targeted intervention paradigm that is applied to only a single targeted agent, so the problem of global guidance can be mitigated. In implementation, we introduce a causal inference technique—referred to as Pre-Strategy Intervention (PSI)—to realize the targeted intervention paradigm. Since MAIDs can be regarded as a special class of causal diagrams, a composite desired outcome that integrates the primary task goal and an additional desired outcome can be achieved by maximizing the corresponding causal effect through the PSI. Moreover, the bundled relevance graph analysis of MAIDs provides a tool to identify whether an MARL learning paradigm is workable under the design of an MARL interaction paradigm. In experiments, we demonstrate the effectiveness of our proposed targeted intervention, and verify the result of relevance graph analysis.

---

## 论文详细总结（自动生成）

# 论文总结：A Principle of Targeted Intervention for Multi-Agent Reinforcement Learning

## 1. 论文的核心问题与整体含义
- **研究动机**：大规模合作多智能体强化学习（MARL）中，人类对全局系统进行直接指导往往不切实际；现有的外部协调机制（如内在奖励、人类反馈）多依赖经验调参，缺乏系统性的理论分析工具。
- **核心问题**：能否仅对**单个目标智能体**施加额外期望目标，通过其影响力带动整个系统实现有效协调？
- **整体意义**：提出基于多智能体影响图（MAIDs）的图形化框架，为 MARL 交互范式提供形式化分析与设计工具，并由此提出目标干预原则（Targeted Intervention Paradigm），为解决大规模 MARL 中的全局指导难题提供新思路。

## 2. 论文提出的方法论
- **核心思想**：利用 MAIDs 建模 MARL 中的决策依赖和信号流，定义三种交互范式（自组织、全局干预、目标干预），并通过 **相关性图（Relevance Graph）** 分析学习范式的可解性。
- **关键技术**：提出 **Pre-Strategy Intervention (PSI)**，在目标智能体的决策变量前添加前决策变量（Pre-decision variable）\( D_{pre} \)，通过最大化因果效应来引导系统收敛到**偏好纳什均衡**（即同时满足主任务目标与额外期望目标的复合结果）。
- **公式与算法**：
  - 定义因果效应：\( \Delta CE(U_{tot}=u^*) = P_I - P_U \)，其中 \( P_I \) 是干预后达到期望总效用 \( u^* \) 的概率，\( P_U \) 是干预前概率。
  - 预策略 \( \sigma_{pre} \) 由预策略网络 \( \delta_{pre}: Pa(D) \times Z \to \Delta(\text{dom}(\sigma_{pre})) \) 生成，\( Z \) 为额外目标信号（如内在奖励）。
  - 训练时，联合优化原始任务奖励与针对单个智能体的内在奖励，实现因果效应最大化。

## 3. 实验设计
- **环境与场景**：
  - **MPE (Multi-Agent Particle Environment)**：Simple Spread 任务，3 个智能体合作覆盖 3 个地标。设定两种内在奖励场景（固定目标地标、动态选择最远地标）。
  - **Hanabi**：2 人（及 4 人）不完全信息合作游戏，内在奖励对应两种常见公约：“5 Save” 和 “The Chop”。
- **对比方法**：
  - **Base MARL**：IQL、VDN、QMIX（MPE）；IPPO、MAPPO、PQN-IQL、PQN-VDN（Hanabi）。
  - **Intrinsic Reward**：去除预策略模块，仅给目标智能体额外内在奖励。
  - **Global Intervention**：GPSI（对所有智能体应用 PSI）、LIIR、LAIES（全局引导方法，仅关注主任务）。
  - 另设消融实验（预策略模块 vs. 无）、噪声实验、异构实验等。
- **评测指标**：**外在回报**（主任务完成度）和**内在回报**（额外目标达成度）。

## 4. 资源与算力
- **硬件**：NVIDIA RTX 4090 和 A100 GPU（文中未明确给出具体数量）。
- **训练时长**：Hanabi 每轮约 1 小时，MPE 每轮约 5 分钟；总算力需求适中。

## 5. 实验数量与充分性
- **实验组数**：覆盖 MPE 和 Hanabi 两大环境，使用 6 种以上基础 MARL 算法，两类内在奖励定义，两种干预范围（单个 vs. 全部），并包含消融、噪声、异构、4 人扩展等额外验证（共 10 余组独立实验）。
- **充分性**：实验设计较全面，对照组设置合理（Base MARL、Intrinsic Reward、Global Intervention），统计报告 5 个随机种子下的均值与 95% 置信区间，结果客观公平。

## 6. 论文的主要结论与发现
- **核心发现**：仅对单个智能体施加额外内在奖励（如指导其遵循 Hanabi 公约或趋近特定地标），通过 PSI 即可**实现全局协调**，甚至提升主任务完成度。
- **用户可解性验证**：MAIDs 相关性图预测独立学习（IL）在自组织范式下不可解，而目标干预范式可使 IL 变得可解，实验验证了该预测（例如 MPE 中 IQL+PSI 性能接近 CTDE 算法 VDN）。
- **目标干预优于全局干预**：PSI 在额外目标达成上显著优于 GPSI，主任务性能持平。
- **预策略模块的作用**：消融实验表明，仅加内在奖励而无预策略模块会导致主任务性能下降，证明预策略模块在平衡主任务与额外目标中的关键作用。

## 7. 优点
- **理论创新**：首次将 MAIDs 引入 MARL 交互范式分析，为外部协调机制设计提供形式化工具。
- **方法实用**：PSI 作为轻量级预策略模块，可嵌入任意基础 MARL 算法，仅需修改目标智能体，对外部开销小。
- **实验验证充分**：多环境、多算法、多场景、多消融的综合评估，结果可信。
- **易于扩展**：框架支持未来在多个目标智能体、自适应选择等方面的扩展。

## 8. 不足与局限
- **假设依赖**：当前方法假定 MAID 结构已知或可精确建模；在复杂系统中预先定义该结构可能困难。
- **范围局限**：论文主要聚焦单个目标智能体介入场景，未验证多目标智能体同时干预的效果。
- **实验覆盖**：虽然环境包括 MPE 和 Hanabi，但仍属模拟场景；现实应用（如自动驾驶、电网调度）中的噪声与不确定性更大，需进一步验证鲁棒性。
- **算力信息不完整**：未明确报告 GPU 数量与总训练算力，限制可重复性评估。
- **未来方向**：需进一步研究自动学习 MAID 结构、最优目标智能体选择、异步更新混合学习范式等。

（完）
