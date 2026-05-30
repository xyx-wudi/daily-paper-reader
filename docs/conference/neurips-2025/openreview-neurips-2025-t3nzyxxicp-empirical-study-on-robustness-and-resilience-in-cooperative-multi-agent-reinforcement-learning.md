---
title: Empirical Study on Robustness and Resilience in Cooperative Multi-Agent Reinforcement Learning
title_zh: 合作多智能体强化学习中鲁棒性与弹性的实证研究
authors: "Simin Li, Zihao Mao, Hanxiao Li, Zonglei Jing, Zhuohang bian, Jun Guo, Li Wang, Zhuoran Han, Ruixiao Xu, Xin Yu, Chengdong Ma, Yuqing Ma, Bo An, Yaodong Yang, Weifeng Lv, Xianglong Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=t3NzYXXICp"
tags: ["query:marl"]
score: 8.0
evidence: 合作多智能体强化学习鲁棒性研究
tldr: 针对合作多智能体强化学习在现实不确定性下缺乏鲁棒性和弹性的问题，开展大规模实证研究（超过8万次实验）。评估了合作性能、鲁棒性和弹性，揭示了现有方法在现实场景中的弱点，为构建可信赖MARL提供指导。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 694, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 809, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 597, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1423, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 721, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1421, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1421, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1321, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1423, \"height\": 730, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1471, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1436, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1445, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1436, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1433, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1431, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1428, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1445, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 634, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t3nzyxxicp/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 629, \"height\": 478, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 811, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1463, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 430, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1329, \"height\": 1478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1328, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 1483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1453, \"height\": 99, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t3nzyxxicp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1386, \"height\": 1032, \"label\": \"Table\"}]"
motivation: 现有MARL策略在理想环境下调参优化，但实际环境中鲁棒性和弹性不足。
method: 设计大规模实验框架，在四个真实世界场景下系统评估合作、鲁棒性和弹性。
result: 发现当前方法在不确定性下性能显著下降，并总结了关键影响因素。
conclusion: 鲁棒性和弹性应成为MARL系统评估的关键指标。
---

## Abstract
In cooperative Multi-Agent Reinforcement Learning (MARL), it is a common practice to tune hyperparameters in ideal simulated environments to maximize cooperative performance. However, policies tuned for cooperation often fail to maintain robustness and resilience under real-world uncertainties. Building trustworthy MARL systems requires a deep understanding of \emph{robustness}, which ensures stability under uncertainties, and \emph{resilience}, the ability to recover from disruptions—a concept extensively studied in control systems but largely overlooked in MARL. In this paper, we present a large-scale empirical study comprising over 82,620 experiments to evaluate cooperation, robustness, and resilience in MARL across 4 real-world environments, 13 uncertainty types, and 15 hyperparameters. Our key findings are: (1) Under mild uncertainty, optimizing cooperation improves robustness and resilience, but this link weakens as perturbations intensify. Robustness and resilience also varies by algorithm and uncertainty type. (2) Robustness and resilience do not generalize across uncertainty modalities or agent scopes: policies robust to action noise for all agents may fail under observation noise on a single agent. (3) Hyperparameter tuning is critical for trustworthy MARL: surprisingly, standard practices like parameter sharing, GAE, and PopArt can hurt robustness, while early stopping, high critic learning rates, and Leaky ReLU consistently help. By optimizing hyperparameters only, we observe substantial improvement in cooperation, robustness and resilience across all MARL backbones, with the phenomenon also generalizing to robust MARL methods across these backbones.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

合作多智能体强化学习（MARL）在理想仿真环境中通过调参优化合作性能已成为常见做法，但所学策略在现实部署中面对观测误差、动作扰动、环境突变等不确定性时，往往缺乏**鲁棒性**（维持稳定）和**弹性**（从扰动中恢复）。现有研究常将鲁棒性与弹性混为一谈，忽视了二者的本质区别，且缺乏对超参数影响的系统性理解。论文旨在通过大规模实证研究，揭示合作性能、鲁棒性和弹性之间的关系，并识别影响可信赖MARL的关键超参数与不确定性类型。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 明确定义鲁棒性与弹性：鲁棒性衡量策略在持续不确定性下维持性能的能力；弹性衡量策略在遭遇扰动后从扰动状态恢复的能力。
- 设计统一评估框架，在合作、鲁棒性、弹性三个维度上对MARL算法进行系统评测。
- 通过单变量调参、相关分析、方差分析等方法，量化超参数、算法、不确定性类型对三者的影响。

### 关键技术细节
- **问题形式化**：采用Dec-POMDP模型，定义鲁棒性目标为 \( J_{\text{robust}}(\pi) = \mathbb{E}_{u \sim U} \left[ \mathbb{E}_{s_0 \sim \rho_0} \left[ \sum \gamma^t r_t \right] \right] \)，弹性目标为从扰动后初始状态 \( s_u \) 开始的预期回报。
- **超参数选择**：包含15个通用与算法特定超参数（如隐藏层大小、折扣因子、激活函数、学习率、参数共享、GAE、PopArt、早停等），每个超参数取多个值（共34种配置）。
- **不确定性类型**：覆盖13种不确定性，包括观测噪声（高斯、贪婪最坏情况、最优学习攻击，分别作用于单智能体或全体）、动作噪声（随机、贪婪、最优，分别作用于单/全体）和环境不确定性（从超参数随机集采样）。

