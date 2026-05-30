---
title: Enhancing Cooperative Multi-Agent Reinforcement Learning with State Modelling and Adversarial Exploration
title_zh: 通过状态建模与对抗性探索增强合作多智能体强化学习
authors: "Andreas Kontogiannis, Konstantinos Papathanasiou, Yi Shen, Giorgos Stamou, Michael M. Zavlanos, George Vouros"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TCsdlqzZNL"
tags: ["query:marl"]
score: 9.0
evidence: 合作多智能体强化学习与状态建模
tldr: 针对分布式部分可观测环境中无通信的合作MARL挑战，提出状态建模框架，使智能体从局部观测推断有用信念表征，并利用该表征增强探索与协作策略。实验验证了该方法在合作任务上的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1482, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1047, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1258, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 710, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 463, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 485, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 752, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 947, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1470, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1459, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1762, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 734, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1567, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1765, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 580, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 569, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 567, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1728, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 682, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 691, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1457, \"height\": 890, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 568, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1653, \"height\": 1026, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 532, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 724, \"height\": 1143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 744, \"height\": 1012, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 537, \"height\": 795, \"label\": \"Table\"}]"
motivation: 解决分布式部分可观测环境下无通信的多智能体协作学习难点。
method: 提出状态建模框架，智能体推断非可观测状态的信念表征，并过滤冗余信息以优化策略。
result: 在合作任务中显著提升探索效率与任务完成能力。
conclusion: 状态建模有效促进无通信环境下的多智能体协作。
---

## Abstract
Learning to cooperate in distributed partially observable environments with no communication abilities poses significant challenges for multi-agent deep reinforcement learning (MARL). This paper addresses key concerns in this domain, focusing on inferring state representations from individual agent observations and leveraging these representations to enhance agents' exploration and collaborative task execution policies. To this end, we propose a novel state modelling framework for cooperative MARL, where agents infer meaningful belief representations of the non-observable state, with respect to optimizing their own policies, while filtering redundant and less informative joint state information. Building upon this framework, we propose the MARL SMPE$^2$ algorithm. In SMPE$^2$, agents enhance their own policy's discriminative abilities under partial observability, explicitly by incorporating their beliefs into the policy network, and implicitly by adopting an adversarial type of exploration policies which encourages agents to discover novel, high-value states while improving the discriminative abilities of others. Experimentally, we show that SMPE$^2$ outperforms a plethora of state-of-the-art MARL algorithms in complex fully cooperative tasks from the MPE, LBF, and RWARE benchmarks.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：在分布式、部分可观测（partial observability）且 **无通信能力** 的协作多智能体环境中，如何让智能体仅依赖自身局部观测推断全局状态信息，并利用这些推断提升探索效率和协作策略？现有方法存在三个主要缺陷：(a) 推断的信念表征未针对策略优化进行学习，导致与策略脱节；(b) 未过滤冗余的非信息性状态特征，反而损害性能；(c) 未利用推断表征改进初始随机探索，尤其难以处理稀疏奖励任务。
- **整体含义**：该研究旨在弥合状态表示学习与策略优化之间的鸿沟，提出一个统一框架，使智能体在训练时通过集中训练（CTDE）学习有用的状态信念，并在执行时仅依赖本地观测和信念进行协作，从而提升复杂协作任务的求解能力。

#### 2. 方法论：核心思想与关键技术细节
- **核心思想**：提出 **状态建模（State Modelling, SM）** 框架，每个智能体 i 学习一个概率编码器-解码器（Variational Encoder-Decoder, ED），从自身观测 o_i 推断隐变量 z_i（信念），该信念应包含可帮助策略优化的非可观测状态信息。同时引入 **AM（Agent Modelling）过滤器** w_i（可学习权重）来过滤其他智能体观测 o_{-i} 中的冗余、不可推断特征，仅保留对策略有价值的部分。
- **关键技术细节**：
  1. **自监督状态建模**：使用变分自编码器（VAE），编码器 q_{ω_i}(z_i|o_i) 生成信念，解码器 p_{ϕ_i}（目标：w_i·o_{-i}）重建经过滤的其他智能体观测。损失函数包括重建误差 L_rec、KL 散度 L_KL 和正则项 L_norm。
  2. **信念增强策略**：每个智能体的策略网络条件于历史 h_i^t 和当前信念 z_i^t：π_{ψ_i}(a_i^t | h_i^t, z_i^t)。
  3. **对抗式探索（Adversarial Exploration）**：基于信念 z_i 设计内在奖励 ˆr_i，采用 SimHash 计数方法，鼓励智能体发现新颖观测（从而新颖 z_i），这些观测对其他智能体的重建模型形成“对抗性”挑战，促使其他智能体改进状态推断。总奖励 ˜r_i = r_i + β ˆr_i。
  4. **双重 Critic**：标准 Critic V_ξ(s) 用于策略优化；第二个 Critic V_k(ˆs) 利用过滤状态 ˆs = o_i ⊕ (w_i·o_{-i})，将 w_i 的训练与策略价值联系起来，确保 w_i 过滤掉非信息性特征。
- **算法流程**：基于 MAA2C 架构，每个时间步采样信念和动作，收集经验，定期更新 ED、AM 过滤器和 Critic（见论文 Algorithm 1）。

