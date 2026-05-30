---
title: "MisoDICE: Multi-Agent Imitation from Mixed-Quality Demonstrations"
title_zh: MisoDICE：来自混合质量演示的多智能体模仿
authors: "The Viet Bui, Tien Anh Mai, Thanh Hong Nguyen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=krG6UHAvYr"
tags: ["query:marl"]
score: 9.0
evidence: 合作多智能体离线模仿学习，处理混合质量演示
tldr: 该论文研究合作多智能体离线模仿学习中混合质量演示的利用问题。提出两阶段方法MisoDICE：第一阶段利用大语言模型和偏好强化学习构建渐进标签管道区分专家轨迹；第二阶段提出新型多智能体IL算法利用标签学习鲁棒策略，同时处理大联合状态空间的复杂度。在实验上验证了其对异构无标签数据的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1289, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1430, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1299, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1386, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 730, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1393, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 734, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1107, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1106, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-krg6uhavyr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 728, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1376, \"height\": 998, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1060, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 741, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1134, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1118, \"height\": 834, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1166, \"height\": 752, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1164, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1034, \"height\": 874, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1450, \"height\": 908, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1205, \"height\": 798, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1238, \"height\": 819, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1237, \"height\": 814, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1236, \"height\": 841, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 957, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-krg6uhavyr/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1235, \"height\": 801, \"label\": \"Table\"}]"
motivation: 演示数据质量混合且无标签，现有方法难以有效利用。
method: 用LLM偏好标签管道标注轨迹，再用MisoDICE算法进行多智能体模仿学习。
result: 在多个合作多智能体任务上优于现有离线IL方法。
conclusion: 两阶段标签+IL范式有效解决了混合质量演示问题。
---

## Abstract
We study offline imitation learning (IL) in cooperative multi-agent settings, where demonstrations have unlabeled mixed quality - containing both expert and suboptimal trajectories. Our proposed solution is structured in two stages: trajectory labeling and multi-agent imitation learning, designed jointly to enable effective learning from heterogeneous, unlabeled data. In the first stage, we combine advances in large language models and preference-based reinforcement learning to construct a progressive labeling pipeline that distinguishes expert-quality trajectories. In the second stage, we introduce MisoDICE, a novel multi-agent IL algorithm that leverages these labels to learn robust policies while addressing the computational complexity of large joint state-action spaces. By extending the popular single-agent DICE framework to multi-agent settings with a new value decomposition and mixing architecture, our method yields a convex policy optimization objective and ensures consistency between global and local policies. We evaluate MisoDICE on multiple standard multi-agent RL benchmarks and demonstrate superior performance, especially when expert data is scarce.

---

## 论文详细总结（自动生成）

# 论文《MisoDICE: Multi-Agent Imitation from Unlabeled Mixed-Quality Demonstrations》中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究问题**：离线多智能体模仿学习（Offline Multi-Agent Imitation Learning）中，演示数据通常混合了专家与次优轨迹，且质量标签缺失。现有方法大多假设高质量专家数据充足，难以处理此类异构无标签数据。
- **背景意义**：现实多智能体场景（如星海争霸、多机器人协作）中获取大规模完全专家标注数据代价高昂，而混合质量数据极易获得。本文首次系统解决“未标注混合质量演示下的离线多智能体模仿学习”这一挑战性设定，填补了该领域的空白。

## 2. 方法论：核心思想、关键技术细节
- **整体框架**：两阶段流水线——（1）**轨迹标注阶段**：从无标签混合数据中自动识别专家级轨迹；（2）**多智能体模仿学习阶段**：利用标注结果学习鲁棒策略。
- **阶段一：渐进式轨迹标注**
  - **LLM 初始偏好生成**：从无标签数据中随机采样轨迹对，使用 GPT-4o 根据高层语义（如单位血量、位置、动作）提供偏好标签，得到初始偏好数据集 \( \mathcal{P} \)。
  - **O-MAPL 偏好学习与奖励恢复**：使用离线偏好多智能体 RL 算法 O-MAPL 训练软 Q 函数，然后通过 \( R \approx Q - \gamma V \) 恢复每个状态-动作对的奖励。
  - **轨迹排序与专家筛选**：计算每条轨迹的总回报 \( G(\sigma) = \sum_{(s,a)\in\sigma} R(s,a) \)，降序排列，选择前 \( K \) 条作为专家数据集 \( \mathcal{D}_E \)，其余为次优混合数据集 \( \mathcal{D}_{\text{Mix}} \)。
