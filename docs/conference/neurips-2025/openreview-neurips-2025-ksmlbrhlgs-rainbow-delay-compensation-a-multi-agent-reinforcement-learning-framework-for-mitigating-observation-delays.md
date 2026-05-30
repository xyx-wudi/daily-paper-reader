---
title: "Rainbow Delay Compensation: A Multi-Agent Reinforcement Learning Framework for Mitigating Observation Delays"
title_zh: 彩虹延迟补偿：缓解观测延迟的多智能体强化学习框架
authors: "Songchen Fu, Siang Chen, Shaojing Zhao, Letian Bai, Hong Liang, Ta Li, Yonghong Yan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=KsmlBRhLgs"
tags: ["query:marl"]
score: 9.0
evidence: 针对观测延迟的去中心化多智能体强化学习框架
tldr: 该工作针对现实多智能体系统中普遍存在的观测延迟问题，首先形式化了去中心化随机个体延迟部分可观测马尔可夫决策过程（DSID-POMDP），然后提出彩虹延迟补偿（RDC）训练框架，用于处理具有不同延迟特征的离散观测组件。该框架在多种延迟场景下显著提升了MARL算法的鲁棒性和性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 870, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 722, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 578, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 859, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 860, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 861, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 862, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 859, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 858, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1401, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 727, \"height\": 912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1415, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1422, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1448, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1447, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1423, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ksmlbrhlgs/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1424, \"height\": 532, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1054, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1202, \"height\": 1005, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1333, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 1138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1327, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1424, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1344, \"height\": 1218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1312, \"height\": 1219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ksmlbrhlgs/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1304, \"height\": 411, \"label\": \"Table\"}]"
motivation: 观测延迟普遍存在且各组件延迟不同，影响MARL决策。
method: 提出DSID-POMDP模型和RDC框架进行延迟补偿训练。
result: 在标准基准测试上有效提升了延迟环境下的性能。
conclusion: RDC为处理多智能体观测延迟提供了有效方案。
---

## Abstract
In real-world multi-agent systems (MASs), observation delays are ubiquitous, preventing agents from making decisions based on the environment's true state. An individual agent's local observation typically comprises multiple components from other agents or dynamic entities within the environment. These discrete observation components with varying delay characteristics pose significant challenges for multi-agent reinforcement learning (MARL). In this paper, we first formulate the decentralized stochastic individual delay partially observable Markov decision process (DSID-POMDP) by extending the standard Dec-POMDP. We then propose the Rainbow Delay Compensation (RDC), a MARL training framework for addressing stochastic individual delays, along with recommended implementations for its constituent modules. We implement the DSID-POMDP's observation generation pattern using standard MARL benchmarks, including MPE and SMAC. Experiments demonstrate that baseline MARL methods suffer severe performance degradation under fixed and unfixed delays. The RDC-enhanced approach mitigates this issue, remarkably achieving ideal delay-free performance in certain delay scenarios while maintaining generalizability. Our work provides a novel perspective on multi-agent delayed observation problems and offers an effective solution framework. The source code is available at https://github.com/linkjoker1006/RDC-pymarl.

---

## 论文详细总结（自动生成）

# 论文总结：Rainbow Delay Compensation: A Multi-Agent Reinforcement Learning Framework for Mitigating Observation Delays

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：在现实多智能体系统（MAS）中，观测延迟普遍存在，且每个智能体观测的不同组件（如其他智能体状态、环境状态）可能具有**不同的随机延迟**，这破坏了马尔可夫假设，导致标准MARL算法性能严重下降。
- **背景**：现有工作多集中于单智能体固定延迟或简单扩展，缺乏对多智能体下**随机个体延迟**的系统建模与解决方案。
- **意义**：作者定义了**DSID-POMDP**（去中心化随机个体延迟部分可观测马尔可夫决策过程），并提出了**RDC**（彩虹延迟补偿）框架，为处理多智能体观测延迟问题提供了统一的理论模型和实用的训练框架。

## 2. 方法论
### 核心思想
通过**补偿模块**重建当前时刻的无延迟观测，并结合**延迟协调评论家**、**课程学习演员**和**知识蒸馏**，使智能体在训练和推理中有效抵抗延迟影响。

### 关键技术细节
- **DSID-POMDP**：扩展Dec-POMDP，引入状态扩展（包含过去T步状态）和个体延迟分布，每个实体只暴露自身状态。
- **延迟补偿器**：
  - **Flash模式**：单步直接重建，速度快，资源消耗低，适合延迟变化较小的场景。
  - **Echo模式**：自回归多步重建，逐步补偿，适应性强，但推理较慢。
  - 实现架构：GRU或Transformer，输入包括历史观测、历史动作、延迟值向量。
  - 损失函数：`L_flash = L_CE + L_MSE`（分类+回归）；`L_echo = (1/T) Σ(L_CE + L_MSE)` 对每一步。
- **延迟协调评论家**：训练时使用全局无延迟状态作为评论家输入，推理时不需评论家，兼容CTDE范式。
- **课程学习演员**：训练初期给演员提供无延迟观测，逐步过渡到补偿观测，采用线性退火策略，防止早期不收敛。
- **知识蒸馏**：先训练一个低延迟环境下的教师模型，然后在学生模型训练时，用教师模型指导学生的动作分布、Q值和隐藏表示。
  - 蒸馏损失：`L_kd = L_CE(actions) + β1·L_MSE(Q) + β2·L_MSE(hidden)`
  - 整体训练损失：`L_rdc_rl = α L_rl + (1-α) L_kd`，α退火。
