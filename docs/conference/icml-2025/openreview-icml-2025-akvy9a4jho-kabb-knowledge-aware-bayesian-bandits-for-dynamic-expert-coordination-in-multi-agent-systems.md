---
title: "KABB: Knowledge-Aware Bayesian Bandits for Dynamic Expert Coordination in Multi-Agent Systems"
title_zh: KABB：多智能体系统中知识感知贝叶斯臂的动态专家协调
authors: "Jusheng Zhang, Zimeng Huang, Yijia Fan, Ningyuan Liu, Mingyan Li, Zhuojie Yang, Jiawei Yao, Jian Wang, Keze Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AKvy9a4jho"
tags: ["query:marl"]
score: 4.0
evidence: 多智能体系统中基于知识感知贝叶斯臂的动态专家协调
tldr: 多智能体系统在大语言模型成本高企下成为替代方案，但面临静态知识和协调低效问题。本文提出KABB框架，内含知识距离模型、双适应机制和知识感知汤普森采样，实现语义驱动的动态专家协调。实验表明其达到最优成本性能权衡。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 786, \"height\": 884, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 978, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 819, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 844, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 839, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 727, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1764, \"height\": 955, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1531, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1532, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 610, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 725, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1279, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 1813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1782, \"height\": 2086, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1783, \"height\": 1694, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1785, \"height\": 1796, \"label\": \"Table\"}]"
motivation: 多智能体系统存在静态知识假设与协调低效。
method: 构建知识距离模型与双适应机制，采用知识感知汤普森采样进行专家选择。
result: 在成本与性能间达到最优平衡，维持高协调性能。
conclusion: 语义理解的贝叶斯方法可有效提升多智能体协调效率。
---

## Abstract
As scaling large language models faces prohibitive costs, multi-agent systems emerge as a promising alternative, though challenged by static knowledge assumptions and coordination inefficiencies. We introduce Knowledge-Aware Bayesian Bandits (KABB), a novel framework that enhances multi-agent system coordination through semantic understanding and dynamic adaptation. The framework features three key innovations: a customized knowledge distance model for deep semantic understanding, a dual-adaptation mechanism for continuous expert optimization, and a knowledge-aware Thompson Sampling strategy for efficient expert selection. Extensive evaluation demonstrates KABB achieves an optimal cost-performance balance, maintaining high performance while keeping computational demands relatively low in multi-agent coordination.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义
- **研究动机**：大型语言模型（LLM）扩展面临高昂成本，多智能体系统（MAS）成为替代方案，但现有方法（如MoA、MoE）存在**静态知识假设**（专家能力不变、知识领域固定）和**协调低效**（冗余、噪声、计算成本随代理数线性增长）。
- **核心问题**：如何动态协调多专家，在保持高性能的同时降低计算成本，并实现语义层面的自适应。
- **整体含义**：本文提出**KABB**（Knowledge-Aware Bayesian Bandits）框架，将知识图谱与贝叶斯多臂赌博机（MAB）结合，实现基于语义理解的动态专家协调，在成本-性能平衡上达到最优。

## 2. 论文提出的方法论
### 2.1 核心思想
- 将多专家系统建模为**动态组合选择问题**：每步任务到来，从专家集合中选出最优子集，结合知识距离和团队协同，使用贝叶斯MAB平衡探索与利用。
- 三大创新：
  - **知识距离模型**：深度融合语义概念重叠、依赖路径、历史性能、团队互补性等五维信息。
  - **双适应机制**：贝叶斯参数时间衰减更新 + 知识图谱持续演化。
  - **知识感知Thompson采样**：将知识距离、时间衰减、协同效应融入Beta分布采样。

### 2.2 关键技术细节
- **知识距离函数** (公式4)：  
  \[
  \text{Dist}(S,t) = \log(1+d_t) \cdot \left[ \omega_1(1-\rho_{\text{overlap}}) + \omega_2\frac{|R_{\text{dep}}|}{K} + \omega_3(1-\bar{H}_S) + \omega_4(1-\text{Synergy}(S)) \right]
  \]
  - \(d_t\)：任务难度（知识图深度）
  - \(\rho_{\text{overlap}}\)：Jaccard相似度（专家子集-任务概念交集）
  - \(|R_{\text{dep}}|\)：依赖边数
  - \(\bar{H}_S\)：历史平均成功率
  - \(\text{Synergy}(S)\)：团队互补性（专家间协同得分）
  - 权重\(\omega_i\)可学习，满足和为1。

