# NLU Emotion Classification using DistilBERT

## Overview
This project implements a Natural Language Understanding (NLU) system for emotion classification using a fine tuned Transformer model. The goal is to classify short text inputs into one of several emotional categories such as joy, sadness, anger, fear, love, or surprise.

The project demonstrates the complete NLU pipeline including data preparation, model fine tuning, evaluation, and inference, using modern NLP tools from the Hugging Face ecosystem.

---

## Task Description
Natural Language Understanding task  
Emotion and intent classification from raw text

Key objectives:
- Fine tune a pretrained Transformer model for an NLU task
- Evaluate performance using accuracy and F1 score
- Provide an inference function suitable for chatbot or API integration

---

## Dataset
The project uses the **Emotion Dataset** from Hugging Face Datasets.

- Source: Hugging Face `emotion` dataset
- Data splits: Train, Validation, Test
- Labels: anger, disgust, fear, joy, sadness, surprise, love

The dataset contains short English sentences annotated with a single dominant emotion.

---

## Model Selection
- Model: `distilbert-base-uncased`
- Architecture: Transformer based encoder
- Reason for choice:
  - Lightweight and efficient compared to full BERT
  - Strong performance on text classification tasks
  - Suitable for real world deployment scenarios

The model is fine tuned using supervised learning on the emotion dataset.

---

## Data Preprocessing
- Text tokenization using Hugging Face AutoTokenizer
- Fixed maximum sequence length of 128 tokens
- Padding and truncation applied
- Raw text column removed after tokenization

---

## Training Configuration
- Learning rate: 2e-5
- Batch size: 32
- Number of epochs: 3
- Weight decay: 0.01
- Best model selected based on validation performance

Training and evaluation are handled using the Hugging Face Trainer API.

---

## Evaluation Metrics
Model performance is evaluated using:
- Accuracy
- Weighted F1 score
- Detailed classification report on the test set

These metrics provide insight into both overall performance and per class behavior.

---

## Inference and Integration
The project includes a prediction function that:
- Accepts raw text input
- Tokenizes input
- Runs inference on the trained model
- Returns predicted emotion and confidence score

This function can be easily integrated into:
- Chatbots
- REST APIs
- Text analysis systems

---

## Example Prediction
```text
Input: "I am so happy today!"
Output: joy (confidence: 92%)

