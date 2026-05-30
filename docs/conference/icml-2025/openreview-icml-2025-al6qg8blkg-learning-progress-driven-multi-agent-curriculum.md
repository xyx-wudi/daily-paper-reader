---
title: Learning Progress Driven Multi-Agent Curriculum
title_zh: 学习进度驱动的多智能体课程学习
authors: "Wenshuai Zhao, Zhiyuan Li, Joni Pajarinen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Al6qG8BlKg"
tags: ["query:marl"]
score: 9.0
evidence: 基于学习进度的多智能体课程学习
tldr: 针对多智能体课程学习中人工定义难度和奖励方差问题，提出基于TD误差的学习进度度量，自动调整智能体数量作为课程变量，在多个MARL任务中提升学习效率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 676, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 805, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 823, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 1743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 821, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1766, \"height\": 1751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1765, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1274, \"height\": 1063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-al6qg8blkg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1765, \"height\": 867, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1569, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1183, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 614, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 484, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 562, \"height\": 861, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 563, \"height\": 863, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 636, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-al6qg8blkg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 567, \"height\": 966, \"label\": \"Table\"}]"
motivation: 手动定义的课程存在缺陷，基于奖励的自动课程高方差且加剧信用分配问题。
method: 使用TD误差衡量学习进度，自动推进智能体数量从少到多。
result: 在多个MARL任务中加速学习并提升最终性能。
conclusion: 基于学习进度的课程有效提升MARL训练效率。
---

## Abstract
The number of agents can be an effective curriculum variable for controlling the difficulty of multi-agent reinforcement learning (MARL) tasks. Existing work typically uses manually defined curricula such as linear schemes. We identify two potential flaws while applying existing reward-based automatic curriculum learning methods in MARL: (1) The expected episode return used to measure task difficulty has high variance; (2) Credit assignment difficulty can be exacerbated in tasks where increasing the number of agents yields higher returns which is common in many MARL tasks. To address these issues, we propose to control the curriculum by using a TD-error based *learning progress* measure and by letting the curriculum proceed from an initial context distribution to the final task specific one. Since our approach maintains a distribution over the number of agents and measures learning progress rather than absolute performance, which often increases with the number of agents, we alleviate problem (2). Moreover, the learning progress measure naturally alleviates problem (1) by aggregating returns. In three challenging sparse-reward MARL benchmarks, our approach outperforms state-of-the-art baselines.

---

## 论文详细总结（自动生成）

# Learning Progress Driven Multi-Agent Curriculum 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在多智能体强化学习（MARL）中，智能体数量是控制任务难度的自然课程变量。现有工作通常采用手动定义的课程（如线性增加智能体数量），但存在两个潜在缺陷：  
  - 基于**期望回合回报**（episode return）衡量任务难度时，由于稀疏奖励，估计方差高。
  - 在**奖励随智能体数量增加而增加**的常见MARL任务中（如Simple-Spread任务），使用回报作为目标可能加剧**信用分配困难**，且导致课程倾向于选择更多智能体（易获得高回报但不利于策略改进）。
- **整体含义**：需要一种更智能的、基于**学习进度**而非绝对性能的自动课程学习方法来控制智能体数量，以提升稀疏奖励下MARL的训练效率和最终性能。

## 2. 论文提出的方法论

### 核心思想
- 构建一个**上下文强化学习**框架，其中上下文变量c为智能体数量。维护一个关于c的分布，通过**两阶段优化**自动调整该分布，使其从初始分布向目标任务分布推进。
- 关键改进：用**TD误差（价值损失）** 替代回合回报作为衡量学习进度的指标，从而：
  - 降低估计方差（TD误差基于所有状态转移，而非仅回合结束时一个值）。
  - 避免因智能体增多导致回报自然升高而误导课程（TD误差反映策略改进潜力，而非绝对回报）。

### 关键技术细节
- **定义**：
  - 学习进度 \( LP(c) = \frac{1}{2} \mathbb{E}_{s, a \sim \pi(a|s,c)} \left[ \|R(s,a) - V(s)\|^2 \right] \)，即TD误差的平方。
  - 利用集中式训练-分散执行（CTDE）框架，可以获取完整状态信息以准确估计价值损失。
- **算法流程（SPMARL）**：
  1. 初始化上下文分布（如智能体数量的高斯分布）、策略参数、目标分布等。
  2. 在每个迭代中：
     - **策略学习**：从当前上下文分布中采样多个智能体数量，收集轨迹，用MAPPO等MARL算法更新策略和价值网络。
     - **上下文分布更新**（两阶段）：
       - **阶段1（提升学习进度）**：若当前平均性能低于阈值 \( V_{LB} \)，则最大化加权学习进度（通过重要性采样调整新分布下的LP），同时受KL散度约束（保持分布变化平滑）。
       - **阶段2（逼近目标）**：若性能达到阈值，则最小化当前分布与目标分布之间的KL散度，仍保持KL约束，从而逐步收敛到目标智能体数量。
- **对比先前方法**：SPRLM（直接扩展SPRL到多智能体）仍使用回合回报，而SPMARL使用学习进度，同时保留两阶段结构和KL约束。

## 3. 实验设计

