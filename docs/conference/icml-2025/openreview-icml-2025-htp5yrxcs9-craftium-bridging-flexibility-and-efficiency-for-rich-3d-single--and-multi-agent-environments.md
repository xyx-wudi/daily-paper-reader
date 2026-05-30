---
title: "Craftium: Bridging Flexibility and Efficiency for Rich 3D Single- and Multi-Agent Environments"
title_zh: Craftium：为丰富的3D单智能体和多智能体环境搭建灵活与高效的桥梁
authors: "Mikel Malagón, Josu Ceberio, Jose A. Lozano"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=htP5YRXcS9"
tags: ["query:marl"]
score: 7.0
evidence: 提供了一个创建多智能体环境的平台
tldr: 针对现有2D环境无法满足3D空间推理需求而3D环境计算昂贵且缺乏多智能体支持的问题，提出Craftium平台。该平台高度可定制且易于使用，支持构建丰富的3D单智能体和多智能体环境。展示了从简单到复杂的多种环境，为多智能体强化学习研究提供了灵活的测试平台。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 723, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1511, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 319, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1096, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 754, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 406, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1637, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1749, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 835, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1715, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1804, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1681, \"height\": 1392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1776, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1778, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 549, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 814, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1402, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1708, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1250, \"height\": 1221, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1820, \"height\": 68, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1439, \"height\": 1075, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1796, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1776, \"height\": 1052, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1808, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 530, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-htp5yrxcs9/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1806, \"height\": 1181, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1522, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1254, \"height\": 707, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1399, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 498, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1649, \"height\": 1066, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-htp5yrxcs9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1005, \"height\": 403, \"label\": \"Table\"}]"
motivation: 现有环境要么缺乏3D能力，要么计算昂贵且不支持多智能体。
method: 设计并实现了Craftium平台，支持快速构建3D单/多智能体环境。
result: Craftium能够灵活高效地创建不同复杂度的3D环境。
conclusion: Craftium为多智能体强化学习提供了实用的环境平台。
---

## Abstract
Advances in large models, reinforcement learning, and open-endedness have accelerated progress toward autonomous agents that can learn and interact in the real world. To achieve this, flexible tools are needed to create rich, yet computationally efficient, environments. While scalable 2D environments fail to address key real-world challenges like 3D navigation and spatial reasoning, more complex 3D environments are computationally expensive and lack features like customizability and multi-agent support. This paper introduces Craftium, a highly customizable and easy-to-use platform for building rich 3D single- and multi-agent environments. We showcase environments of different complexity and nature: from single- and multi-agent tasks to vast worlds with many creatures and biomes, and customizable procedural task generators. Benchmarking shows that Craftium significantly reduces the computational cost of alternatives of similar richness, achieving +2K steps per second more than Minecraft-based frameworks.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：当前用于自主智能体研究的仿真环境存在两难困境：2D环境（如ALE、Griddly）计算高效但缺乏3D导航、空间推理等真实世界挑战；3D环境（如Minecraft平台）虽然更丰富，但计算开销大、灵活性差，且大多不支持多智能体场景。
- **背景**：强化学习、具身AI、开放性问题等领域的发展高度依赖环境。研究者常需在计算效率与环境丰富度之间权衡，尤其在持续学习、无监督环境设计、多智能体RL等对计算敏感的领域，往往只能使用简单的2D环境。
- **意义**：亟需一个既能提供丰富3D世界，又具备高效性、可定制性和多智能体支持的平台，以推动自主智能体研究的前沿发展。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于开源体素游戏引擎 **Luanti**（原名Minetest）构建Craftium平台，利用其强大的Lua Modding API和C++底层高效实现，提供可编程、可定制的3D环境创建工具。
- **关键技术细节**：
    - **架构**：Craftium包含两个主要组件：1）修改版Luanti引擎（负责世界逻辑、渲染）；2）Python环境接口（基于Gymnasium和PettingZoo标准）。两者通过专用通信通道交互。
    - **观察与动作**：观察为RGB图像（可自定义尺寸、帧堆叠、帧跳过）；默认动作空间包含21个键盘按钮和鼠标移动（连续值），可通过包装器（BinaryActionWrapper、DiscreteActionWrapper）简化。
    - **奖励与环境逻辑**：通过Lua脚本（mod）定义奖励函数、终止条件等。论文扩展了Luanti API，新增了`set_reward`、`set_termination`、`soft reset`等函数。
    - **世界生成**：支持预定义地图生成器、自定义脚本生成（如程序化随机迷宫），也可直接使用社区制作的游戏（如VoxeLibre）。
    - **多智能体支持**：通过修改引擎实现每个智能体独立客户端，同步更新，支持PettingZoo接口。

