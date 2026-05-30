---
title: "AI for Global Climate Cooperation: Modeling Global Climate Negotiations, Agreements, and Long-Term Cooperation in RICE-N"
title_zh: AI推动全球气候合作：在RICE-N中建模全球气候谈判、协议与长期合作
authors: "Tianyu Zhang, Andrew Robert Williams, Phillip Wozny, Kai-Hendrik Cohrs, Koen Ponse, Marco Jiralerspong, Soham Rajesh Phade, Sunil Srinivasa, Lu Li, Yang Zhang, Prateek Gupta, Erman Acar, Irina Rish, Yoshua Bengio, Stephan Zheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=PX29zF9wRb"
tags: ["query:marl"]
score: 8.0
evidence: MARL应用于全球气候合作建模
tldr: 全球气候合作面临复杂博弈挑战。本文提出RICE-N模型，利用多智能体强化学习模拟多个区域在气候谈判中的策略行为。智能体在没有中央权威的情况下学习长期合作策略，实验表明MARL能有效促进气候协议达成并平衡经济发展。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1425, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 439, \"height\": 173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 850, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1791, \"height\": 884, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1690, \"height\": 1290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1691, \"height\": 1295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-px29zf9wrb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 877, \"height\": 569, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1759, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1718, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1708, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1717, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1729, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 1412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-px29zf9wrb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1344, \"height\": 1232, \"label\": \"Table\"}]"
motivation: 全球气候合作缺乏中央权威，需要模型模拟复杂博弈。
method: 使用多智能体强化学习（MARL）驱动智能体在集成评估模型RICE-N中学习合作策略。
result: MARL智能体能够达成有效气候协议，支持长期合作。
conclusion: MARL是模拟和促进全球气候合作的有力工具。
---

## Abstract
Global cooperation on climate change mitigation is essential to limit temperature increases while supporting long-term, equitable economic growth and sustainable development. Achieving such cooperation among diverse regions, each with different incentives, in a dynamic environment shaped by complex geopolitical and economic factors, without a central authority, is a profoundly challenging game-theoretic problem. This article introduces RICE-N, a multi-region integrated assessment model that simulates the global climate, economy, and climate negotiations and agreements. RICE-N uses multi-agent reinforcement learning (MARL) to encourage agents to develop strategic behaviors based on the environmental dynamics and the actions of the others. We present two negotiation protocols: (1) Bilateral Negotiation, an exemplary protocol and (2) Basic Club, inspired from Climate Clubs and the carbon border adjustment mechanism (Nordhaus, 2015; Comissions, 2022). We compare their impact against a no-negotiation baseline with various mitigation strategies, showing that both protocols significantly reduce temperature growth at the cost of a minor drop in production while ensuring a more equitable distribution of the emission reduction costs.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：全球气候变化合作面临“公地悲剧”困境——各地区（国家）在没有中央权威的情况下，出于自身利益最大化动机，难以达成并维持有效的减排合作。这是一个复杂的博弈论问题，涉及动态环境、政治经济异质性、长期利益权衡等挑战。
- **研究背景**：现有综合评估模型（IAM，如DICE/RICE）通常预设固定的外生政策路径，无法反映各地区的策略性行为；而传统博弈论模型又过于简化（如囚徒困境），缺乏多边、多目标、动态演化的真实性。IPCC报告强调需要立即行动，但现实中减排投资分布不均，发达国家与发展中国家存在巨大差异。
- **整体含义**：本文旨在通过引入多智能体强化学习（MARL），构建一个更真实的模拟平台（RICE-N），用于探索不同的气候谈判协议对长期气候-经济结果的影响，为政策设计提供理论和仿真依据。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- 将每个全球区域视为一个理性智能体（agent），通过MARL训练其策略，使其在动态气候-经济环境中通过学习最大化长期效用（福利函数）。谈判协议作为智能体之间的通信和约束机制，改变后续决策空间，从而影响合作结果。

### 关键技术细节

