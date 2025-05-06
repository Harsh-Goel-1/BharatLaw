⚖️🇮🇳 BharatLaw: Fine-Tuned Legal Query Assistant for Indian Law

🧠 Project Overview
BharatLaw is an AI-powered legal assistant designed to interpret informal legal queries and map them to the correct Indian laws, acts, and sections.
It's built by fine-tuning the Qwen2-0.5B model — a lightweight, open-source language model — on a custom legal dataset.


🔧 Technical Summary
🧩 Base Model: Qwen2-0.5B, a compact LLM from Alibaba, optimized for efficiency.
📂 Dataset: Custom-created dataset of ~1,000+ synthetic samples pairing informal legal queries with structured outputs (acts + sections + explanations).
🏷️ Task: Multi-label classification + generation.
Classifies which legal acts/sections apply.
Generates concise, section-specific explanations.
⚙️ Fine-tuning Objective: Supervised fine-tuning (SFT) for domain adaptation.
📦 Deployment Ready: Lightweight enough for deployment on consumer-grade hardware or Colab notebooks.
🧠 Capabilities
🤖 Understands informal, colloquial legal queries (e.g., "Can I get fired without notice?", "Flat owner not giving deposit back")
🗃️ Maps them to structured legal references (e.g., Industrial Disputes Act, Indian Contract Act)
🧾 Provides explanatory answers with direct reference to the applicable act/section


📌 Applications

🧑‍🎓 Legal awareness tools for students
📱 Chatbot integrations for law-related FAQs
🏛️ Civic tech platforms to simplify public access to legal information
🧑‍💼 Assistive tool for legal professionals doing quick triage

🔗 Hugging Face Model Repo
📍 harsh580g/qwen2-0.5B-fine-tuned-on-legal-data-v2

