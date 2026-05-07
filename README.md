# Parallel Financial News Event Detection and Temporal Relation Extraction Using Distributed NLP Pipelines

## Overview

This project presents a complete Natural Language Processing (NLP) pipeline for financial news analysis using domain-adapted transformer models and distributed preprocessing techniques.

The system performs:

- Financial event detection from news text
- Temporal relation extraction between financial events
- Cross-sentence event linking
- Financial timeline construction
- Parallel preprocessing benchmarking using distributed NLP pipelines

The project uses **FinBERT**, a finance-specialized transformer model, for both event classification and temporal reasoning tasks.

The pipeline combines financial NLP, temporal reasoning, graph-based event sequencing, and parallel computing into a unified end-to-end architecture.

---

# Research Contributions

## Key Contributions

- Built an end-to-end financial NLP pipeline using FinBERT
- Implemented financial event detection on Financial PhraseBank
- Implemented temporal relation extraction using MATRES
- Developed cross-sentence event linking using cosine similarity
- Constructed directed financial event timeline graphs
- Benchmarked sequential vs parallel preprocessing pipelines
- Achieved scalable preprocessing using Python ThreadPoolExecutor
- Integrated distributed NLP processing with transformer-based reasoning

---

# System Pipeline

The system consists of eight major stages:

1. Data Preparation
2. Text Preprocessing
3. Financial Event Detection
4. Cross-Sentence Event Linking
5. Temporal Relation Classification
6. Parallel Pipeline Benchmarking
7. Financial Timeline Graph Construction
8. Evaluation and Reporting

---

# Architecture

## Core Technologies

- FinBERT (ProsusAI/finbert)
- PyTorch
- HuggingFace Transformers
- spaCy
- ThreadPoolExecutor
- NetworkX
- Python NLP Pipelines

---

# Tasks Performed

## 1. Financial Event Detection

Classifies financial news sentences into:

- Positive
- Negative
- Neutral

Dataset Used:
- Financial PhraseBank

---

## 2. Temporal Relation Extraction

Predicts temporal relationships between events:

- BEFORE
- AFTER
- VAGUE

Dataset Used:
- MATRES

---

## 3. Cross-Sentence Event Linking

Links semantically related financial events using:

- FinBERT CLS embeddings
- Cosine similarity scoring
- Sliding window event matching

Dataset Used:
- FinRED

---

## 4. Timeline Construction

Builds directed temporal graphs representing chronological financial event flows.

---

# Datasets

## Financial PhraseBank

Used for financial event detection.

### Statistics
- Total Sentences: 4,885
- Training: 3,419
- Validation: 733
- Test: 733

---

## MATRES

Used for temporal relation extraction.

### Statistics
- Total Event Pairs: 13,106
- Training: 9,174
- Validation: 1,966
- Test: 1,966

### Labels
- BEFORE
- AFTER
- VAGUE

---

## FinRED

Used for cross-sentence financial event linking.

### Statistics
- Total Relation Pairs: 11,121

---

# Model Architecture

## Shared Encoder
- ProsusAI/finbert

## Neural Network Structure

```text
CLS Token
   ↓
Dropout (0.3)
   ↓
Linear Layer (768 → 256)
   ↓
ReLU Activation
   ↓
Linear Layer (256 → 64)
   ↓
ReLU Activation
   ↓
Output Layer
```

---

# Training Configuration

| Parameter | Value |
|-----------|-------|
| Optimizer | AdamW |
| Learning Rate | 2e-5 |
| Epochs | 5 |
| Batch Size | 16 |
| Max Sequence Length | 128 |
| Gradient Clipping | 1.0 |
| Dropout | 0.3 |

---

# Experimental Environment

| Component | Details |
|-----------|----------|
| Platform | Google Colab |
| GPU | NVIDIA Tesla T4 |
| Framework | PyTorch |
| NLP Library | spaCy |
| Transformer Library | HuggingFace Transformers |

---

# Results

# Financial Event Detection Results

| Metric | Score |
|--------|-------|
| Accuracy | 87.86% |
| Weighted F1 | 0.8783 |
| Precision | 0.8781 |
| Recall | 0.8786 |

### Binary Event Detection
| Metric | Score |
|--------|-------|
| Accuracy | 88.40% |
| F1-Score | 0.8557 |

---

# Temporal Relation Classification Results

| Metric | Score |
|--------|-------|
| Accuracy | 70.75% |
| Weighted F1 | 0.6643 |

## Per-Class F1 Scores

| Class | F1 Score |
|------|-----------|
| BEFORE | 0.7832 |
| AFTER | 0.7125 |
| VAGUE | 0.0308 |

---

# Cross-Sentence Linking Results

| Metric | Value |
|--------|-------|
| Candidate Pairs | 3,817 |
| Confirmed Event Pairs | 1,358 |
| Event Graph Nodes | 1,318 |
| Directed Edges | 1,358 |

---

# Parallel Processing Benchmark

## Sequential vs Parallel Preprocessing

| Documents | Sequential Time | Parallel Time | Speedup |
|-----------|-----------------|---------------|----------|
| 50 | 0.008s | 0.023s | 0.33× |
| 100 | 0.088s | 0.062s | 1.43× |
| 200 | 0.092s | 0.109s | 0.84× |
| 300 | 0.156s | 0.172s | 0.91× |
| 500 | 0.355s | 0.241s | 1.47× |

Maximum observed speedup:
- **1.47× using parallel preprocessing**

---

# Features

- Financial event detection
- Temporal reasoning between events
- FinBERT-based NLP pipeline
- Distributed preprocessing
- Parallel CPU benchmarking
- Cross-sentence event linking
- Timeline graph generation
- Financial news analytics
- Transformer-based sequence modeling
- Graph-based chronological event analysis


# Future Improvements

- Add SIMULTANEOUS temporal relation class
- Improve VAGUE class performance
- Integrate GPU-based distributed inference
- Use larger financial corpora
- Apply Graph Neural Networks
- Add real-time financial news streaming
- Implement scalable distributed event processing

---

# Authors

- Wajeeha Khalid
- Amaim Anwar

Department of Data Science  
FAST National University of Computer and Emerging Sciences  
Islamabad, Pakistan

---


# Acknowledgments

This work builds upon:

- FinBERT
- Financial PhraseBank
- MATRES
- FinRED
- HuggingFace Transformers
- spaCy NLP Framework
- Recent research in temporal relation extraction and financial NLP
