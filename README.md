# Multimodal Paper Reading

> A systematic study of multimodal learning through paper reading, from-scratch PyTorch implementations, mini experiments, and research-oriented analysis.

## 🎯 Goal

This repository records my learning journey in multimodal machine learning.

Instead of only reading papers, I aim to build a complete learning loop:

**Paper Reading → Understanding → Implementation → Experiment → Analysis → Research Insight**

The long-term goal is to develop the ability to:

- understand modern multimodal architectures;
- translate mathematical formulations into PyTorch implementations;
- reproduce core ideas from research papers;
- design controlled experiments;
- analyze model behavior rather than only report results;
- identify limitations and potential research questions;
- build a solid foundation for future research in multimodal learning, parameter-efficient fine-tuning, and federated multimodal learning.

---

# 🗺️ Learning Roadmap

## Stage 1 — Transformer Foundations

### 01. Attention Is All You Need

**Topics**

- Self-Attention
- Scaled Dot-Product Attention
- Multi-Head Attention
- Feed Forward Network
- Residual Connection
- Positional Encoding

**Implementation**

- [ ] Scaled Dot-Product Attention
- [ ] Multi-Head Attention
- [ ] Feed Forward Network
- [ ] Transformer Block
- [ ] Positional Encoding
- [ ] Minimal Transformer model

**Experiment**

- [ ] Visualize attention maps
- [ ] Compare different numbers of attention heads
- [ ] Analyze tensor shapes throughout the model

---

## Stage 2 — Vision Transformer

### 02. An Image is Worth 16×16 Words

**Topics**

- Patch Embedding
- CLS Token
- Position Embedding
- Transformer for vision
- CNN vs Transformer inductive bias

**Implementation**

- [ ] Patch Embedding
- [ ] Vision Transformer block
- [ ] Minimal ViT classifier

**Experiment**

- [ ] Compare different patch sizes
- [ ] Compare model parameter counts
- [ ] Visualize image patches

---

# 🌉 Stage 3 — Vision-Language Alignment

## 03. CLIP

**Paper**

Learning Transferable Visual Models From Natural Language Supervision

**Topics**

- Image Encoder
- Text Encoder
- Shared Embedding Space
- Contrastive Learning
- Temperature Scaling
- Zero-shot Classification

**Implementation**

- [ ] Image encoder interface
- [ ] Text encoder
- [ ] Feature normalization
- [ ] Image-text similarity matrix
- [ ] Contrastive loss
- [ ] Zero-shot inference

**Experiment**

- [ ] Temperature ablation
- [ ] Embedding dimension comparison
- [ ] Zero-shot image classification
- [ ] Image-text retrieval

---

# 🧠 Stage 4 — Vision-Language Pretraining

## 04. BLIP

Focus:

- multimodal encoder-decoder architecture;
- image-text contrastive learning;
- image-text matching;
- language modeling;
- data bootstrapping.

Tasks:

- [ ] Read paper
- [ ] Architecture diagram
- [ ] Understand training objectives
- [ ] Analyze CapFilt
- [ ] Implement simplified components

---

# 🔗 Stage 5 — Connecting Vision Models and LLMs

## 05. Flamingo

Focus:

- Perceiver Resampler
- Gated Cross-Attention
- Frozen vision encoder
- Frozen language model
- Interleaved image-text sequences

Tasks:

- [ ] Understand architecture
- [ ] Implement simplified cross-attention
- [ ] Analyze parameter-efficient multimodal adaptation

---

## 06. BLIP-2

Architecture:

```text
Frozen Vision Encoder
        ↓
     Q-Former
        ↓
    Frozen LLM
```

Focus:

- modality gap;
- Querying Transformer;
- frozen pretrained models;
- two-stage training.

Tasks:

- [ ] Understand Q-Former
- [ ] Draw complete architecture
- [ ] Study two-stage training
- [ ] Implement simplified Query Transformer
- [ ] Compare BLIP vs BLIP-2

---

# 💬 Stage 6 — Multimodal Large Language Models

## 07. LLaVA

Architecture:

```text
Image
  ↓
CLIP Vision Encoder
  ↓
Projection Layer
  ↓
LLM
  ↓
Response
```

Focus:

