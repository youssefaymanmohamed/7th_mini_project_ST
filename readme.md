# Text Summarization Models Comparison Project
[![Python](https://img.shields.io/badge/Python-3.11.7-blue.svg)](https://www.python.org/)
[![Transformers](https://img.shields.io/badge/Transformers-latest-green.svg)](https://huggingface.co/transformers/)
[![ROUGE](https://img.shields.io/badge/ROUGE-latest-red.svg)](https://pypi.org/project/rouge/)

## 📊 Overview
This project provides a comprehensive comparison of three state-of-the-art text summarization models:
- **BERTSUM** (Extractive Summarization)
- **T5** (Abstractive Summarization)
- **BART** (Abstractive Summarization)

## 📈 Performance Metrics

| Model    | ROUGE-1 | ROUGE-2 | ROUGE-L |
|----------|---------|---------|----------|
| BERTSUM  | 0.96    | 0.92    | 0.96    |
| T5       | 0.57    | 0.49    | 0.53    |
| BART     | 0.55    | 0.47    | 0.55    |

## 🏗️ Model Architectures

### BERTSUM
- **Type**: Extractive Summarization
- **Architecture**: BERT base model with specialized inter-sentence Transformer layers
- **Key Features**: Classifier layer for sentence importance scoring; uses `[CLS]` and `[SEP]` tokens for text delimitation.

### T5
- **Type**: Abstractive Summarization
- **Architecture**: Transformer encoder-decoder
- **Key Features**: Pre-trained on diverse text-to-text tasks, requiring `summarize:` prefix for input.

### BART
- **Type**: Abstractive Summarization
- **Architecture**: Transformer encoder-decoder with denoising autoencoder
- **Key Features**: Optimized for text generation tasks, accepts plain text input without special tokens.

## 🔍 Key Findings

1. **BERTSUM**
   - Achieves the highest ROUGE scores but may sacrifice readability.
   - Effective at preserving the structure of original content.

2. **T5**
   - Delivers a balance of readability and relevance.
   - Effective at capturing essential points with less focus on extractive similarity.

3. **BART**
   - Natural language generation with good semantic preservation.
   - Strong performance in capturing general context in summary form.

## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install transformers rouge torch
```
### 2. Import Required Modules
```python
from transformers import (
    BertTokenizer, BertForSequenceClassification,
    T5Tokenizer, T5ForConditionalGeneration,
    BartTokenizer, BartForConditionalGeneration
)
from rouge import Rouge
```

## 📦 Model Sources
- [BERT Base Uncased](https://huggingface.co/google-bert/bert-base-uncased)
- [T5 Small](https://huggingface.co/google-t5/t5-small)
- [BART Large CNN](https://huggingface.co/facebook/bart-large-cnn)

## 👥 Contributors
- Youssef Ayman (211000348)
- Adham Bahnasy (211000117)

## 📚 References
- [JMLR Paper](https://jmlr.org/papers/volume21/20-074/20-074.pdf)
- [Hugging Face Documentation](https://huggingface.co/docs)