## 3. 实验设计：数据集/场景、benchmark、对比方法

### 环境与任务
- 四个真实世界环境（共18个任务）：
  - **Dexhand**（灵巧手操作）：6个任务，连续控制，约80步，Isaac Gym仿真，强调精确控制。
  - **Quads**（四旋翼群控）：6个任务，连续控制，约1600步，OpenAI Gym仿真，强调长程任务分配。
  - **Traffic**（交通控制）：3个同构观测/动作空间任务，离散控制，约1000步，SUMO仿真，强调长程控制。
  - **Voltage**（主动电压控制）：3个任务，连续控制，约200步，IEEE标准仿真，强调复杂动态与噪声。

### 对比方法
- 三种主流MARL算法：MADDPG、MAPPO、HAPPO（均支持连续控制）。
- 此外，在泛化实验中测试了鲁棒MARL方法ERNIE。

### Benchmark
- 论文未采用单一现成Benchmark，而是自建评估框架，包含合作基线、13种鲁棒性评估、13种弹性评估，共27个评估设置。

## 4. 资源与算力

- 总计算量约 **230K GPU hours**，实测于 **GTX 4090**（附录A提及）。每次实验使用5个随机种子，共82,620次实验，经换算约需大量并行计算资源。论文未提供具体GPU数量及并行策略细节。

## 5. 实验数量与充分性

### 数量
- **总计82,620次实验**：5种子 × 27不确定性设置 × 18任务 × 34超参数配置。
- 每个任务下，对每个超参数每次改变一个值，生成34种模型，并逐一评估合作、鲁棒性、弹性。

### 充分性与公平性
- **充分性**：覆盖4类真实场景、13种不确定性（含单智能体/全体、弱/强攻击）、15个超参数，规模庞大，统计检验充分（如Pearson相关、配对t检验、双因素ANOVA、OLS回归）。
- **公平性**：所有算法使用相同默认超参数，调参时只改变单个变量；报告统计显著性，并采用5% winsorization抑制极端值。但论文指出可能存在任务特异性，某些结论在特定任务上不成立。

## 6. 论文的主要结论与发现

1. **合作与鲁棒性/弹性关系**：轻度不确定性下，优化合作可提升鲁棒性和弹性，但随扰动加剧，相关性显著减弱。不同算法对不确定性类型敏感：MADDPG更抗动作噪声，MAPPO/HAPPO更抗观测噪声。
2. **鲁棒性/弹性不泛化**：对一种不确定性（如全体动作噪声）鲁棒的策略可能在另一种不确定性（如单智能体观测噪声）下失败；观测、动作、环境三类不确定性之间无显著相关性，单智能体与全体攻击之间也无显著相关性。
3. **超参数的关键作用**：常见做法（参数共享、GAE、PopArt）在不确定性下反而有害；早停、高评论家学习率、Leaky ReLU始终有益。仅通过优化超参数，合作平均提升52.60%，鲁棒性提升34.78%，弹性提升60.34%；该改进泛化到鲁棒MARL方法上（合作+89.43%，鲁棒+65.83%，弹性+82.96%）。
4. **超参数影响常大于算法选择**：在9/18的任务中，双因素ANOVA表明单超参数变化对性能的影响超过更换MARL算法（p<0.001）。

## 7. 优点：方法或实验设计上的亮点

- **规模与系统性**：超过8万次实验，系统覆盖多环境、多不确定性、多超参数，统计严谨，结论可信。
- **清晰定义区分鲁棒性与弹性**：借鉴控制理论等领域的定义，并给出可操作的评估流程（鲁棒性评估持续扰动下性能，弹性评估从扰动状态恢复）。
- **实用指导性**：提炼出针对不同场景的具体建议表（Table 3），可直接为MARL实践者提供调参指南。
- **代码开源与扩展性**：提供模块化代码库，支持自定义算法与环境集成，便于后续研究复用。
- **反直觉发现**：挑战了参数共享、GAE、PopArt的普遍有效性，揭示了任务依赖性的重要性。

## 8. 不足与局限

- **算法覆盖有限**：仅评估了基于策略梯度的连续控制算法（MADDPG、MAPPO、HAPPO），未覆盖基于值分解的方法（如QMIX）或离散控制算法，可能限制结论的泛化。
- **超参数搜索不完全**：采用单变量调参，未系统探索超参数交互效应（虽附录B.7用OLS分析协同效应，但非完全网格搜索）。
- **环境代表性**：虽然涵盖4个真实世界环境，但均为仿真；实际部署中可能存在未模拟的不确定性（如通信延迟、硬件故障）。
- **弹性定义假设**：弹性评估假设扰动仅发生在初始时间步，未考虑持续扰动后的恢复过程，与某些现实场景不完全吻合。
- **计算成本高**：230K GPU小时使得复现成本极高，可能阻碍后续验证。
- **部分结论统计显著但效应量小**：例如早停的平均提升（合作2.85%，鲁棒13.62%，弹性2.48%）虽显著，但绝对数值较小，需结合任务具体分析。

（完）
