---
title: "PARCO: Parallel AutoRegressive Models for Multi-Agent Combinatorial Optimization"
title_zh: PARCO：面向多智能体组合优化的并行自回归模型
authors: "Federico Berto, Chuanbo Hua, Laurin Luttmann, Jiwoo Son, Junyoung Park, Kyuree Ahn, Changhyun Kwon, Lin Xie, Jinkyoo Park"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=9F2Cmgo17M"
tags: ["query:marl"]
score: 8.0
evidence: 多智能体组合优化中基于Transformer的通信实现协作
tldr: 针对多智能体组合优化中协调困难、泛化差和延迟高的问题，本文提出PARCO框架，采用Transformer通信层实现代理间高效协作，并结合并行自回归生成快速构建高质量解。实验表明该方法在多个NP难问题上优于现有方法，显著提升协调效果和泛化能力，为多智能体组合优化提供通用高效的强化学习方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 656, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 468, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 734, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-9f2cmgo17m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1321, \"height\": 1489, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 1327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1094, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1235, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1311, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-9f2cmgo17m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 337, \"label\": \"Table\"}]"
motivation: 现有学习方法在多智能体组合优化中协调不佳、泛化差且延迟高。
method: 提出PARCO强化学习框架，集成Transformer通信层和并行自回归生成，实现高效协作。
result: 在多个组合优化问题上，PARCO取得更优解质量和更低的计算延迟。
conclusion: PARCO为多智能体组合优化提供了一种通用高效的强化学习解决方案。
---

## Abstract
Combinatorial optimization problems involving multiple agents are notoriously challenging due to their NP-hard nature and the necessity for effective agent coordination. Despite advancements in learning-based methods, existing approaches often face critical limitations, including suboptimal agent coordination, poor generalization, and high computational latency. To address these issues, we propose PARCO (Parallel AutoRegressive Combinatorial Optimization), a general reinforcement learning framework designed to construct high-quality solutions for multi-agent combinatorial tasks efficiently. To this end, PARCO integrates three key novel components: (1) transformer-based communication layers to enable effective agent collaboration during parallel solution construction, (2) a multiple pointer mechanism for low-latency, parallel agent decision-making, and (3) priority-based conflict handlers to resolve decision conflicts via learned priorities. We evaluate PARCO in multi-agent vehicle routing and scheduling problems, where our approach outperforms state-of-the-art learning methods, demonstrating strong generalization ability and remarkable computational efficiency. We make our source code publicly available to foster future research: https://github.com/ai4co/parco.

---

## 论文详细总结（自动生成）

# PARCO：面向多智能体组合优化的并行自回归模型 — 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：多智能体组合优化（Multi-Agent Combinatorial Optimization）问题如多车辆路径规划、生产调度等，具有NP-hard特性且要求智能体间有效协作。现有基于学习的方法面临三大局限：智能体协调不佳（suboptimal coordination），导致解质量低；泛化能力差，无法适应问题规模和智能体数量的变化；计算延迟高（high computational latency），因为传统自回归模型需要串行生成每一步动作。
- **整体意义**：本文提出PARCO框架，通过并行化解决方案构建，提高多智能体组合优化的效率和质量，旨在提供一种通用、高效的强化学习解决方案，以替代传统精确算法和启发式方法，并克服现有神经组合优化（NCO）方法的缺陷。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将多智能体组合优化建模为合作式多智能体马尔可夫决策过程（Cooperative Multi-Agent MDP），智能体在每一步并行选择动作，通过冲突处理机制保证可行性。并行自回归生成显著减少总构建步骤（从每个智能体的串行步骤之和降为最大步骤数）。
- **关键组件**：
  1. **Transformer通信层（Communication Layers）**：在解码阶段，将智能体的动态上下文嵌入通过多头部自注意力（MHA）和MLP处理，使智能体之间能交换状态信息，增强协作。该层对智能体数量无关，支持任意数量智能体。
  2. **多指针机制（Multiple Pointer Mechanism）**：在解码器中，所有智能体的查询向量经过通信层后，与节点嵌入进行交叉注意力，生成联合logit矩阵，并行输出每个智能体的动作概率分布，减少延迟。
  3. **基于优先级的冲突处理（Priority-based Conflict Handler）**：当多个智能体选择同一动作时，根据学习到的优先级（模型输出概率）决定哪个智能体执行该动作，其它智能体执行回退动作（如保持当前位置）。优先级也可基于启发式（如最小成本、最近距离），但学习到的优先级效果最佳。
- **训练方案**：采用REINFORCE梯度估计器，结合共享基线（shared baseline，如SymNCO的K个对称增广），损失函数为策略梯度。训练时每个批次采样多个问题实例，并计算优势函数。

## 3. 实验设计：数据集/场景、benchmark、对比方法
- **场景与问题**：
  - **HCVRP**（异构容量车辆路径问题，min-max目标）：客户60/100个，智能体3/5/7个。
  - **OMDCPDP**（开放多仓库容量取送货问题，最小化延迟）：客户50/100个，智能体5/7/10/10/15/20个。
  - **FFSP**（柔性流水车间调度问题，最小化makespan）：作业20/50/100个，机器12/18/24/30个。