- **阶段二：MisoDICE 算法**
  - **优化目标**：最小化学习策略与专家分布的 KL 散度，同时加入与混合数据分布的 KL 散度（参数 α 控制）：  
    \[
    \min_{\pi_{\text{tot}}} D_{\text{KL}}(\rho^{\pi_{\text{tot}}} \| \rho^E_{\text{tot}}) + \alpha D_{\text{KL}}(\rho^{\pi_{\text{tot}}} \| \rho^U_{\text{tot}})
    \]
  - **DICE 框架转化**：将上述目标转化为关于占用量度 \( \rho \) 的凸优化，通过拉格朗日对偶得到关于全局值函数 \( \nu_{\text{tot}} \) 和权重 \( w_{\text{tot}} \) 的鞍点问题，并进一步化简为仅关于 \( \nu_{\text{tot}} \) 的闭式非对抗目标。
  - **值分解（Value Factorization）**：采用 **线性混合网络** \( M_\phi \) 将全局值函数分解为局部值函数之和：\( \nu_{\text{tot}}(s) = M_\phi[\{\nu_i(s_i)\}] = \sum_i \phi_i \nu_i(s_i) + \phi_0 \)。**关键理论**：线性混合网络保持目标函数凸性，并保证局部-全局一致性（Proposition 5.1, 5.4）。
  - **占用量比率估计**：通过训练线性分解的判别器（CTDE 框架）估计 \( \rho^E_{\text{tot}} / \rho^U_{\text{tot}} \)，用于计算优势函数。
  - **策略提取**：通过加权行为克隆（Weighted BC）恢复每个智能体的局部策略，权重由学习到的 \( w_{\text{tot}} \) 提供。理论推导给出局部策略的闭式解（Proposition 5.5），形式为软最大化函数。
- **算法流程**（Algorithm 1）：交替训练判别器、值函数和策略网络，均为神经网络，共享参数以提升效率。

## 3. 实验设计
- **数据集与场景**
  - **SMACv1 & SMACv2**：星际争霸多智能体微操挑战，离散动作，团队对战内置 AI。SMACv2 增加随机性和多样性。
  - **MAMuJoCo**：连续控制任务（Hopper, Ant, HalfCheetah），多智能体协作。
  - **数据构造**：从已有 O-MAPL 数据集（含 expert, medium, poor 三个质量级别）中取 200 条 expert 和 1000 条 poor 轨迹混合、打乱，构成无标签混合数据集 \( \mathcal{D}_U \)（共 1200 条）。专家数据集 \( \mathcal{D}_E \) 通过阶段一从 \( \mathcal{D}_U \) 中标注出 top-200 获得。
- **对比基线**
  - **MA-BC**：多智能体行为克隆，调节 β 平衡专家/混合数据权重（β=0.0, 0.5, 1.0）。
  - **OMAPL**：端到端偏好学习基线（仅用阶段一的偏好数据）。
  - **INDD**：独立 DemoDICE（每个智能体独立应用单智能体 DemoDICE）。
  - **MARL-SL**：先通过监督学习从偏好数据学奖励，再用 MARL 优化策略。
  - **MisoDICE-VDN**：消融变体，将 MisoDICE 的可学习混合器替换为简单求和（VDN）。
- **评估指标**：平均回报（Returns）和胜率（Win Rates），均在 4 个随机种子下运行，每评估步 32 个 episode。