- **动态Beta分布更新** (公式5)：  
  \[
  \alpha_S^{(t+1)} = \gamma^{\Delta t}\alpha_S^{(t)} + r_S^{(t)} + \delta\cdot \text{KM}(S,t)
  \]
  \[
  \beta_S^{(t+1)} = \gamma^{\Delta t}\beta_S^{(t)} + (1-r_S^{(t)}) + \delta\cdot(1-\text{KM}(S,t))
  \]
  - \(\gamma^{\Delta t}=e^{-\kappa\Delta t}\)：指数时间衰减
  - \(\text{KM}(S,t)=\rho_{\text{overlap}}\cdot\text{Synergy}(S)\)：知识匹配指数
  - 最新反馈与知识匹配修正历史参数。

- **联合知识-时间-团队采样** (公式6)：  
  \[
  \tilde{\theta}_S^{(t)} = \frac{\alpha_S^{(t)}}{\alpha_S^{(t)}+\beta_S^{(t)}} \cdot \exp(-\lambda\cdot\text{Dist}(S,t)) \cdot e^{-\kappa\Delta t} \cdot \text{Synergy}(S)^\eta
  \]
  综合历史期望、知识距离惩罚、时间衰减、团队协同效应。

- **算法流程**（系统架构）：
  1. 任务解析为概念需求向量\(d_t\)
  2. 专家能力映射为向量\(v_e\)
  3. 通过知识感知Thompson采样选择最优子集\(S_t\)
  4. 各专家独立处理任务，聚合器通过语义冲突检测和加权融合生成最终输出
  5. 收集反馈更新贝叶斯参数

- **理论保证**：知识距离满足伪度量性质（非负、条件对称、近似三角不等式）；动态选择策略的累积后悔上界为\(O(\sqrt{T\log T})\)（定理3.3）。

## 3. 实验设计
### 3.1 数据集与场景
- **AlpacaEval 2.0**：805条指令，模拟真实用户查询，使用GPT-4作为自动评判器，主要报告**长度控制（LC）胜率**（与人类判断Spearman相关系数0.98）。
- **MT-Bench**：多轮对话，包含第一轮和第二轮得分。
- **FLASK-Hard**：89个困难实例，覆盖12个技能维度（鲁棒性、正确性、常识、洞察、元认知、可读性等）。
- **BBH**（BIG-Bench Hard）：推理与问题解决（附录D）。
- **MATH**：数学问题（附录D）。
- **Arena-Hard**：500个挑战性问题（附录D）。

### 3.2 基准方法
- **单模型**：GPT-4系列、Qwen2-72B-Instruct、LLaMa-3-70B-Instruct、WizardLM-2-8x22B、Gemma-2-27B、Deepseek-V3、Deepseek-R1。
- **多智能体基线**：**MoA**（Mixture of Agents，2层，6个proposer+1个aggregator）。
- **消融变体**：KABB w/o Deepseek（排除Deepseek模型）、KABB-Single-LLaMa3（仅用LLaMa-3）。
- **路由策略对比**：知识感知（KA） vs. 分类器（CL）路由；优化算法比较：MAB vs. PPO、MCTS、A2C。
- **新增评价指标**：**RAS**（路由对齐分数，与人工标注一致率）、**PWRS**（偏好加权路由分数，结合输出质量和人类偏好）。

### 3.3 对比方法完整列表
| 类别 | 方法 |
|------|------|
| 单模型 | GPT-4 Omni/Turbo/Preview, Qwen2-72B, LLaMa-3-70B, WizardLM-2, Gemma-2, Deepseek-V3, Deepseek-R1 |
| 多智能体 | MoA（6 proposers + aggregator）, KABB及其变体 |
| 优化算法 | PPO, MCTS, A2C, MAB |

