# BharatLaw – Qwen2-0.5B Fine-Tuned for Indian Legal Query Classification

[![Model on HuggingFace](https://img.shields.io/badge/HuggingFace-Model-yellow?logo=huggingface)](https://huggingface.co/harsh580g/qwen2-0.5B-fine-tuned-on-legal-data-v2)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Overview

**BharatLaw** is a lightweight and domain-specific legal AI model fine-tuned on **Qwen2-0.5B** to classify **informal Indian legal queries** into applicable **laws, acts, and sections**. It is built with efficiency, affordability, and speed in mind — ideal for resource-constrained deployments or real-time assistance.

👉 **[Click here to try the model on Hugging Face 🤗](https://huggingface.co/harsh580g/qwen2-0.5B-fine-tuned-on-legal-data-v2)**

---

## 🔍 What It Does

* ✅ Classifies legal queries into **multiple applicable laws/sections**.
* ✅ Supports **multi-label outputs** for complex or compound legal scenarios.
* ✅ Understands informal, colloquial query phrasing (e.g., "can i get bail under 376?").

---

## ⚙️ Model Details

| Property         | Value                                                                                                                         |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Base Model       | [Qwen2-0.5B](https://huggingface.co/Qwen/Qwen2-0.5B)                                                                          |
| Fine-tuned Model | [`harsh580g/qwen2-0.5B-fine-tuned-on-legal-data-v2`](https://huggingface.co/harsh580g/qwen2-0.5B-fine-tuned-on-legal-data-v2) |
| Task             | Multi-label legal classification                                                                                              |
| Dataset          | \~1,000 synthetic legal query-answer pairs                                                                                    |
| Language         | English (Indian legal context)                                                                                                |
| Optimized For    | Speed, efficiency, affordability                                                                                              |

---

## 🚀 Quick Start

```bash
pip install transformers
```

```python
from transformers import AutoTokenizer, AutoModelForSequenceClassification
import torch

# Load model and tokenizer
model_name = "harsh580g/qwen2-0.5B-fine-tuned-on-legal-data-v2"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForSequenceClassification.from_pretrained(model_name)

# Example query
query = "My landlord is forcing us to leave immediately without any warning, is this legal?"

# Tokenize and get model output
inputs = tokenizer(query, return_tensors="pt", truncation=True)
with torch.no_grad():
    outputs = model(**inputs)
    logits = outputs.logits
    probs = F.softmax(logits, dim=1)

# Get predicted class and probability
predicted_class = torch.argmax(probs, dim=1).item()
confidence = probs[0][predicted_class].item()

print(f"Predicted class: {predicted_class}, Confidence: {confidence:.2f}")

```

---

## 🧠 Dataset

* Manually crafted and programmatically augmented \~1,000 query-answer samples.
* Covers:

  * Bail conditions
  * Criminal offenses
  * Juvenile justice
  * NDPS-related queries
  * Basic constitutional rights

---

## 📌 Applications

* Legal help chatbots
* Pre-filtering in legal research tools
* Cost-effective assistants for paralegals and students
* Edge-device deployment in rural legal outreach programs

---

## 📄 License

This project is released under the [MIT License](LICENSE).

---

## 👤 Author

Developed by [@harsh580g](https://huggingface.co/harsh580g)
Part of the ongoing **BharatLaw AI Initiative** for accessible legal technology in India.
