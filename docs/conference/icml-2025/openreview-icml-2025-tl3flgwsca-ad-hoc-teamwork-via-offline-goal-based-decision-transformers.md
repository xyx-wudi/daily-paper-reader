---
title: Ad Hoc Teamwork via Offline Goal-Based Decision Transformers
title_zh: 基于离线目标决策变换器的临时团队合作
authors: "Xinzhi Zhang, Hohei Chan, Deheng Ye, Yi Cai, Mengchen Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tl3FlgWScA"
tags: ["query:marl"]
score: 7.0
evidence: 离线目标决策变换器的临时团队合作，协作多智能体
tldr: 临时团队合作（AHT）需要在线交互与精心设计的队友，这在实际中不可行。本文将AHT扩展到离线场景，提出TAGET层次化序列建模框架，动态预测考虑队友的奖励-待完成量，解决离线数据有限、部分可观测和在线适应问题。实验证明了其有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1685, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1773, \"height\": 970, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1765, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1775, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tl3flgwsca/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1396, \"height\": 870, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1629, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 914, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 981, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1752, \"height\": 905, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tl3flgwsca/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 570, \"label\": \"Table\"}]"
motivation: 现有AHT要求在线交互与设计队友，实际难以满足。
method: 提出TAGET框架，利用层次化序列建模从离线数据集学习队友感知的奖励预测。
result: 在离线AHT场景中显著优于基线。
conclusion: 离线序列建模可有效解决临时团队合作中的关键挑战。
---

## Abstract
The ability of agents to collaborate with previously unknown teammates on the fly, known as ad hoc teamwork (AHT), is crucial in many real-world applications. Existing approaches to AHT require online interactions with the environment and some carefully designed teammates. However, these prerequisites can be infeasible in practice. In this work, we extend the AHT problem to the offline setting, where the policy of the ego agent is directly learned from a multi-agent interaction dataset. We propose a hierarchical sequence modeling framework called TAGET that addresses critical challenges in the offline setting, including limited data, partial observability and online adaptation. The core idea of TAGET is to dynamically predict teammate-aware rewards-to-go and sub-goals, so that the ego agent can adapt to the changes of teammates’ behaviors in real time. Extensive experimental results show that TAGET significantly outperforms existing solutions to AHT in the offline setting.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：临时团队合作（Ad Hoc Teamwork, AHT）要求智能体在无事先协调的情况下与未知队友实时协作，但现有方法普遍依赖在线环境交互和精心设计的队友策略库，这在实际场景（如救援机器人、自动驾驶）中往往不可行——环境模拟器昂贵或不可用，且队友策略空间巨大难以穷举。
- **研究动机**：探索“离线 AHT”问题——即仅从预先收集的多智能体交互数据集中直接学习自我智能体（ego agent）的策略，避免在线交互。该设置面临三大挑战：①离线数据覆盖有限，难以泛化到多样队友行为；②部分可观测环境下精确建模队友更加困难；③传统序列建模方法（如决策变换器 DT）依赖固定的回报-待完成量（RTG）信号，无法捕捉队友意图的动态变化。
- **整体含义**：本文首次将 AHT 问题系统性地拓展到离线设置，并提出有效解决方案，为实际场景下无需模拟器的合作决策提供了新的范式。

## 2. 论文提出的方法论
### 核心思想
- 提出层次化序列建模框架 **TAGET**（Teammate-Aware Goal driven hierErarchical Decision Transformers），通过动态预测“队友感知的回报-待完成量（TA-RTG）”和“队友感知的子目标（TA-Goal）”，使自我智能体能实时适应队友行为变化。

### 关键技术细节
1. **离线数据预处理**：采用“轨迹镜像策略”（trajectory mirroring），将每条多智能体轨迹中的每个智能体轮流视作自我智能体，生成多条镜像轨迹，从而极大提升有限数据的利用效率（公式 3）。
2. **高模块：队友感知的目标预测**
   - 设计两个编码器：**团队上下文编码器**（用全局观测编码团队变量 \(h_t\)）和**代理编码器**（仅用局部观测编码近似变量 \(z_t\)），通过 KL 散度正则化（公式 6）强制两者对齐，使自我智能体在部分可观测下仍能推断团队状态。
   - **TA-RTG 预测器**：以团队上下文 \(h_t\) 为输入，预测未来剩余回报 \(\hat{R}_t\)，通过 MSE 损失（公式 7）训练。
   - **TA-Goal 解码器**：以 \(h_t\) 和 \(\hat{R}_t\) 为输入，预测未来 \(k\) 步后的全局状态（拼接所有智能体的离散化观测），作为高模块子目标，通过交叉熵损失（公式 8）训练。
3. **低模块：目标条件化的动作生成**
   - 使用基于因果 Transformer 的决策变换器，输入序列为过去 \(K\) 步的 TA-Goal、局部观测、动作，输出当前动作。将传统 RTG 替换为 TA-Goal 作为引导信号（公式 10, 11）。

### 算法流程（文字说明）
- **训练阶段**（算法 2）：从处理后的离线数据集采样轨迹 → 计算团队上下文和代理编码 → 预测 TA-RTG → 解码 TA-Goal → 用目标条件化 DT 预测动作 → 联合优化高、低模块损失（公式 9 + 公式 11）。
- **测试阶段**（算法 3）：在线接收局部观测 → 通过代理编码器提取 \(z_t\) → 预测 TA-RTG 和 TA-Goal → 更新序列 → DT 生成动作。

