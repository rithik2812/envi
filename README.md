#  WasteWise+ — Semantic Waste Classification System

An intelligent waste segregation assistant that classifies household items into appropriate disposal categories using **NLP-based semantic similarity**.

---

##  Overview

WasteWise+ is a lightweight **text classification system** that helps users determine how to dispose of everyday items (e.g., *plastic bottle*, *banana peel*, *old charger*).

The system maps user input to categories like:

* 🟢 Wet Waste
* 🔵 Dry Waste
* ♻️ Recyclable
* 🔴 E-Waste

It improves upon traditional rule-based systems by leveraging **sentence embeddings** to understand the *meaning* of user queries rather than exact keyword matches.

---

##  Key Features

*  **Semantic Classification** using Sentence Transformers
*  **Cosine Similarity Matching** for category prediction
*  **Environmental Insights** (decomposition time, impact)
*  **Interactive Web UI** for real-time usage
*  Handles **unseen inputs** better than keyword-based systems

---

## System Architecture

```text
User Input (text)
        ↓
Text Preprocessing
        ↓
Sentence Embedding (Transformer)
        ↓
Cosine Similarity
        ↓
Category Matching
        ↓
Result + Environmental Info
```

---

## Tech Stack

* **Frontend:** HTML, CSS, JavaScript
* **Backend (optional upgrade):** Python
* **NLP Model:** Sentence Transformers (`all-MiniLM-L6-v2`)
* **Similarity Metric:** Cosine Similarity
* **API Integration:** Wikipedia API (for eco facts)

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/wastewise-plus.git
cd wastewise-plus
```

### 2. Install dependencies (for ML version)

```bash
pip install sentence-transformers scikit-learn
```

### 3. Run the application

```bash
streamlit run app.py
```

---

## Example Inputs

| Input          | Predicted Category |
| -------------- | ------------------ |
| plastic bottle | Recyclable      |
| banana peel    | Wet Waste       |
| phone charger  | E-Waste         |
| old clothes    | Dry Waste       |

---

## Approach

### Baseline (Rule-Based)

* Keyword matching using predefined lists
* Limited to known patterns

### Improved (Current System)

* Convert text → embeddings using transformer model
* Compare input with category descriptions
* Select category with highest cosine similarity

> This enables **zero-shot classification** and better generalization.

---

## 📁 Dataset

This project does **not rely on a large labeled dataset**.

Instead, it uses:

* Pre-trained transformer embeddings
* A small **reference dataset** of category descriptions

Example:

```python
categories = {
    "recyclable": "plastic bottles, glass, metal cans",
    "wet": "food waste, organic waste, banana peel",
    "ewaste": "electronics, chargers, batteries",
    "dry": "clothes, rubber, wood"
}
```

---

## Improvements Over Rule-Based Systems

| Feature                | Rule-Based | WasteWise+ |
| ---------------------- | ---------- | ---------- |
| Keyword dependency     | High       | Low        |
| Generalization         | Poor       | Good       |
| Handles new inputs     | ❌          | ✅          |
| Semantic understanding | ❌          | ✅          |

---

## Limitations

* Uses **pre-trained embeddings (no custom training)**
* Accuracy depends on quality of category descriptions
* Not optimized for large-scale deployment

---

## Future Enhancements

* Train a supervised ML model (Naive Bayes / BERT)
* Add multilingual support
* Deploy as a mobile/web application
* Improve dataset with real-world waste samples


## Achievements

* Selected in **Top 30 — Hackathon Project (WasteWise+)**
* Built to promote sustainable waste management