- Visual Instruction Tuning
- Vision-Language Alignment
- Multimodal instruction data
- Projection layers
- LLM fine-tuning

Tasks:

- [ ] Study training stages
- [ ] Understand instruction dataset construction
- [ ] Implement simplified multimodal projector
- [ ] Analyze trainable parameters

---

## 08. InstructBLIP

Focus:

- instruction-aware visual feature extraction;
- Q-Former;
- comparison with BLIP-2 and LLaVA.

Tasks:

- [ ] Compare BLIP-2 / InstructBLIP / LLaVA
- [ ] Analyze architecture differences
- [ ] Analyze instruction tuning strategies

---

# 🌐 Stage 7 — Beyond Vision-Language

## 09. ImageBind

Modalities:

- Image
- Text
- Audio
- Depth
- Thermal
- IMU

Focus:

- joint embedding space;
- multimodal alignment;
- image as an alignment anchor.

Tasks:

- [ ] Understand joint embedding learning
- [ ] Compare CLIP and ImageBind
- [ ] Explore multimodal retrieval

---

# 🔬 Stage 8 — Modern MLLM Training

## 10. MM1

Focus:

- multimodal pretraining;
- data mixture;
- model architecture;
- connector design;
- instruction tuning.

Main question:

> What actually matters when training a multimodal large language model?

Tasks:

- [ ] Analyze data composition
- [ ] Analyze architecture choices
- [ ] Summarize empirical findings
- [ ] Compare with LLaVA and BLIP-2

---

# 🚀 Stage 9 — Modern Multimodal Models

## 11. Qwen-VL Series

Focus:

- dynamic resolution;
- OCR;
- document understanding;
- grounding;
- video understanding;
- multimodal agents.

Tasks:

- [ ] Study Qwen-VL architecture evolution
- [ ] Compare different generations
- [ ] Analyze modern MLLM design trends

---

# 🧪 Mini Projects

Paper reproduction is only the first step.

The following projects will integrate knowledge learned across multiple papers.

## Mini Project 1 — Mini CLIP

Build a lightweight CLIP implementation from scratch.

Pipeline:

```text
Image
 ↓
Vision Encoder
 ↓
Embedding
       ↘
        Contrastive Loss
       ↗
Embedding
 ↑
Text Encoder
 ↑
Text
```

Goals:

- train a small CLIP model;
- implement contrastive learning;
- perform image-text retrieval;
- perform zero-shot classification.

---

## Mini Project 2 — LoRA for Vision-Language Models

Compare:

- Full Fine-tuning
- Frozen Backbone
- LoRA

Metrics:

- Trainable Parameters
- GPU Memory
- Training Time
- Accuracy / Task Performance

Experiments:

- [ ] rank = 2
- [ ] rank = 4
- [ ] rank = 8
- [ ] rank = 16

---

## Mini Project 3 — Federated Multimodal Learning

Explore multimodal learning under federated settings.

Potential questions:

- How does multimodal Non-IID affect aggregation?
- Which multimodal parameters should be shared?
- Should vision and language LoRA modules use the same aggregation strategy?
- Can different clients use different LoRA ranks?
- How should modality-specific knowledge be preserved?

---

# 📄 Standard Workflow for Every Paper

Every paper should go through the following process.

## Step 1 — Read

Focus on:

1. Problem
2. Existing limitation
3. Core idea
4. Architecture
5. Training objective
6. Experiments
7. Limitations

---

## Step 2 — Explain Without Notes

After reading, I should be able to explain the paper in 3–5 minutes:

```text
Problem
↓
Why existing methods fail
↓
Proposed method
↓
Why it works
↓
Experimental evidence
↓
Limitations
```

---

## Step 3 — Draw the Architecture

Reconstruct the architecture without looking at the paper.

If I cannot draw it, I probably do not fully understand it.

---

## Step 4 — Implement the Core Idea

Do not immediately reproduce the complete repository.

First implement the smallest meaningful component.

Examples:

```text
Transformer → Multi-Head Attention

ViT → Patch Embedding

CLIP → Contrastive Loss

BLIP-2 → Q-Former

LLaVA → Multimodal Projector

LoRA → LoRALinear
```

---

## Step 5 — Run a Mini Experiment

Every implementation should answer at least one question.

