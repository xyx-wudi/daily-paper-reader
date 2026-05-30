---
title: Role-aware Multi-agent Reinforcement Learning for Coordinated Emergency Traffic Control
title_zh: 面向协调应急交通控制的角色感知多智能体强化学习
authors: "Ming Cheng, Hao Chen, Zhiqing Li, Jia Wang, Senzhang Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=R3xbcRIzUd"
tags: ["query:marl"]
score: 8.0
evidence: 基于角色感知的多智能体强化学习应急交通控制
tldr: 该论文提出角色感知多智能体交通控制（RMTC）框架，用于应急交通场景中的协调。通过异构时序交通图（HTTG）动态分配角色，考虑各交通组件与应急车辆的关系，自适应调整策略。实验表明，RMTC能有效提升应急通行效率，是多智能体强化学习在交通控制中的成功应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-r3xbcrizud/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1399, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r3xbcrizud/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r3xbcrizud/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r3xbcrizud/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 658, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r3xbcrizud/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 622, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r3xbcrizud/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 992, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-r3xbcrizud/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1114, \"height\": 785, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-r3xbcrizud/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1384, \"height\": 640, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-r3xbcrizud/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1050, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-r3xbcrizud/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1128, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-r3xbcrizud/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1171, \"height\": 496, \"label\": \"Table\"}]"
motivation: 现有模型仅关注交通灯控制，缺乏对紧急车辆和普通车辆的导航策略，导致延误。
method: 提出RMTC框架，通过异构时序交通图动态分配角色，自适应调整策略。
result: 在应急交通场景中实现了更好的协调和通行效率。
conclusion: 展示了角色感知在多智能体交通控制中的有效性。
---

