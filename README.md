<p align="center">
  <picture>
    <source media="(max-width: 640px)" srcset="assets/hero-mobile.svg">
    <img src="assets/hero.svg" alt="Awesome Weight-Space Programming — neural weights, readable and writable" width="100%">
  </picture>
</p>

<h1 align="center">Awesome Weight-Space Programming</h1>

<p align="center">
  A curated collection of papers, code, and benchmarks for weight-space programming.
</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge-flat2.svg" alt="Awesome"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-CC0_1.0-5ad9bf?style=flat-square&amp;labelColor=17263c" alt="License: CC0 1.0"></a>
  <a href="CONTRIBUTING.md"><img src="https://img.shields.io/badge/contributions-welcome-8da9ed?style=flat-square&amp;labelColor=17263c" alt="Contributions welcome"></a>
</p>

<p align="center">
  <a href="#start-here"><strong>Start here</strong></a> &nbsp; · &nbsp;
  <a href="#research-library"><strong>Browse the library</strong></a> &nbsp; · &nbsp;
  <a href="README.zh-CN.md">简体中文</a> &nbsp; · &nbsp;
  <a href="https://github.com/brighterr/awesome-wsp/issues/new/choose">Suggest a resource ↗</a>
</p>

<p align="center">
  <sub>⭐ Find this useful? Star the repo to bookmark the collection and help others discover it.</sub>
</p>

---

## Start here

<table>
<tr>
<td width="50%" valign="top">
<sub>01 / DISCOVER</sub>
<h3><a href="https://rikiyat.github.io/blog/weight-space-programming/">Sparks of Weight-Space Programming ↗</a></h3>
<p>Read, repair, and construct networks by reasoning about their weights.</p>
<sub>AUTHOR REPORT · EXPERIMENT LOGS</sub>
</td>
<td width="50%" valign="top">
<sub>02 / UNDERSTAND</sub>
<h3><a href="https://csinva.io/weight-space-programming-autoresearch/analyze/toy_examples/report.html">From scratch on simple tasks ↗</a></h3>
<p>See how arithmetic, sorting, and parity become explicit neural circuits.</p>
<sub>INTERACTIVE GUIDE · CODE SNAPSHOTS</sub>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<sub>03 / BUILD</sub>
<h3><a href="https://github.com/google-deepmind/tracr">Compile with Tracr ↗</a></h3>
<p>Turn readable programs into transformer weights with known mechanisms.</p>
<sub>RESEARCH PAPER · OPEN-SOURCE COMPILER</sub>
</td>
<td width="50%" valign="top">
<sub>04 / EXPLORE</sub>
<h3><a href="#community-experiments-and-benchmarks">Experiments &amp; benchmarks →</a></h3>
<p>Compare replications, weight-reading tests, and evaluation tools.</p>
<sub>COMMUNITY PROJECTS · REPRODUCTION</sub>
</td>
</tr>
</table>

## Research library

