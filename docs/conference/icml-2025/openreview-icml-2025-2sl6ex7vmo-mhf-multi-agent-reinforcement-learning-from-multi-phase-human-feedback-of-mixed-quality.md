---
title: "M³HF: Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality"
title_zh: M³HF：基于多阶段混合质量人类反馈的多智能体强化学习
authors: "Ziyan Wang, Zhicheng Zhang, Fei Fang, Yali Du"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2Sl6Ex7Vmo"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体强化学习框架，集成人类反馈
tldr: 针对多智能体强化学习中奖励函数设计困难的问题，提出M3HF框架，整合不同质量的多阶段人类反馈，利用大语言模型解析反馈并持续优化策略。实验表明该方法在多智能体协调场景中有效提升策略对齐和行为质量。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1699, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1727, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1057, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 667, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1697, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1620, \"height\": 904, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 888, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 885, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 884, \"height\": 492, \"label\": \"Table\"}]"
motivation: 解决多智能体强化学习中奖励设计困难导致策略次优或行为失调的问题。
method: 提出多阶段混合质量人类反馈框架，利用大语言模型解析人类反馈，在训练中定期暂停进行人类评估。
result: 通过集成专家与非专家反馈，持续优化多智能体策略，提升协作环境中的行为对齐。
conclusion: M3HF有效利用混合质量人类反馈改进MARL训练，为奖励设计提供新思路。
---

## Abstract
Designing effective reward functions in multi-agent reinforcement learning (MARL) is a significant challenge, often leading to suboptimal or misaligned behaviors in complex, coordinated environments. We introduce Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality ($\text{M}^3\text{HF}$), a novel framework that integrates multi-phase human feedback of mixed quality into the MARL training process. By involving humans with diverse expertise levels to provide iterative guidance, $\text{M}^3\text{HF}$ leverages both expert and non-expert feedback to continuously refine agents' policies. During training, we strategically pause agent learning for human evaluation, parse feedback using large language models to assign it appropriately and update reward functions through predefined templates and adaptive weights by using weight decay and performance-based adjustments. Our approach enables the integration of nuanced human insights across various levels of quality, enhancing the interpretability and robustness of multi-agent cooperation. Empirical results in challenging environments demonstrate that $\text{M}^3\text{HF}$ significantly outperforms state-of-the-art methods, effectively addressing the complexities of reward design in MARL and enabling broader human participation in the training process.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在多智能体强化学习（MARL）中，设计有效的奖励函数极具挑战性，尤其是在复杂、协作的环境中，容易导致智能体策略次优或行为失调（reward misalignment）。稀疏或复杂的奖励信号使得智能体难以学习高效的协调行为。
- **背景**：现有方法如人类反馈强化学习（RLHF）大多局限于单智能体场景或离线单阶段偏好比较（如PbMARL），未能充分利用多轮、混合质量的人类反馈在线指导MARL训练。同时，大语言模型（LLM）在奖励设计中的应用也主要针对单智能体环境（如EUREKA）。
- **本文目标**：提出一个能够集成多阶段、不同质量水平人类反馈的MARL框架，利用迭代的人类指导来持续优化智能体策略，提升多智能体协作的鲁棒性和可解释性，同时降低对完美专家反馈的依赖。

## 2. 论文提出的方法论

- **核心思想**：扩展传统马尔可夫博弈（Markov Game）为**多阶段人类反馈马尔可夫博弈（MHF-MG）**，在标准元组中加入人类话语集和人类策略。训练分为多个世代（generation），每个世代中智能体先与环境交互训练，然后暂停并生成 rollout 视频供人类评估，人类根据自身策略提供文本反馈，框架利用LLM解析反馈并更新奖励函数。
- **关键技术细节**：
  1. **Rollout生成与性能估计**：每个世代后，收集X条独立轨迹，利用强数定律保证估计的收敛性（命题4.1）。
  2. **反馈解析**：使用LLM将人类自然语言反馈分配给特定智能体或全体智能体，生成结构化指令。
  3. **奖励函数生成**：基于预定义模板集F（包括距离型、动作型、状态型、时间型、成功型等），LLM根据解析后的反馈参数化模板，产生新的奖励函数组件。
  4. **自适应权重调整**：每个智能体维护一个奖励函数池，新组件初始权重为1/|Pool|，随后对旧权重进行指数衰减（衰减因子α），并根据性能变化（基于原始奖励评估的差值）动态调整（增加或减少β），最后归一化。公式（12）~（15）。
  5. **鲁棒性分析**：命题4.2证明，即使存在低质量反馈，算法性能累积积极贡献，而消极反馈仅在单个世代内产生有界退化，保证长期稳定性。

- **算法流程**（Algorithm 1）：
  - 初始化每个智能体的奖励函数池包含原始奖励。
  - 对每个世代k：
    * 多智能体训练：每个智能体使用当前组合奖励函数训练策略。
    * 生成Rollout轨迹。
    * 人类提供反馈uk。
    * LLM解析并分配到各智能体。
    * 为新反馈生成新奖励函数，加入池中。
    * 更新权重：先对旧权重应用衰减，再根据性能差调整新组件权重，然后归一化，得到最终组合奖励用于下一世代。

## 3. 实验设计

