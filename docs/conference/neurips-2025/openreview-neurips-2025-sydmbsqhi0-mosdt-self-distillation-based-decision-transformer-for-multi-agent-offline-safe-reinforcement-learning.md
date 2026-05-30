---
title: "MOSDT: Self-Distillation-Based Decision Transformer for Multi-Agent Offline Safe Reinforcement Learning"
title_zh: MOSDT：基于自蒸馏的多智能体离线安全强化学习决策Transformer
authors: "Yuchen Xia, Yunjian Xu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SYDmbsqHI0"
tags: ["query:marl"]
score: 9.0
evidence: 多智能体离线安全强化学习，决策Transformer
tldr: 本文首次提出针对多智能体离线安全强化学习（MOSRL）的算法MOSDT。采用策略自蒸馏（PSD）和全局信息重建，结合参数共享，大幅提升效率。在自建基准MOSDB上，MOSDT在保证安全约束的同时，回报提升最高达38.4倍，为多智能体离线安全学习提供了有效方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sydmbsqhi0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 591, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sydmbsqhi0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 766, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sydmbsqhi0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sydmbsqhi0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sydmbsqhi0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1385, \"height\": 2017, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sydmbsqhi0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1389, \"height\": 2022, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sydmbsqhi0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1387, \"height\": 461, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 658, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 707, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 688, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 747, \"height\": 900, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 903, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1458, \"height\": 1074, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1320, \"height\": 889, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1334, \"height\": 1020, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1392, \"height\": 823, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1388, \"height\": 968, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1453, \"height\": 1089, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1456, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1458, \"height\": 800, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sydmbsqhi0/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1458, \"height\": 811, \"label\": \"Table\"}]"
motivation: 多智能体离线安全强化学习尚无专用算法和基准。
method: 提出策略自蒸馏和全局信息重建，结合参数共享和成本二值嵌入模块。
result: 在MOSDB基准上，MOSDT在安全约束下显著提升回报，且参数效率高。
conclusion: MOSDT填补了多智能体离线安全RL的空白，展示了结合蒸馏和Transformer的潜力。
---

## Abstract
We introduce MOSDT, the first algorithm designed for multi-agent offline safe reinforcement learning (MOSRL), alongside MOSDB, the first dataset and benchmark for this domain. Different from most existing knowledge distillation-based multi-agent RL methods, we propose policy self-distillation (PSD) with a new global information reconstruction scheme by fusing the observation features of all agents, streamlining training and improving parameter efficiency. We adopt full parameter sharing across agents, significantly slashing parameter count and boosting returns up to 38.4-fold by stabilizing training. We propose a new plug-and-play cost binary embedding (CBE) module, which binarizes cumulative costs as safety signals and embeds the signals into return features for efficient information aggregation. On the strong MOSDB benchmark, MOSDT achieves state-of-the-art (SOTA) returns in 14 out of 18 tasks (across all base environments including MuJoCo, Safety Gym, and Isaac Gym) while ensuring complete safety, with only 65% of the execution parameter count of a SOTA single-agent offline safe RL method CDT. Code, dataset, and results are available at this website: https://github.com/Lucian1115/MOSDT.git

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- 多智能体离线安全强化学习（Multi-Agent Offline Safe Reinforcement Learning, MOSRL）结合了多智能体协作、离线学习与安全约束三大挑战，但此前既无专用算法也无专用数据集和基准。
- 现有的离线RL方法（如Decision Transformer CDT）和离线MARL方法（如知识蒸馏MADTKD）无法直接适配MOSRL：前者缺乏多智能体框架，后者忽略安全约束且训练效率低（两阶段蒸馏）。
- 本文首次提出MOSRL算法MOSDT，并构建首个MOSRL数据集与基准MOSDB，填补了该领域的空白。

## 2. 论文提出的方法论

### 核心思想
采用决策Transformer（DT）作为基础网络，通过策略自蒸馏（Policy Self-Distillation, PSD）实现集中训练与去中心化执行（CTDE），并引入全参数共享与成本二值嵌入模块优化训练稳定性和安全信号处理。

### 关键技术细节

1. **策略自蒸馏（PSD）**：
   - 将学生网络集成到教师网络中，实现教师-学生策略一体化，无需两阶段蒸馏。
   - 提出全局信息重建方案：所有智能体的观察特征经学生编码后求和得到全局特征，教师网络基于全局特征进行集中训练。
   - 同步进行三种损失优化：学生监督损失（DSSL）、教师监督损失（CTSL）和策略蒸馏损失（PSD，包含KL散度与特征距离）。
   - 相比传统知识蒸馏，减少35%训练参数和24%训练时间。

2. **全参数共享**：
   - 所有智能体的学生网络共享完全相同参数，仅教师动作头和特征投影头保持独立。
   - 显著稳定训练（避免多智能体动态策略改进导致的波动），在3个及以上智能体任务中回报提升10.1~38.4倍。
   - 减少47%训练参数和58%执行参数，提升可扩展性。