Examples:

- What happens when the number of attention heads changes?
- How does patch size affect ViT?
- How does CLIP temperature affect contrastive learning?
- How does LoRA rank affect trainable parameters?
- Which layers are worth fine-tuning?

---

## Step 6 — Research Reflection

Each paper should end with:

### What I Learned

What new concept did this paper teach me?

### Limitations

What assumptions or weaknesses exist?

### Research Questions

What questions remain unanswered?

### Connection to My Research

Can this idea be applied to:

- multimodal learning;
- LoRA / PEFT;
- federated learning;
- multimodal Non-IID?

---

# 📊 Progress

| # | Paper | Notes | Implementation | Experiment | Research Insight |
|---|---|---|---|---|---|
| 01 | Transformer | ⬜ | ⬜ | ⬜ | ⬜ |
| 02 | ViT | ⬜ | ⬜ | ⬜ | ⬜ |
| 03 | CLIP | ⬜ | ⬜ | ⬜ | ⬜ |
| 04 | BLIP | ⬜ | ⬜ | ⬜ | ⬜ |
| 05 | Flamingo | ⬜ | ⬜ | ⬜ | ⬜ |
| 06 | BLIP-2 | ⬜ | ⬜ | ⬜ | ⬜ |
| 07 | LLaVA | ⬜ | ⬜ | ⬜ | ⬜ |
| 08 | InstructBLIP | ⬜ | ⬜ | ⬜ | ⬜ |
| 09 | ImageBind | ⬜ | ⬜ | ⬜ | ⬜ |
| 10 | MM1 | ⬜ | ⬜ | ⬜ | ⬜ |
| 11 | Qwen-VL | ⬜ | ⬜ | ⬜ | ⬜ |

Legend:

- ⬜ Not started
- 🟡 In progress
- ✅ Completed

---

# 📁 Repository Structure

```text
multimodal-paper-reading/
│
├── README.md
├── requirements.txt
│
├── 01-transformer/
│   ├── README.md
│   ├── notes.md
│   ├── src/
│   ├── experiments/
│   └── results/
│
├── 02-vit/
├── 03-clip/
├── 04-blip/
├── 05-flamingo/
├── 06-blip2/
├── 07-llava/
├── 08-instructblip/
├── 09-imagebind/
├── 10-mm1/
├── 11-qwen-vl/
│
├── mini-projects/
│   ├── mini-clip/
│   ├── vlm-lora/
│   └── federated-multimodal/
│
└── research-notes/
    ├── multimodal-roadmap.md
    ├── paper-comparison.md
    └── ideas.md
```

---

# ✅ Definition of Done

A paper is considered **completed** only when:

- [ ] I have read the paper.
- [ ] I have written structured notes.
- [ ] I can explain the main idea without notes.
- [ ] I can draw the architecture.
- [ ] I understand the core equations.
- [ ] I have implemented at least one core component.
- [ ] I have run at least one experiment.
- [ ] I have recorded the experimental result.
- [ ] I have written limitations.
- [ ] I have written at least one research question.

Simply watching a lecture or reading the paper does **not** count as completion.

---

# 🧾 Commit Convention

Use meaningful Git commits to record the learning process.

Examples:

```text
docs: add Transformer paper notes

feat: implement scaled dot-product attention

feat: implement multi-head attention

test: verify attention tensor shapes

exp: compare different attention heads

docs: analyze Transformer experiment results
```

Recommended prefixes:

```text
docs:
feat:
fix:
test:
exp:
refactor:
```

---

# 🛠️ Environment

Main tools:

- Python
- PyTorch
- CUDA
- Jupyter Notebook
- Hugging Face Transformers
- Git / GitHub

The goal is to implement core ideas from scratch whenever practical, while using established libraries for large-scale experiments.

---

# 🌱 Long-Term Goal

The purpose of this repository is not to collect as many papers as possible.

The goal is to gradually build the ability to:

```text
Read Research
      ↓
Understand Research
      ↓
Implement Research
      ↓
Experiment
      ↓
Critically Analyze
      ↓
Generate Research Ideas
      ↓
Conduct Independent Research
```

Ultimately, this repository will evolve from a paper-reading record into a research portfolio in multimodal machine learning.
