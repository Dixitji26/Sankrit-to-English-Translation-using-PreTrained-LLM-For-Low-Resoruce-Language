📘 Assignment 2: Sanskrit–English Neural Machine Translation (NMT)
🔍 Overview

This assignment implements a Neural Machine Translation (NMT) system for Sanskrit–English translation using a pre-trained sequence-to-sequence model. Unlike embedding-based approaches, this system performs direct text generation, translating input sentences from source to target language.

The implementation uses pre-trained models from Helsinki-NMT via Hugging Face Transformers.

🎯 Objectives
Perform automatic translation between Sanskrit and English
Use pre-trained NMT models (no training from scratch)
Evaluate translation quality using standard metrics
Analyze translation outputs and common errors

🏗️ Methodology
1. Model
   
Model type: Seq2Seq Transformer (Encoder–Decoder)
Implementation: Helsinki-NMT
Backend: MarianMT

The model consists of:

Encoder → processes input sentence
Decoder → generates translated output

2. Tokenization
   
Uses SentencePiece tokenization
Converts sentences into subword units
Handles rare and morphologically rich words

3. Translation Process

Pipeline:

Input sentence (source language)
Tokenization
Encoder generates contextual representation
Decoder generates output tokens sequentially
Tokens converted back to text

4. Decoding Strategy
Beam Search used for inference
Keeps top-k candidate sequences at each step

Typical configuration:

num_beams = 4 or 5

This improves translation quality compared to greedy decoding.

📊 Evaluation
Metrics Used
BLEU Score → measures overlap with reference translation
BERTScore (if used) → measures semantic similarity

These metrics evaluate:

Fluency
Adequacy
Semantic correctness
🧪 Experiments
Translation on dev/test datasets
Comparison of predicted vs reference sentences
Analysis of:
High-quality translations
Poor translations

📌 Analysis
Observations

✔ Good performance on:

Simple sentences
Common vocabulary

❌ Weak performance on:

Complex Sanskrit structures
Long sentences
Rare words
Error Types
Incorrect word order
Missing information
Over/under translation
Incorrect handling of morphology
⚠️ Limitations
Sanskrit is low-resource, so model support is limited
Pre-trained model may not be optimized for this dataset
No fine-tuning performed
Errors increase with sentence complexity
🚀 Future Work
Fine-tune model on Sanskrit–English parallel data
Use larger multilingual NMT models
Improve preprocessing for Sanskrit grammar
Experiment with different decoding strategies

⚙️ Installation
pip install transformers sentencepiece torch
▶️ Usage

Run the notebook:
jupyter notebook Assignment2_Sanskrit_NMT.ipynb

📚 References
Helsinki-NMT
Hugging Face Transformers
MarianNMT Framework
Vaswani et al. (2017) — Transformer

📌 Pre-trained Model Disclosure

This assignment uses the following pre-trained model:

Model: Helsinki-NMT
Architecture: Transformer-based Seq2Seq (MarianMT)
Training: Pre-trained on multilingual parallel corpora
Usage: Direct inference without fine-tuning

👤 Author

Shasank Dixit

✅ Note

This implementation focuses on inference using pre-trained NMT models, not training from scratch.
