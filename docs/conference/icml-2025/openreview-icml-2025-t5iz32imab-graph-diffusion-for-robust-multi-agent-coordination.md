---
title: Graph Diffusion for Robust Multi-Agent Coordination
title_zh: 图扩散实现鲁棒多智能体协调
authors: "Xianghua Zeng, Hang Su, Zhengyi Wang, Zhiyuan LIN"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=T5IZ32ImAB"
tags: ["query:marl"]
score: 9.0
evidence: 离线多智能体强化学习，图扩散协调
tldr: 离线多智能体强化学习面临分布外状态动作估计困难。本文提出MCGD框架，利用图扩散模型构建稀疏协调图，聚合连续节点与离散边属性，提升协作策略的鲁棒性。实验验证了该方法在动态环境下的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 703, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 726, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 844, \"height\": 633, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1792, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 859, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 657, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 776, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1774, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 420, \"label\": \"Table\"}]"
motivation: 离线MARL中忽略多智能体协调动态导致策略鲁棒性下降。
method: 构造包含节点与边属性的稀疏协调图，基于图扩散模型进行多智能体协调。
result: 在多个环境上优于基线方法，提升了协作鲁棒性。
conclusion: 图扩散模型可有效增强离线多智能体协调策略的鲁棒性。
---

## Abstract
Offline multi-agent reinforcement learning (MARL) struggles to estimate out-of-distribution states and actions due to the absence of real-time environmental feedback. While diffusion models show promise in addressing these challenges, their application primarily focuses on independently diffusing the historical trajectories of individual agents, neglecting crucial multi-agent coordination dynamics and reducing policy robustness in dynamic environments. In this paper, we propose MCGD, a novel Multi-agent Coordination framework based on Graph Diffusion models to improve the effectiveness and robustness of collaborative policies. Specifically, we begin by constructing a sparse coordination graph that includes continuous node attributes and discrete edge attributes to effectively identify the underlying dynamics of multi-agent interactions. Next, we derive transition probabilities between edge categories and present adaptive categorical diffusion to capture the structure diversity of multi-agent coordination. Leveraging this coordination structure, we define neighbor-dependent forward noise and develop anisotropic diffusion to enhance the action diversity of each agent. Extensive experiments across various multi-agent environments demonstrate that MCGD significantly outperforms existing state-of-the-art baselines in coordination performance and policy robustness in dynamic environments.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题背景**：离线多智能体强化学习（Offline MARL）在没有实时环境交互的条件下从历史数据集学习策略，面临严重的分布外（Out-of-Distribution, OOD）状态和动作估计问题。
- **现有方法不足**：当前基于扩散模型的方法（如MADIFF、DOM2）通常**独立地对每个智能体的历史轨迹进行扩散**，忽略了智能体之间的**协调结构动态变化**（例如某个智能体速度改变或突然离线），导致策略在动态环境下的鲁棒性不足。
- **研究目标**：提出一种能**显式建模多智能体协调结构**并同时处理**动作多样性**的生成框架，提升离线协作策略的有效性和鲁棒性。

## 2. 方法论
- **核心思想**：构建稀疏协调图（结构 + 动作），分别对边（离散）和节点（连续）设计差异化扩散过程，并联合去噪恢复原始属性，实现结构与动作的双重多样化。
- **关键技术细节**：
  - **稀疏协调图的构建**：在每个时间步，根据智能体观测的余弦相似度，每个智能体选择k个最近邻构成无向图G_t=(A_t, E_t)，其中节点属性A_t为连续动作，边属性E_t为二进制邻接矩阵（0/1）。
  - **边上的分类扩散（Categorical Diffusion）**：
    - 定义自适应转移矩阵Q_t = exp(\beta_k (C-D))，其中C是余弦相似度矩阵，D是度矩阵。
    - 前向过程：q(E_{t,k}|E_{t,k-1}) = Cat(E_{t,k}|E_{t,k-1} Q_{\beta_k})。
    - 优点：满足对称性、可加性、局部性与收敛性，能根据代理间的相关性动态调整转移概率。
  - **节点上的各向异性扩散（Anisotropic Diffusion）**：
    - 对每个智能体i，使用其邻居动作A_t^i的协方差矩阵Σ_i定义各向异性高斯噪声。
    - 前向过程：q(a_{i,t,k}|a_{i,t,k-1}) = N(a_{i,t,k}; √(1-β_k) a_{i,t,k-1}, β_k Σ_i)。
    - 闭式边缘分布可用，便于训练。
  - **逆去噪过程**：
    - 设计图变换网络f_θ（Graph Transformer），输入噪声图G_{t,K}，输出预测边属性\hat{E}_t^θ和节点属性\hat{A}_t^θ。
    - 边损失：交叉熵L_ce(E_t, \hat{E}_t^θ)。
    - 节点损失：L_ad = Σ_i [||a_i - \hat{a}_i||^2 - λ Q_{\phi_i}(o_i, \hat{a}_i)]，结合Q值引导。
  - **策略采样（算法1）**：训练后，对每个智能体从候选动作集中选出Q值最高的动作，初始化全连接图，通过逐步去噪得到最终协作动作。离散动作通过softmax + argmax转换。

