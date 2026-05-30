---
title: Bi-Level Knowledge Transfer for Multi-Task Multi-Agent Reinforcement Learning
title_zh: 面向多任务多智能体强化学习的双层知识迁移
authors: "Junkai Zhang, Jinmin He, Yifan Zhang, Yifan Zang, Ning Xu, Jian Cheng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6jKed3sx4f"
tags: ["query:marl"]
score: 8.0
evidence: 多任务多智能体强化学习中的双层知识迁移
tldr: 针对多任务多智能体强化学习在线训练成本高的问题，提出双层知识迁移方法BiKT。在个体层提取可迁移技能嵌入，在团队层捕捉协调知识。通过离线数据实现零样本泛化，实验证明显著提升跨任务迁移效果。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 858, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 846, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1443, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6jked3sx4f/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 482, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 1294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1423, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1384, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1235, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1231, \"height\": 1072, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1348, \"height\": 1493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1154, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 674, \"height\": 773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 1046, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1455, \"height\": 891, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6jked3sx4f/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 794, \"label\": \"Table\"}]"
motivation: 多任务MARL中从头学习每个任务代价高，需要有效的策略复用。
method: 提出双层迁移框架，分别提取个体技能嵌入和团队协调知识进行迁移。
result: 在多个MARL任务上，零样本泛化性能显著优于单层迁移方法。
conclusion: 团队协调知识的迁移对于多任务泛化至关重要。
---

## Abstract
Multi-Agent Reinforcement Learning (MARL) has achieved remarkable success in various real-world scenarios, but its high cost of online training makes it impractical to learn each task from scratch. 
To enable effective policy reuse, we consider the problem of zero-shot generalization from offline data across multiple tasks. 
While prior work focuses on transferring individual skills of agents, we argue that the effective policy transfer across tasks should also capture the team-level coordination knowledge.
In this paper, we propose Bi-Level Knowledge Transfer (BiKT) for Multi-Task MARL, which performs knowledge transfer at both the individual and team levels. 
At the individual level, we extract transferable individual skill embeddings from offline MARL trajectories.
At the team level, we define tactics as coordinated patterns of skill combinations and capture them by leveraging the learned skill embeddings. 
We map skill combinations into compact tactic embeddings and then construct a tactic codebook.
To incorporate both skills and tactics into decision-making, we design a bi-level decision transformer that infers them in sequence.
Our BiKT leverages both the generalizability of individual skills and the diversity of tactics, enabling the learned policy to perform effectively across multiple tasks.
Extensive experiments on SMAC and MPE benchmarks demonstrate that BiKT achieves strong generalization to previously unseen tasks.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义
- **研究动机**：多智能体强化学习（MARL）在现实场景中取得显著成功，但针对每个新任务从头进行在线训练成本极高，难以实际应用。因此，研究者希望从已知任务的离线数据中提炼策略，并将其迁移到未见但相关的任务上，实现零样本泛化。
- **问题界定**：现有的知识迁移方法主要关注个体智能体的技能（skill）迁移，而忽略了团队层面的协调知识（tactic）。作者认为，有效的策略迁移需要同时捕获个体行为模式和团队协作模式，且不同任务可能共享相同的团队战术，但需要根据任务特性自适应选择。
- **整体含义**：论文提出双层知识迁移（BiKT）框架，从离线多任务数据中提取个体技能和团队战术，并设计策略模型利用这两层知识进行决策，从而提升多任务MARL的零样本泛化性能。

