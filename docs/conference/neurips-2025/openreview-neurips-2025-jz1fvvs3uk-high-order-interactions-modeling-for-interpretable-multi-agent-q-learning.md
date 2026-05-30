---
title: High-order Interactions Modeling for Interpretable Multi-Agent Q-Learning
title_zh: 面向可解释多智能体Q学习的高阶交互建模
authors: "Qinyu Xu, Yuanyang Zhu, Xuefei Wu, Chunlin Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=JZ1fVVS3uk"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体Q学习中的高阶交互建模
tldr: 该论文针对多智能体强化学习中高阶交互建模的组合爆炸和黑箱问题，提出连分数Q学习（QCoFr）框架，能以线性复杂度灵活捕获任意阶智能体交互，避免了组合爆炸。进一步引入变分信息瓶颈增强可解释性。实验表明QCoFr在协作任务中优于现有价值分解方法，并能揭示交互机制。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 449, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 920, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1435, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1423, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 1255, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1434, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1438, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jz1fvvs3uk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1436, \"height\": 459, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jz1fvvs3uk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 533, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jz1fvvs3uk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jz1fvvs3uk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 571, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jz1fvvs3uk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 566, \"height\": 430, \"label\": \"Table\"}]"
motivation: 现有高阶交互建模受限于组合爆炸或网络黑箱。
method: 提出连分数Q学习框架，用线性复杂度捕获任意阶交互。
result: 在协作环境中性能优于现有方法并具有可解释性。
conclusion: QCoFr有效平衡了建模能力与计算效率。
---

## Abstract
The ability to model interactions among agents is crucial for effective coordination and understanding their cooperation mechanisms in multi-agent reinforcement learning (MARL). 
However, previous efforts to model high-order interactions have been primarily hindered by the combinatorial explosion or the opaque nature of their black-box network structures.
In this paper, we propose a novel value decomposition framework, called Continued Fraction Q-Learning (QCoFr), which can flexibly capture arbitrary-order agent interactions with only linear complexity $\mathcal{O}\left({n}\right)$ in the number of agents, thus avoiding the combinatorial explosion when modeling rich cooperation. 
Furthermore, we introduce the variational information bottleneck to extract latent information for estimating credits.
This latent information helps agents filter out noisy interactions, thereby significantly enhancing both cooperation and interpretability.
Extensive experiments demonstrate that QCoFr not only consistently achieves better performance but also provides interpretability that aligns with our theoretical analysis.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
在合作式多智能体强化学习（MARL）中，智能体之间的交互建模是实现有效协调和揭示合作机制的关键。然而，现有方法在建模高阶交互时面临两大挑战：一方面，直接展开高阶项会导致组合爆炸（$O(2^n)$复杂度）；另一方面，采用黑盒网络（如QMIX中的单调混合网络）虽然能隐式建模高阶交互，但缺乏可解释性，无法揭示具体的协作模式。为此，论文提出一种兼具表达能力和内在可解释性的价值分解框架——连分数Q学习（Continued Fraction Q-Learning, QCoFr），旨在以线性复杂度建模任意阶智能体交互，并同时提升合作性能与可解释性。

## 2. 论文提出的方法论
### 核心思想
- 利用连分数（Continued Fraction）的递归结构来逼近任意阶的智能体交互，其深度为d的截断对应Padé近似，能够以$O(n)$复杂度显式建模d阶交互，避免组合爆炸。
- 结合变分信息瓶颈（Variational Information Bottleneck, VIB）从智能体的隐藏状态中提取与最优联合动作相关的潜在信息，用于辅助信用分配，减少全局状态s带来的混淆效应。

### 关键技术细节
- **个体动作价值函数**：每个智能体采用GRU循环Q网络，基于局部观测、历史信息、上一动作输出$Q_i(\tau_i, u_i)$。
- **辅助信息生成模块**：通过VIB生成潜在表示$m$，满足马尔可夫链$h \rightarrow m \rightarrow u^*$。目标函数为$J_{IB} = I(m,u^*) - \beta I(m,h)$，通过变分近似得到可优化的下界和上界，最终损失为$\mathcal{L}_{VIB} = \frac{1}{N}\sum_i \mathbb{E}_{\epsilon}[-\log q(u_i^*|f(h_i,\epsilon))] + \beta \text{KL}[p(m|h_i)||\tilde{q}(m)]$。
- **混合网络（CFN）**：将$l$个不同深度的连分数梯子（ladder）的输出加权求和，每个梯子对应一种交互阶数的有理逼近。权重$\alpha_k$通过全局状态$s$和辅助信息$m$经softmax计算得到，满足IGM原则（采用严格非负激活函数）。联合价值函数表示为$Q_{tot} = \sum_{k} \alpha_k \hat{Q}_k$，其展开形式等价于各阶交互项的线性组合。
- **整体损失**：结合TD误差和VIB损失，端到端训练。