- **环境与场景**：基于**Overcooked**游戏（三个代理合作制作沙拉），采用宏观动作（macro-actions）简化操作。包含三种厨房布局（Overcooked-A、B、C，难度递增）和两种食谱（莴苣-番茄沙拉；莴苣-洋葱-番茄沙拉）。另在**Google Research Football 5v5**上进行了扩展实验。
- **基准方法**：
  - **MAC-based Baseline**：来自Xiao et al. (2022)的最佳宏观动作方法（Mac-IAICC和Mac-CAC的平均）。
  - **IPPO**：独立PPO。
  - **MAPPO**：中心化价值函数PPO。
  - **IRAT**：基于内在奖励的方法的三种变体（rw1, rw2, rw3）。
- **对比设置**：所有方法在相同超参数下训练，使用三个随机种子报告均值和标准差。

## 4. 资源与算力

- 论文未明确给出精确的GPU训练时长或具体算力消耗。
- 硬件配置：**多种CPU（Dual Intel Xeon E5系列）**，**3块NVIDIA A30 GPU**；**180个CPU核心**，**500GB系统内存**。操作系统为Ubuntu Linux的异构计算集群。

## 5. 实验数量与充分性

- **主要实验**：在Overcooked上共进行6种场景（3种布局 × 2种食谱）的完整比较，每个实验3个随机种子。结果以学习曲线和均值±标准差展示（图3）。
- **消融实验**：
  - **反馈解析与权重调整消融**（表1）：比较“原始反馈无解析”、“LLM解析无权重调整”与完整M³HF在Overcooked-B复杂食谱下的平均回报。
  - **单阶段 vs 多阶段反馈消融**（表2）：仅初始阶段提供反馈 vs 多阶段迭代反馈。
  - **与内在奖励方法对比**（表3）：IRAT三种变体与M³HF在400、600、800、1000迭代时的表现。
- **额外实验**：
  - **混合质量反馈影响**（图4c）：比较低质量反馈、VLM反馈和理想人类反馈下的性能。
  - **VLM反馈生成实验**（图4a-c）：使用Gemini-1.5-Pro生成反馈的效果。
  - **Google Football 5v5扩展**（附录图5-6）：展示M³HF在更复杂场景下的性能提升。
- **充分性评价**：实验覆盖了多种难度、多种反馈质量、多个消融因子，并验证了鲁棒性理论，设计较为全面。但未在更多MARL基准（如SMAC、MPE）上测试，限制了泛化性结论。

## 6. 论文的主要结论与发现

1. **M³HF显著优于现有SOTA方法**：在Overcooked所有场景中，M³HF均比IPPO、MAPPO和Mac-based Baseline获得更高的平均回报和更快的收敛速度。
2. **多阶段反馈优于单阶段反馈**：迭代提供反馈比仅初始一次反馈带来显著性能提升（表2）。
3. **结构化解析和自适应权重调整是关键**：LLM解析+权重调整相比仅解析或原始反馈有大幅提升（表1）。
4. **对低质量反馈具有鲁棒性**：即使提供无关或错误反馈，M³HF性能仅略微低于基线IPPO，不会大幅退化（支持命题4.2）。
5. **VLM替代人类反馈暂未达到理想效果**：当前VLM（Gemini-1.5-Pro）提供的反馈缺乏具体性，难以有效转化为奖励设计，性能提升有限，但未来模型进步后可能改善。
6. **可扩展到更复杂场景**：在Google Football 5v5中，M³HF在胜率、传球次数、射门质量等指标上超越基线。

## 7. 优点

- **方法创新性**：首次在MARL中引入多阶段、混合质量的人类在线反馈，并利用LLM实现自然语言到结构化奖励的自动转换，降低了专家参与门槛。
- **鲁棒性理论分析**：提供了严格证明（命题4.2），表明算法能自动降低低质量反馈的影响，保障长期学习稳定性。
- **自适应权重机制**：结合权重衰减和性能反馈，动态平衡新旧奖励组件，避免了手动调参。
- **实验设计全面**：覆盖不同难度环境、不同食谱、多种反馈质量、多种消融，并扩展至足球环境，验证了通用性。
- **人类参与少**：整个训练过程仅需最多5次人类交互，效率高。

## 8. 不足与局限

- **实验场景局限**：主要基于Overcooked环境，虽然扩展到足球，但尚未在经典MARL基准（如SMAC、MPE、粒子世界）上验证，结论的通用性有待进一步检验。
- **VLM反馈效果有限**：实验表明当前VLM难以提供足够具体的策略建议，无法有效代替人类，限制了自动化潜力。
- **计算开销**：每次世代需生成rollout视频并调用LLM解析和生成奖励函数，可能带来额外的时间与计算成本，论文未提供详细的效率对比。
- **人类反馈质量假设**：尽管理论上有鲁棒性，但极端恶劣的连续错误反馈仍可能积累负面影响（有界但可能较大），实际应用中需考虑人类参与的质量控制。
- **未讨论多模态交互**：仅使用文本反馈，未探索视觉、演示等更丰富的人类指导形式。
- **超参数敏感性**：权重衰减因子α、性能调整量β等需要预设，论文未进行敏感性分析。

（完）
