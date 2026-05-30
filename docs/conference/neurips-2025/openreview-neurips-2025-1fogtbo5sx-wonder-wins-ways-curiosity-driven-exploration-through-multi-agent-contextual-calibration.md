---
title: "Wonder Wins Ways: Curiosity-Driven Exploration through Multi-Agent Contextual Calibration"
title_zh: 奇妙致胜之路：通过多智能体上下文校准的好奇心驱动探索
authors: "Yiyuan Pan, Zhe Liu, Hesheng Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1fOGTbO5Sx"
tags: ["query:marl"]
score: 9.0
evidence: 去中心化多智能体强化学习，好奇心驱动探索
tldr: 在去中心化无通信的多智能体强化学习中，现有好奇心机制易混淆随机性和新颖性。本文受儿童观察他人行为启发，提出多智能体上下文校准的好奇心驱动探索方法，利用同伴行为新颖性来校准自身探索。实验表明该方法在稀疏奖励任务中显著优于基线，实现了高效的去中心化探索。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1377, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1410, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1409, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1011, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1fogtbo5sx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1402, \"height\": 436, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 699, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 545, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 621, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1fogtbo5sx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 935, \"label\": \"Table\"}]"
motivation: 现有好奇心机制在去中心化MARL中难以区分环境随机性和有意义的新颖性。
method: 提出多智能体上下文校准方法，利用同伴行为新颖性来调整探索信号。
result: 在稀疏奖励环境下，该方法大幅提升了探索效率和最终性能。
conclusion: 智能体间上下文校准为去中心化MARL探索提供了有效新范式。
---

## Abstract
Autonomous exploration in complex multi-agent reinforcement learning (MARL) with sparse rewards critically depends on providing agents with effective intrinsic motivation. While artificial curiosity offers a powerful self-supervised signal, it often confuses environmental stochasticity with meaningful novelty. Moreover, existing curiosity mechanisms exhibit a uniform novelty bias, treating all unexpected observations equally. However, peer behavior novelty, which encode latent task dynamics, are often overlooked, resulting in suboptimal exploration in decentralized, communication-free MARL settings. To this end, inspired by how human children adaptively calibrate their own exploratory behaviors via observing peers, we propose a novel approach to enhance multi-agent exploration. We introduce CERMIC, a principled framework that empowers agents to robustly filter noisy surprise signals and guide exploration by dynamically calibrating their intrinsic curiosity with inferred multi-agent context. Additionally, CERMIC generates theoretically-grounded intrinsic rewards, encouraging agents to explore state transitions with high information gain. We evaluate CERMIC on benchmark suites including VMAS, Meltingpot, and SMACv2. Empirical results demonstrate that exploration with CERMIC significantly outperforms SoTA algorithms in sparse-reward environments.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：在去中心化、无通信的多智能体强化学习（MARL）中，稀疏奖励环境下的自主探索极具挑战性。人工好奇心（artificial curiosity）作为一种自监督信号可以驱动探索，但现有方法存在两大缺陷：
  - **“Noisy-TV”问题**：容易将环境随机性（如不可学习噪声）误判为有意义的新颖性，从而被无效信号误导。
  - **均匀新颖性偏差**：对所有意外观察一视同仁，忽视了同伴行为中蕴含的任务动态信息，导致在部分可观测、无通信场景下探索效率低下。
- **核心动机**：受人类儿童通过观察同伴来自适应校准自身探索行为的认知发展机制启发，希望让智能体在部分可观测、无通信条件下，能够利用推理出的同伴意图来校准自身的好奇心，从而过滤噪声、聚焦于有语义意义的新颖性。
- **整体含义**：提出了一种社交上下文校准的好奇心驱动探索框架，为去中心化MARL提供了一种鲁棒、可控的探索信号，显著提升了稀疏奖励环境下的学习效率和最终性能。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：基于信息瓶颈（Information Bottleneck, IB）原理，学习一个多智能体上下文感知的探索性表征，使得探索信号聚焦于语义新颖性，同时过滤随机噪声。关键创新在于利用动态图神经网络建模其他智能体的意图，并以此校准原始好奇心信号。
- **关键技术细节**：
  - **表示学习**：当前状态-动作对通过编码器得到隐变量 $x_t \sim g_\phi(s_t, a_t)$（高斯分布）。训练目标为最大化 $I(X_t; S_{t+1})$（保持对新颖状态的预测信息）的同时最小化 $I(X_t; [S_t, A_t])$（压缩当前上下文）。
  - **多智能体上下文校准**：
    - 构建动态图 $G_n$，节点为各智能体的预测状态表示，边为相对空间关系。通过图神经网络（GNN）提取上下文特征 $f_{\text{on}}$。
    - 采用分布鲁棒机会约束（distributionally robust chance constraint）将 $f_{\text{on}}$ 整合到压缩损失中，形成上界损失 $L_{\text{exploit}}^{\text{UB}}$ 和下界损失 $L_{\text{exploit}}^{\text{LB}}$，确保校准的鲁棒性。
    - 任务自适应校准因子 $\gamma = I([r_{t-1}, f_{\text{on}}^{t-1}]; f_{\text{on}}^t)$ 通过InfoNCE损失近似，用于动态调整上下文特征的置信度，适应不同学习阶段和任务类型。
  - **内在奖励生成**：基于贝叶斯惊奇（Bayesian Surprise）设计内在奖励 $r_t^i = \sqrt{D_{\text{KL}}(p(\Theta|(s_t,a_t,s_{t+1})\cup D_m) \| p(\Theta|D_m))}$，鼓励探索对模型更新信息量大的转移。通过数据预处理不等式推导出可计算的下界，并在线性MDP下证明其与LSVI-UCB探索奖励的关系。
  - **总损失函数**：$L_{\mathcal{C}} = L_{\text{exploit}}^{\text{UB}} + L_{\text{exploit}}^{\text{LB}} - \alpha L_{\text{explore}}$，其中 $L_{\text{explore}}$ 为最大化预测似然。
