# Structuring Arguments: EDU Segmentation and Content Zone Classification in German Writing

This project presents a two-stage NLP pipeline for analyzing **German student essays** by:
1. Segmenting texts into **Elementary Discourse Units (EDUs)**
2. Classifying each EDU into an **argumentative content zone** (e.g., thesis, support, counterargument)

The system uses **XLM-RoBERTa** for segmentation and compares transformer-based vs. traditional machine learning models (SVM, Random Forest) for classification.

---

## 📚 Abstract

We present a two-stage approach for discourse analysis in German writing. EDU segmentation is treated as a token classification problem using a fine-tuned XLM-RoBERTa model trained on RST-annotated German corpora. Data augmentation and chunked inputs significantly improve performance (best F1: 0.968).

For content zone classification, traditional ML models (Random Forest, SVM) trained on syntactic, sentiment, and semantic features outperform transformers, achieving a top F1 of 0.86.

This work contributes to argument mining and automated feedback systems in educational settings.

---

## 🧠 Features

- EDU segmentation using chunked token classification with XLM-RoBERTa
- Content zone classification with:
  - Transformer fine-tuning (XLM-RoBERTa)
  - Feature-based SVM and Random Forest models
- Custom feature extractor:
  - Word count, sentiment, punctuation
  - POS & dependency counts via spaCy
  - Sentence embeddings via Sentence-BERT
- Data augmentation techniques:
  - Synonym replacement, back translation, word swap, random deletion

---

## 🗃️ Datasets

Used corpora:
- Potsdam Commentary Corpus (PCC)
- APA-RST Corpus
- German blog post corpus (RST-annotated)
- German student essay corpus (manually segmented and labeled)

Augmented datasets created using:
- **Back translation** (via MarianMT)
- **Easy data augmentation (EDA)**: WordNet synonyms, deletion, swap


