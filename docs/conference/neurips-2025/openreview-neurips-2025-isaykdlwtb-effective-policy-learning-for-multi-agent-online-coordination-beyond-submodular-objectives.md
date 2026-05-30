---
title: Effective Policy Learning for Multi-Agent Online Coordination Beyond Submodular Objectives
title_zh: 超越子模目标的有效多智能体在线协调策略学习
authors: "Qixin Zhang, Yan Sun, Can Jin, Xikun ZHANG, Yao Shu, Puning Zhao, Li Shen, Dacheng Tao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=isAYKdLwtB"
tags: ["query:marl"]
score: 9.0
evidence: 提出两种在线策略学习算法用于多智能体协调
tldr: 本文针对多智能体在线协调问题，提出了MA-SPL等两种在线策略学习算法。MA-SPL不仅能应对子模目标，还首次处理了弱DR-子模和弱子模场景，并给出最优近似保证。后续算法进一步减少了对未知参数的依赖。实验表明所提算法在多种弱子模场景下均有效，拓展了多智能体协调的理论边界。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-isaykdlwtb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1417, \"height\": 245, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isaykdlwtb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1416, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isaykdlwtb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isaykdlwtb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1409, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isaykdlwtb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1382, \"height\": 407, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-isaykdlwtb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-isaykdlwtb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1460, \"height\": 406, \"label\": \"Table\"}]"
motivation: 多智能体在线协调问题中，现有方法局限于子模目标，无法处理更一般的弱子模场景。
method: 提出MA-SPL算法，利用子模曲率实现最优近似；再提出一种无需参数先验的在线算法。
result: MA-SPL在子模、弱DR-子模和弱子模场景下均取得最优近似比，实验验证有效性。
conclusion: 本文扩展了多智能体在线协调的理论边界，为弱子模场景提供了有效算法。
---

## Abstract
In this paper, we present two effective  policy learning algorithms for multi-agent online coordination(MA-OC) problem. The first one, **MA-SPL**,  not only can achieve the optimal $(1-\frac{c}{e})$-approximation guarantee for the MA-OC problem with submodular objectives but also can handle the unexplored  $\alpha$-weakly DR-submodular and $(\gamma,\beta)$-weakly submodular scenarios, where $c$ is the curvature of the investigated submodular functions, $\alpha$ denotes the diminishing-return(DR) ratio and the tuple$(\gamma,\beta)$ represents the submodularity ratios.  Subsequently, in order to reduce the reliance on the unknown parameters $\alpha,\gamma,\beta$ inherent in the **MA-SPL** algorithm, we then introduce the second online algorithm named **MA-MPL**. This **MA-MPL** algorithm is entirely *parameter-free* and simultaneously can maintain the same approximation ratio as the first  **MA-SPL** algorithm. The core of our **MA-SPL** and **MA-MPL** algorithms is a novel continuous-relaxation technique term as policy-based continuous extension. Compared with the well-established multi-linear extension, a notable advantage of this new policy-based continuous extension is its ability to provide a lossless rounding scheme for any set function, thereby enabling us to tackle the challenging  weakly submodular objective functions. Finally, extensive simulations are conducted to demonstrate the effectiveness of our proposed algorithms.

---

## 论文详细总结（自动生成）

## 论文总结：Effective Policy Learning for Multi-Agent Online Coordination Beyond Submodular Objectives

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：多智能体在线协调（MA-OC）问题普遍存在，但现有算法大多局限于严格的子模目标函数，无法处理实际中更一般的弱子模场景（如α-弱DR-子模或(γ,β)-弱子模）。同时，即使对于子模目标，现有分布式算法（如MA-OSMA、MA-OSEA）也只能达到次优的(1-e^{-c})/c近似，而非最优的(1-c/e)。
- **动机**：许多应用（如UAV多目标跟踪、LLM数据选择）呈现“接近子模但不严格子模”的性质，亟需能处理弱子模的在线算法，并提升子模场景的近似保证。
- **整体含义**：本文首次为MA-OC问题提供了能处理弱子模目标的在线策略学习算法，并实现了子模场景下的最优近似比，拓展了理论边界。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：提出一种新颖的连续松弛技术——**策略基连续扩展（policy-based continuous extension）**，将离散集合函数最大化问题转化为连续优化，且能对任意集合函数提供无损舍入（lossless rounding），而传统多线性扩展仅对子模函数有效。
- **关键技术细节**：
  - **策略基连续扩展**：每个智能体i学习一个策略π_i∈Δ^{κ_i}（定义在其动作集V_i上的概率分布），则扩展函数Ft(π_1,...,π_n) = E_{a_i~π_i}[f_t(∪_i{a_i})]。
  - **性质**：当f_t子模时，Ft是连续DR-子模；当f_t弱子模时，Ft满足相应的弱DR-子模或弱子模不等式。
  - **代理函数（Surrogate Functions）**：为提升驻点的近似保证，对Ft设计梯度为加权平均的代理函数F^s_t。对于α-弱DR-子模权重为w(z)=e^{α(z-1)}；对于(γ,β)-弱子模权重为w(z)=e^{φ(γ,β)(z-1)}；对于子模（曲率c）则使用F^s_t + G_t/e，其中G_t为线性函数。
  - **MA-SPL算法（Algorithm 1）**：基于共识机制（consensus）和代理梯度估计，每个智能体维护局部策略向量，通过梯度上升和投影更新。每轮采样动作、交换信息、估计梯度（利用随机集S_i(t)），对于子模情况额外加上最小边际贡献。
  - **MA-MPL算法（Algorithm 2）**：为消除对参数α,γ,β的依赖，采用“元动作（meta-actions）”框架，利用K个在线线性最大化预言机（如在线Frank-Wolfe）和批量梯度估计，实现免参数化，并保持相同近似比。