## 4. 资源与算力
- **实验硬件**：所有KABB实验在**单张NVIDIA GeForce RTX 3090**上运行（附录F）。论文未明确说明训练或推理的总时长或GPU数量。
- **推断成本**：使用Together Inference Endpoint和OpenAI API获取定价，基于公开API价格计算成本（图4）。
- **TFLOPS分析**：图5给出各模型平均TFLOPS作为计算负载代理指标，KABB在保持高性能的同时TFLOPS显著低于MoA。

## 5. 实验数量与充分性
### 实验数量
- **主要结果**：AlpacaEval 2.0（表1）、MT-Bench（表1）、FLASK-Hard雷达图（图3）。
- **路由策略消融**（表2）：KA vs. CL，四种优化算法。
- **组合参数影响**（图6）：概念数（2-5）和专家数（1-6）的LC胜率曲面。
- **推理与问题解决**（附录表3、表4）：BBH、MATH、Arena-Hard。
- **参数敏感性**（附录B）：知识距离阈值（0.55-0.95）和时间衰减因子（0.2-1.0）的影响。
- **案例分析**（附录E）：高质量和低质量答案的专家输出展示。
- **错误分析**（附录表7-8）：不适当专家选择与通过团队扩展部分恢复的案例。

### 充分性与公平性
- **充分**：覆盖多个主流基准，包含消融、参数分析、路由策略对比、成本效率分析。
- **客观**：AlpacaEval 2.0使用GPT-4自动评判，采用LC胜率消除长度偏差；FLASK-Hard使用12个细粒度技能分数；MT-Bench按回合评分。
- **公平**：KABB与MoA使用相同的6个模型配置；变体实验控制变量；所有模型在相同推断环境下评估。

## 6. 论文的主要结论与发现
1. **性能领先**：KABB在AlpacaEval 2.0上LC胜率达**77.9%**，比MoA（68.1%）提升9.8%；MT-Bench平均分9.60（MoA为9.41）；FLASK-Hard在2/3技能上超越或持平GPT-4。
2. **成本效率**：KABB仅需**2-3个专家**即可达到或超过MoA（6个专家）的性能；成本仅为MoA的约1/7，位于帕累托前沿。
3. **路由机制优势**：知识感知（KA）优于分类器（CL）；MAB优于PPO、MCTS、A2C（表2）。
4. **动态适应性**：贝叶斯参数更新配合时间衰减和知识匹配，能快速适应专家能力变化。
5. **团队协同重要性**：Synergy项显著影响性能，高质量团队互补性降低冗余。

## 7. 优点
- **创新性融合**：首次将知识图谱与贝叶斯MAB系统结合，提出完整的动态专家协调框架。
- **理论深度**：给出知识距离的伪度量性质证明和累计后悔上界，为方法提供理论基础。
- **全面实验设计**：跨多个基准（对话、对齐、推理、数学）、多种对比基线（单模型、MoA、强化学习算法）、多维度分析（路由策略、参数、成本）。
- **实用导向**：明确分析成本-性能权衡，提供实际部署参考（图4、图5）。
- **可解释性**：知识距离和团队协同指标使专家选择理由透明；图引导的响应整合过程提供推理路径。

## 8. 不足与局限
- **依赖预定义概念**：需要预先设定知识概念集和专家能力向量，在不同领域迁移时可能需要重新设计。
- **专家选择偶尔不当**：案例分析（附录E）显示对高度技术性任务（如代码）可能引入冗余；错误分析（附录表7）出现非相关领域专家被选中的情况。
- **简洁性不足**：FLASK-Hard中KABB在“简洁性”维度得分低于MoA和GPT-4，输出详细但可能冗长（论文承认此trade-off）。
- **推理任务优势不突出**：在Arena-Hard和BBH上，KABB表现与MoA相近，未显著超越（附录D）；数学任务（MATH）提升明显（+2.5%），但整体不如Deepseek-R1。
- **计算资源未完全统计**：仅说明使用单张RTX 3090，未报告训练/推理总时长，可能影响可复现性。
- **模型规模局限**：实验仅基于6个开源模型（最大约72B参数），未验证在更大规模或更多专家时的可扩展性。
- **依赖GPT-4评判**：AlpacaEval 2.0的自动评估基于GPT-4，可能存在偏好偏差（尽管LC胜率有高Spearman相关）。

（完）
