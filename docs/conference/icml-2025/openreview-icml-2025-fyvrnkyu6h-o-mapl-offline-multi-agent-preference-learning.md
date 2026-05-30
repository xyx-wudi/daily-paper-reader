---
title: "O-MAPL: Offline Multi-agent Preference Learning"
title_zh: "O-MAPL: 离线多智能体偏好学习"
authors: "The Viet Bui, Tien Anh Mai, Thanh Hong Nguyen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=FYvrNKYu6H"
tags: ["query:marl"]
score: 9.0
evidence: 离线多智能体偏好学习用于合作MARL
tldr: 针对多智能体强化学习中从人类偏好推断奖励函数的两阶段训练不稳定问题，本文提出O-MAPL，利用合作MARL中奖励函数与Q函数的内在联系，设计端到端偏好学习方法。在多个合作任务上，O-MAPL显著优于基线，训练更稳定，为多智能体偏好学习提供高效方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1502, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 905, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 975, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1170, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1407, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1160, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1405, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1169, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1403, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1158, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1410, \"height\": 681, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 908, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1781, \"height\": 1052, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1237, \"height\": 1054, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1176, \"height\": 1023, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1607, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1188, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1277, \"height\": 823, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1271, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1357, \"height\": 828, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1192, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1279, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1267, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1357, \"height\": 831, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1779, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1778, \"height\": 719, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1607, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1167, \"height\": 972, \"label\": \"Table\"}]"
motivation: 多智能体强化学习中奖励推断的两阶段训练不稳定，需要端到端方法。
method: 利用合作MARL中奖励函数与Q函数的联系，提出端到端偏好学习框架。
result: 在多个合作任务上优于现有基线，训练更稳定。
conclusion: O-MAPL为多智能体偏好学习提供稳定高效的解决方案。
---

## Abstract
Inferring reward functions from demonstrations is a key challenge in reinforcement learning (RL), particularly in multi-agent RL (MARL). The large joint state-action spaces and intricate inter-agent interactions in MARL make inferring the joint reward function especially challenging. While prior studies in single-agent settings have explored ways to recover reward functions and expert policies from human preference feedback, such studies in MARL remain limited. Existing methods typically combine two separate stages, supervised reward learning, and standard MARL algorithms, leading to unstable training processes. In this work, we exploit the inherent connection between reward functions and Q functions in cooperative MARL to introduce a novel end-to-end preference-based learning framework.
Our framework is supported by a carefully designed multi-agent value decomposition strategy that enhances training efficiency. Extensive experiments on two state-of-the-art benchmarks, SMAC and MAMuJoCo, using preference data generated by both rule-based and large language model approaches demonstrate that our algorithm consistently outperforms existing methods across various tasks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在多智能体强化学习（MARL）中，从人类偏好数据推断奖励函数是提升训练效率与效果的关键，但现有方法通常采用“两阶段”流程——先通过监督学习训练奖励模型，再通过标准 MARL 算法优化策略。这种分离式方法存在两大弊端：
  1. 需要大量偏好数据覆盖巨大的联合状态-动作空间；
  2. 两阶段之间可能出现不一致，导致策略质量下降与训练不稳定。
- **整体含义**：本文旨在设计一种**端到端**的多智能体偏好学习（PbRL）方法，直接从轨迹偏好数据中学习策略，而不显式建模奖励函数。该方法利用最大熵强化学习中奖励函数与软 Q 函数之间的一一对应关系，将奖励学习转化为 Q 学习问题，简化流程、提升稳定性，并适用于离线设置。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：基于最大熵 RL 框架，利用逆软贝尔曼算子 `T*Q = r`（即奖励可由 Q 函数唯一表示），将偏好数据的似然最大化目标从奖励空间转换到 Q 空间。通过 Bradley-Terry 模型定义偏好概率：
  ```
  P(σ1 ≻ σ2 | Q) = exp(Σ_{(s,a)∈σ1} (T*Q)(s,a)) / (exp(...) + exp(...))
  ```
  从而直接学习全局 Q 函数，再通过软策略公式 `π(a|s) ∝ μ(a|s) exp((Q - V)/β)` 提取最优策略，避免显式奖励建模。

- **关键技术细节**：
  1. **价值分解（Value Factorization）**：在集中训练分散执行（CTDE）范式下，引入线性混合网络 `M_w`，将局部 Q 函数 `q_i` 和局部 V 函数 `v_i` 组合为全局 Q 和 V，即 `Q_tot = M_w[q], V_tot = M_w[v]`。线性混合网络确保了偏好损失函数的凹性和极值 V 损失的凸性，保证稳定收敛。
  2. **极值 Q 学习（Extreme Q-Learning）**：高效更新 V 函数，避免离散 action 空间的求和计算。
  3. **局部策略提取**：提出**加权行为克隆（WBC）** 方法，通过最大化 `E[exp((Q - V)/β) log π_i]` 来优化每个智能体的局部策略。该方法满足全局-局部一致性（GLC），即使使用非线性混合结构也能保证局部策略的有效性。