## 4. 资源与算力
- **硬件**：单张 NVIDIA H100 NVL Tensor Core GPU。
- **软件**：PyTorch，数据集压缩为 H5 格式。
- **训练轮数**：100 epochs（附录 B.4）。
- **明确性说明**：文中未给出单次训练总时长或 GPU 小时数，仅说明在 H100 上运行。

## 5. 实验数量与充分性
- **实验数量**：主实验涵盖 SMACv2 共 18 个具体场景（分 Protoss, Terran, Zerg 三族，每族 5-6 个地图），SMACv1 有 4 个地图，MAMuJoCo 有 3 个任务。表 1 和表 4-5 展示了主结果。
- **消融研究**：共 8 组：
  1. 专家轨迹数量（top-k，50/200/400/800/1200）。
  2. 超参数 α（0.00 ~ 10.0）。
  3. LLM 能力对比（GPT-4o vs GPT-4o-mini）。
  4. 规则型偏好标注 vs LLM 偏好标注。
  5. 使用真实标签（idealized upper bound）。
  6. 噪声偏好标签（5%~30% 随机翻转）。
  7. 阶段一标签与真实标签的准确率对比（表 16，平均 90.5%）。
  8. 跳过阶段一的影响（“无标注”变体）。
- **充分性评价**：实验设计全面，覆盖了主要变量（数据量、质量、标注方法、超参数、噪声鲁棒性），统计信息充分（均值 ± 标准差），对比基线合理。结论具有很强的可信度。

## 6. 论文的主要结论与发现
- **性能优势**：MisoDICE 在所有 SMACv1/v2 和 MAMuJoCo 任务上均显著优于所有基线，尤其在专家数据稀缺（仅 200 条）时提升幅度最大。
- **标注方法有效**：LLM+O-MAPL 渐进标注能有效分离专家轨迹，准确率达 90.5%；且 top-200 左右可获得最佳性能（过多或过少均下降）。
- **价值分解贡献**：与简单的 VDN 混合器相比，可学习线性混合网络带来一致性能提升，证实了理论凸性带来的稳定训练。
- **超参数 α**：适中 α（0.05）表现最好，过大或过小均会降低性能；但 MisoDICE 对 α 在合理范围内鲁棒。
- **噪声容忍度**：偏好标签噪声升高时性能逐渐下降，但仍优于无标签时的随机混合学习。

## 7. 优点
- **问题新颖性**：首次系统解决离线多智能体模仿学习中“未标注混合质量演示”这一现实难题。
- **方法完整性**：两阶段设计——标注与学习互为支撑，LLM 提供初始语义偏好后，O-MAPL 进行精细奖励恢复和排序，构成闭环。
- **理论保障**：严格证明线性混合网络下目标函数的凸性、全局-局部策略一致性，以及局部策略的闭式软最大化形式，为算法稳定性和可解释性提供基础。
- **实验严谨性**：大量消融实验（8 类），包括 LLM 消融、噪声分析、真实标签理想情况等，全面验证了各部分贡献。
- **实际可操作性**：CTDE 架构下网络共享，适合扩展至更多智能体；代码和数据已公开，可复现。

## 8. 不足与局限
- **环境局限**：方法仅在完全合作场景下验证，未扩展至竞争或混合动机环境（如零和博弈）。
- **LLM 依赖**：阶段一使用 LLM（GPT-4o）生成偏好，在缺乏明确抽象语义的环境（如 MAMuJoCo）中 LLM 难以提供有意义反馈，需回退到规则方法（文中已注明）。
- **实验覆盖偏差**：主要评估在 SMAC 系列（离散动作），MAMuJoCo 实验较少（仅 3 个任务），且 MAMuJoCo 中采用规则偏好而非 LLM，可能低估框架在连续控制上的潜力。
- **算力细节缺失**：未报告训练需要的具体 GPU 小时数，不利于其他研究者估算复现成本。
- **超参数敏感性**：尽管 α 鲁棒，但 top-k 的选择对性能有显著影响（最佳值 200），在实际应用中可能需要调参或依赖启发式规则。

（完）