- **完整性**：所有模块（除蒸馏外）均在线训练，与RL同步更新。

## 3. 实验设计
### 数据集/场景
- **MPE**（Multi-Agent Particle Environment）：simple-tag（竞争/合作）、simple-spread（合作）、simple-reference（合作+通信）。
- **SMAC**（StarCraft Multi-Agent Challenge）：3s_vs_5z、5m_vs_6m、6h_vs_8z（难度递增，离散动作，部分可观测）。
### 基准方法
- **Oracle**：无延迟环境下用基线算法训练（理想上界）。
- **Base**：FT-QMIX或FT-VDN（代码优化版）在有延迟环境下直接训练。
- **Base+DR**：Base + 延迟协调评论家。
- **Base+C**：Base + 课程学习演员。
- **Base+DR+C**：Base + DR + C。
- **Flash/ Echo + 各子模块消融**：如Flash+DR、Flash+H+DR、Flash+H+DR+KD等。
- **延迟设置**：固定延迟（0~12）、随机延迟（均匀分布3-9、6-12），以及二项分布、正态分布、泊松分布。
### 评价指标
- MPE：平均奖励（每10K训练步测试64或32个episode，最终测试1,280个episode）。
- SMAC：胜率（Win Rate），同时记录奖励。

## 4. 资源与算力
- **硬件**：NVIDIA A30 GPU（约24GB VRAM），Intel Xeon Gold 6242R（3.10GHz）或6338（2.00GHz）CPU。
- **训练时间**（以RDC+Transformer补偿器为例）：
  - MPE：Echo约23.8小时，Flash约10.8小时（含教师模型训练时间）。
  - SMAC：Echo约58.3小时，Flash约34.5小时（含教师模型训练时间）。
- **说明**：以上为单次运行耗时，未提及具体GPU数量（推测单卡训练）。

## 5. 实验数量与充分性
- **实验数量**非常丰富：涵盖6个场景（3 MPE + 3 SMAC）、多种延迟范围（固定0-12，随机3-9/6-12）、多种延迟分布（均匀、二项、正态、泊松）、多种消融（历史输入、DR、C、KD、补偿器模式、网络架构GRU/Transformer、基线算法FT-QMIX/FT-VDN）、以及历史长度影响、教师强制训练模式对比、超参数敏感性（附录D表3-9、图16-21）。
- **充分性**：所有实验均报告了误差条或置信区间（多次运行），训练曲线和测试表格完整。消融实验系统评估了每个模块的贡献，对比公平（训练步骤数一致，Oracle额外训练10M步验证上界）。
- **评价**：实验设计客观、全面，结论可靠。

## 6. 主要结论与发现
- 基线（Base）在延迟环境下性能**急剧下降**，尤其是复杂SMAC任务（5m_vs_6m、6h_vs_8z）胜率接近0。
- **RDC显著提升性能**：在多种固定和随机延迟下，RDC增强的方法**接近甚至达到无延迟Oracle水平**，尤其在MPE的SPREAD和REFERENCE任务中，奖励几乎不受延迟影响。
- **Echo vs Flash**：Echo泛化性更好，在未见过延迟分布下表现更稳健；Flash推理更快，但对历史长度敏感，易过拟合。
- **知识蒸馏贡献大**：利用低延迟教师模型指导，显著提升学生模型收敛速度和最终性能，且不依赖教师补偿器。
- **延迟协调评论家与课程学习**：在复杂任务（SMAC）中必不可少，简单任务（MPE）中课程学习无效。
- **分布泛化**：在均匀分布训练后，对二项、正态、泊松分布测试仍保持良好性能。

## 7. 优点
- **理论贡献**：首次形式化定义DSID-POMDP，为多智能体随机延迟观测提供统一数学框架。
- **模块化框架**：RDC解耦了补偿、训练、蒸馏等组件，可灵活替换和扩展，兼容多种MARL算法（不仅限于actor-critic）。
- **双补偿器模式**：Flash（快速）和Echo（精确），满足不同场景需求。
- **实验全面**：覆盖两个主流基准、多种延迟模式、多种基线、充分消融，代码开源。
- **实用性**：在固定和随机延迟下均能达到接近无延迟性能，具有很强的实际应用价值。

## 8. 不足与局限
- **理论假设**：DSID-POMDP假设每个实体只暴露自身状态，不能处理信息跳转或中继场景（如通过其他实体传递信息）。
- **泛化性不足**：SMAC任务下，随着延迟增加，胜率快速下降，说明补偿器在高延迟复杂场景下泛化能力仍有限。
- **训练开销大**：需要训练教师模型，且在线训练补偿器，整体训练时间比基线长（尤其Echo模式）。
- **未覆盖连续动作空间**：实验仅在离散动作环境（MPE、SMAC）进行，连续控制场景未验证。
- **超参数依赖**：蒸馏权重、退火步数等需要针对场景调参，未提供自适应策略。
- **单卡资源**：未测试大规模多智能体场景的扩展性，仅使用单GPU。

（完）