## 3. 实验设计
- **数据集/场景**：
  - **MPE**（Multi-Agent Particle Environments）：Spread, Tag, World三个任务，使用Expert/Good/Medium/Medium-Replay/Random等级离线数据集（来自OMAR）。
  - **MAMuJoCo**：2halfcheetah, 2ant, 4ant，使用Good/Medium/Poor数据集（来自Off-the-Grid）。
  - **SMAC**：3m, 2s3z, 5m6m, 8m，同样使用Good/Medium/Poor数据集。
  - **Shifted环境**（鲁棒性测试）：改变速度（MPE）或动力/密度/摩擦参数（MAMuJoCo），以及将某个智能体固定（模拟断连）。
- **对比的基线方法**：
  - 传统离线MARL：MA-ICQ, MA-CQL, OMAR。
  - 单智能体扩散扩展：MA-SfBC。
  - 扩散型MARL：DOM2, MADIFF。
- **评估指标**：平均回合回报（episodic return），运行5次取均值±标准差。

## 4. 资源与算力
- **论文明确说明**：使用 **NVIDIA A800-SXM4-80GB GPU** 和 **64-core Intel Xeon Platinum 8336C CPU (2.30 GHz)**。
- **未提及**：具体GPU数量、单次训练时长或总GPU小时数。因此无法提供精确算力消耗。

## 5. 实验数量与充分性
- **实验数量**：
  - 主实验（表1）：在3个benchmark的多个数据集（Expert/Good）上对比7种方法，共10个任务。
  - 鲁棒性测试（表2）：4个任务 × 2种扰动（属性变化、结构变化），共8个对比。
  - 消融实验（图6）：去除分类扩散或各向异性扩散，在SMAC 3个难度等级上各4个地图（共12个实验）。
  - 邻居处理方式消融（表3）：SMAC 4个地图 × 2种方式。
  - 敏感性分析（图7）：MPE Tag任务4个数据集，λ从0.1到20。
  - 采样效率（表6）：4个规模 × 2种方法。
  - 附录：表7-9补充了更多难度等级（Random/Medium-Replay/Medium/Poor）下的性能对比。
- **充分性与公平性**：实验覆盖了多种环境、多种数据质量、多种扰动场景；消融验证了核心模块的作用；对比基线均为近年来代表性方法。但未包含真实世界实验，仅在仿真中评估。

## 6. 主要结论与发现
- MCGD在所有benchmark上**显著超越所有基线**，在Expert/Good数据集上平均提升5.1%~12.8%（MPE）、6.5%~12.2%（MAMuJoCo）、4.7%~12.8%（SMAC）。
- 在shifted环境下优势更明显，尤其在协调结构变化时提升高达14.2%，证明了对协调结构建模的重要性。
- 消融实验表明：**两种扩散模块（分类扩散 + 各向异性扩散）均对性能有正向贡献**，且两者结合效果最佳。
- 敏感度分析显示：正则化系数λ在不同数据集上存在最优区间（专家级需较小λ，低质量数据需较大λ）。
- 采样效率：MCGD相比MADIFF额外开销很小（约5~8 ms），且随智能体数量增加保持稳定。

## 7. 优点
- **方法创新**：首次将图扩散模型引入多智能体离线协调，**分别处理结构多样性与动作多样性**，突破了现有独立扩散的局限。
- **理论严谨**：对边扩散的转移矩阵性质进行了数学证明（对称性、可加性、局部性、收敛性）。
- **鲁棒性突出**：在多种环境扰动下均保持高性能，设计针对性的邻居依赖各向异性噪声，避免过度不确定性导致碰撞。
- **广泛验证**：覆盖三个主流benchmark，多种数据质量等级，消融分析和敏感度分析完整。

## 8. 不足与局限
- **缺乏真实世界验证**：作者在结论中提及正致力于在真实多机器人场景中部署，但当前版本未包含实地实验，结果仅来自仿真环境。
- **计算开销**：虽然采样效率尚可，但相比简单独立扩散方法仍有微小增加；未报告训练时间，可能对大规模智能体场景有影响。
- **离散动作处理**：对离散动作空间需要softmax+argmax，可能丢失连续动作的平滑性；作者虽说明适用离散，但主要实验多为连续环境。
- **协调图构建可扩展性**：基于k-NN构建图，当智能体数量极大时（如>100），邻接矩阵计算和扩散过程可能成为瓶颈。
- **未讨论对异质任务（actions不同）的适应性**：所有任务中智能体动作维度相同，若动作空间异构，可能需要调整图构建策略。
- **随机性**：仅报告5次运行结果，标准差在某些场景下较大（如表2的MAMuJoCo 2halfcheetah 属性变化中MCGD标准差达273.0），可能表明对随机种子敏感。

（完）