## 3. 实验设计
### 数据集/场景与基准
- **LBF**（Level-Based Foraging）：两种配置（3 agents - 3 foods, 4 agents - 2 foods），10×10网格世界。
- **SMAC**（StarCraft Multi-Agent Challenge）：6个地图，包括简单（2s3z）、困难（2c_vs_64zg, 3s_vs_5z, 5m_vs_6m）、超困难（3s5z_vs_3s6z, 6h_vs_8z）。
- **SMACv2**：3个场景（protoss_5_vs_5, terran_5_vs_5, zerg_5_vs_5），具有随机起始位置、随机单位类型等，增加随机性。

### 对比方法
共9种基线：VDN, QMIX, QPLEX, CW-QMIX, CDS, SHAQ, GoMARL, ReBorn, NA²Q。

## 4. 资源与算力
论文未详细说明训练时长，仅提及“训练时间从1到16小时不等，取决于任务复杂度和回合长度”。硬件为NVIDIA RTX 3080TI GPU + Intel i9-12900k CPU。所有实验在该单一设备上完成，未使用多GPU或集群。

## 5. 实验数量与充分性
- **性能对比**：三大benchmark共约11个场景，每个场景5个随机种子，报告均值±标准差。
- **消融实验**：
  - 交互阶数d的影响（d=1,2,4,6对比）。
  - CFN结构变体（CFN-C, CFN-D）的对比。
  - VIB模块的有无对比。
  - IGM约束的有无对比。
  - 将VIB加在NA²Q上的额外对比。
  
实验较为充分，覆盖了不同复杂度环境、多种消融维度，且与多种SOTA方法公平对比（统一使用PyMARL框架和相同超参数）。结果曲线清晰，统计性良好。

## 6. 论文的主要结论与发现
- QCoFr在LBF、SMAC、SMACv2上均达到或超过现有最佳方法，尤其在超困难SMAC场景上优势显著。
- 建模高阶交互（d>1）比仅用一阶交互带来明显性能提升，但过高的阶数可能因过拟合导致性能下降，存在与任务复杂度匹配的最优阶数。
- VIB模块显著加速收敛并提升最终性能，表明辅助信息有效促进了信用分配。
- CFN结构相比黑盒混合网络（QMIX）和简单加和（VDN）能产生更多样化的智能体行为（余弦相似度更低），且能通过可视化交互系数揭示个体和联盟的贡献，提供了清晰的可解释性。

## 7. 优点
- **理论与方法创新**：首创将连分数网络引入价值分解，以线性复杂度显式建模任意阶交互，且从数学上证明其与Padé近似的等价性。
- **内在可解释性**：不同于后验解释方法，QCoFr通过连分数系数直接量化各阶交互的重要性，可动态展示智能体间及联盟的贡献。
- **实验全面**：在三大主流基准上验证，涵盖简单到超困难场景，消融实验覆盖核心组件，对比方法丰富且公平。
- **高效实用**：复杂度仅$O(n)$，易于扩展到大规模智能体场景。

## 8. 不足与局限
- **固定阶数限制**：当前实现中每个任务的CFN深度d是固定的，可能不是最优或造成计算浪费，论文指出未来可探索自适应调整深度。
- **IGM约束**：论文虽验证了无IGM约束时仍可行，但默认采用IGM设计可能限制了表达力，未来可结合完全的IGM-free方法。
- **算力报告不完整**：未提供精确的训练时间、GPU利用率等细节，可复现性方面稍弱。
- **实验环境**：主要在StarCraft II和LBF上测试，缺乏更多样化（如连续控制、大规模工业场景）的验证。
- **潜在偏差风险**：可解释性分析主要基于可视化案例和倾向性统计，缺乏定量的因果验证，可能存在观察者偏差。

（完）