- **算法流程**（Algorithm 1）：
  1. 初始化CERMIC模块和Actor-Critic网络。
  2. 每个episode，各智能体基于策略采样动作，收集经验 $(s_t, a_t, s_{t+1})$。
  3. 根据式(12)计算内在奖励 $r_t^i$，与外在奖励求和得到总奖励 $r_t = r_t^i + r_t^e$。
  4. 用收集的on-policy经验更新Actor-Critic网络和CERMIC模块。

## 3. 实验设计

- **数据集/场景**：三个主流MARL基准套件：
  - **VMAS**（9个任务，如Disperse、Navigation、Sampling、Passage、Transport、Balance、GiveWay、WheelGathering、Flocking，均改造为稀疏奖励版本）。
  - **MeltingPot**（4个任务：StagHuntRepeated、Cleanup、ChickenGameRepeated、PrisonersDilemmaRepeated）。
  - **SMACv2**（2个任务：Protoss5v5、Zerg5v5，同样改为稀疏奖励）。
- **评估指标**：VMAS用平均episode奖励；MeltingPot用平均episode回报；SMACv2用平均测试胜率。
- **对比方法**：分为三类：
  - **标准MARL基线**：MAPPO、QMIX、MAPPO-ϵGreedy。
  - **当前SOTA方法**：VMAS上的CPM，SMACv2上的QMIX-SPECTRA。
  - **其他好奇心驱动方法**：MAPPO-DB、MACE、QPLEX-ICES。
  - **集成CERMIC的变体**：QMIX-CERMIC、MAPPO-CERMIC。

## 4. 资源与算力

论文在附录H中说明：训练和评估在**NVIDIA Quadro RTX 8000 GPU**上完成，训练最大帧数为3,000,000帧，其他超参数（如学习率1e-4、批次大小等）有详细记录。但未明确报告GPU数量、训练总时长等具体算力开销。总体而言，计算资源描述较为简略，属于中等规模的实验配置。

## 5. 实验数量与充分性

- **实验数量**：共覆盖16个任务（9+4+2），每个算法至少运行多个随机种子，报告中包含均值与标准差（部分表注显示误差条）。
- **对比充分性**：基础对比包含12种算法（含变体），消融实验涵盖损失模块、覆盖率α、记忆类型（GRU vs Graph），还做了奖励密度泛化实验（密集→稀疏迁移）和噪声鲁棒性实验。
- **结论**：实验设计较为全面，覆盖多个领域和任务类型，消融和泛化分析合理，体现了方法在不同场景下的有效性。但部分结果仅报告单次或少量种子（文中未详细说明种子数量），可能存在一定方差风险。

## 6. 主要结论与发现

- CERMIC在16个任务中的12个上取得了新的SOTA性能，尤其在稀疏奖励、强交互的MeltingPot任务上提升最显著。
- 与MAPPO-DB对比显示，CERMIC通过上下文校准避免了因忽视同伴行为导致的探索退化，尤其在智能体数量增加时，MAPPO-DB的每智能体贡献下降，而CERMIC保持稳定。
- 定性可视化表明：CERMIC驱动的智能体更频繁地接近同伴以获取信息（而非简单模仿），且内在奖励在关键交互时刻（如首次遇到其他智能体）达到峰值，并随时间衰减。
- 泛化实验证明：从密集奖励环境训练后迁移到稀疏奖励环境时，CERMIC能显著缓解性能下降，表明其不依赖密集反馈即可学到任务理解能力。

## 7. 优点

- **方法创新性强**：将社会学习（观察同伴）融入好奇心驱动探索，提出多智能体上下文校准的鲁棒机制，理论结合实践（信息瓶颈、分布鲁棒优化、InfoNCE等）。
- **模块化设计**：CERMIC作为轻量级即插即用模块，可方便地集成到多种MARL算法（MAPPO、QMIX）中。
- **理论支撑充分**：给出了内在奖励与LSVI-UCB探索奖励的理论关系，并在附录中完成完整推导。
- **实验验证扎实**：覆盖三种主流基准、多种任务类型，包含消融、泛化、噪声鲁棒性等多维度分析，实验结果清晰支持核心论点。

## 8. 不足与局限

- **初始学习效率偏低**：在部分任务中，CERMIC的初期学习曲线较慢，作者归因于从零学习多智能体意图建模的困难（部分可观测性导致）。
- **意图建模依赖局部观测**：在无通信、部分可观测条件下准确建模其他智能体意图仍具挑战，限制了算法在极端环境下的表现。
- **可扩展性存疑**：当前图构建和一步潜状态转移模型在更高维或多模态任务中可能需要扩展（如层次化潜模型）。
- **实验可重复性细节**：未公开所有超参数搜索范围和种子数量，部分实验仅以柱状图形式呈现误差，数值表中部分结果缺少误差范围（如表2、表4部分值仅单数值）。
- **算力报告不完整**：未提供完整训练时间、GPU数量等细节，不利于其他研究者复现。
- **社会影响**：作者声明无负面社会影响，但未讨论潜在滥用可能（如应用于竞争性无人机编队等）。

（完）
