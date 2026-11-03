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

Four starting points, from the first ideas to hands-on exploration.

1. **[Sparks of WSP](https://rikiyat.github.io/blog/weight-space-programming/)** · Discover<br>
   Read behavior from weights; explore network repair and construction.

2. **[WSP from Scratch](https://csinva.io/weight-space-programming-autoresearch/analyze/toy_examples/report.html)** · Understand<br>
   Explore neural circuits for arithmetic, sorting, and parity.

3. **[Tracr](https://github.com/google-deepmind/tracr)** · Build<br>
   Compile readable programs into transformer weights.

4. **[Community Experiments](#community-experiments-and-benchmarks)** · Explore<br>
   Find replications, weight-reading tests, and evaluation tools.

## Research library

Begin with direct experiments and community projects, then explore the foundations.

[Direct work](#direct-weight-space-programming) · [Community](#community-experiments-and-benchmarks) · [Compilers](#programs-to-transformer-weights) · [Weight generation](#learned-weight-generation) · [Weight-space models](#networks-that-process-weights) · [Model editing](#related-model-editing) · [Foundations](#mechanistic-foundations)

### Direct weight-space programming

#### Sparks of Weight-Space Programming

<sub>Rikiya Takehi, Jayden Teoh, Alex Zhang, Omar Khattab · 2026 · Blog + released experiment artifacts</sub>

[Article](https://rikiyat.github.io/blog/weight-space-programming/) · [Code, logs and networks](https://github.com/RikiyaT/lm_understand-logs)

Explores identifying network behavior from weights, repairing a control policy, writing game-playing networks, and editing a language model.

Useful for studying the difference between reading weights, constructing a network, and repairing an existing one.

<details>
<summary>Experimental conditions & evidence</summary>

- **Access conditions vary:** some experiments use a single response without tools; others allow an external Python sandbox and bounded feedback. The repository documents these conditions per experiment.
- **Evidence note:** the release contains reported runs, not all earlier prompt trials. Its README lists omitted artifacts and reconstruction instructions; do not interpret the release as an exhaustive search history.

</details>

#### Weight-Space Programming from scratch on simple tasks

<sub>Chandan Singh · 2026 · Blog + autonomous coding experiments</sub>

[Article and interactive circuits](https://csinva.io/weight-space-programming-autoresearch/analyze/toy_examples/report.html) · [Code and snapshots](https://github.com/csinva/weight-space-programming-autoresearch) · [Agent instructions](https://github.com/csinva/weight-space-programming-autoresearch/blob/main/evolve/program.md)

An agent assigns small transformer weights and may change the architecture, then iterates using evaluation feedback.

Covers arithmetic, sorting, parity, counting, Boolean expressions, and other bounded tasks; the saved programs make concrete circuit inspection possible.

<details>
<summary>Experimental conditions & evidence</summary>

- **Evidence note:** reported algorithmic scores use finite evaluation samples. The article acknowledges evaluation leakage in language tasks, fitting in the SNLI run, and parameter-count gaming through buffers. These are not valid demonstrations of general training-free language understanding.

</details>

### Community experiments and benchmarks

Community work, listed separately from the original reports. Summarized from public sources; not independently rerun here.

- **[Weight-Space Claude](https://github.com/nihilistau/weight-space-claude)**<br>
  A Claude-based harness, scorers, and side-by-side results for selected Sparks prompts.

- **[Weight-Space Programming experiments — Notes by Lex](https://github.com/lextoumbourou/weight-space-programming-experiments)**<br>
  Cross-model game identification and a separate DQN checkpoint blind test with a restricted tensor reader.

- **[WSPBench](https://github.com/alexcarterhq/wspbench)**<br>
  A research preview separating unaided, weight-analysis, and instrumented conditions; public CPU replay of saved submissions.

- **[Beyond Math](https://github.com/Unjuno/beyond-math-weight-space-programming)**<br>
  Audit of released editing traces and paired non-math probes of base and edited checkpoints.

- **[Weight-Space Programming for the Social Safety Net](https://github.com/ctrimm/weight-space-programming)**<br>
  Construction of networks implementing stipulated piecewise-linear formulas, with protocols and trained comparators.

<details>
<summary>Project scope & reproduction notes</summary>

Early community projects are listed separately from the originating reports. Descriptions below summarize public READMEs checked on the curation date; we have not rerun their experiments. A replay of saved outputs, a checkpoint evaluation, and a fresh replication of an editing procedure are different forms of evidence.

- **Weight-Space Claude** — Covers game identification, diffusion-shape reading, and MinAtar construction; not a replication of every original experiment.
- **Weight-Space Programming experiments — Notes by Lex** — Includes shape-only controls; small checkpoint samples do not establish a general success rate.
- **WSPBench** — The published pilot covers the unaided condition on small constructed circuits. Replay does not rerun model inference.
- **Beyond Math** — Separates author benchmark records from small local probes; does not reproduce the original editing search.
- **Weight-Space Programming for the Social Safety Net** — Simplified formula experiments, not operational benefit calculators or evidence about full eligibility decisions.

</details>

### Programs to transformer weights

Foundational and closely related work. Compilation provides a useful baseline for asking what a general-purpose LLM adds.

- **[Thinking Like Transformers](https://arxiv.org/abs/2106.06981)**<br>
  <sub>Gail Weiss, Yoav Goldberg, Eran Yahav. ICML 2021.</sub>

  Introduces RASP, a programming language expressing attention-style computations such as histograms and sorting. A conceptual basis for writing transformer algorithms.

- **[Tracr: Compiled Transformers as a Laboratory for Interpretability](https://arxiv.org/abs/2301.05062)**<br>
  <sub>David Lindner et al. NeurIPS 2023.</sub>

  Compiles readable programs into transformer weights with known structure, enabling controlled interpretability experiments. [Code](https://github.com/google-deepmind/tracr).

- **[Learning Transformer Programs](https://arxiv.org/abs/2306.01128)**<br>
  <sub>Dan Friedman, Alexander Wettig, Danqi Chen. NeurIPS 2023.</sub>

  Trains constrained transformers that can be converted into discrete, human-readable programs. This method uses gradient training; it is a related alternative, not a no-training construction result. [Code](https://github.com/princeton-nlp/TransformerPrograms).


### Learned weight generation

These methods train a weight generator. They should not be conflated with a general-purpose LLM reasoning directly over weights without task-specific generator training.

- **[HyperNetworks](https://arxiv.org/abs/1609.09106)**<br>
  <sub>David Ha, Andrew Dai, Quoc V. Le. 2016 preprint.</sub>

  Uses one network to generate the weights of another, trained end-to-end. A foundational comparison for any claim about generating networks rather than optimizing each target independently.

- **[Parameter Prediction for Unseen Deep Architectures](https://arxiv.org/abs/2110.13100)**<br>
  <sub>Boris Knyazev et al. NeurIPS 2021.</sub>

  Predicts parameters from architecture graphs and introduces DeepNets-1M, providing a learned alternative to direct construction. [Code and dataset tools](https://github.com/facebookresearch/ppuda).


### Networks that process weights

Neurons can often be permuted without changing a network's function. These works help explain why raw tensor coordinates are not a unique semantic representation.

- **[Permutation Equivariant Neural Functionals](https://arxiv.org/abs/2302.14040)**<br>
  <sub>Allan Zhou et al. NeurIPS 2023.</sub>

  Builds layers that process weights while respecting neuron-permutation symmetries; applications include prediction and editing of implicit neural representations. [Code](https://github.com/AllanYangZhou/nfn).

- **[Neural Functional Transformers](https://arxiv.org/abs/2305.13546)**<br>
  <sub>Allan Zhou et al. NeurIPS 2023.</sub>

  Uses attention to construct permutation-equivariant models over weight spaces. Useful for comparing learned weight readers with general-purpose LLM readers. [Code](https://github.com/AllanYangZhou/nfn).

- **[Equivariant Deep Weight Space Alignment](https://arxiv.org/abs/2310.13397)**<br>
  <sub>Aviv Navon et al. ICML 2024.</sub>

  Learns to align networks under permutation symmetries, relevant to comparing and combining parameter representations. [Code](https://github.com/AvivNavon/deep-align).


### Related model editing

Selected comparison points for changing behavior through parameter updates; this is not a comprehensive knowledge-editing or model-merging bibliography.

- **[Locating and Editing Factual Associations in GPT](https://arxiv.org/abs/2202.05262)**<br>
  <sub>Kevin Meng et al. NeurIPS 2022.</sub>

  Introduces ROME, which localizes and edits factual associations through targeted feed-forward weight updates. It is an editing algorithm with an optimization component, not an LLM directly writing a solution from scratch. [Code](https://github.com/kmeng01/rome).

- **[Editing Models with Task Arithmetic](https://arxiv.org/abs/2212.04089)**<br>
  <sub>Gabriel Ilharco et al. ICLR 2023.</sub>

  Constructs task vectors from fine-tuned weight differences and combines them arithmetically to steer behavior. Useful for distinguishing weight composition from direct circuit synthesis. [Code](https://github.com/mlfoundations/task_vectors).


### Mechanistic foundations

- **[A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html)**<br>
  <sub>Nelson Elhage et al. 2021 research article.</sub>

  Develops residual-stream, QK, and OV views of transformer computation. Supplies vocabulary for both reading trained circuits and designing explicit ones.


## About this list

[Reproduction checklist](#reproduction-checklist) · [Contributing](#contributing) · [Acknowledgments](#acknowledgments) · [License](#license)

Awesome Weight-Space Programming is an independent, open-source resource list for researchers, engineers, and anyone exploring neural networks as programmable artifacts. Contributions are welcome from the community.

Weight-space programming explores how an agent can inspect, construct, or modify neural network parameters to implement a specified behavior. This collection connects direct LLM-driven experiments to program compilation, learned weight generation, weight-space representations, and targeted model editing.

**Scope.** Direct weight reasoning and construction are the focus. Related papers are labeled as foundations; they need not use the term “weight-space programming.” General fine-tuning, prompt optimization, and architecture search without weight construction are outside the main scope.

**Curation.** Last curated November 3, 2026. This is a selective collection, not an exhaustive survey. Inclusion means a resource is useful to inspect; it does not mean its results have been independently reproduced here. The two originating reports are blog posts, not verified peer-reviewed publications.

<details>
<summary>Compare five research routes</summary>

### Research routes

| Research route | How weights are produced or used | Why it matters |
| --- | --- | --- |
| Direct LLM programming | An LLM reasons about tensors or writes code that assigns them. | The central topic of this list. |
| Program compilation | A compiler maps a formal program to a network. | Provides explicit mechanisms and useful correctness baselines. |
| Learned weight generation | A trained hypernetwork predicts another network's parameters. | A distinct route to generating weights. |
| Weight-space modeling | A model reads or transforms another model's parameters. | Addresses symmetries and representations of networks. |
| Targeted editing | An algorithm updates selected weights or combines task vectors. | Offers comparison points for behavior modification. |

</details>

## Reproduction checklist

<details>
<summary>Open the reproduction checklist</summary>

When comparing results or proposing a new entry, make the experimental contract visible:

- **Target and architecture:** fixed or editable architecture; parameter, buffer, and constant storage; numerical precision.
- **Access:** weights only, tensor tools, forward passes, activations, examples, labels, or environment feedback.
- **Construction:** direct assignment, compilation, lookup tables, learned generation, or fitted coefficients.
- **Evaluation:** unseen seeds or splits, exhaustive finite-domain checks where feasible, boundary cases, and length generalization.
- **Search budget:** attempts, model identity, token usage, execution time, and selection procedure.
- **Evidence:** runnable artifacts and exact configurations; separate reported scores, independent regrading, checkpoint reruns, and fresh procedure replications.

“No gradients” alone does not imply no fitting, no feedback, or no search. A low parameter count does not imply low total storage when constants are moved into buffers or code. Constructed explanations are valuable hypotheses that still benefit from causal or equivalence checks.

</details>

## Contributing

New papers, working projects, replications, and corrections are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md), then open a pull request or [suggest a resource](https://github.com/brighterr/awesome-wsp/issues/new/choose).

Prefer primary sources and a short explanation of why the item belongs. Keep direct work separate from related foundations, and label experimental status accurately.

## Acknowledgments

<details>
<summary>Design references & acknowledgments</summary>

List structure follows the curation principles of the [Awesome manifesto](https://github.com/sindresorhus/awesome/blob/main/awesome.md), with organizational inspiration from [Awesome Node.js](https://github.com/sindresorhus/awesome-nodejs) and [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents). The visual introduction also draws on the banner-first layouts of [Dify](https://github.com/langgenius/dify) and [n8n](https://github.com/n8n-io/n8n), and the reading hierarchy of [Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM). The cover artwork is original to this list. All research and software credit belongs to the linked authors and maintainers. The Awesome badge does not imply inclusion in the central Awesome index.

</details>

## License

This list's original text is dedicated to the public domain under [CC0 1.0](LICENSE). Linked papers, code, models, and datasets retain their respective licenses.

<sub>Also known as Awesome-WSP / awesome-wsp.</sub>
