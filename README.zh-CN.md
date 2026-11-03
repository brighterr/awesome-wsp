<p align="center">
  <picture>
    <source media="(max-width: 640px)" srcset="assets/hero-mobile.svg">
    <img src="assets/hero.svg" alt="Awesome Weight-Space Programming — 神经网络权重，可读亦可写" width="100%">
  </picture>
</p>

<h1 align="center">Awesome Weight-Space Programming</h1>

<p align="center">
  精选权重空间编程领域的论文、代码与评测基准。
</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge-flat2.svg" alt="Awesome"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-CC0_1.0-5ad9bf?style=flat-square&amp;labelColor=17263c" alt="许可协议：CC0 1.0"></a>
  <a href="CONTRIBUTING.md"><img src="https://img.shields.io/badge/contributions-welcome-8da9ed?style=flat-square&amp;labelColor=17263c" alt="欢迎贡献"></a>
</p>

<p align="center">
  <a href="#从这里开始"><strong>从这里开始</strong></a> &nbsp; · &nbsp;
  <a href="#资源目录"><strong>浏览资源</strong></a> &nbsp; · &nbsp;
  <a href="README.md">English</a> &nbsp; · &nbsp;
  <a href="https://github.com/brighterr/awesome-wsp/issues/new/choose">推荐资源 ↗</a>
</p>

<p align="center">
  <sub>⭐ 如果这份清单对你有帮助，欢迎 Star 收藏，让更多人发现它。</sub>
</p>

---

## 从这里开始

四个入口，从理解概念到动手探索。

