# System Architecture and Dataset Documentation

## 1. Problem Statement

Traditional agricultural AI systems perform disease classification and only predict disease labels.

Example:

Input:
Potato tuber image

Output:
"Black Scurf"

While useful, this does not explain:

- What symptoms are visible
- Disease severity
- Affected regions
- Surface abnormalities

This project solves this by generating natural language descriptions.

Example:

"The potato tuber shows moderate black scurf infection with visible dark lesions distributed across the surface."

---

# 2. Complete System Pipeline

┌────────────────────┐
│ Raw Agricultural Images │
└──────────┬─────────┘
│
▼
┌────────────────────┐
│ Image Preprocessing │
└──────────┬─────────┘
│
▼
┌────────────────────┐
│ Caption Processing │
└──────────┬─────────┘
│
▼
┌────────────────────┐
│ Dataset Splitting │
└──────────┬─────────┘
│
▼
┌────────────────────┐
│ Model Training │
└──────────┬─────────┘
│
▼
┌────────────────────┐
│ Caption Generation │
└──────────┬─────────┘
│
▼
┌────────────────────┐
│ Evaluation │
└────────────────────┘

---

# 3. Dataset Overview

## Image Source

Images were captured under real field conditions using:

- Vivo V27
- Vivo 1189
- iPhone
- Poco
- Realme

This introduces:

- Lighting variations
- Angle variations
- Device variability
- Background variability

which improves real-world robustness.

---

# 4. Disease Severity Structure

Each disease category contains:

Healthy
Mild
Moderate
Severe

This enables severity-aware caption generation.

---

# 5. Dataset Organization

dataset/

├── train/
│ ├── images/
│ └── captions.json
│
├── val/
│ ├── images/
│ └── captions.json
│
└── test/
├── images/
└── captions.json

---

# 6. Image Preprocessing Pipeline

## Step 1

Image Verification

- Remove corrupt images
- Verify readability

## Step 2

Image Cropping

- Remove unnecessary background
- Focus on tuber region

## Step 3

RGB Conversion

Convert all images to RGB.

## Step 4

Resizing

Images resized according to model requirements.

Examples:

- ViT → 224×224
- BLIP → 384×384

## Step 5

Normalization

Normalize pixel values.

---

# 7. Caption Preprocessing

## Operations

### Lowercasing

Before:

Moderate Black Scurf Infection

After:

moderate black scurf infection

### Cleaning

Remove unnecessary symbols.

### Tokenization

Convert text into tokens.

### Padding

Ensure fixed sequence length.

### Truncation

Prevent excessively long captions.

---

# 8. Model Architectures

## CNN + LSTM

Image
↓
CNN Encoder
↓
Feature Vector
↓
LSTM Decoder
↓
Caption

### Encoder

ResNet-based CNN

### Decoder

LSTM

### Strengths

- Fast
- Lightweight

### Weaknesses

- Weak semantic understanding

---

## Vision Transformer

Image
↓
Patch Embedding
↓
Transformer Encoder
↓
Transformer Decoder
↓
Caption

### Strengths

- Global attention
- Better context capture

### Weaknesses

- Higher computational cost

---

## BLIP-1

Image
↓
Vision Encoder
↓
Text Encoder
↓
Text Decoder
↓
Caption

### Strengths

- Strong image-text alignment
- Rich semantic reasoning

---

## BLIP-2

Image
↓
Frozen Vision Encoder
↓
Q-Former
↓
LLM
↓
Caption

### Strengths

- Advanced multimodal reasoning
- Better language generation

---

# 9. Training Strategy

## Loss Function

Cross Entropy Loss

## Optimizers

- Adam
- AdamW

## Techniques

- Teacher Forcing
- Mixed Precision Training
- Gradient Checkpointing
- Efficient Batch Loading

---

# 10. Inference Pipeline

Image
↓
Preprocessing
↓
Trained Model
↓
Beam Search Decoding
↓
Generated Caption

---

# 11. Evaluation Metrics

BLEU-1
BLEU-2
BLEU-3
BLEU-4
METEOR
ROUGE-L
CIDEr

Primary Metric:
CIDEr

Reason:
Best reflects human judgment in image captioning.

---

# 12. Comparative Findings

CNN+LSTM
→ Baseline

ViT
→ Better visual understanding

BLIP-1
→ Best overall model

BLIP-2
→ Strong performance but computationally expensive

---

# 13. Key Conclusions

1. Vision-Language Models outperform traditional architectures.
2. Transformer-based models provide better contextual understanding.
3. BLIP-1 achieves the best balance between performance and efficiency.
4. Agricultural image captioning provides greater interpretability than disease classification.
5. Multimodal learning is highly effective for precision agriculture applications.