#### 3. 实验设计
- **Benchmark 与场景**：
  - **MPE**（Multiagent Particle Environment）：Spread（3/4/5/8 智能体）、Double Speaker-Listener。
  - **LBF**（Level-Based Foraging）：6 个任务，包括 2s-9x9-3p-2f、4s-11x11-3p-2f、7s-20x20-5p-3f 等。
  - **RWARE**（Multi-Robot Warehouse）：tiny-2ag-hard、tiny-4ag-hard、small-4ag-hard。
- **对比方法**：
  - 基础：MAA2C、COMA、MAPPO、QMIX。
  - 探索类：EOI、EMC、MASER。
  - 建模类：ATM、SIDE、MLIAM（自实现多智能体扩展的 LIAM）。
- **评价指标**：平均回合回报（episodic reward），报告 25%-75% 置信区间，结果基于 6 个随机种子。

#### 4. 资源与算力
- 论文在附录 E.4.12 中给出了运行时间比较的硬件规格：**GPU RTX 3080 Ti，CPU 11th Gen Intel Core i9-11900，64GB RAM**。未明确说明训练时的具体 GPU 数量或并行方式，仅提及使用 10 个并行环境（Nenvs=10）。训练步数：MPE 和 LBF 为 10M 步，RWARE 为 40M 步。未报告总训练时长，仅提供了部分方法在单个任务上的相对运行时间比较（如 SMPE² 比 MASER 快约 25 倍）。

#### 5. 实验数量与充分性
- **实验数量**：在三大 benchmark 共约 12 个任务上进行了主实验，每个任务 6 个种子，结果含置信区间。消融实验包括：组件选择（是否有 AM 过滤器、KL、L2 正则、内在奖励、标准 SimHash 替代）、学习方式（是否使用第二个 Critic）、超参数（λ_rec, λ_norm）、与 MLIAM/SIDE 的对比、与 MAPPO 组合的灵活性、t-SNE 可视化及逻辑回归定量分析、内在奖励动态分析、AM 过滤器可视化分析。
- **充分性与客观性**：实验设计较为全面，覆盖了不同复杂度、不同稀疏奖励程度的任务，对比了多种 SOTA 方法。结果报告了统计不确定性（置信区间），且所有方法使用相同训练步数并基于公共代码库（EPyMARL）。消融实验验证了各组件的必要性。因此，实验是充分、客观、公平的。

#### 6. 主要结论与发现
- SMPE² 在所有三个 benchmark 上均优于现有 SOTA 方法，尤其擅长解决稀疏奖励和需要高度协作的任务（如 LBF 的 11x11 任务、RWARE hard 任务）。
- 状态建模信念 z_i 能够有效捕获全局状态信息，且通过 AM 过滤器滤除冗余特征后，显著提升策略的判别能力。
- 对抗式探索机制（基于信念的内在奖励）比单纯的观测计数探索更有效，不仅促进个体发现新颖状态，还通过挑战其他智能体的重建模型间接提升了整体协作。
- 信念表征的 t-SNE 可视化表明，加入 KL 正则后，智能体的信念更加凝聚且相互关联，有利于协作。

#### 7. 优点
- **方法创新**：将状态表示学习与策略优化紧密结合，提出“状态建模框架”，并通过双重 Critic 确保 AM 过滤器朝向价值最大化方向学习，避免脱节。
- **AM 过滤器的自监督学习**：自动识别并过滤冗余信息，降低了状态空间噪声对策略的干扰。
- **对抗式探索**：将内在探索与多智能体互动结合，引导智能体发现对其他智能体重建有挑战性的观测，从而提升整体推断能力。
- **灵活性**：可以轻松集成到不同的 actor-critic 骨架（如 MAA2C 和 MAPPO）中。
- **实验扎实**：在三个广泛使用的 benchmark 上进行了全面比较，包含大量消融实验和可视化分析，验证了各组件的贡献。

#### 8. 不足与局限
- **计算开销**：每个智能体需要维护编码器-解码器、AM 过滤器及第二个 Critic，相对于基础 MAA2C 有额外的参数和训练步骤，尽管运行时间仍远低于某些复杂探索方法（如 EMC、MASER），但在极大规模场景下可能仍显昂贵。
- **假设前提**：论文假设联合观测足以区分状态，但真实环境中观测噪声或缺失可能导致推断不准确；未在随机性更强（如 noisy observations）的环境进行测试。
- **部分可观测性限制**：信念仅依赖于当前观测 o_i 而非历史 h_i，虽然策略网络使用了历史，但探索过程中的内在奖励仅基于单步 z_i，可能会忽略轨迹级的新颖性。作者在 Remark 3.1 中讨论了此设计选择，但可能在某些场景下（如需要长时间探索）效果有所削弱。
- **超参数依赖**：控制各项损失的权重（λ_rec, λ_norm, λ_KL, β 等）需要针对不同任务调优，论文虽给出了典型值，但未提供自适应调整方案。
- **理论保证有限**：Proposition 2.1 证明了状态建模目标与标准 Dec-POMDP 目标的最优值相等，但未给出收敛性分析或最优性条件。
- **应用风险**：如论文 Impact Statement 所述，MARL 方法在实际部署前需经过严格测试，存在泛化性、可解释性和安全伦理等问题。

（完）
