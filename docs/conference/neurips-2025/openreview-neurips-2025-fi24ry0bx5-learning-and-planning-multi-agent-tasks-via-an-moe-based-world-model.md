---
title: Learning and Planning Multi-Agent Tasks via an MoE-based World Model
title_zh: 基于MoE世界模型的多智能体任务学习与规划
authors: "Zijie Zhao, Zhongyue Zhao, Kaixuan Xu, Yuqian Fu, Jiajun Chai, Yuanheng Zhu, Dongbin Zhao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fi24ry0BX5"
tags: ["query:marl"]
score: 7.0
evidence: 多任务多智能体强化学习与MoE世界模型
tldr: 针对多任务多智能体强化学习中单策略难以泛化的问题，提出基于混合专家模型的世界模型方法M3W。利用不同任务间动力学的有界相似性，将MoE应用于世界模型而非策略，实现跨任务规划。实验表明在多种多智能体任务中显著提升了泛化能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 722, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1088, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 550, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1412, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1409, \"height\": 1150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1362, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1368, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1360, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1368, \"height\": 583, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1205, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1264, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1376, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1462, \"height\": 1072, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1230, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 826, \"height\": 731, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 960, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1442, \"height\": 837, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1441, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1465, \"height\": 1013, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1311, \"height\": 131, \"label\": \"Table\"}]"
motivation: 多任务MARL中，不同任务最优策略差异大，单个策略模型难以有效泛化。
method: 将MoE应用于世界模型，利用任务间动力学相似性进行模块化建模。
result: 在多个MARL基准上，跨任务迁移效果优于现有方法。
conclusion: 世界模型模块化是处理多任务MARL的有效手段。
---

