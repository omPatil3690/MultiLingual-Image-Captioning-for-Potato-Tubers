# Potato Tuber Disease Captioning using Vision-Language Models

An AI-powered agricultural image captioning system that generates descriptive textual explanations for potato tuber diseases instead of only predicting disease labels.

The project benchmarks multiple deep learning and vision-language architectures for agricultural disease understanding and compares their ability to generate semantically meaningful, context-aware captions describing disease symptoms, severity, and crop conditions.

---

## Project Overview

Traditional crop disease detection systems primarily perform classification and output only disease labels.

This project extends disease analysis beyond classification by generating natural language descriptions of potato tuber conditions using image captioning models.

The system analyzes potato tuber images and produces captions describing:

- Disease symptoms
- Severity level
- Surface abnormalities
- Visible lesions
- Crop condition observations

This improves interpretability and practical usefulness for:

- Precision Agriculture
- Farmer Assistance Systems
- Crop Monitoring Platforms
- Disease Advisory Applications

---

## Key Features

- Agricultural Image Captioning
- Vision-Language Learning
- Disease Severity Understanding
- Multi-Model Benchmarking
- Transformer-Based Caption Generation
- Multimodal Learning
- Comparative Evaluation Framework
- Real-World Agricultural Dataset

---

## Dataset

The dataset consists of potato tuber cross-sectional images captured under real field conditions using multiple smartphone devices.

### Characteristics

- Real-world agricultural images
- Expert-supervised annotations
- Multiple captions per image
- Disease-specific descriptions
- Severity-aware labeling

### Severity Levels

- Healthy
- Mild
- Moderate
- Severe

### Challenges

- Device variability
- Lighting variation
- Background noise
- Disease progression diversity
- Caption diversity

---

## Implemented Architectures

### 1. CNN + LSTM

Traditional image captioning architecture.

**Encoder**

- CNN (ResNet-based)

**Decoder**

- LSTM

**Advantages**

- Lightweight
- Faster training
- Lower computational cost

**Limitations**

- Limited contextual understanding
- Weak long-range dependency modeling

---

### 2. Vision Transformer (ViT)

Transformer-based image captioning architecture.

**Encoder**

- Vision Transformer

**Decoder**

- Transformer Decoder

**Advantages**

- Global attention mechanism
- Better contextual understanding
- Strong visual representation learning

---

### 3. BLIP-1

Bootstrapping Language Image Pretraining.

**Architecture**

- Vision Encoder
- Text Encoder
- Text Decoder

**Advantages**

- Strong image-text alignment
- Rich semantic understanding
- Excellent caption quality

---

### 4. BLIP-2

Advanced multimodal architecture.

**Architecture**

- Frozen Image Encoder
- Q-Former
- Large Language Model

**Advantages**

- Powerful multimodal reasoning
- Context-rich caption generation
- Better language fluency

---

## Training Pipeline

1. Dataset Collection
2. Image Preprocessing
3. Caption Preprocessing
4. Dataset Splitting
5. Model Training
6. Caption Generation
7. Evaluation
8. Comparative Analysis

---

## Preprocessing

### Image Processing

- Image Verification
- RGB Conversion
- Cropping
- Resizing
- Normalization
- Tensor Conversion

### Caption Processing

- Lowercase Conversion
- Symbol Removal
- Tokenization
- Padding
- Truncation
- Vocabulary Construction

---

## Evaluation Metrics

The models were evaluated using standard image captioning metrics.

### BLEU

- BLEU-1
- BLEU-2
- BLEU-3
- BLEU-4

### METEOR

Measures semantic similarity.

### ROUGE-L

Measures sequence-level similarity.

### CIDEr

Measures caption quality and alignment with human annotations.

---

## Results

| Model      | BLEU-1 | BLEU-2 | BLEU-3 | BLEU-4 | METEOR | ROUGE-L | CIDEr  |
| ---------- | ------ | ------ | ------ | ------ | ------ | ------- | ------ |
| CNN + LSTM | 0.6646 | 0.5873 | 0.5257 | 0.4623 | 0.3023 | 0.3093  | 0.5505 |
| ViT        | 0.7399 | 0.6969 | 0.6182 | 0.5691 | 0.3523 | 0.3563  | 0.8357 |
| BLIP-1     | 0.8240 | 0.7499 | 0.7011 | 0.6658 | 0.3719 | 0.3486  | 1.1419 |
| BLIP-2     | 0.7764 | 0.7172 | 0.6703 | 0.6320 | 0.3566 | 0.3457  | 0.9141 |

---

## Best Performing Model

BLIP-1 achieved the strongest overall performance across BLEU, METEOR, and CIDEr metrics and demonstrated superior semantic understanding and caption generation quality.

---

## Technology Stack

### Deep Learning

- PyTorch
- HuggingFace Transformers

### Data Processing

- NumPy
- Pandas

### Visualization

- Matplotlib

### Environment

- Google Colab
- Kaggle Notebooks

---

## Applications

- Precision Agriculture
- Smart Farming
- Disease Advisory Systems
- Agricultural Decision Support
- Crop Monitoring Platforms
- Explainable AI for Agriculture

---

## Future Work

- Larger Agricultural Datasets
- Domain-Specific BLIP Fine-Tuning
- Mobile Deployment
- Multilingual Caption Generation
- Disease Recommendation System
- Farmer Chat Assistant Integration

---

## Authors

- Om Patil
- Chataniya Dhanai
- Shubham Kumar Das
- Sandesh Lavshetty

Indian Institute of Information Technology, Nagpur