**[Direct work](#direct-weight-space-programming)** · **[Community projects](#community-experiments-and-benchmarks)** · **[Compilers](#programs-to-transformer-weights)** · **[Weight generation](#learned-weight-generation)** · **[Weight-space models](#networks-that-process-weights)** · **[Model editing](#related-model-editing)**

<details>
<summary><strong>Full directory &amp; reading notes</strong></summary>

- [Direct weight-space programming](#direct-weight-space-programming)
- [Community experiments and benchmarks](#community-experiments-and-benchmarks)
- [Programs to transformer weights](#programs-to-transformer-weights)
- [Learned weight generation](#learned-weight-generation)
- [Networks that process weights](#networks-that-process-weights)
- [Related model editing](#related-model-editing)
- [Mechanistic foundations](#mechanistic-foundations)
- [About this list and research routes](#about-this-list)
- [Reproduction checklist](#reproduction-checklist)
- [Contributing](#contributing)
- [Acknowledgments](#acknowledgments)
- [License](#license)

</details>

## Direct weight-space programming

### Sparks of Weight-Space Programming

**Rikiya Takehi, Jayden Teoh, Alex Zhang, Omar Khattab · 2026 · Blog + released experiment artifacts**

[Article](https://rikiyat.github.io/blog/weight-space-programming/) · [Code, logs and networks](https://github.com/RikiyaT/lm_understand-logs)

- Explores identifying network behavior from weights, repairing a control policy, writing game-playing networks, and editing a language model.
- Useful for studying the difference between reading weights, constructing a network, and repairing an existing one.
- **Access conditions vary:** some experiments use a single response without tools; others allow an external Python sandbox and bounded feedback. The repository documents these conditions per experiment.
- **Evidence note:** the release contains reported runs, not all earlier prompt trials. Its README lists omitted artifacts and reconstruction instructions; do not interpret the release as an exhaustive search history.

### Weight-Space Programming from scratch on simple tasks

**Chandan Singh · 2026 · Blog + autonomous coding experiments**

[Article and interactive circuits](https://csinva.io/weight-space-programming-autoresearch/analyze/toy_examples/report.html) · [Code and snapshots](https://github.com/csinva/weight-space-programming-autoresearch) · [Agent instructions](https://github.com/csinva/weight-space-programming-autoresearch/blob/main/evolve/program.md)

- An agent assigns small transformer weights and may change the architecture, then iterates using evaluation feedback.
- Covers arithmetic, sorting, parity, counting, Boolean expressions, and other bounded tasks; the saved programs make concrete circuit inspection possible.
- **Evidence note:** reported algorithmic scores use finite evaluation samples. The article acknowledges evaluation leakage in language tasks, fitting in the SNLI run, and parameter-count gaming through buffers. These are not valid demonstrations of general training-free language understanding.

## Community experiments and benchmarks

Early community projects are listed separately from the originating reports. Descriptions below summarize public READMEs checked on the curation date; we have not rerun their experiments. A replay of saved outputs, a checkpoint evaluation, and a fresh replication of an editing procedure are different forms of evidence.

| Project | What to explore | Scope and limitations |
| --- | --- | --- |
| [Weight-Space Claude](https://github.com/nihilistau/weight-space-claude) | A Claude-based harness, scorers, and side-by-side results for selected Sparks prompts. | Covers game identification, diffusion-shape reading, and MinAtar construction; not a replication of every original experiment. |
| [Weight-Space Programming experiments — Notes by Lex](https://github.com/lextoumbourou/weight-space-programming-experiments) | Cross-model game identification and a separate DQN checkpoint blind test with a restricted tensor reader. | Includes shape-only controls; small checkpoint samples do not establish a general success rate. |
| [WSPBench](https://github.com/alexcarterhq/wspbench) | A research preview separating unaided, weight-analysis, and instrumented conditions; public CPU replay of saved submissions. | The published pilot covers the unaided condition on small constructed circuits. Replay does not rerun model inference. |
| [Beyond Math](https://github.com/Unjuno/beyond-math-weight-space-programming) | Audit of released editing traces and paired non-math probes of base and edited checkpoints. | Separates author benchmark records from small local probes; does not reproduce the original editing search. |
| [Weight-Space Programming for the Social Safety Net](https://github.com/ctrimm/weight-space-programming) | Construction of networks implementing stipulated piecewise-linear formulas, with protocols and trained comparators. | Simplified formula experiments, not operational benefit calculators or evidence about full eligibility decisions. |

## Programs to transformer weights

Foundational and closely related work. Compilation provides a useful baseline for asking what a general-purpose LLM adds.

- **[Thinking Like Transformers](https://arxiv.org/abs/2106.06981)** — Gail Weiss, Yoav Goldberg, Eran Yahav. **ICML 2021.** Introduces RASP, a programming language expressing attention-style computations such as histograms and sorting. A conceptual basis for writing transformer algorithms.
- **[Tracr: Compiled Transformers as a Laboratory for Interpretability](https://arxiv.org/abs/2301.05062)** — David Lindner et al. **NeurIPS 2023.** Compiles readable programs into transformer weights with known structure, enabling controlled interpretability experiments. [Code](https://github.com/google-deepmind/tracr).
- **[Learning Transformer Programs](https://arxiv.org/abs/2306.01128)** — Dan Friedman, Alexander Wettig, Danqi Chen. **NeurIPS 2023.** Trains constrained transformers that can be converted into discrete, human-readable programs. This method uses gradient training; it is a related alternative, not a no-training construction result. [Code](https://github.com/princeton-nlp/TransformerPrograms).

## Learned weight generation

These methods train a weight generator. They should not be conflated with a general-purpose LLM reasoning directly over weights without task-specific generator training.

- **[HyperNetworks](https://arxiv.org/abs/1609.09106)** — David Ha, Andrew Dai, Quoc V. Le. **2016 preprint.** Uses one network to generate the weights of another, trained end-to-end. A foundational comparison for any claim about generating networks rather than optimizing each target independently.
- **[Parameter Prediction for Unseen Deep Architectures](https://arxiv.org/abs/2110.13100)** — Boris Knyazev et al. **NeurIPS 2021.** Predicts parameters from architecture graphs and introduces DeepNets-1M, providing a learned alternative to direct construction. [Code and dataset tools](https://github.com/facebookresearch/ppuda).

## Networks that process weights

Neurons can often be permuted without changing a network's function. These works help explain why raw tensor coordinates are not a unique semantic representation.

- **[Permutation Equivariant Neural Functionals](https://arxiv.org/abs/2302.14040)** — Allan Zhou et al. **NeurIPS 2023.** Builds layers that process weights while respecting neuron-permutation symmetries; applications include prediction and editing of implicit neural representations. [Code](https://github.com/AllanYangZhou/nfn).
- **[Neural Functional Transformers](https://arxiv.org/abs/2305.13546)** — Allan Zhou et al. **NeurIPS 2023.** Uses attention to construct permutation-equivariant models over weight spaces. Useful for comparing learned weight readers with general-purpose LLM readers. [Code](https://github.com/AllanYangZhou/nfn).
- **[Equivariant Deep Weight Space Alignment](https://arxiv.org/abs/2310.13397)** — Aviv Navon et al. **ICML 2024.** Learns to align networks under permutation symmetries, relevant to comparing and combining parameter representations. [Code](https://github.com/AvivNavon/deep-align).

## Related model editing

Selected comparison points for changing behavior through parameter updates; this is not a comprehensive knowledge-editing or model-merging bibliography.

- **[Locating and Editing Factual Associations in GPT](https://arxiv.org/abs/2202.05262)** — Kevin Meng et al. **NeurIPS 2022.** Introduces ROME, which localizes and edits factual associations through targeted feed-forward weight updates. It is an editing algorithm with an optimization component, not an LLM directly writing a solution from scratch. [Code](https://github.com/kmeng01/rome).
- **[Editing Models with Task Arithmetic](https://arxiv.org/abs/2212.04089)** — Gabriel Ilharco et al. **ICLR 2023.** Constructs task vectors from fine-tuned weight differences and combines them arithmetically to steer behavior. Useful for distinguishing weight composition from direct circuit synthesis. [Code](https://github.com/mlfoundations/task_vectors).

## Mechanistic foundations

- **[A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html)** — Nelson Elhage et al. **2021 research article.** Develops residual-stream, QK, and OV views of transformer computation. Supplies vocabulary for both reading trained circuits and designing explicit ones.

## About this list

Awesome Weight-Space Programming is an independent, open-source resource list for researchers, engineers, and anyone exploring neural networks as programmable artifacts. Contributions are welcome from the community.

Weight-space programming explores how an agent can inspect, construct, or modify neural network parameters to implement a specified behavior. This collection connects direct LLM-driven experiments to program compilation, learned weight generation, weight-space representations, and targeted model editing.

**Scope.** Direct weight reasoning and construction are the focus. Related papers are labeled as foundations; they need not use the term “weight-space programming.” General fine-tuning, prompt optimization, and architecture search without weight construction are outside the main scope.

**Curation.** Last curated November 3, 2026. This is a selective collection, not an exhaustive survey. Inclusion means a resource is useful to inspect; it does not mean its results have been independently reproduced here. The two originating reports are blog posts, not verified peer-reviewed publications.

### Research routes

| Research route | How weights are produced or used | Why it matters |
| --- | --- | --- |
| Direct LLM programming | An LLM reasons about tensors or writes code that assigns them. | The central topic of this list. |
| Program compilation | A compiler maps a formal program to a network. | Provides explicit mechanisms and useful correctness baselines. |
| Learned weight generation | A trained hypernetwork predicts another network's parameters. | A distinct route to generating weights. |
| Weight-space modeling | A model reads or transforms another model's parameters. | Addresses symmetries and representations of networks. |
| Targeted editing | An algorithm updates selected weights or combines task vectors. | Offers comparison points for behavior modification. |

## Reproduction checklist

When comparing results or proposing a new entry, make the experimental contract visible:

- **Target and architecture:** fixed or editable architecture; parameter, buffer, and constant storage; numerical precision.
- **Access:** weights only, tensor tools, forward passes, activations, examples, labels, or environment feedback.
- **Construction:** direct assignment, compilation, lookup tables, learned generation, or fitted coefficients.
- **Evaluation:** unseen seeds or splits, exhaustive finite-domain checks where feasible, boundary cases, and length generalization.
- **Search budget:** attempts, model identity, token usage, execution time, and selection procedure.
- **Evidence:** runnable artifacts and exact configurations; separate reported scores, independent regrading, checkpoint reruns, and fresh procedure replications.

“No gradients” alone does not imply no fitting, no feedback, or no search. A low parameter count does not imply low total storage when constants are moved into buffers or code. Constructed explanations are valuable hypotheses that still benefit from causal or equivalence checks.

## Contributing

New papers, working projects, replications, and corrections are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md), then open a pull request or [suggest a resource](https://github.com/brighterr/awesome-wsp/issues/new/choose).

Prefer primary sources and a short explanation of why the item belongs. Keep direct work separate from related foundations, and label experimental status accurately.

## Acknowledgments

List structure follows the curation principles of the [Awesome manifesto](https://github.com/sindresorhus/awesome/blob/main/awesome.md), with organizational inspiration from [Awesome Node.js](https://github.com/sindresorhus/awesome-nodejs) and [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents). The visual introduction also draws on the banner-first layouts of [Dify](https://github.com/langgenius/dify) and [n8n](https://github.com/n8n-io/n8n), and the reading hierarchy of [Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM). The cover artwork is original to this list. All research and software credit belongs to the linked authors and maintainers. The Awesome badge does not imply inclusion in the central Awesome index.

## License

This list's original text is dedicated to the public domain under [CC0 1.0](LICENSE). Linked papers, code, models, and datasets retain their respective licenses.

<sub>Also known as Awesome-WSP / awesome-wsp.</sub>