## 3. 实验设计：使用的数据集/场景、Benchmark、对比方法

- **场景（Illustrative Examples）**：
    - **单智能体RL**：5个任务——ChopTree（砍树）、SmallRoom/Room（寻宝）、Speleo（探索洞穴深度）、SpidersAttack（击杀蜘蛛，逐步增加数量）。观察64×64 RGB，离散动作空间。
    - **多智能体RL**：MACombat（一vs一战斗环境），自对弈训练。
    - **开放世界**：基于VoxeLibre，包含技能树（工具、狩猎、防御三支），测试PPO+LSTM与零样本LLaVa-Agent。
    - **程序化环境生成用于持续RL**：生成10个难度递增的迷宫地牢（随机房间、怪物、目标钻石），比较从头训练（FS）与L2正则化微调（FT-L2）。
- **Benchmark**：性能对比主要针对**MineDojo**（Minecraft框架）和**VizDoom**（2.5D框架）。测量步骤/秒（单环境、并行环境）、内存使用、不同分辨率/复杂度的性能。
- **对比方法**：PPO（单智能体任务）、自对弈PPO（多智能体任务）、FS vs FT-L2（持续RL）、PPO+LSTM vs LLaVa-Agent（开放世界任务）。未进行系统超参数调优。

## 4. 资源与算力

- 论文明确说明性能测试硬件：**单个NVIDIA A5000 GPU** + **Intel Xeon Silver 4309Y CPU**。
- 训练细节：PPO训练**1M步/任务**（单智能体任务），未进行大规模调优；LSTM+PPO同样1M步；LLaVa-Agent运行1小时（约7000次提示）。
- **未明确说明**：多组实验的总GPU小时数、并行环境数量（除性能分析外）等；论文强调未针对性能进行优化，仅作为示例。

## 5. 实验数量与充分性

- **实验数量**：
    - 性能对比：5次重复，3个环境/框架，共约15次运行（单环境）。并行环境测试24种不同环境数（2~30）。
    - 单智能体任务：每个任务5个随机种子，共5任务→25次PPO训练。
    - 多智能体：1个环境，5个随机种子。
    - 开放世界：PPO+LSTM和LLaVa-Agent各10次重复。
    - 持续RL：FS和FT-L2各5次重复（10个任务）。
- **充分性**：实验覆盖了多场景（单/多智能体、开放世界、程序化生成），性能对比具有统计意义（多次重复）。但作为“示例性”展示，并非完整benchmark，未进行大规模超参数搜索或与其他算法更全面的对比。缺乏消融实验（如动作空间简化效果、不同观察分辨率的影响等）。

## 6. 论文的主要结论与发现

- **效率**：Craftium单环境步骤/秒（≈2747）显著高于MineDojo（≈72），比VizDoom（≈2092）略高。并行时可达12K+步/秒。
- **灵活性**：通过Lua API可轻松创建复杂3D环境，代码量少（示例环境<160行）。支持多智能体、开放世界、程序化生成。
- **跨领域适用性**：展示了Craftium在单/多智能体RL、具身AI、持续RL等领域的应用，能兼容现有工具（Stable-Baselines3、CleanRL等）。
- **多智能体性能**：增加智能体数量对性能影响<4%，支持最多CPU核数数量的智能体。

## 7. 优点

- **高效性**：基于C++实现且开源可修改，比Minecraft框架快~38倍，同时保持相似丰富度。
- **高度可定制**：利用强大的Lua Modding API，无需DSL，支持实时修改环境行为。社区有大量现成资源（mod、游戏）。
- **接口标准化**：实现Gymnasium和PettingZoo，即开即用兼容主流RL库。
- **多智能体原生支持**：是首个同时提供丰富3D开放世界和多智能体能力的框架。
- **软重置机制**：避免繁琐的重启，提高训练效率。

## 8. 不足与局限

- **智能体数量限制**：最大智能体数受限于CPU核心数，不适用于大规模多智能体场景（如数百个智能体）。
- **实验覆盖有限**：作为平台介绍论文，未提供全面benchmark；PPO结果仅为示例，缺乏与最优超参数的比较。
- **可扩展性**：单环境性能受世界复杂度影响（复杂世界性能下降约30%），但论文认为这是可控的权衡。
- **多智能体同步问题**：虽然实现了同步更新，但论文未讨论网络延迟或分布式训练支持。
- **文档与维护**：依赖第三方社区项目（如VoxeLibre）可能带来版本兼容风险。
- **未讨论**：教学任务设计、与更复杂VLM/Robotics仿真器的比较等。

（完）