## 2. 方法论
- **核心思想**：将知识迁移分解为个体层（技能）和团队层（战术）。个体技能捕获单智能体的动作模式，团队战术则定义为技能组合的协调模式。通过VQ-VAE构建离散的战术码本，使得同一战术可在不同任务中复用（应对智能体数量变化）。最终使用双层的决策变压器（BDT）先推断战术索引，再基于战术推断个体技能，再解码为动作。
- **关键技术细节**：
  - **个体技能学习**：采用VAE框架，个体技能编码器 \(p_{\text{skill}}(z|s,a,i)\) 从全局状态、联合动作和智能体索引中提取技能嵌入 \(z_i\)；动作解码器 \(q_{\text{act}}(a|\tau_i,z_i)\) 基于局部历史重建动作。损失函数为技能重构损失和KL散度正则项。
  - **团队战术学习**：采用VQ-VAE框架。战术编码器 \(p_{\text{tac}}(\hat{c}|s,\{z_i\})\) 将全局状态和所有个体技能嵌入映射为连续表示 \(\hat{c}\)；通过最近邻搜索将其离散化为码本 \(C=\{c_k\}_{k=1}^K\) 中的某个战术 \(c_k\)；技能解码器 \(q_{\text{skill}}(\hat{z}|\tau_i,c_k)\) 基于局部历史和战术重建个体技能。损失函数包括技能重建损失、码本承诺损失和码本间距正则项（促进多样性）。
  - **双层决策变压器（BDT）**：策略模型 \(\pi_i^\theta\) 以历史序列（包括预测回报、解耦的观测、先前战术索引和先前技能）为输入，先预测当前战术索引 \(I_c^t\)（分类），再基于战术 \(c_{I_c^t}\) 和上下文预测当前技能 \(z_i^t\)。训练时使用预训练的个体技能编码器和战术编码器生成监督信号（\(z_i\) 和 \(I_c^t\)）。损失函数为战术预测的交叉熵和技能预测的均方误差的加权和。
- **算法流程**（文字说明）：
  1. 从离线数据集采样，用VAE训练个体技能编码器和动作解码器（最小化 \(L_{\text{skill}}\)）。
  2. 固定技能编码器，用VQ-VAE训练战术编码器、技能解码器和战术码本（最小化 \(L_{\text{tactic}}\)）。
  3. 固定技能编码器和码本，监督训练BDT（最小化 \(L_{\text{policy}}\)），以预生成的任务标签和技能标签为监督。
  4. 执行时：BDT接收历史，预测战术索引，从码本检索战术，再生成个体技能，最终由动作解码器输出动作。

## 3. 实验设计
- **数据集/场景**：
  - **SMAC**：三个任务集：
    - Marine-Hard：源任务包括3m, 5m_vs_6m, 9m_vs_10m；未见任务包括4m, 5m, 10m, 12m, 7m_vs_8m等（共11个任务）。
    - Marine-Easy：源任务3m, 5m, 10m；未见任务4m, 6m, 7m等（共11个任务）。
    - Stalker-Zealot：源任务2s3z, 2s4z, 3s5z；未见任务1s3z, 1s4z, 4s3z等（共12个任务）。
  - **MPE中的Cooperative Navigation（CN）**：CN-2和CN-4为源任务，CN-3和CN-5为未见任务。
  - 每个任务均有不同质量的离线数据集：Expert, Medium, Medium-Expert, Medium-Replay（共4种）。
- **对比方法**：
  - **UPDeT**：基于Transformer的通用多任务策略。
  - **ODIS**：基于协调技能的迁移方法。
  - **HiSSD**：层次化技能学习框架。
  - 此外，论文还进行了消融实验，对比了多个变体：MADT_w_OD（去除技能和战术的直接DT）、L=5（缩短上下文长度）、CK=32（扩大码本）、w/o C（无战术）、Con-Tac（连续战术嵌入）。
- **评估指标**：各任务上的胜率（win rate），取5次随机种子的均值与标准差。

## 4. 资源与算力
- **文中说明**：论文附录C.3指出，实验使用Intel(R) Xeon(R) Gold 5220 CPU和NVIDIA TITAN RTX GPU，每个任务集的训练平均耗时约8小时。未明确说明GPU数量、总卡时或集群规模。
- **补充说明**：由于未提供详细资源消耗数据，无法精确评估计算开销。