### 3. 实验设计：数据集/场景、基准测试、对比方法
- **场景一：多目标跟踪（子模目标）**：20个智能体跟踪30个目标，目标分为随机、对抗、折线三类，共T=1250步。使用设施选址目标函数（已证明是子模）。
  - 对比方法：OSG（在线序列贪心）、MA-OSMA、MA-OSEA、MA-SPL、MA-MPL。考虑完全图和Erdos-Renyi随机图（平均度4）。
- **场景二：扩展卡尔曼滤波框架下的目标跟踪（弱DR-子模）**：使用A-最优准则目标函数，已验证为α-弱DR-子模。T=500步。
  - 对比方法：RANDOM（随机选择）、MA-SPL（α=0.1和α=1），MA-MPL。同样考虑完全图和随机图。
- **超参数测试**：对α进行0.1步长网格搜索（0.1到1），报告最优和最差情况。未提供具体的数据集名称，但给出了仿真参数（平面范围、速度、角度等）。

### 4. 资源与算力
- **文中未明确说明**：未提及GPU型号、数量、训练时长或计算资源。仅在附录C.3中提到使用CVX优化器进行投影，且算法均为CPU可运行。因此无法量化具体算力消耗。

### 5. 实验数量与充分性
- **子模场景**：三种目标比例（8:1:1, 6:3:1, 4:5:1），每种比例下测试两种通信图（完全图和随机图），并评估平均效用、平均距离、目标覆盖数。每个实验重复5次。
- **弱DR-子模场景**：对α进行10种取值测试，并对比MA-MPL和RANDOM（仅一种比例）。同样测试两种图。
- **充分性**：实验覆盖了不同目标动态、不同通信拓扑、不同弱子模参数，对比了多个代表性基线，结果与理论一致。但弱子模场景仅使用A-最优设计一种，缺乏更多实际弱子模应用（如数据子集选择）的验证；且未提供统计误差线（仅称重复5次，但图中未显示）。总体较充分，但可进一步扩展。

### 6. 论文的主要结论与发现
- **MA-SPL**：在子模目标下达到最优(1-c/e)近似，在α-弱DR-子模下达到(1-e^{-α})近似，在(γ,β)-弱子模下达到[γ^2(1-e^{-φ})/φ]近似，动态遗憾界为O(√(P_T T)/(1-τ))。
- **MA-MPL**：免参数化，保持相同近似比，遗憾界为O(d(G)√(P_T T))。实验验证其性能优于MA-OSMA/MA-OSEA（子模）和RANDOM（弱子模）。
- **核心突破**：首次在线解决弱子模MA-OC问题；策略基连续扩展比多线性扩展更通用，支持无损舍入任意集合函数。

### 7. 优点
- **理论创新**：提出策略基连续扩展及其代理函数，从理论上解决了弱子模目标的在线近似，并补全了子模场景下最优近似比的缺失。
- **算法设计**：MA-SPL和MA-MPL均支持局部反馈（仅需边际查询），适用于实际通信受限环境；MA-MPL无需参数先验，实用性强。
- **实验验证**：在两个不同目标跟踪场景、多种目标动态和通信图下验证，结果与理论吻合。

### 8. 不足与局限
- **实验覆盖**：弱子模场景仅用一种A-最优目标，缺乏其他弱子模应用（如传感器选择、数据摘要）；未在更大规模智能体或真实机器人平台上测试。
- **偏差风险**：仿真假设目标运动模型简单（Brownian motion），未考虑传感器噪声、通信延迟等实际因素。
- **应用限制**：MA-MPL通信复杂度高于MA-SPL（T^{3/2} vs T），对通信敏感场景可能不适用；算法需要知道目标函数（或边际收益）的上界M（用于分析），但在实现中未显式依赖。
- **自身局限性提及**：附录I指出MA-MPL通信复杂度更高，未来可通过阻塞策略优化。

（完）