#### (a) RICE-N 综合评估模型
- 基于RICE模型扩展，包含**气候动态**（碳循环、温度上升）、**经济动态**（产出、资本、人口、技术）、**国际贸易与关税**（Armington需求模型）、以及**谈判协议模块**。
- 内生变量：资本、贸易平衡、碳质量、温度；外生变量：人口、技术、碳强度等。
- 关键方程（文字描述）：
  - 碳质量演化：三库模型（大气、上层海洋、下层海洋），受排放影响。
  - 温度演化：两层能量平衡模型，受大气CO₂浓度影响。
  - 产出：柯布-道格拉斯生产函数，\( Y = A K^\gamma L^{1-\gamma} \)。
  - 资本演化：考虑折旧、投资、气候损害（损伤函数）和减排成本。
  - 减排成本：\( \theta_1 \mu^{\theta_2} \)，其中 \( \theta_1 \) 随时间衰减。
  - 贸易：区域设定进口出价和出口上限，关税影响消费，消费组合使用Armington CES函数。
  - 效用函数：基于人均消费的常弹性效用（考虑福利损失因子 \( w \) 反映关税影响）。

#### (b) 谈判协议
- **双边谈判**：每个智能体向其他每个智能体提出减排率建议和请求，评估后接受或拒绝，最终承诺所有已接受提议中的最高减排率（产生强约束）。
- **基本俱乐部**：每个智能体提议一个俱乐部减排率，形成共同最低减排率的俱乐部，对俱乐部外成员征收差价关税（类似碳边境调整机制）。结果通过动作掩码（action mask）约束后续可选择的减排率下限。

#### (c) MARL训练
- 使用**A2C**（异步优势演员-评论家）算法，策略网络共享参数但输入包含区域独热编码和特异性特征。
- 每个智能体最大化γ折扣累计效用：\( \max_{\pi_i} \mathbb{E}[\sum_t \gamma^t r_{i,t}] \)，其中 \( r_{i,t} \) 由效用函数给出。
- 行动空间：减排率、储蓄率、关税、进出口出价与上限、谈判提议/决策等。

## 3. 实验设计：使用的数据集/场景、基准、对比方法

### 数据集/场景
- **虚构的27个区域**：基于世界银行数据（GDP、资本、人口、CO₂排放），通过合并和拆分真实国家生成，非真实国家边界，但反映区域异质性。每个区域有校准的参数（初始资本、人口、技术增长率等）。
- **时间跨度**：每步代表5年，共步长 \( H \)（默认从2015年至2115年，即100年20步）。
- **气候模块**：默认使用DICE2016气候模型和损伤函数；扩展实验还使用了FaIR气候模型和更高损伤的H&S函数。

### 基准（Baseline）
1. **最小减排**：始终选择最低减排率（0%）。
2. **最大减排**：始终选择最高减排率（1）。
3. **无谈判**：智能体完全通过RL学习，没有谈判协议，自由选择减排率等行动。

### 对比方法
- **双边谈判**：应用上述双边谈判协议。
- **基本俱乐部**：应用基本俱乐部协议。
- 此外还比较了不同气候模型和损伤函数下的结果（图2）。

### 评估指标
- 全球温度异常、累积碳排放、全球GDP、全球消费。
- 公平性：基尼系数（针对减排成本占GDP比例、减排率、碳排放、消费）。

## 4. 资源与算力

- 文中明确提到：训练27个智能体、100,000 episodes，在**30个CPU的集群**上大约需要**3小时**。未提及GPU型号或数量，也未说明其他环境中使用的具体算力（如A2C实现包含CPU和GPU两种版本，但默认实验可能使用CPU集群）。
- 扩展实验（敏感性分析等）可能耗费额外资源，但未详细说明。
- **注意**：训练成本相对较低，表明模型在计算上可行，但大规模参数搜索或更复杂的MARL算法可能需要更多算力。

## 5. 实验数量与充分性

- **主要训练实验**：5种模型（最大减排、最小减排、无谈判、双边谈判、基本俱乐部），每种训练30,000 episodes（比文中提到的100k episodes少？注意：实际训练30k episodes用于评估，100k episodes用于27区域训练示例——存在不一致，但通常以30k为准）。然后对每种模型进行50次rollout（不同随机种子）获取均值与标准误。
- **扩展分析**：
  - 不同气候动态（DICE vs FaIR）和损伤函数（DICE2016 vs H&S）的比较（图2）。
  - 敏感性分析：扰动折扣因子、福利损失权重、消费替代率、国内商品偏好等参数（幅度±4%），观察温度、碳排放、GDP的变化百分比（图6）。
  - 公平性分析：报告基尼系数表（表1）。
  - 减排率分布分析（图9）。