## 5. 实验数量与充分性
- **实验数量**：
  - 主实验：3个SMAC任务集（每个含4种数据质量） + 1个MPE任务集（含2种数据质量） = 共14组实验（实际表格中呈现了Expert/Medium/Medium-Expert/Medium-Replay下的性能）。
  - 消融实验：在Marine-Hard Expert数据集上测试了5个变体（MADT_w_OD, L=5, CK=32, w/o C, Con-Tac），报告了所有原子任务结果。
  - 可视化分析：t-SNE展示技能嵌入聚类、战术使用频率分布、具体技能与战术语义举例。
- **充分性与公平性**：
  - 实验覆盖了同质/异质、对称/非对称、不同智能体数量的多种任务，来源与未见任务区分明确。
  - 对比了多个同期前沿方法，且复用了ODIS提供的离线数据集（确保数据一致）。
  - 所有结果均报告5次随机种子均值和标准差，统计严谨。
  - 消融实验系统分析了各组件贡献，有效支持了核心论点。
  - 未发现实验设计有显著偏差或不公平之处。

## 6. 主要结论与发现
- **性能优越**：BiKT在绝大多数任务上（尤其是Expert和Medium-Expert数据）显著优于UPDeT、ODIS和HiSSD，特别是在复杂不对称任务（如5m_vs_6m, 7m_vs_8m）上提升明显。
- **双层迁移的必要性**：消融实验表明，仅迁移个体技能（w/o C）或使用连续战术（Con-Tac）均导致性能下降，证明离散战术码本和团队层迁移是关键。
- **战术码本的有效性**：可视化显示，不同任务中部分战术被一致使用（如集中火力），而部分战术频率因任务而异，表明模型能自适应选择合适战术。
- **技能的可迁移性**：技能嵌入在源任务上呈现清晰聚类，且同一技能在不同任务中具有相似语义（如“冲锋”“逃逸”），说明技能具备跨任务泛化能力。
- **对低质量数据的鲁棒性**：在Medium-Replay等低质量数据上，BiKT仍能保持优于基线的性能，但部分困难任务（如13m_vs_15m）仍难以突破。

## 7. 优点
- **方法创新**：首次在MARL中同时考虑个体技能和团队战术的双层知识迁移，并引入离散码本实现可复用的协调模式。
- **架构设计**：BDT将战术索引预测与技能生成解耦，使策略能根据任务动态选择团队行为，避免固定技能组合。
- **理论支撑**：损失函数设计合理（VAE + VQ-VAE + 分类/回归多任务学习），并包含停梯度操作、码本多样性正则等技巧。
- **实验充分**：覆盖多种场景（同质/异质、对称/不对称）和多样数据质量，消融实验系统完备，可视化结果直观支撑结论。
- **可解释性**：通过t-SNE和战术使用频率分析，展示了所学知识和决策模式的可解释性。

## 8. 不足与局限
- **大规模任务泛化**：论文在附录F中坦诚，当任务分布高度多样和大规模时，当前方法是否能保持性能仍是开放问题，需要更鲁棒的嵌入机制。
- **计算资源依赖**：BDT基于Transformer，随着智能体数量增加，其输入序列长度和注意力计算复杂度可能上升，实验中最多的智能体约15个，更大规模场景未验证。
- **离线数据质量敏感**：在低质量数据（如Medium-Replay）上，BiKT在部分困难任务（如10m_vs_12m, 13m_vs_15m）上的性能依然很低，说明数据质量仍是瓶颈。
- **假设限制**：论文假设源任务和目标任务共享相似的单元类型和任务结构（如Marine系列、Stalker-Zealot系列），对于完全异构或动态变化的任务泛化能力未知。
- **未探索在线微调**：论文专注于零样本泛化，未讨论结合少量在线交互进行微调是否能进一步提升性能。

（完）
