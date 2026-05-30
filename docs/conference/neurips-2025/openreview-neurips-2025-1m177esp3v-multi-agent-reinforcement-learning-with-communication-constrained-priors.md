---
title: Multi-Agent Reinforcement Learning with Communication-Constrained Priors
title_zh: 基于通信受限先验的多智能体强化学习
authors: "Guang Yang, Tianpei Yang, Jingwen Qiao, Yanqing Wu, Jing Huo, Xingguo Chen, Yang Gao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1m177EsP3V"
tags: ["query:marl"]
score: 9.0
evidence: 合作多智能体强化学习中的通信受限先验
tldr: 该论文针对多智能体系统中的有损通信问题，提出一种广义通信受限模型作为学习先验。该模型能够统一刻画不同场景下的通信条件，并区分有损和无损消息对分布式决策的影响。实验表明该方法在复杂动态环境中具有更好的可扩展性和鲁棒性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1m177esp3v/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 686, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1m177esp3v/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 981, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1m177esp3v/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1103, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1m177esp3v/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1m177esp3v/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 944, \"label\": \"Table\"}]"
motivation: 现有通信多智能体强化学习在复杂动态环境中可扩展性和鲁棒性不足，尤其在有损通信条件下表现不佳。
method: 提出一种广义通信受限模型作为学习先验，区分有损和无损消息，并解耦其对分布式决策的影响。
result: 该方法在多种有损通信场景下显著提升了合作策略的学习效率和鲁棒性。
conclusion: 通信受限先验能够有效提升多智能体系统在现实有损通信环境中的适应能力。
---

## Abstract
Communication is one of the effective means to improve the learning of cooperative policy in multi-agent systems. However, in most real-world scenarios, lossy communication is a prevalent issue. Existing multi-agent reinforcement learning with communication, due to their limited scalability and robustness, struggles to apply to complex and dynamic real-world environments. To address these challenges, we propose a generalized communication-constrained model to uniformly characterize communication conditions across different scenarios. Based on this, we utilize it as a learning prior to distinguish between lossy and lossless messages for specific scenarios. Additionally, we decouple the impact of lossy and lossless messages on distributed decision-making, drawing on a dual mutual information estimatior, and introduce a communication-constrained multi-agent reinforcement learning framework, quantifying the impact of communication messages into the global reward. Finally, we validate the effectiveness of our approach across several communication-constrained benchmarks.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：在多智能体强化学习（MARL）中，通信是提升合作策略性能的有效手段。然而，现实场景中的通信往往是有损的（如带宽限制、噪声干扰、延迟、丢包等），现有基于通信的MARL方法在面对复杂动态环境时，可扩展性和鲁棒性不足，难以应对多样化的有损通信情况。
- **核心问题**：如何设计一种能够统一刻画不同有损通信场景（如水下、洞穴、无线网络等）的模型，并基于此提升多智能体在通信受限环境下的协作学习鲁棒性。
- **整体含义**：本文提出一种**通信受限先验模型**，能够区分有损和无损消息，并通过**双重互信息估计器**解耦不同类型消息对决策的影响，从而在全局奖励中量化消息的作用，最终提升策略学习的适应性和鲁棒性。

## 2. 方法论