### 使用场景与基准（Benchmark）
| 场景 | 描述 | 目标智能体数量 |
|------|------|----------------|
| **MPE Simple-Spread** | 智能体覆盖地标，稀疏奖励（仅当≥4个地标被覆盖时获正奖励） | 8个智能体，8个地标 |
| **XOR Matrix Game** | N玩家协作游戏，需所有玩家选择不同动作才获正奖励 | 20个玩家 |
| **SMAC-v2**（StarCraft多智能体挑战） | 四种Protoss任务（5v5至8v8），稀疏奖励（胜者+1负者-1） | 5v5至8v8 |
| 额外：SMAC-v2 Terran/Zerg任务、BenchMARL的Balance和Wheel（密集奖励） | 进一步验证 |

### 对比方法
- **W/O teacher**：无课程，直接训练目标任务（因稀疏奖励均失败，图中未展示）
- **Linear**：线性增加/减少智能体数量（现有工作抽象）
- **ALPGMM**：基于绝对学习进度的高斯混合模型采样（但仍基于奖励差值）
- **VACL**：变分自动课程学习，使用SVGD更新任务分布
- **SPRLM**：直接应用单智能体SPRL到多智能体（使用回合回报）
- **SPMARL**：本文方法（使用TD误差学习进度）

### 评估指标
- **目标任务上的评估回报/胜率**（主要指标）
- **生成的课程曲线**（智能体数量随时间变化）
- **训练过程中回报**（反映算法在不同任务上的探索效率）

## 4. 资源与算力

- 论文**未明确说明具体GPU型号、数量和训练时长**。仅在致谢中提及：
  - 使用CSC（芬兰IT科学中心）提供的**LUMI超算**（EuroHPC联合事业）以及**Aalto Science-IT项目**的计算资源。
  - 研究由芬兰研究理事会资助（357301）。
- 实验涉及多轮随机种子（5个种子）和多个基准，算力需求较大，但细节未公开。

## 5. 实验数量与充分性

### 主要实验组数
- **主基准**：3个核心基准（Simple-Spread、XOR、SMAC-v2 4种任务），每个方法5个随机种子，共约30条学习曲线。
- **补充实验**（附录）：
  - SMAC-v2 Terran和Zerg的另外4个任务
  - BenchMARL的2个任务（Balance和Wheel）
  - 方差对比（4个任务）
  - 超参数 \( V_{LB} \) 消融（2个任务）
  - 显著性检验（Mann-Whitney U检验）
- **总计约15个不同任务**，覆盖稀疏和密集奖励、不同智能体规模。

### 充分性与公平性
- **充分**：涵盖了常见的自动课程学习方法，并专门设计了对比以凸显问题（如Linear从少到多失败、VACL不收敛于目标分布）。
- **公平**：所有方法共享相同的底层MARL算法（MAPPO），超参数尽量保持一致。对于SPRLM和SPMARL，KL散度约束等设置相同。
- **客观**：提供了95%置信区间和p值统计检验，结果透明。

## 6. 论文的主要结论与发现

1. **智能体数量是有效的课程变量**，在稀疏奖励问题中显著提升探索效率。
2. **直接使用回合回报的自动课程方法（如SPRLM）存在方差高和信用分配恶化问题**，在SMAC-v2等任务中表现不稳定甚至失败。
3. **基于TD误差的学习进度指标（SPMARL）**：
   - 估计方差更低，提供更稳定的课程更新信号。
   - 能自动生成合理的课程（先利用较多智能体快速获得奖励，再收敛到目标任务），加速学习并提升最终性能。
4. **SPMARL在大部分任务上优于或持平于现有方法**，尤其在稀疏奖励的Simple-Spread、XOR、SMAC-v2 Protoss任务上表现突出。在密集奖励的BenchMARL任务中性能相当，但课程分布能正确收敛到目标。
5. 消融实验表明，性能阈值 \( V_{LB} \) 在较大范围内鲁棒。

## 7. 优点

- **方法创新**：首次将**TD误差**作为学习进度指标用于MARL课程学习，解决了奖励信号的两个突出问题。
- **理论直觉清晰**：将价值损失与策略改进潜力联系起来，类比于优先经验回放（PER）但应用于课程生成。
- **实验设计全面**：涵盖多种难度、多种奖励结构（稀疏/密集），并进行了统计显著性检验和消融。
- **算法实用性强**：SPMARL使用两阶段优化与KL约束，保持训练稳定，且能自动收敛到目标任务分布。
- **代码开源**（GitHub链接提供），便于复现。

## 8. 不足与局限

- **实验覆盖的局限性**：
  - 仅测试了MAPPO作为底层算法，未验证其他MARL方法（如QMix、VDN）下的表现。
  - 未在更复杂的大规模任务（如数百个智能体）上测试。
  - BenchMARL密集奖励任务中优势不明显，说明方法对稀疏奖励环境更有效。
- **计算资源细节不透明**：未报告具体GPU型号、训练时长，影响复现和效率评估。
- **理论基础有待深化**：虽然TD误差直观，但未严格证明其与策略改进的单调关系；KL约束在第二阶段仍沿用自SPRL，作者也提到可进一步研究是否必要。
- **实际应用限制**：课程生成依赖于性能阈值 \( V_{LB} \) 的设定（需先验知识或手动调节），虽然消融显示鲁棒，但最佳值仍取决于任务。
- **未考虑异构智能体或动态变化的智能体类型**：仅支持同构智能体数量变化，无法处理智能体角色不同的场景。

（完）
