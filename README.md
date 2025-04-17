# 💘 OkCupid Matching Algorithm

Welcome to my OkCupid Matching Algorithm project! This repository explores a data-driven approach to online dating by using feature engineering, embeddings, and approximate nearest neighbor (ANN) search to recommend compatible user profiles. The goal: create smart, customizable match suggestions while mitigating biases like extreme age gaps.

---

## 📌 Project Overview

This project leverages the [OkCupid profiles dataset](https://www.kaggle.com/datasets/blackmatrix7/okcupid-profiles) from Kaggle to simulate a matchmaking algorithm. Using natural language processing, statistical filtering, and vector similarity, it builds personalized profile recommendations based on interests, writing prompts, and user preferences.

### Key Features:
- **Profile Feature Embedding**: Converts bios, essays, and other text fields into meaningful numerical vectors.
- **Prompt Embedding**: Captures the tone and personality in user responses using modern NLP models.
- **Approximate Nearest Neighbors (ANN)**: Efficiently finds top profile matches using the FAISS or Annoy library.
- **Age Gap Penalty**: Integrates a compatibility penalty for large age gaps (>7 years) to promote socially aligned match recommendations.

---

## 🔍 Matching Logic

1. **Preprocessing**:
   - Clean and normalize profile text (essays, prompts, etc.)
   - Encode demographic features (age, gender, orientation)

2. **Embedding Profiles**:
   - Use sentence embeddings (e.g., `DistilBertTokenizer`) for bios and prompt answers
   - Concatenate embeddings with numeric features (e.g., age, location bucket)

3. **Approximate Nearest Neighbors Search**:
   - Construct index with FAISS/Annoy
   - Retrieve top-N similar profiles for a query profile

4. **Post-Processing**:
   - Apply **age gap penalty** using a Gaussian or logistic adjustment
   - Rerank matches based on penalized similarity score

---
