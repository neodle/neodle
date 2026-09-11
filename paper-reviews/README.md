# 📚 Paper Notes: Efficient Machine Intelligence (2026)

My reading notes on the **2026 papers from the [Efficient Machine Intelligence Lab](https://emilab-ku.github.io/), Korea University**.<br/>
Each note follows the same format: **TL;DR → Problem → Key Idea → Results → My Takeaway**.

[← Back to profile](../README.md)

| # | Paper | Venue | Theme |
|:---:|---|---|---|
| 1 | [ZOO-Prune](#zoo-prune) | CVPR 2026 | Token pruning for VLMs |
| 2 | [VisRef](#visref) | CVPR 2026 | Test-time scaling for multimodal reasoning |
| 3 | [Real-Time Visual Attribution Streaming](#visual-attribution) | ICML 2026 Spotlight | Amortized attribution for thinking models |
| 4 | [Block Recursive Transformers](#block-recursive) | EMNLP 2026 Findings | Structured parameter sharing |
| 5 | [MD-SNN](#md-snn) | DATE 2026 | Quantized spiking neural networks |
| 6 | [MC-GRPO](#mc-grpo) | Preprint | Small-rollout RL for LLMs |
| 7 | [SkillRet](#skillret) | Preprint | Skill retrieval for LLM agents |

---

<a id="zoo-prune"></a>
## 1. ZOO-Prune: Training-Free Token Pruning via Zeroth-Order Gradient Estimation in Vision-Language Models
`CVPR 2026` · Youngeun Kim\*, Youjia Zhang\*, Huiling Liu, Aecheon Jung, Sunwoo Lee, Sungeun Hong · [arXiv](https://arxiv.org/abs/2509.24837) · [Project](https://aim-skku.github.io/ZOO-Prune/)

**TL;DR**: Find which visual tokens really matter by adding small random perturbations at the projection layer, then keep only those tokens. No training and no backpropagation.

- **Problem**: Large VLMs spend most of their compute on redundant visual tokens. Attention-based pruning depends on attention scores that are unstable across layers and heads. Diversity-based pruning can drop regions the prediction actually needs.
- **Key Idea**: Estimate each token's **sensitivity** with zeroth-order perturbations applied only at the lightweight projection layer. Highly sensitive tokens influence the output more and carry *complementary* rather than redundant visual cues.
- **Results**
  - LLaVA-1.5-7B: pruning **88.9%** of tokens (keeping 64) retains **95.5%** of performance
  - LLaVA-NeXT-7B: pruning **94.4%** of tokens (keeping 160 of 2,880) retains **95.4%** of performance
  - Up to **2.30× faster** end-to-end inference
- **My Takeaway**: The trick is to measure importance where it is cheapest to probe (the projector) instead of through the whole LLM. In my Lightweight CycleGAN work I cut blocks and channels by hand. This paper shows a *data-dependent*, training-free way to decide what to cut, and I'd like to try the same idea on generative pipelines like my FLUX work, where most image tokens are background.

---

<a id="visref"></a>
## 2. VisRef: Visual Refocusing while Thinking Improves Test-Time Scaling in Multi-Modal Large Reasoning Models
`CVPR 2026` · Soumya Suvra Ghosal\*, Youngeun Kim\*, Zhuowei Li, Ritwick Chaudhry, Linghan Xu, Hongjing Zhang, Jakub Zablocki, Yifan Xing, Qin Zhang · [CVPR Open Access](https://openaccess.thecvf.com/CVPR2026)

**TL;DR**: As multimodal reasoning models "think" longer, they gradually stop looking at the image. VisRef re-injects a small, well-chosen set of visual tokens during reasoning.

- **Problem**: In vision-dependent tasks, longer textual reasoning at inference time can *hurt* accuracy. The model loses attention to visual tokens and relies more and more on textual priors.
- **Key Idea**: A visually grounded test-time scaling framework that needs **no extra RL fine-tuning**. During reasoning, it re-injects a **coreset of visual tokens** that are relevant to the current reasoning context and also diverse and representative of the whole image.
- **Results**: On three visual reasoning benchmarks with state-of-the-art multimodal reasoning models, VisRef beats existing test-time scaling methods by **up to 6.4%** under the same compute budget.
- **My Takeaway**: This is the mirror image of ZOO-Prune. One paper *removes* tokens to save compute, the other *re-adds* a few tokens to spend compute better. Both depend on choosing a small, representative token subset, which suggests token selection is a central tool of efficient multimodal AI.

---

<a id="visual-attribution"></a>
## 3. Real-Time Visual Attribution Streaming in Thinking Model
`ICML 2026 · Spotlight` · Seil Kang, Woojung Han, Junhyeok Kim, Jinyeong Kim, Youngeun Kim, Seong Jae Hwang · [arXiv](https://arxiv.org/abs/2604.16587)

**TL;DR**: Shows *which image regions* a thinking model relies on, streamed live while it reasons, at close to the faithfulness of expensive causal methods.

- **Problem**: Multimodal thinking models produce long reasoning traces (e.g., code from a screenshot, math from an image) that should be grounded in visual evidence. Causal attribution is faithful but needs many repeated backward passes. Attention maps are instant but unreliable.
- **Key Idea**: An **amortized** framework that learns to estimate the causal effect of semantic image regions from signals already present in attention features. The cost of attribution is paid once during training rather than on every query.
- **Results**: On five benchmarks and four thinking models, faithfulness is **comparable to exhaustive causal methods**, while attribution streams in real time.
- **My Takeaway**: Amortization is an efficiency idea in its own right: replace a costly per-sample procedure with a lightweight learned predictor. It's similar in spirit to how I used a small GCN to refine YOLO keypoints at almost no FPS cost.

---

<a id="block-recursive"></a>
## 4. Block Recursive Transformers for Structured Parameter Sharing
`EMNLP 2026 Findings` · Josep Marques, HyunYoung Cho, Youngeun Kim, Youjia Zhang, Aecheon Jung, Kyuhong Shim, Sungeun Hong

> ⏳ The full paper was not publicly available when I wrote this note, so this section covers background only. I'll update it once the paper is out.

- **Background**: Recursive Transformers compress models by **reusing the same block of layers in a loop**, so there are far fewer unique parameters. Earlier work such as [Relaxed Recursive Transformers](https://arxiv.org/abs/2410.20672) relaxes strict layer tying with depth-wise LoRA to recover accuracy.
- **What I want to learn from this paper**: how *block-level* (structured) sharing chooses which layers to tie, and how it balances parameter savings against accuracy compared with full-model recursion.
- **My Takeaway (so far)**: This is the architectural side of compression. My Lightweight CycleGAN reduced the *number* of residual blocks; parameter sharing keeps depth but removes redundant *weights*, a different axis I haven't explored yet.

---

<a id="md-snn"></a>
## 5. MD-SNN: Membrane Potential-aware Distillation on Quantized Spiking Neural Network
`DATE 2026` · Donghyun Lee, Abhishek Moitra, Youngeun Kim, Ruokai Yin, Priyadarshini Panda · [arXiv](https://arxiv.org/abs/2512.04443)

**TL;DR**: Quantizing SNNs disturbs the membrane potential that decides when neurons spike. MD-SNN uses the membrane potential itself as the distillation target to fix this.

- **Problem**: SNNs are energy-efficient thanks to sparse binary spikes, but their spatio-temporal dynamics still cost memory and compute. Naive quantization creates a **membrane potential mismatch**, which changes spike firing and lowers accuracy.
- **Key Idea**: **Membrane potential-aware knowledge distillation** that reduces the mismatch after quantizing weights, membrane potentials, and batch normalization. According to the authors, this is the first use of membrane potential KD in SNNs.
- **Results**: Evaluated on CIFAR-10, CIFAR-100, N-Caltech101, and TinyImageNet. On N-Caltech101 (SpikeSim hardware evaluation) compared with floating-point SNNs:
  - **14.85×** lower energy-delay-area product
  - **2.64×** higher TOPS/W
  - **6.19×** higher TOPS/mm²
- **My Takeaway**: A good reminder that you should distill the signal that actually drives the model's behavior, not just its outputs. It also shows that efficiency claims are strongest when they're backed by hardware metrics, not only FLOPs.

---

<a id="mc-grpo"></a>
## 6. MC-GRPO: Median-Centered Group Relative Policy Optimization for Small-Rollout Reinforcement Learning
`Preprint` · Youngeun Kim · [arXiv](https://arxiv.org/abs/2601.22582)

**TL;DR**: With only a few rollouts per prompt, GRPO's mean baseline gets noisy. Switching to a median baseline stabilizes training at almost no extra cost.

- **Problem**: GRPO-style methods normalize rewards against the mean reward of a group of rollouts. When the rollout budget is small, the mean is noisy and causes **advantage sign flips**: some completions receive the wrong-direction learning signal.
- **Key Idea**: Generate **G+1** rollouts and use the **group median** as the baseline. The median completion gets zero advantage and is excluded from backprop, so the number of gradient-contributing samples stays at G.
- **Results**: Consistently stabilizes training across GRPO-family methods and model scales. The gap between **G=2 and G=8 shrinks to within 1%**, while the core update cost stays the same as standard G-rollout training.
- **My Takeaway**: Efficiency here comes from *statistics*, not architecture: a more robust estimator makes a small compute budget behave like a large one. It's a simple change with a clear failure analysis (sign flips), which I find very convincing.

---

<a id="skillret"></a>
## 7. SkillRet: A Large-Scale Benchmark for Skill Retrieval in LLM Agents
`Preprint` · Ryangkyung Kang, Hongcheol Cho, Youngeun Kim · [arXiv](https://arxiv.org/abs/2605.05726)

**TL;DR**: As LLM agents gain thousands of reusable skills, picking the right one becomes a retrieval problem. SkillRet is a benchmark and training set for it.

- **Problem**: With small skill libraries, users can call skills by name. That assumption breaks as skill ecosystems grow under tight context and latency budgets, and skill retrieval had few benchmarks.
- **Key Idea**: A benchmark with **16,129** public agent skills, semantic tags, and a two-level taxonomy (6 categories, 18 sub-categories). It provides **63,259** training samples and **4,392** evaluation queries with disjoint skill pools.
- **Results**: Off-the-shelf retrievers struggle on realistic large libraries. Fine-tuning on SkillRet improves **NDCG@10 by 12.9 points** over the strongest prior skill retriever and **16.2 points** over the strongest off-the-shelf retriever. The gains come from better focus on small skill-relevant signals in long, noisy queries.
- **My Takeaway**: I used skill- and harness-based agent workflows (Claude Code) during my ETRI internship, so this problem feels concrete to me. Loading every skill into context doesn't scale, and retrieval is the efficient alternative.

---

## 🔭 Common Threads I Noticed

1. **Choose a small, representative subset**: tokens (ZOO-Prune, VisRef), skills (SkillRet), rollouts (MC-GRPO).
2. **Replace expensive procedures with cheap estimators**: zeroth-order perturbation instead of backprop, amortized attribution instead of repeated causal passes, a median instead of a noisy mean.
3. **Compress without losing what matters**: parameter sharing (Block Recursive Transformers) and quantization guided by the right internal signal (MD-SNN).