- **核心思想**：构建一个通用的通信受限先验，利用二元通信链路参数 ι 表征消息可靠性；基于先验区分有损/无损消息；对无损消息最大化其与智能体行为的互信息下界，对有损消息最小化其与行为的互信息上界，从而增强有效消息的正面影响、抑制无效消息的负面影响，并将此量化融入全局奖励。
- **关键技术细节**：
  - **通信受限先验建模**：定义 `ι_{ij} = f_{θ_e}(s_{ij})`，其中 `f_{θ_e}` 可手动定义或通过二分类预训练获得，用于动态判断链路状态（0表示有损，1表示无损）。消息被分为 `M+`（无损）和 `M-`（有损）两类。
  - **双重互信息估计器（Du-MIE）**：
    - 对无损消息，使用基于Jensen-Shannon散度的互信息下界估计器 `I_{JSD}(m_{ji}; a_i)`，通过最小化损失 `L_{ji}(θ_1)` 逼近下界，鼓励智能体行为与有效消息高度相关。
    - 对有损消息，使用基于对比对数比上界（CLUB）的互信息上界估计器 `I_{CLUB}(m_{ji}; a_i)`，通过最小化损失 `L_{ji}(θ_2)` 逼近上界，抑制智能体行为与有损消息的关联。
    - 总体损失：`L_{CC}(θ_1, θ_2) = Σ_i Σ_{j≠i} [ ι_{ji} L_{ji}(θ_1) + (1-ι_{ji}) L_{ji}(θ_2) ]`。
  - **奖励塑形**：将互信息估计值加入全局奖励：`\tilde{r}_t = r_t + Σ_i Σ_{j≠i} [ α ι_{ji} I_{JSD}(m_{ji}; a_i) - β (1-ι_{ji}) I_{CLUB}(m_{ji}; a_i) ]`，其中 α、β 为权重系数。然后最大化塑形后的折扣回报。
  - **算法流程**：与CTDE（中心化训练分布式执行）框架结合，如MADDPG。在训练中，收集轨迹时额外记录通信消息和链路状态；每k步更新Du-MIE；根据塑形奖励计算TD误差或策略梯度损失进行优化（具体见论文Algorithm 1）。
- **公式/算法（文字说明）**：论文给出了Du-MIE的JSD估计式（公式3）、CLUB估计式（公式4）、总损失（公式5）、塑形奖励（公式6）以及MARL框架中的TD损失（公式7）和策略损失（公式8）。算法1详细描述了采样、Du-MIE更新、网络参数更新的步骤。

## 3. 实验设计

- **场景与基准**：使用**多智能体粒子环境（MPE）** 中的三个任务：Simple_Tag（捕食者-猎物）、Simple_Spread（覆盖地标）、Simple_Reference（协作导航）。还使用了Simple_Adversary（对抗任务）作为补充。
- **通信约束模型**：
  - **基于马尔可夫的通信（MBC）**：使用状态转移概率矩阵模拟通信链路在无损和有损状态间切换，通过状态数量控制损失程度（轻/中/重，对应3/6/8个状态）。
  - **基于距离的通信（DBC）**：根据智能体间距离设置阈值（5/3/1，分别对应轻/中/重度约束），距离越小消息丢失率越高。
- **对比方法**：
  - **MAIC**（基于激励的通信方法）
  - **FC-MADDPG**（完全通信MADDPG，理想通信下训练）
  - **Dropout-MADDPG**（训练时以不同概率随机丢弃消息，概率0.2/0.5/0.8）
  - **标准MADDPG**（无通信）
  - **本文方法CC-MADDPG**（默认使用dropout-0.2作为先验，并与MADDPG结合）
- **评价指标**：平均回合累积奖励（均值±标准差），在训练后运行100个episode测试。

## 4. 资源与算力

- 文中在附录A.1.2中明确说明：使用**NVIDIA RTX A5000 24GB GPU**。
- 没有明确说明使用了多少块GPU或具体训练时长，但给出了总训练时间步为`4.0 × 10^6`，批次大小通常为1024（在Simple_Tag任务中6/9智能体时调整为512以避免显存溢出）。训练过程中每100总时间步更新一次模型参数。
- 整体算力描述较为粗略，未提供完整的GPU数量、并行度或总耗时。

## 5. 实验数量与充分性

- **实验数量**：
  - **总体性能**（表1）：在4个任务场景（Simple_Tag, Simple_Spread, Simple_Reference, Simple_Adversary）下，针对MBC（轻/中/重）和DBC（轻/中/重）共7种测试环境（加上无约束）进行了对比，每个算法重复多次取均值和标准差。
  - **通信先验影响**（表2）：在Simple_Spread和Simple_Reference的DBC环境下，对比了通用dropout-0.2先验与“测试环境匹配先验”的性能。
  - **Du-MIE消融实验**（表3）：在Simple_Tag和Simple_Spread的7种测试环境下，对比了基线（无MI优化）、仅JSD、仅CLUB和完整CC-MADDPG四个变体。
  - **规模扩展性实验**（附录表4）：在Simple_Tag下将智能体数量从3增加到6和9，重复上述对比。