## Abstract
Emergency traffic control presents an increasingly critical challenge, requiring seamless coordination among emergency vehicles, regular vehicles, and traffic lights to ensure efficient passage for all vehicles. Existing models primarily only focus on traffic light control, leaving emergency and regular vehicles prone to delay due to the lack of navigation strategies. To address this issue, we propose the ***R*ole-aware *M*ulti-agent *T*raffic *C*ontrol (RMTC)** framework, which dynamically assigns appropriate roles to traffic components for better cooperation by considering their relations with emergency vehicles and adaptively adjusting their policies. Specifically, RMTC introduces a *Heterogeneous Temporal Traffic Graph (HTTG)* to model the spatial and temporal relationships among all traffic components (traffic lights, regular and emergency vehicles) at each time step. Furthermore, we develop a *Dynamic Role Learning* model to infer the evolving roles of traffic lights and regular vehicles based on HTTG. Finally, we present a *Role-aware Multi-agent Reinforcement Learning* approach that learns traffic policies conditioned on the dynamically roles. Extensive experiments across four public traffic scenarios show that RMTC outperforms existing traffic light control methods by significantly reducing emergency vehicle travel time, while effectively preserving traffic efficiency for regular vehicles. The code is released at [https://github.com/mingchenghexi/RMTC](https://github.com/mingchenghexi/RMTC).

---

## 论文详细总结（自动生成）

### 论文总结：Role-aware Multi-agent Reinforcement Learning for Coordinated Emergency Traffic Control (RMTC)

#### 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：应急车辆（EMV，如消防车、救护车）的快速通行在紧急事件中至关重要，但现有交通控制方法大多只关注交通灯调度，忽略了与普通车辆（REV）导航的协同，导致EMV和REV均可能因缺乏协调而延误。
- **核心问题**：如何实现交通灯、EMV和REV三类交通组件的联合、动态协同控制，在保障EMV优先通行的同时，维持整体交通效率（即“跷跷板问题”）。
- **整体含义**：该研究可集成到导航软件（如Google Maps、高德地图）中，在实际场景中帮助节省财产和生命，具有显著的社会价值。

#### 2. 方法论：核心思想与关键技术细节

- **核心思想**：通过动态角色分配实现组件间的自适应协同。构建异构时序交通图（HTTG）建模组件间的时空关系，利用动态角色学习推断各组件（交通灯、REV）随时间演变的角色，并基于角色设计状态表示与奖励，驱动多智能体强化学习（MARL）训练。
- **关键技术细节**：
  - **HTTG构建**：节点集包含所有EMV、REV和交通灯；边集包括四种关系：TL-REV（交通灯-普通车辆）、TL-EMV（交通灯-应急车辆）、TL-TL（相邻交通灯）、EMV-REV（基于观测相似度的余弦相似度>阈值δ的边）。利用异构图卷积（Heterogeneous Role Convolution）更新节点特征。
  - **动态角色学习（Dynamic Role Learning）**：包含三个损失项：
    - **EMV位置角色影响**：最大化每个智能体角色嵌入与EMV特征之间的互信息下界（式5）。
    - **EMV轨迹角色影响**：最大化角色嵌入与EMV历史轨迹（经GRU编码）之间的互信息下界（式6）。
    - **角色一致性约束**：通过对比学习使相邻时间步的角色嵌入更接近，防止突变（式8）。
    整体损失：`L_role = Σ_t [ -I(h; h_emv) - I(h; g_emv) + L_cons ]`。
  - **角色感知多智能体RL**：
    - **策略设计**：智能体状态 = 环境观测 o(t) 拼接角色嵌入 h(t)，输入Actor网络产生动作分布 `π(a|o,h)`。
    - **角色感知内在奖励**：对每个非EMV智能体，计算其角色与EMV角色特征的余弦相似度，选出top-k，用相似度加权EMV的外部奖励作为内在奖励 `r_intr = Σ_i s(h_n, h_emv,i) * r_emv,i,extr`。总奖励 = `r_extr + λ * r_intr`。
    - **多智能体优化**：采用PPO算法，同类型智能体（如所有REV、所有交通灯）共享策略网络参数以提升可扩展性。优势函数A(t)同时包含外部奖励和内在奖励。

#### 3. 实验设计

- **数据集**：四个公开交通场景：
  - 合成场景：Grid 4×4（16个四臂路口）、Avenue 4×4（16个四臂路口）
  - 真实场景：Cologne8（德国科隆区域，8个路口，含二/三/四臂）、FengLin（中国枫林走廊，7个路口）
- **评测指标**：EMV平均旅行时间（T_emv）、REV平均旅行时间（T_rev）
- **对比方法**：
  - 规则方法：Fixed-Time (FT)、MaxPressure (MP)
  - RL方法：CoLight、IPPO、rMAPPO、X-Light、RECAL、EMVlight
  - 所有基线均采用标准的EMV信号预抢占（绿色波浪）策略以公平比较。
- **实验设置**：使用SUMO交通模拟器，每个交叉口配置8个信号相位。模拟不同交通密度（车辆生成率1~3辆/秒）和EMV数量（1~5辆）。

#### 4. 资源与算力

- 所有实验在**单张NVIDIA GeForce RTX 3090 GPU（24GB内存）**上完成。
- 使用Adam优化器，学习率0.0005，隐藏层维度64，PPO clip参数0.2，GAE lambda 0.95。
- 训练时间随网络规模增长呈线性：8个信号路口约122秒/episode，16个约161秒，25个约240秒；推理时间约0.028~0.051秒/步，满足实时性要求。

#### 5. 实验数量与充分性

- **主实验**：在4个数据集上与8种基线对比，报告了EMV和REV旅行时间（表1）。结果均标注了统计显著性（p<0.05或p<0.01）。
- **消融实验**（图3）：在Grid 4×4上移除四个关键组件（EMV位置影响、EMV轨迹影响、一致性约束、内在奖励），验证每个组件的必要性。
- **不同交通流实验**（图4）：在Grid 4×4上变化车辆生成率1~3辆/秒，与FT对比，显示RMTC稳定性。
- **不同EMV数量实验**（表2）：EMV数量1~5，与IPPO、rMAPPO对比，验证可扩展性和鲁棒性。
- **超参数分析**（图5）：对交通灯智能体的奖励平衡系数λ（0.001~0.1）进行敏感性分析，确定最优值0.01。
- **案例研究**（图6）：可视化科隆数据集上EMV和REV轨迹，展示角色机制的实际效果。
- **效率分析**（表4）：比较不同信号路口规模下有无GNN和MI组件的训练/推理时间和奖励。
- **总体评价**：实验覆盖多个场景、多种基线、充分的消融和敏感性分析，设计严谨客观，公平性良好（所有基线均采用绿色波浪机制适应应急场景）。

#### 6. 主要结论与发现

- RMTC在所有数据集上**显著优于**所有基线：EMV旅行时间降低4%~23.5%，REV旅行时间降低4%~7.8%，表明在优先EMV的同时不会明显牺牲普通交通效率。
- 消融实验证实：**EMV位置影响、轨迹影响、角色一致性约束、内在奖励**四个组件均对性能有重要贡献，移除任一个都会导致T_emv和T_rev恶化。
- 在不同交通流密度下，RMTC始终保持较低的旅行时间，且随密度增加性能不显著下降，表明其**适应性强**。
- 随着EMV数量增加（1→5），RMTC的REV旅行时间保持稳定，而基线急剧上升，说明其**多EMV协调能力**优越。
- 角色嵌入使得靠近EMV的智能体主动让行，远离的智能体保持正常行为，实现了**精细化协同**。

#### 7. 优点

- **创新性**：首次将动态角色学习引入多智能体交通控制，通过异构时序图建模不同组件间的复杂关系，并设计互信息最大化来捕获EMV的位置和轨迹影响。
- **全面性**：同时控制交通灯、EMV和REV，解决了“跷跷板问题”，实验证明在EMV优先和总体效率之间取得良好平衡。
- **可扩展性**：共享策略网络设计、近线性训练时间增长，使其能扩展到更大路网。
- **鲁棒性**：在不同交通密度和EMV数量下表现稳定，消融和敏感性分析充分验证了各部分的有效性。

#### 8. 不足与局限

- **依赖应急事件**：角色感知协调机制仅在EMV出现时激活，若没有应急场景则无额外收益。
- **理想化假设**：假定所有车辆严格遵守导航路线，实际中驾驶员可能因个人偏好或外部约束偏离推荐路径，削弱协调效果。
- **实验覆盖**：虽然使用了四个场景（含真实数据），但真实场景仅涉及德国和中国的两个区域，缺乏更多元化的真实路网验证。
- **偏差风险**：合成场景（Grid、Avenue）结构规则，可能高估方法在非规则路网上的泛化性。作者在科隆数据上包含了非四臂路口，但整体数据量有限。
- **计算开销**：HTTG的构建和图卷积增加了训练时间（相比无GNN变体慢约35%），尽管推理速度仍可行，但在超大规模路网（如上百个路口）上的可扩展性尚未充分验证。

（完）