1. **[Sparks of WSP](https://rikiyat.github.io/blog/weight-space-programming/)** · 了解起点<br>
   从权重读取行为，探索网络的修复与构造。

2. **[WSP from Scratch](https://csinva.io/weight-space-programming-autoresearch/analyze/toy_examples/report.html)** · 理解原理<br>
   用算术、排序与奇偶判断理解神经电路。

3. **[Tracr](https://github.com/google-deepmind/tracr)** · 动手构建<br>
   将可读程序编译为 Transformer 权重。

4. **[社区实验](#社区实验与评测基准)** · 继续探索<br>
   发现复现项目、权重读取测试与评测工具。

## 资源目录

先看直接实验与社区项目，再按兴趣深入相关基础研究。

[直接权重编程](#直接权重空间编程) · [社区项目](#社区实验与评测基准) · [程序编译](#从程序到-transformer-权重) · [权重生成](#学习式权重生成) · [权重空间模型](#处理权重的神经网络) · [模型编辑](#相关模型编辑) · [机制基础](#机制基础)

### 直接权重空间编程

#### Sparks of Weight-Space Programming

<sub>Rikiya Takehi、Jayden Teoh、Alex Zhang、Omar Khattab · 2026 · 博客与公开实验产物</sub>

[文章](https://rikiyat.github.io/blog/weight-space-programming/) · [代码、日志与网络](https://github.com/RikiyaT/lm_understand-logs)

探索从权重识别网络行为、修复控制策略、编写游戏网络以及编辑语言模型。

有助于理解读取权重、构造网络与修复已有网络之间的区别。

<details>
<summary>实验条件与证据说明</summary>

- **访问条件各不相同：**部分实验仅允许一次无工具回答，另一些允许外部 Python 执行环境和有限反馈。仓库逐项记录了这些条件。
- **证据说明：**公开内容包含报告中的运行记录，并未涵盖所有早期提示词尝试。README 列出了未公开的产物及重建方法，因此不能将其视为完整搜索历史。

</details>

#### Weight-Space Programming from scratch on simple tasks

<sub>Chandan Singh · 2026 · 博客与自主编程实验</sub>

[文章与交互式电路](https://csinva.io/weight-space-programming-autoresearch/analyze/toy_examples/report.html) · [代码与快照](https://github.com/csinva/weight-space-programming-autoresearch) · [Agent 指令](https://github.com/csinva/weight-space-programming-autoresearch/blob/main/evolve/program.md)

Agent 为小型 Transformer 直接赋予权重，也可以修改架构，再根据评测反馈迭代。

覆盖算术、排序、奇偶判断、计数、布尔表达式等有界任务；保存的程序便于具体检查电路机制。

<details>
<summary>实验条件与证据说明</summary>

- **证据说明：**算法任务分数来自有限评测样本。文章承认语言任务存在评测泄漏、SNLI 实验使用拟合，以及通过 buffer 规避参数计数等问题。这些结果不能作为无需训练即可获得通用语言理解能力的有效证明。

</details>

### 社区实验与评测基准

社区项目与原始报告分开收录；以下为公开资料整理，尚未在本仓库独立复现。

- **[Weight-Space Claude](https://github.com/nihilistau/weight-space-claude)**<br>
  基于 Claude 的实验框架、评分器，以及部分 Sparks 提示词的并排结果。

- **[Weight-Space Programming experiments — Notes by Lex](https://github.com/lextoumbourou/weight-space-programming-experiments)**<br>
  跨模型游戏识别，以及使用受限张量读取器的独立 DQN checkpoint 盲测。

- **[WSPBench](https://github.com/alexcarterhq/wspbench)**<br>
  区分无辅助、权重分析和工具辅助条件的研究预览；提供已保存提交的公开 CPU 重放。

- **[Beyond Math](https://github.com/Unjuno/beyond-math-weight-space-programming)**<br>
  审查公开编辑轨迹，并对基础与编辑后的 checkpoint 进行配对的非数学任务探测。

- **[Weight-Space Programming for the Social Safety Net](https://github.com/ctrimm/weight-space-programming)**<br>
  构造实现给定分段线性公式的网络，提供实验协议和经过训练的对照模型。

<details>
<summary>项目范围与复现说明</summary>

早期社区项目与原始报告分开列出。以下说明依据整理日期时的公开 README，本仓库尚未重新运行这些实验。重放已保存输出、评测已有 checkpoint，以及重新执行编辑流程，属于不同层次的证据。

- **Weight-Space Claude** — 覆盖游戏识别、扩散形状读取与 MinAtar 网络构造，并非复现全部原始实验。
- **Weight-Space Programming experiments — Notes by Lex** — 包含仅使用形状信息的对照；少量 checkpoint 样本无法确立普遍成功率。
- **WSPBench** — 公开试验覆盖小型构造电路上的无辅助条件；重放不重新执行模型推理。
- **Beyond Math** — 区分作者基准记录与小规模本地探测；没有复现原始编辑搜索。
- **Weight-Space Programming for the Social Safety Net** — 属于简化公式实验，不能作为实际福利计算器或完整资格判定能力的证据。

</details>

### 从程序到 Transformer 权重

基础与紧密相关的工作。编译方法提供了有用的基线，用于考察通用 LLM 带来了哪些额外能力。

- **[Thinking Like Transformers](https://arxiv.org/abs/2106.06981)**<br>
  <sub>Gail Weiss、Yoav Goldberg、Eran Yahav。 ICML 2021。</sub>

  提出 RASP，用编程语言表达直方图、排序等注意力式计算，为编写 Transformer 算法提供概念基础。

- **[Tracr: Compiled Transformers as a Laboratory for Interpretability](https://arxiv.org/abs/2301.05062)**<br>
  <sub>David Lindner 等。 NeurIPS 2023。</sub>

  将可读程序编译成结构已知的 Transformer 权重，支持受控的可解释性实验。[代码](https://github.com/google-deepmind/tracr)。

- **[Learning Transformer Programs](https://arxiv.org/abs/2306.01128)**<br>
  <sub>Dan Friedman、Alexander Wettig、Danqi Chen。 NeurIPS 2023。</sub>

  训练受约束的 Transformer，再将其转换为离散、人类可读的程序。该方法使用梯度训练，属于相关替代路线，而非无需训练的构造结果。[代码](https://github.com/princeton-nlp/TransformerPrograms)。


### 学习式权重生成

这些方法需要训练权重生成器，应与通用 LLM 无需针对任务训练生成器、直接推理权重的方式区分开来。

- **[HyperNetworks](https://arxiv.org/abs/1609.09106)**<br>
  <sub>David Ha、Andrew Dai、Quoc V. Le。 2016 年预印本。</sub>

  使用一个网络生成另一个网络的权重，并进行端到端训练。对于“生成网络而非逐一优化目标网络”的主张，这是重要的基础比较对象。

- **[Parameter Prediction for Unseen Deep Architectures](https://arxiv.org/abs/2110.13100)**<br>
  <sub>Boris Knyazev 等。 NeurIPS 2021。</sub>

  根据架构图预测参数，并提出 DeepNets-1M，为直接构造提供学习式替代方法。[代码与数据集工具](https://github.com/facebookresearch/ppuda)。


### 处理权重的神经网络

神经元通常可以在不改变网络功能的情况下进行置换。这些工作帮助解释为什么原始张量坐标并不是唯一的语义表示。

- **[Permutation Equivariant Neural Functionals](https://arxiv.org/abs/2302.14040)**<br>
  <sub>Allan Zhou 等。 NeurIPS 2023。</sub>

  构建尊重神经元置换对称性的权重处理层，应用包括隐式神经表示的预测与编辑。[代码](https://github.com/AllanYangZhou/nfn)。

- **[Neural Functional Transformers](https://arxiv.org/abs/2305.13546)**<br>
  <sub>Allan Zhou 等。 NeurIPS 2023。</sub>

  使用注意力构造权重空间上的置换等变模型，适合比较经过训练的权重读取器与通用 LLM 权重读取器。[代码](https://github.com/AllanYangZhou/nfn)。

- **[Equivariant Deep Weight Space Alignment](https://arxiv.org/abs/2310.13397)**<br>
  <sub>Aviv Navon 等。 ICML 2024。</sub>

  学习在置换对称性下对齐网络，与参数表示的比较和组合密切相关。[代码](https://github.com/AvivNavon/deep-align)。


### 相关模型编辑

精选通过参数更新改变行为的比较对象，并非完整的知识编辑或模型合并文献综述。

- **[Locating and Editing Factual Associations in GPT](https://arxiv.org/abs/2202.05262)**<br>
  <sub>Kevin Meng 等。 NeurIPS 2022。</sub>

  提出 ROME，通过定向更新前馈层权重来定位和编辑事实关联。这是一种包含优化步骤的编辑算法，而非 LLM 从零直接写出解决方案。[代码](https://github.com/kmeng01/rome)。

- **[Editing Models with Task Arithmetic](https://arxiv.org/abs/2212.04089)**<br>
  <sub>Gabriel Ilharco 等。 ICLR 2023。</sub>

  从微调前后的权重差构造任务向量，再通过算术组合调整模型行为，有助于区分权重组合与直接电路合成。[代码](https://github.com/mlfoundations/task_vectors)。


### 机制基础

- **[A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html)**<br>
  <sub>Nelson Elhage 等。 2021 年研究文章。</sub>

  从残差流、QK 与 OV 等视角分析 Transformer 计算，为读取训练后的电路和设计显式电路提供概念工具。


## 关于本清单

[复现检查清单](#复现检查清单) · [参与贡献](#参与贡献) · [致谢](#致谢) · [许可协议](#许可协议)

Awesome Weight-Space Programming 是独立的开源资源清单，面向研究者、工程师，以及希望探索神经网络可编程性的人，欢迎社区共同完善。

权重空间编程研究 Agent 如何检查、构造或修改神经网络参数，以实现指定行为。本清单将 LLM 直接操作权重的实验与程序编译、学习式权重生成、权重空间表示及定向模型编辑联系起来。

**收录范围。** 重点关注直接权重推理与构造。相关论文作为基础工作标注，它们不一定使用“权重空间编程”一词。通用微调、提示词优化，以及不涉及权重构造的架构搜索，不属于主要范围。

**整理说明。** 最后整理日期：2026 年 11 月 3 日。这是一份精选清单，并非穷尽式综述。收录表示资源值得查阅，不表示其结果已在本仓库独立复现。两项原始报告均为博客，尚未核实为经过同行评审的出版物。

<details>
<summary>比较五条研究路线</summary>

### 研究路线

| 研究路线 | 权重如何产生或被使用 | 意义 |
| --- | --- | --- |
| LLM 直接编程 | LLM 推理张量，或编写为张量赋值的代码。 | 本清单的核心主题。 |
| 程序编译 | 编译器将形式化程序映射为网络。 | 提供明确机制与有用的正确性基线。 |
| 学习式权重生成 | 训练后的超网络预测另一个网络的参数。 | 一条独立的权重生成路线。 |
| 权重空间建模 | 模型读取或变换另一个模型的参数。 | 处理网络的对称性与表示问题。 |
| 定向编辑 | 算法更新选定权重或组合任务向量。 | 为行为修改提供比较对象。 |

</details>

## 复现检查清单

<details>
<summary>展开复现检查清单</summary>

比较结果或推荐新条目时，请清楚说明实验条件：

- **目标与架构：**架构固定还是可修改；参数、buffer 与常量的存储量；数值精度。
- **访问权限：**仅权重，还是允许张量工具、前向传播、激活、样例、标签或环境反馈。
- **构造方式：**直接赋值、编译、查表、学习式生成，还是拟合系数。
- **评测方式：**未见过的随机种子或数据划分、可行时对有限输入域进行穷举检查、边界情况与长度泛化。
- **搜索预算：**尝试次数、模型身份、token 用量、执行时间与筛选流程。
- **证据：**可运行产物与确切配置；区分报告分数、独立重新评分、checkpoint 重测与完整流程的重新复现。

“没有梯度”本身不代表没有拟合、反馈或搜索。若常量被移到 buffer 或代码中，参数量低也不代表总存储量低。对构造电路的解释是有价值的假设，仍可通过因果或等价性检查进一步验证。

</details>

## 参与贡献

欢迎补充论文、可运行项目、复现与纠错。请先阅读 [贡献指南](CONTRIBUTING.md)，再发起 PR 或 [推荐资源](https://github.com/brighterr/awesome-wsp/issues/new/choose)。

优先引用一手来源，并简要说明收录理由。区分直接相关工作与基础工作，准确标注实验状态。

## 致谢

<details>
<summary>设计参考与致谢</summary>

清单结构遵循 [Awesome 宣言](https://github.com/sindresorhus/awesome/blob/main/awesome.md) 的整理原则，组织方式参考了 [Awesome Node.js](https://github.com/sindresorhus/awesome-nodejs) 与 [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents)。首页视觉参考了 [Dify](https://github.com/langgenius/dify) 和 [n8n](https://github.com/n8n-io/n8n) 的封面优先布局，以及 [Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM) 的阅读层次。封面为本清单原创。研究与软件成果归相应作者及维护者所有。Awesome 徽章不代表已被 Awesome 主索引收录。

</details>

## 许可协议

本清单的原创文字通过 [CC0 1.0](LICENSE) 贡献至公共领域。链接中的论文、代码、模型与数据集仍遵循各自的许可协议。

<sub>项目别名：Awesome-WSP / awesome-wsp。</sub>
