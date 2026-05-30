---
title: "Learning Preferences without Interaction for Cooperative AI: A Hybrid Offline-Online Approach"
title_zh: 无交互偏好学习：协作AI的混合离线-在线方法
authors: "Haitong Ma, Haoran Yu, Haobo Fu, Shuai Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QVheAhJefR"
tags: ["query:marl"]
score: 7.0
evidence: 协作AI中的偏好学习
tldr: 针对协作智能体忽视人类偏好问题，提出混合离线-在线方法学习偏好。利用少量离线反馈，结合在线学习调整策略。实验表明能有效对齐人类偏好，提升协作体验。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1201, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 563, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 792, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qvheahjefr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1246, \"height\": 974, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 695, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 697, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 840, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1183, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1145, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 905, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 775, \"height\": 930, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 779, \"height\": 1148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 847, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1186, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qvheahjefr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 800, \"height\": 238, \"label\": \"Table\"}]"
motivation: 现有协作智能体只优化任务性能，忽视人类偏好，而人类偏好与奖励最大化目标常不一致。
method: 提出混合框架，利用离线偏好数据预训练，再通过在线微调解决分布偏移。
result: 在多人协作环境中，代理能有效学习并遵循人类偏好。
conclusion: 偏好对齐在协作AI中至关重要，混合方法解决了实际交互限制。
---

## Abstract
Reinforcement learning (RL) for collaborative agents capable of cooperating with humans to accomplish tasks has long been a central goal in the RL community. While prior approaches have made progress in adapting collaborative agents to diverse human partners, they often focus solely on optimizing task performance and overlook human preferences—despite the fact that such preferences often diverge from the reward-maximization objective of the environment.
Addressing this discrepancy poses significant challenges: humans typically provide only a small amount of offline, preference-related feedback and are unable to engage in online interactions, resulting in a distributional mismatch between the agent’s online learning process and the offline human data. To tackle this, we formulate the problem as an online&offline reinforcement learning problem that jointly integrates online generalization and offline preference learning, entirely under an offline training regime.
We propose a simple yet effective training framework built upon existing RL algorithms that alternates between offline preference learning and online generalization recovery, ensuring the stability and alignment of both learning objectives.
We evaluate our approach on a benchmark built upon the Overcooked environment—a standard environment  for human-agent collaboration—and demonstrate remarkable performance across diverse preference styles and cooperative scenarios.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：协作式强化学习智能体（Cooperative AI）在与人类合作时，通常只关注环境奖励最大化（任务性能），而忽视了人类用户的个性化偏好（如喜欢烹饪特定食材、特定协作方式）。这种偏好与奖励最大化目标之间的不一致，导致智能体在与人类实际合作时协调不佳、用户体验差。
- **实际场景**：在多人游戏（如《英雄联盟》《王者荣耀》）中，用户赛后可以通过“点赞”等形式提供少量偏好反馈，这些反馈反映在离线轨迹中。但用户无法在线交互，且偏好数据极其有限（仅几条“喜欢”的轨迹）。
- **关键挑战**：
  - 有限偏好数据且无在线交互，导致分布偏移（离线人类数据分布与智能体在线学习分布不匹配）。
  - 泛化（与多种人类伙伴合作）与偏好对齐（适配特定用户风格）之间存在目标冲突：优化偏好会损害泛化能力。
- **研究目标**：提出一种既能保持零样本泛化能力，又能从少量离线偏好数据中学习对齐的协作智能体训练框架。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：受NLP中“预训练 → 监督微调（SFT）”范式的启发，将协作智能体的泛化训练类比为预训练，将离线偏好学习类比为下游微调。
- **三阶段训练框架**：
  - **Stage 1: Pretrain（泛化先验）**：使用策略池（Policy Pool）中的多样化代理进行在线交互，基于MAPPO算法训练智能体，使其具备与未知人类伙伴协作的泛化能力。
  - **Stage 2: 偏好学习 + 恢复（Preference Learning with Recovery）**：
    - 先对少量“点赞”轨迹进行离线行为克隆（BC）直至收敛，获得偏好对齐特征。
    - 再进行在线泛化恢复（与策略池交互），以弥补因偏好学习导致的泛化性能下降（环境回报可下降1/3以上）。
  - **Stage 3: 逐轮交替恢复（Epoch-wise Alternation Recovery, EAR）**：重复以下过程直至偏好精度恢复至第二阶段水平：
    - 1 epoch 的行为克隆（轻量级偏好学习）。
    - 在线恢复（泛化能力恢复到基线水平）。
- **关键技术细节**：
  - 使用策略池（18个不同检查点）近似人类策略分布。
  - 偏好学习目标：最大化“点赞”轨迹上的动作似然（标准BC）。
  - 恢复阶段：当平均环境回报达到预训练基线时停止恢复。
  - 算法伪代码见 Algorithm 1，核心思路是交替训练，维持偏好记忆的同时恢复泛化。