- **充分性评价**：实验设计较为系统，覆盖了关键基线、多种协议、敏感性分析和公平性测量。但存在一些不足：
  - 未与真实世界谈判历史数据进行对比验证（模型输出是模拟，无法直接验证）。
  - 每个实验仅使用A2C算法，未比较其他MARL算法（如PPO、QMIX等）的影响。
  - 未进行完整的超参数搜索（如学习率、网络架构）。
  - 区域数量固定为27，未测试少区域或多区域下的鲁棒性。
  - 敏感性分析仅针对四个参数，且扰动幅度较小（±4%），可能不足以揭示模型在极端参数下的行为。
- 总体而言，实验在已有条件下较为充分，但在算法对比、超参数优化、验证与可推广性方面存在局限。

## 6. 论文的主要结论与发现

- **谈判协议显著改善气候结果**：与无谈判基线相比，双边谈判和基本俱乐部均大幅降低温度上升和累积碳排放，几乎匹配最大减排基准的水平。
- **经济成本较小**：谈判协议在早期经济产出略低于无谈判，但长期（2115年）基本俱乐部的GDP反超无谈判，且消费水平接近最小减排基线，表明可持续增长。
- **公平性提高**：谈判协议下，减排成本、减排率的基尼系数显著降低，说明各地区分担更均衡。
- **基本俱乐部优于双边谈判**：基本俱乐部在保持更好经济产出的同时，气候结果接近双边谈判（温度略高但GDP更高），且更贴近现实政策（如CBAM）。
- **模型参数敏感性较低**：在±4%扰动下，主要变量变化不超过3.16%，表明结果稳定。
- **损伤函数和气候模型的影响**：使用更高损伤函数（H&S）和更现实气候模型（FaIR）后，未谈判基线仍无法自发减排，但2°C目标理论上仍可达。

## 7. 优点

- **创新性**：首次将MARL与校准的IAM结合，用于模拟真实气候谈判，填补了现有模型无法处理策略性行为的空白。
- **模块化设计**：气候、经济、贸易、谈判组件松散耦合，易于扩展和替换（如不同气候模型、损伤函数、谈判协议）。
- **现实政策启发**：基本俱乐部协议基于Nordhaus的气候俱乐部和欧盟CBAM，具有实际法律和政策参考价值。
- **公平性分析**：引入基尼系数评估不同协议对区域间不平等的影响，不仅关注总效率也关注分配正义。
- **开源代码**：提供GitHub仓库，便于复现和后续研究。
- **敏感性分析**：验证了主要结论对关键经济参数的鲁棒性。

## 8. 不足与局限

- **模型简化与现实差距**：
  - 未考虑区域内温度差异、区域间损害异质性、以及社会经济阶层对气候损害的影响（忽略了气候正义中的阶级维度）。
  - 时间跨度有限（100年），未使用更长的300年版本（已有扩展但未用）。
  - 谈判过程是黑箱（神经网络的策略输出），缺乏可解释性。
  - 承诺是强制性的（通过动作掩码），无法模拟真实世界中的违约或“廉价谈话”（cheap talk）现象。
- **实验局限性**：
  - 仅使用A2C算法，未对比其他MARL算法，可能结论受算法选择影响。
  - 未与真实世界谈判结果进行校准或验证，结论纯粹是模拟的。
  - 区域数量固定为27，未测试不同聚合级别下的表现（如3个、7个、189个区域）。
  - 敏感性分析参数范围较窄（±4%），且仅四个参数，可能遗漏相互作用。
  - 实验只进行了一次训练（每个模型单一运行），未报告多次重复训练的策略稳定性。
- **应用风险**：模型不能直接用于实际政策制定，可能因简化假设产生误导；如果被滥用，可能加剧经济不平等（如俱乐部机制对发展中国家构成事实上的碳税，无补偿）。
- **碳足迹**：使用模型本身也有碳排放，建议用户关注能源消耗并抵消。

（完）
