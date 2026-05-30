---
title: Evolutionary Distributed Training
title_zh: 进化分布式训练
authors: Yushu Jiang
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=tESKKiKhVp"
tags: ["query:marl"]
score: 5.0
evidence: 针对多智能体环境的进化式分布式训练
tldr: 该工作提出进化分布式训练（EDT），用评估、交叉和变异替代集中式梯度同步，实现松散连接设备上的高效训练。在多智能体环境中，EDT通过同时进化策略和奖励函数促进了多样化奖励探索和涌现策略，在适应性和策略多样性上优于传统方法。尽管在语言模型预训练上效果有限，但EDT为分布式多智能体训练提供了新思路。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-teskkikhvp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1074, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-teskkikhvp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1080, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-teskkikhvp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 935, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-teskkikhvp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1307, \"height\": 740, \"label\": \"Figure\"}]"
motivation: 分布式训练中梯度同步通信开销大，需要更灵活的协作方式。
method: 用评估、交叉和变异取代集中梯度同步，进化策略和奖励函数。
result: 在多智能体环境中，EDT提升了策略多样性和适应性。
conclusion: EDT是分布式多智能体训练的有前景框架。
---

## Abstract
We introduce Evolutionary Distributed Training (EDT), a nature-inspired approach to distributed model training. EDT replaces centralized gradient synchronization with evaluation, pairwise model crossover, and mutation, enabling communication-efficient training across loosely connected devices. While early investigations show limited effectiveness in language model pretraining, EDT demonstrates strong potential in reinforcement learning (RL). In complex multi-agent environments, EDT facilitates diverse reward exploration and emergent strategies by evolving both policy and reward functions, outperforming traditional training in adaptability and strategic diversity. We also hypothesize EDT as a promising framework for post-training and alignment, offering optimization towards multi-objective, non-differentiable goals. This work positions EDT as a scalable, evolutionary recipe for distributed learning, offering early insights into where it may best fit within the deep learning landscape.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **动机**：传统分布式训练依赖集中式梯度同步，通信开销大，且难以适应松散连接设备。受自然界进化（高并行、去中心化、两两繁殖）启发，作者提出用进化算法替代梯度同步，探索在深度学习不同阶段（预训练、强化学习、后训练）的应用潜力。
- **背景**：现有工作如 DiLoCo 实现了低通信分布式训练，但仍需中心聚合。EDT 旨在提供一种完全去中心化、通信开销 O(1) 的替代方案，尤其适用于多智能体环境中稀疏奖励和探索困难的问题。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将分布式训练视为一个进化过程——每个 worker 独立训练局部模型，然后通过评估（fitness）、选择（selection）、两两交叉（crossover）和变异（mutation）产生后代，无需梯度同步。
- **关键技术细节**：
  - **语言模型预训练**：基于 DiLoCo 框架，用**两两模型平均**替代全局平均。流程：① 每个 worker 在固定验证集上评估 fitness；② 基于排名选择父母；③ 对父母对的权重进行线性插值得到基础模型，平均训练 delta 作为梯度，平均 velocity buffer，用 SGD + Nesterov 更新；④ 后代继续本地训练。
  - **强化学习**：将奖励函数编码为“DNA 序列”（6 个奖励项），每个 worker 使用自己独特的奖励 DNA 训练策略（64k 参数 Transformer）。流程：① 本地 PPO 训练一代；② 通过双败淘汰赛计算 Elo 评分作为 fitness；③ 选择父母，策略权重用球形线性插值交叉，DNA 均匀混合；④ 部分后代随机变异奖励项。
- **算法流程**（文字说明）：初始化种群 → 每个 worker 本地训练 → 评估 fitness → 选择父母 → 交叉产生后代（策略+DNA）→ 变异 → 重复。

### 3. 实验设计：数据集/场景、基准、对比方法

- **语言模型预训练**：
  - 数据集：TinyStories（子集）。
  - 模型：6M 参数 LLaMA 架构，GPT-2 tokenizer。
  - 对比方法：DiLoCo 基线（8 worker）、EDT rank-based 选择、EDT random 选择、EDT 4x 更频繁更新。
- **强化学习**：
  - 环境：Smash Bros 风格平台格斗游戏（自建 gym 环境）。
  - 模型：64k 参数 Transformer 策略，PPO 优化。
  - 对比方法：标准 Population-Based Training（PBT，固定手动奖励函数）。
  - 设置：8 worker 和 32 worker 两种规模，40 个 generation。
- **语言模型后训练**：仅提出概念框架，未进行实验。

### 4. 资源与算力

- **初始实验**：单台笔记本电脑 RTX 4070，模拟多 worker 循环。
- **主要 RL 实验**：32 张 RTX 4080 完成（用于 32 worker 场景）。
- **后训练实验**：因作者被大学告知不允许在校园基础设施上做个人研究，未进行。
- **未明确**：具体训练时长、每代耗时等细节未提供。

### 5. 实验数量与充分性

- **实验组数**：预训练对比 4 种配置，RL 对比 2 种（EDT vs PBT）并做了 8 worker 和 32 worker 两种规模，共约 6 组主要实验。
- **充分性**：作者承认计算受限，**未重复多次实验**，因此缺少误差棒和统计显著性分析。预训练结果仅用一次运行，RL 结果也未报告方差。实验设计相对清晰，但复现性和严谨性不足。公平性方面，对比了标准基线，但未在更大规模或更多随机种子下验证。

### 6. 论文的主要结论与发现

- **预训练**：EDT 性能显著差于 DiLoCo，困惑度下降缓慢并趋于停滞；rank-based 与 random 选择效果几乎相同；增加更新频率仅短暂加速，最终困惑度相近。结论：EDT 不适合 LLM 预训练。
- **强化学习**：EDT 在 8 worker 下与 PBT 竞争力相当；在 32 worker 下 40 代后涌现出新颖策略（如“地面砸击”），通过奖励变异（如“地板是岩浆”惩罚）引导探索，最终产生强大战术。结论：EDT-RL 在多智能体环境中能有效促进探索与策略多样性，优于传统方法。
- **后训练**：理论上适合多目标、非可微优化，但未实验验证。

### 7. 优点：方法或实验设计上的亮点

- **通信高效**：EDT 仅需在交叉时交换模型，通信开销 O(1)，适合松散连接设备。
- **天然促进探索**：通过奖励函数变异和策略交叉，自动探索行为多样性，无需人工设计复杂奖励。
- **涌现能力**：32 worker 实验中，EDT 使代理发现“地面砸击”等非预设策略，展示了进化算法的创造性。
- **框架灵活性**：可扩展至后训练等非可微目标优化场景，具有通用性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖不足**：仅在小模型（6M/64k 参数）和单一环境（格斗游戏）上验证，大规模 LLM 预训练或更复杂 RL 任务未测试。
- **缺乏统计可靠性**：未重复多次实验，结果可能受随机性影响，无法排除偶然性。
- **可复现问题**：代码未公开（计划未来发布），且训练细节（如超参数、数据拆分）描述不够详尽。
- **后训练仅概念**：无实证支持，削弱了论文声称的潜力。
- **计算资源限制**：作者因外部原因无法完成更多实验，导致整体实验规模较小。
- **性能局限**：在 LLM 预训练上明显不如标准方法，表明方法适用范围有限，可能过度依赖任务特性。

（完）