## 3. 实验设计：数据集、场景、基准与对比方法

- **环境**：Overcooked（烹饪协作游戏），两个布局：
  - Coordination Ring（环形厨房，简单食谱，需避免碰撞）。
  - Many Orders（方形厨房，多种食谱，偏好选择）。
- **偏好模拟**：基于HSP中的事件级偏好奖励函数，对关键事件（取洋葱、取盘子、上菜等）赋予偏差权重，训练出具有偏好的人类代理策略。
- **离线数据集**：从偏好代理生成的轨迹中筛选出“点赞”轨迹（偏好回报≥最大回报80%）。两个布局下共72条轨迹（每种布局×3种偏好风格），按4:1划分训练/测试。
- **评估指标**：
  - Environment Return：成功交付的汤数量 ×20，衡量任务表现。
  - Preference Score：按偏好奖励函数计算的事件加权得分。
- **对比方法**：
  - BC Only：仅使用离线偏好轨迹进行行为克隆。
  - Pretrain (ZSC)：仅使用FCP训练，无偏好数据。
  - Pretrain + BC：预训练后再进行BC。
  - Pretrain + BC + Recover：BC后进行一次恢复（无交替）。
  - EAR（本文方法）：逐轮交替恢复。
  - 补充实验：对比MEP、TrajDi等多样性增强方法。
- **评估协议**：每个设置使用3个随机种子，报告均值和标准差。同时测试智能体与未见过的偏好代理（非训练用）的合作性能，衡量泛化能力。

## 4. 资源与算力

- **硬件**：单张 NVIDIA GeForce RTX 2080 Ti GPU。
- **训练耗时示例**（Many Orders布局，Style A）：
  - 1-epoch 行为克隆：27.1 秒。
  - 一轮环境采样（200条轨迹）：5.7 秒。
  - 一轮采样后的PPO训练（15 epoch）：10.5 秒。
- **总交互预算**：约 2×10^6 环境步（200×400 每步 × 若干滚轮批次）。
- **EAR收敛所需滚轮批次**：约 188–206 批次（见表4），在合理预算内。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 两个布局 × 三种偏好风格 × 多种方法（至少5种） = 30+ 个实验条件，每个条件3种子 → 约100组试验。
  - 附加消融实验：不同恢复策略（图2、图4）、预训练必要性、交替必要性、泛化测试（表2、表11）。
  - 补充对比MEP/TrajDi（表13）。
- **实验结果充分性**：统计报告了均值与标准差，趋势清晰；EAR在偏好得分和泛化回报上均优于或持平最优基线；消融实验验证了每个组件的必要性。
- **公平性**：使用相同策略池和种子控制；但对真实人类偏好仅用偏好代理模拟，可能引入偏差。

## 6. 论文的主要结论与发现

1. 预训练对于偏好学习至关重要：从零开始在小数据上做BC会导致严重过拟合，且恢复后泛化难以挽回。
2. 即使轻量级（1 epoch）的偏好学习也会显著降低泛化性能，但恢复后能保留部分偏好信息。
3. **EAR方法** 在偏好对齐和泛化能力上均优于其他基线，能够稳定地实现两者平衡。
4. 交替恢复将偏好精度恢复到完全收敛BC的水平，而不会像单次恢复那样下降10%。
5. **局限性**：当前环境相对简单；偏好模拟与真实人类有差距；未利用大量无标签数据。

## 7. 优点

- **问题新颖性**：首次系统提出“在线泛化+离线偏好”的联合问题，贴合实际游戏场景需求。
- **方法简洁有效**：仅需修改训练流程（交替BC与恢复），不改变底层RL算法，易于集成。
- **恢复策略设计巧妙**：观察到恢复后偏好记忆部分保留，设计了逐轮交替来巩固效果。
- **实验充分**：在多个布局、多种偏好风格下验证，包含消融、泛化测试和可视化分析。
- **可复现性**：提供完整超参数、算法伪代码和计算资源信息。

## 8. 不足与局限

- **环境局限性**：仅使用相对简单的Overcooked环境（两个布局），未在更复杂的多人任务（如5v5 MOBA）中验证。
- **偏好模拟偏差**：使用奖励加权的固定偏好代理模拟人类，可能无法完全反映真实人类的动态偏好和噪声。
- **数据利用率低**：未利用用户提供的大量无标签轨迹（仅使用少量“点赞”轨迹），可能错过额外信息。
- **方法扩展性**：当前方法依赖策略池和离线BC，当偏好风格与策略池分布差异极大时，恢复代价可能更高。
- **计算资源**：尽管单GPU可行，但总预算2e6步在更复杂环境中可能不够，需更多研究。
- **未涉及隐私与公平等社会影响**：论文未讨论偏好数据收集的隐私风险或潜在偏见。

（完）