3. **成本二值嵌入（Cost Binary Embedding, CBE）**：
   - 成本二值化：将累积成本按阈值映射为安全信号（0表示安全，1表示不安全），避免实际成本收敛到预定目标。
   - 安全信号嵌入：将二值化的安全信号特征与回报特征拼接，使因果Transformer能同时感知回报-成本相关性，克服注意力掩码导致的信息遗漏。
   - 即插即用模块，不增加额外参数，提升14/18个任务的回报。

### 算法流程（文字描述）

训练过程：
- 从离线数据集中采样轨迹，对每个智能体生成学生特征和动作预测，计算DSSL损失。
- 将所有学生特征按式(2)求和得到全局特征，通过教师网络生成动作预测，计算CTSL损失。
- 计算PSD损失（学生输出与教师输出的KL散度 + 特征欧氏距离）。
- 最小化总损失（三个损失之和）更新学生网络（全参数共享）和教师网络（独立部分）。

执行过程：
- 每个智能体的学生网络基于局部观测序列（含回报和安全信号）预测动作，无需通信。

## 3. 实验设计

### 数据集与场景
- **MOSDB数据集**：首个MOSRL数据集，收集自Safety Gymnasium的所有18个安全MARL任务（排除“Goal 0”系列零成本任务），使用MACPO和MAPPO-Lagrangian两种在线算法，在3种成本阈值（25、15、5）下训练，经密度过滤得到约2×10⁷个数据元组（18.7 GB）。
- **基准任务集**：
  - MOS Velocity（MuJoCo）：速度控制任务，多智能体协作控制身体部位。
  - MOS Goal（Safety Gym）：多智能体导航至目标，避免碰撞和危险地形。
  - MOS Isaac Gym：协作机器人任务（如机械臂交接球等），施加关节运动安全约束。

### 对比方法
- BC、BC-Safe（行为克隆）
- BCQ-Lag、BEAR-Lag（基于Q学习+拉格朗日）
- CDT（决策Transformer基线）
- COptiDICE、CPQ（约束离线RL方法）
- 所有基线均在集中训练集中执行（CTCE）框架下训练，可访问全局信息。
- 实验设置：训练10⁵步，每步评估10个episode，重复3个随机种子，报告最高安全回报。

## 4. 资源与算力

- 硬件：单块NVIDIA GeForce RTX 4090 D GPU（24 GB VRAM）+ AMD Ryzen 9 7950X CPU。
- 训练时长：未明确总时长，但给出每个训练步平均13.18 ms，每个推理0.80 ms/agent。
- 参数规模：MOSDT平均执行参数0.465M，仅为CDT（0.722M）的65%。

## 5. 实验数量与充分性

- **主实验**：18个任务上对比6种基线，给出回报和累积成本，并报告标准差（附录B.6）。
- **消融实验**：针对PSD、全参数共享、CBE三个核心组件逐一移除实验；还进行了部分参数共享（逐组件移除）、特征分离、动作/特征蒸馏分离等补充消融（附录B.3-B.5）。
- **效率分析**：参数计数和训练/推理时间对比（附录B.2）。
- **训练曲线**：在线提供可视化（链接在摘要）。
- **充分性评价**：实验设计全面，覆盖多种环境、多智能体数量（2~9个），消融覆盖每种设计选择，结果客观，有标准差，公平比较（所有基线按DSRL设置）。

## 6. 论文的主要结论与发现

- MOSDT在14/18个任务上取得安全最优回报，且在所有任务上保持完全安全（累积成本不超过阈值）。
- 在多智能体任务（3个以上）上表现尤为突出：3x1Hopper回报1122.23（对比基线最高121.58），4x2Ant回报2083.85（对比最高923.72），6x1HalfCheetah回报1853.64（对比最高447.13）。
- 全参数共享使训练稳定，回报提升最高38.4倍。
- CBE提升14/18个任务回报，且不增加参数。
- PSD对保证安全至关重要（移除后12个任务不安全）。

## 7. 优点

1. **开创性**：首个MOSRL算法与基准，填补领域空白。
2. **创新性**：PSD将自蒸馏引入MARL，简化训练；全参数共享首次用于离线MARL且效果显著；CBE提供新颖的安全信号处理。
3. **高效性**：执行参数仅为CDT的65%，推理速度更快，适合资源受限场景。
4. **鲁棒性**：在18个任务上全面SOTA，消融验证每个组件贡献。
5. **可复现性**：代码、数据集、结果全部开源。

## 8. 不足与局限

1. **成本二值化灵活性**：CBE将成本二值化为固定阈值信号，可能限制模型对动态成本阈值的适应性（但作者指出许多应用有固定阈值）。
2. **潜在负面应用**：MOSRL可能被用于无人机监控等负面场景，但作者检查MOSDB未发现高风险数据。
3. **数据集规模**：目前MOSDB仅包含18个任务，未来需扩展更多环境和任务。
4. **对比方法局限性**：基线均为单智能体方法在CTCE下训练，缺乏真正多智能体离线安全RL方法直接比较（因该领域此前无方法）。
5. **未提供总训练时长**：仅给出每步时间，未说明完整实验的GPU耗时。

（完）