## 3. 实验设计
- **环境/场景**：三个经典多智能体协作环境
  - **Predator-Prey (PP)**：10×10 网格，2 个捕食者需配合捕捉随机移动的 4 个猎物。
  - **Level-Based Foraging (LBF)**：20×20 网格，2 个智能体需协同采集等级匹配的食物。
  - **Overcooked**：厨房布局，2 个智能体需合作完成烹饪和送餐（采用“Surrounding”布局，强制角色分工）。
- **数据集收集**：使用 CSP 中的 SVD 方法训练 4 个策略群体，每个群体含 3 个检查点。随机选取 1 个群体作为测试队友集（含 8 个检查点），其余 3 个用于收集离线轨迹。确保测试队友从未在训练中出现。
- **对比基线**：6 种方法
  - DT (Decision Transformer)
  - Prompt-DT
  - ODITS-off（在线 AHT 方法 ODITS 的离线变体）
  - LIAM-off（在线 AHT 方法 LIAM 的离线变体）
  - CQL（Conservative Q-Learning）
  - MADT（Multi-Agent Decision Transformer）
- **评估指标**：每个测试队友集上运行 50 个 episode 的平均回报，报告 95% 置信区间。

## 4. 资源与算力
- 论文**未明确说明**使用的 GPU 型号、数量、训练时长等具体算力资源。
- 仅在附录 E 中提及网络超参数（如嵌入维度 64、上下文窗口 30、2 层 Transformer、学习率 0.01、batch size 2048 等），但未提供训练时间或硬件细节。

## 5. 实验数量与充分性
- **实验数量**：
  - 主对比实验：6 种环境配置（PP-4/8, LBF-4/8, Overcooked-4/8）× 6 种方法 → 36 组对比曲线（图 3）。
  - 消融实验（图 5）：在全部 3 种环境上测试移除 TA-Goal 解码器、数据预处理、代理编码器等 4 个变体 → 12 组对比。
  - 超参分析（附录 C）：考察“目标步数”（1/2/3/6）对 3 种环境的影响 → 12 组对比。
  - 所有结果均报告 50 次试行的平均回报与 95% 置信区间。
- **充分性**：
  - 覆盖了复杂度和任务特性不同的三个环境，且每个环境包含两种测试队友数量（4 和 8），检验泛化能力。
  - 对比了从序列建模、离线 RL、在线 AHT 变体、多智能体 DT 等多个角度的基线，对比全面。
  - 消融实验系统验证了每个核心组件的贡献，结论可靠。
  - 实验设计客观公平：测试队友完全不同于训练数据，且所有基线在相同数据集上训练。

## 6. 论文的主要结论与发现
- TAGET 在所有环境及测试配置下**显著优于所有基线**，平均提升 37.83%（表 1）。
- 在更复杂的任务（如 Overcooked）和更大测试队友集（如 PP-8）中，TAGET 的稳定性优势更明显，而基线（如 ODITS-off, LIAM-off）波动较大。
- 消融实验表明：① TA-Goal 解码器的移除导致性能下降最大，证明未来状态子目标比标量 RTG 提供更丰富的队友行为信息；② 轨迹镜像策略对泛化能力至关重要，尤其在高复杂度环境中；③ 代理编码器的正则化有效缓解部分可观测问题。
- 目标步数超参分析：最佳值因环境而异——简单场景（PP）需更长步数（6），复杂动态场景（Overcooked）适中（3），中等场景（LBF）较短暂（2），过长步数会因预测噪声导致性能下降。

## 7. 优点
- **问题创新**：首次系统定义并解决离线 AHT 问题，拓宽了 AHT 的应用场景（无需在线交互）。
- **方法设计精巧**：
  - 轨迹镜像策略简单有效，充分利用多智能体轨迹的对称性，缓解数据稀疏。
  - 双编码器+混合 KL 正则化（反向 KL 防过拟合+前向 KL 保持一致性）是处理部分可观测性的优雅方案。
  - TA-Goal 替代 RTG 作为 DT 的条件信号，能够编码队友动态和未来协作意图，提升适应性和鲁棒性。
- **实验验证全面**：多环境、多基线、消融和超参分析，结果统计显著，证据充分。
- **可复现性**：附录提供了详细的网络架构、超参数、算法伪代码，便于复现。

## 8. 不足与局限
- **实验覆盖**：
  - 仅使用网格世界环境（PP, LBF, Overcooked），未在更接近现实的高维连续控制或视觉输入场景（如自动驾驶模拟器）中验证。
  - 队友策略多样性限于 4 个群体的检查点，实际应用中队友策略空间可能更广阔和复杂。
- **偏差风险**：
  - 离线数据收集依赖 SVD 方法，可能引入特定偏差；未讨论数据质量（如噪声、次优轨迹比例）对性能的影响。
  - 与在线 AHT 方法的比较仅限于其离线变体（ODITS-off, LIAM-off），未与直接修改的在线方法做公平对比（但论文已说明在线方法无法直接应用于离线设置）。
- **应用限制**：
  - TA-Goal 预测需要预先定义子目标的表示形式（拼接离散化观测），扩展至连续状态空间或图像观测需额外设计。
  - 方法依赖固定的“目标步数”超参，不同环境需手动调优，自适应机制有待探索。
- **算力与效率**：未报告训练时长或资源消耗，使得实际部署的成本评估不明确。
- **安全性与鲁棒性**：未讨论队友恶意行为或异常策略下的表现，离线数据集难以覆盖所有极端案例。

（完）