- **充分性评估**：
  - **正面**：覆盖了多种通信约束类型（MBC和DBC）、多种损失程度、多种任务，且有消融实验和规模扩展实验。对比基准包括无通信、理想通信、随机丢弃等多种方法，较为全面。
  - **可改进之处**：所有实验仅在MPE模拟环境中进行，未在更复杂的高维环境（如星际争霸、自动驾驶模拟器）中验证。实验次数仅报告了100个episode的均值，未说明是否有多次重复运行（不同随机种子）。论文中随机种子仅设置为1，缺乏对结果稳定性的统计检验。

## 6. 主要结论与发现

1. **有损通信严重破坏合作策略**：FC-MADDPG在理想环境下性能好，但一旦引入通信约束，平均奖励急剧下降（如Simple_Tag从75.9降至1.5），说明理想通信训练的策略在实际有损场景中脆弱。
2. **引入通信受限先验显著提升鲁棒性**：Dropout-MADDPG和CC-MADDPG（均使用dropout-0.2先验）在不同约束下性能远优于FC-MADDPG。CC-MADDPG在极端约束下甚至优于理想通信下的FC-MADDPG（如Simple_Tag重DBC下138.0 vs 75.9）。
3. **测试环境匹配先验可进一步优化**：使用与实际测试相同的通信约束先验训练，性能优于通用dropout先验（如表2所示）。
4. **双重互信息优化效果叠加**：消融实验表明，单独使用JSD（最大化与无损消息的MI）或CLUB（最小化与有损消息的MI）均能提升性能，而两者结合（完整模型）在所有环境下表现最佳。
5. **规模扩展性**：增加智能体数量（6和9）时，FC-MADDPG和Dropout-MADDPG性能下降明显，而CC-MADDPG仍保持较高平均水平，展现出更好的鲁棒性。

## 7. 优点

- **提出统一通信受限先验**：通过二元链路参数抽象了不同场景下有损通信的共性，并支持多种先验获取方式（手工定义、预训练、随机丢弃等），具有良好的通用性。
- **双重互信息估计机制**：创新性地同时利用互信息的下界和上界来分别增强有效通信和抑制无效通信，并通过奖励塑形自然融入MARL训练，避免了复杂的策略约束。
- **与现有MARL算法兼容**：框架可与任何CTDE算法（如MADDPG、值分解方法）结合，具有较好的可扩展性。
- **实验设计全面**：覆盖多种通信约束模型、多种损失程度、多种任务，并包含消融和规模扩展实验，验证了方法的鲁棒性和有效性。
- **推理高效**：测试时仅需利用先验区分消息，无需额外计算互信息估计，开销低。

## 8. 不足与局限

- **实验环境相对简单**：仅在MPE平台进行验证，任务复杂度有限，未在更高维或更接近真实世界的环境（如自动驾驶、无人机编队）中测试，泛化能力存疑。
- **先验获取依赖场景**：先验模型 `f_{θ_e}` 需要手动定义或预训练，对于完全未知的动态环境，可能无法精准建模，影响效果。
- **未报告统计显著性**：仅使用单一随机种子，未提供多次重复实验的置信区间或显著性检验，结果稳定性有待确认。
- **计算资源描述不完整**：仅提供了GPU型号和部分参数，未说明GPU数量、训练时长等细节，可复现性有所欠缺。
- **理论分析薄弱**：尽管使用了互信息理论，但未提供关于收敛性、最优性等理论保证，主要依赖实验验证。
- **现实约束模拟简化**：MBC和DBC模型虽然比随机丢包更真实，但仍与实际无线通信中的复杂现象（如干扰、多径、协议开销）有差距。

（完）