## Abstract
Multi-task multi-agent reinforcement learning (MT-MARL) aims to develop a single model capable of solving a diverse set of tasks. However, existing methods often fall short due to the substantial variation in optimal policies across tasks, making it challenging for a single policy model to generalize effectively. In contrast, we find that many tasks exhibit **bounded similarity** in their underlying dynamics—highly similar within certain groups (e.g., door-open/close) diverge significantly between unrelated tasks (e.g., door-open \& object-catch). To leverage this property, we reconsider the role of modularity in multi-task learning, and propose **M3W**, a novel approach that applies mixture-of-experts (MoE) to world model instead of policy, enabling both learning and planning. For learning, it uses a SoftMoE-based dynamics model alongside a SparseMoE-based predictor to facilitate knowledge reuse across similar tasks while avoiding gradient conflicts across dissimilar tasks. For planning, it evaluates and optimizes actions using the predicted rollouts from the world model, without relying directly on a explicit policy model, thereby overcoming the limitations of policy-centric methods. As the first MoE-based multi-task world model, M3W demonstrates superior performance, sample efficiency, and multi-task adaptability, as validated on Bi-DexHands with 14 tasks and MA-Mujoco with 24 tasks. The demos and anonymous code are available at \url{https://github.com/zhaozijie2022/m3w-marl}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：多任务多智能体强化学习（MT-MARL）旨在训练单一模型解决多种任务，核心挑战在于如何在相似任务间复用知识，同时在异质任务间避免梯度冲突。现有方法大多基于策略中心（policy-centric）的模块化设计（如子任务重组、技能发现、网络分解等），但这些方法未能充分利用任务间“有界相似性”（bounded similarity）的先验属性。

- **核心发现**：作者通过t-SNE可视化发现，不同任务的最优策略分布差异显著，但任务之间的**动力学（dynamics）**却呈现“有界相似性”——在同类任务组内（如开门/关门）高度相似，在不同组间（如开门与抓取）则差异很大。这一发现启发作者：将模块化应用于**世界模型（world model）而非策略网络**，可以更自然地利用动力学相似性进行知识复用，并通过混合专家模型（MoE）隔离不同任务的异质动力学。

- **整体含义**：本文提出首个基于MoE的多任务世界模型M3W（MoE-based World Model for Multi-agent Multi-task），通过将MoE应用于世界模型中的动力学建模和奖励预测，实现更高效的学习和规划，从而克服策略中心方法的泛化局限。

## 2. 方法论

### 核心思想
- 将多智能体动力学建模为序列预测问题（观察-动作对序列 → 下一时刻观察序列），在共享潜空间中进行学习和规划。
- 采用MoE结构：动力学模型基于**SoftMoE**（软路由+多个MLP专家），奖励预测器基于**SparseMoE**（稀疏路由+自注意力专家），路由器根据任务标号（task embedding）动态激活合适的专家。
- 规划阶段：不依赖显式策略网络，而是利用世界模型生成的预测轨迹，通过多智能体MPPI（模型预测路径积分）算法直接评估和优化动作序列。

### 关键技术细节
1. **世界模型结构**（公式1）：
   - 编码器（Encoder）：`z_i^t = p_E(o_i^t, e)`，将观测编码为潜状态。
   - 动力学模型（Dynamics）：`\hat{z}^{t+1} = q_D(z^t, a^t, e)`，基于SoftMoE实现序列到序列预测。
   - 奖励预测器（Reward Predictor）：`\hat{r}^t = q_R(z^t, a^t, e)`，基于SparseMoE实现序列到标量回归。
   - 评论家（Critic）：`\hat{q}^t = Q(z^t, a^t, e)`，用于评估长期回报。
   - 演员（Actor）：仅用于为规划器生成候选动作，不作为显式决策策略。

2. **SoftMoE动力学模型**（图3左）：
   - 路由器生成权重矩阵`W∈R^{n×N}`（n为智能体数，N为专家数）。
   - 输入阶段：对W行softmax，将n个token加权组合为N个专家输入token。
   - 输出阶段：对W列softmax，将N个专家输出token聚合回n个预测潜状态。
   - 专家为独立MLP，避免梯度干扰。

3. **SparseMoE奖励预测器**（图3右）：
   - 路由器生成长度N的得分向量，通过Top-K采样（训练时用轮盘赌，执行时用最高分）激活K个自注意力专家。
   - 专家含多头注意力层和平均池化层，输出统一奖励预测。
   - 加入负载均衡损失（公式6）防止专家过载。

4. **训练目标**（公式2）：
   - 包含潜空间动力学损失、奖励预测损失（soft交叉熵）、Q值损失，以及负载均衡损失。
   - 使用多步TD目标、symlog变换、SimNorm归一化、分类回归等技巧增强稳定性。

5. **规划算法**（MPPI，附录A）：
   - 从高斯分布采样Np条动作序列，加入Nπ条由演员生成的先验序列。
   - 利用世界模型在潜空间进行H步展开，用公式7评估每条轨迹的H步回报。
   - 选择M条精英轨迹，更新动作分布（公式9），迭代Kp次得到最终动作。

## 3. 实验设计

### 使用的数据集/场景
- **Bi-DexHands**：14个双手灵巧操作任务（如开瓶盖、抓取、开门、叠积木等），异构智能体，高维观察（最大229维）和动作空间（最大26维）。
- **MA-Mujoco**：24个多智能体MuJoCo任务，覆盖Cheetah、Humanoid、Walker2D、Swimmer、Hopper、Reacher等机器人套件，每个套件包含多个子任务（如跑、跳、走、反向等）。

### Benchmark与对比方法
- **MACD**：基于Transformer的世界模型（模型基MARL基线）。
- **HMASD**：层次化多智能体技能发现（多任务方法）。
- **MAT、MAPPO、HATRPO**：通用多智能体强化学习算法。
- **Single-MAPPO**：每个任务单独训练的MAPPO（强基线）。
- **其他结构对比**：MLP、Transformer、Switch-Transformer用于消融实验。

### 评估指标
- 在Bi-DexHands上归一化回报（0-100），在MA-Mujoco上使用原始回报。
- 报告均值 ± 95%置信区间，基于5个随机种子（推测，原文未明确说明种子数，但图4/5曲线显示多次运行）。

## 4. 资源与算力
- **原文未明确说明**：未提及使用的GPU型号、数量、训练时长等具体算力信息。
- 仅附录E.6提到在单张RTX A6000 GPU上测试推理时间，训练环境未说明。
- 实验总步数：Bi-DexHands训练50M步，MA-Mujoco训练步数未明确（推测类似时长）。

## 5. 实验数量与充分性

### 实验数量
- **主性能对比**：2个基准（Bi-DexHands 14任务 + MA-Mujoco 24任务），共38个任务，与5种基线对比（Single-MAPPO、MACD、HMASD、MAT、MAPPO、HATRPO），图4/5展示部分任务曲线，表1/10给出全部任务结果。
- **消融实验**：
  - 世界模型预测精度（图6）：在6个MA-Mujoco任务上，对比MLP、Transformer、Switch-Transformer。
  - 规划器贡献（图7）：将规划器加入MACD对比。
  - 演员先验消融（表13）：在全部任务上对比有无演员先验。
  - 奖励尺度鲁棒性（图14）：在Hopper任务上放大stand奖励。
  - 时间开销分析（图15）：不同H和Kp设置，以及早停策略。
  - 可扩展性（图16）：10-agent Swimmer和56-agent MAgent。
- **可视化实验**：专家注意力（图8）、路由权重余弦相似度（图9左）、潜状态t-SNE轨迹（图9右）。

### 实验充分性与公平性
- **充分性**：覆盖多任务学习核心评估维度（性能、样本效率、泛化、鲁棒性、可解释性、计算开销）。在两大异构基准上验证，任务多样性高。
- **公平性**：未报告每种基线的超参数调优过程，但模型基/多任务基线均使用公开实现；所有方法共享相同任务标签嵌入、观测填充等设置；消融实验控制变量。
- **潜在偏差**：未与最新的多任务世界模型方法（如MAZero、MA-TDMPC）直接对比，仅与MACD对比；在SMAC、MPE等环境的泛化性未验证（但在附录D.5用MMD验证了这些环境也存在有界相似性）。

## 6. 主要结论与发现

1. **性能优势**：M3W在Bi-DexHands平均归一化回报84.1（第二名MACD 72.0），在MA-Mujoco平均40.2（第二名HMASD 33.1）。在38个任务中，71%的任务取得最佳性能，统计显著性p<0.05的任务占71%。

2. **样本效率**：在相似任务组（如catch-abreast/catch-underarm）上收敛速度显著快于所有基线，甚至超过单任务强基线。

3. **多任务适应性**：在处理语义相反的任务（如开门/关门）时，M3W能同时学好两种任务，而其他基线会受冲突干扰。

4. **MoE世界模型有效性**：MoE架构在动力学预测误差上比Transformer降低约65%，比MLP降低90%；在奖励预测误差上比Transformer降低约76%。

5. **可解释性**：可视化显示专家已形成功能特化（最高分专家关注运动关键关节）；软路由的余弦相似度矩阵呈现清晰块状结构，表明MoE成功捕捉到有界相似性；潜状态t-SNE显示不同任务聚类分离，相似任务聚集。

## 7. 优点

- **创新性**：首次将MoE应用于多任务世界模型（而非策略），利用动力学有界相似性，思路新颖。
- **方法完备性**：完整覆盖学习（训练）和规划（在线执行），规划器不依赖显式策略，避免策略中心方法的局限。
- **技术设计合理**：SoftMoE适合序列到序列的动力学预测，SparseMoE适合序列到标量的奖励回归；负载均衡损失、symlog等技巧增强稳定性。
- **实验扎实**：在两大挑战基准（38个任务）上全面验证，多个消融实验覆盖预测精度、规划贡献、鲁棒性、计算开销、可扩展性。
- **可解释性贡献**：通过多种可视化揭示了MoE的工作机制（专家特化、有界相似性利用），有助于理解模型行为。
- **代码开源**：提供匿名代码链接，可复现。

## 8. 不足与局限

- **动作空间限制**：当前MPPI规划器仅适用于连续动作空间，无法处理离散动作任务（如SMAC），作者在结论中承认此局限并计划引入MCTS或CEM。
- **未与最新模型基MARL方法对比**：未直接对比MAZero、MA-TDMPC等近期工作，仅与MACD（2024）对比，虽然MACD是目前较新的模型基MARL方法，但可能存在遗漏。
- **计算成本较高**：规划器每步需迭代Kp次（默认6），每次需要大量采样（512+24条轨迹）和世界模型展开，时间开销约25.8ms/步（Bi-DexHands），虽满足实时（<50ms），但比策略方法高一个数量级。附录早停策略可降到9.8ms，但仍有开销。
- **未报告训练总步数和GPU小时数**：缺乏对训练资源消耗的透明报告。
- **泛化性验证有限**：仅在连续控制环境验证，未在SMAC、MPE等经典MARL环境测试。附录D.5虽证明这些环境也存在有界相似性，但未给出在非连续动作空间的实验结果。
- **实验细节不够透明**：未明确随机种子数、基线超参数是否经过调优（可能默认参数），可能影响公平性评估。

（完）