- **算法流程**（文字描述）：
  1. 输入：离线偏好数据集 P、参数 θ、ψ_q、ψ_v、ω_i。
  2. 循环训练：
     - 更新 Q 参数 ψ_q 和混合网络参数 θ，以最大化偏好似然损失 L(ψ_q, ψ_v, θ)。
     - 更新 V 参数 ψ_v，以最小化极值 V 损失 J(ψ_v)。
     - 更新局部策略网络参数 ω_i，以最大化 WBC 损失 Ψ(ω_i)。
  3. 输出：每个智能体的局部策略 π_i(ai|oi; ω_i)。

## 3. 实验设计：数据集、基准、对比方法

- **数据集与场景**：
  - 离散动作环境：**SMACv1**（4个任务：2c vs 64zg, 5m vs 6m, 6h vs 8z, corridor）和 **SMACv2**（15个任务，分 Protoss/Terran/Zerg 三个种族，任务难度从 5 vs 5 到 20 vs 23）。
  - 连续动作环境：**MAMuJoCo**（3个任务：Hopper-v2, Ant-v2, HalfCheetah-v2）。
  - 偏好数据生成方式：**基于规则**（按数据集质量分配标签）和 **基于大语言模型（LLM）**（使用 GPT-4o 根据轨迹最终状态信息标注偏好）。
  - 数据规模：SMAC 各任务 2000 个轨迹对，MAMuJoCo 各任务 1000 个轨迹对。

- **基准对比方法**：
  - BC（行为克隆）
  - IIPL（独立 IPL，单智能体扩展）
  - IPL-VDN（用 VDN 聚合局部 Q 和 V）
  - SL-MARL（两阶段方法：先学奖励再用 OMIGA 训练策略）

- **实验充分性**：
  - 总共在 **22个任务**（4 + 15 + 3）上进行了评估，每个任务多次运行取平均和标准差。
  - 额外进行了消融实验：**数据保留量实验**（25%, 50%, 75%, 100%）、**1层 vs 2层混合网络对比**、**GPT-4o vs GPT-4o-mini 质量对比**。
  - 实验设计全面，包含不同复杂度、不同偏好来源的对比，结果客观公平。

## 4. 资源与算力

- 文中声明：所有实验使用 **PyTorch** 实现，并在 **单张 NVIDIA H100 NVL Tensor Core GPU** 上并行运行。
- 未明确说明训练时长，但提到使用了 OpenAI Batch API 进行 LLM 标注，总费用约 42 美元，属于合理范围。

## 5. 实验数量与充分性

- **实验数量**：主实验涵盖 22 个任务，另有 3 组消融实验（数据保留、混合网络层数、LLM 版本）。
- **充分性**：实验覆盖了离散和连续动作空间、不同难度的合作任务、两种偏好数据生成方式，并与四个代表性基线进行了公平比较。消融实验验证了关键设计选择（如线性混合网络、高质量 LLM 数据）的有效性。结论可靠。

## 6. 论文的主要结论与发现

- **核心结论**：O-MAPL 在所有测试任务上均显著优于现有基线方法，实现了更高的胜率（SMAC）和累积回报（MAMuJoCo）。
- **发现**：
  - 端到端学习避免了显式奖励建模带来的不稳定性和误差传播，训练更稳定、收敛更快。
  - 线性混合网络（1层）比非线性混合网络（2层）在离线偏好学习中效果更好，且满足凸性保证。
  - LLM 生成的偏好数据（GPT-4o）优于基于规则的标签，且高质量 LLM（4o）比低质量版本（4o-mini）带来更好性能，说明偏好质量对最终策略有显著影响。
- **理论贡献**：证明了偏好损失函数在 q 和 w 上凹、极值 V 损失在 v 上凸（线性混合网络下），以及局部 WBC 策略的全局-局部一致性。

## 7. 优点

- **方法层面**：
  - 首次将端到端偏好学习成功应用于多智能体离线 RL，绕过显式奖励建模。
  - 提出简洁有效的价值分解和加权 WBC 提取策略，理论性质良好（凸性、GLC）。
  - 兼容 CTDE 范式，适合实际部署。
- **实验层面**：
  - 跨多个基准（SMACv1/v2、MAMuJoCo）进行验证，涵盖离散/连续动作空间。
  - 考虑两种偏好数据来源，并证明 LLM 可大幅降低人工标注成本。
  - 消融实验充分，验证了关键组件的必要性。

## 8. 不足与局限

- **实验覆盖局限**：
  - 仅考虑完全合作式 MARL，未涉及混合合作-竞争或纯竞争场景。
  - 偏好数据量仍较庞大（1k～2k 对），在需要真实人类反馈时数据获取成本仍然较高。
  - MAMuJoCo 无法使用 LLM 生成偏好，因为状态信息不便于构建有效提示。
- **方法局限**：
  - 线性混合网络虽然带来了凸性优势，但可能限制表达力，在更复杂的环境中未必最优。
  - 部分任务（如 SMACv1 的 5m vs 6m、6h vs 8z）整体胜率很低（<20%），说明方法在面对极端困难场景时仍有改进空间。
- **偏差风险**：
  - LLM 标注可能引入固有偏见，文中未量化这种偏差的影响。
- **应用限制**：目前仅适用于可以获取轨迹级偏好数据的环境，且需要行为策略的分解假设。

（完）