- **对比方法**：
  - **传统求解器**：SISRs、Genetic Algorithm (GA)、Simulated Annealing (SA)、Google OR-Tools、Gurobi。
  - **神经基线**：AM、ET、DPN、DRL Li、2D-Ptr（HCVRP）；HAM、MAPDP（OMDCPDP）；MatNet（FFSP）。
- **评估指标**：平均目标函数值（Obj.）、与最优解的Gap（%）、推理时间（秒）。报告了greedy（g.）和sampling（s.，如1280个样本）两种策略。

## 4. 资源与算力
- 论文明确说明了硬件与训练配置：
  - 硬件：2颗 Intel Xeon Gold 6338 CPU，8张 NVIDIA RTX 4090 GPU（每张24GB VRAM）。
  - 训练：使用4块GPU进行分布式数据并行训练，单模型训练最多100个epoch（HCVRP约15小时，OMDCPDP<5小时，FFSP对应100-200个epoch）。
  - 推理：仅使用一个CPU和一个GPU。
- 软件：Python 3.12, PyTorch 2.5, PyTorch Lightning, RL4CO库, Ubuntu 24.04。

## 5. 实验数量与充分性
- **实验数量**：论文在三大类问题（HCVRP、OMDCPDP、FFSP）上进行了系统性实验，每个问题涵盖多种（节点数×智能体数）配置（共6种×3=18种主要配置）。另外进行了消融实验（通信层、冲突处理器）、大规模泛化实验（节点和智能体规模达训练时的10倍，如N=1000, M=200；以及XXL实验N=5000）、与AR模型的可扩展性对比、以及在mTSP上额外对比分散式方法。消融实验每种设置重复3次求标准差。
- **充分性与公平性**：对比了传统求解器、神经基线中目前最先进的方法，并报告了greedy和sampling两种模式的结果。数据生成和测试数据集规模足够大（如HCVRP用1280个测试实例，OMDCPDP用1000个，FFSP用100个）。消融实验覆盖了关键设计选择。实验设置公开，代码开源，可复现。因此实验设计充分且公平。

## 6. 论文的主要结论与发现
- PARCO在所有三个问题上均优于现有神经方法（包括AR和并行方法），在解质量、泛化能力和推理速度上均取得最佳或接近最优结果。
- 在HCVRP上，PARCO（sampling）的Gap比2D-Ptr降低约1-2个百分点，推理速度2-3倍快。
- 在OMDCPDP上，PARCO（sampling）在多数配置上达到0% Gap（即最优），优于OR-Tools和MAPDP，且推理时间极短（毫秒级）。
- 在FFSP上，PARCO在大规模和高智能体数下显著优于MatNet，速度是MatNet的4倍以上，Gap更低。
- 大规模零样本泛化实验中，PARCO在N=1000、M=200以及N=5000、M=1000上仍保持极低Gap（<1%），而AR方法（HAM）和OR-Tools无法良好泛化或耗时过长。
- 通信层和基于优先级的冲突处理器相比无通信、随机冲突处理等基线均有显著提升，学习到的优先级优于启发式优先级。
- 并行自回归结构相比传统AR模型实现3.3×到24.7×的加速，且智能体越多加速越明显。

## 7. 优点
- **通用性**：框架设计不局限于特定问题，可应用于多智能体路径规划、调度等多种CO任务。
- **高效性**：并行解码极大降低延迟，非常适合实时或大规模场景。
- **强泛化能力**：在训练时未见过的节点/智能体规模下仍保持高质量，零样本泛化表现突出。
- **技术创新**：Transformer通信层实现智能体间高效信息交互；多指针机制支持并行动作生成；基于学习的优先级冲突处理解决了多智能体决策冲突问题。
- **完整开源**：代码、训练配置、模型检查点均公开，便于复现和后续研究。

## 8. 不足与局限
- **固定智能体数量**：PARCO要求预先定义智能体数量M，无法直接处理智能体数量不明确的CO问题（如允许任意数量智能体动态加入）。论文承认此局限，并提出未来可通过预测模块或滚动探索M值来扩展。
- **实验覆盖有限**：虽然涉及三类问题，但未覆盖更多类型（如带时间窗的车辆路径问题、整数线性规划等），可能影响通用性声称的强度。
- **训练成本**：虽然推理快，但训练仍需多GPU和数小时（HCVRP约15小时），对于资源受限的研究者有一定门槛。
- **冲突处理假设**：冲突处理中回退动作为“保持当前状态”，在部分问题中可能导致额外步骤，虽不影响最终解但可能延长构建过程；文中未对回退策略进行深入优化分析。
- **消融实验深度**：通信层、冲突处理器的消融实验仅报告了Gap变化，未分析不同机制对训练稳定性和收敛速度的影响。

（完）
