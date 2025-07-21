---
layout: default
title: "Text"
vega: true
header_type: hero #base, post, hero,image, splash
header_img: assets/images/header.svg
header_title: "Image Analysis"

---

# Like To Read

---

## Analysis Objectives

The textual analysis pursued the following goals:
- Enrich the dataset with missing information (e.g., *gender* and *brand*);
- Analyze the relationship between textual content and likelihood of sale;
- Identify patterns and textual signals predictive of commercial success;
- Evaluate the quality and structure of user-generated texts.

---

## Methodology

### Cleaning and Pre-processing
A classic text preprocessing pipeline was implemented:
- Lowercasing;
- Stopword removal;
- Symbol and emoji removal (preceded by occurrence analysis);
- Handling of ambiguous content.

### NLP Techniques Used:
- **Regex** for cleaning, pattern matching, and initial information extraction;
- **TF-IDF** for exploratory analysis and initial vector representation;
- **Word2Vec** and **Sentence2Vec** for semantic embedding;
- **LLM (GPT-3.5)** for experiments in extracting concepts and topics.  
Overall, the results were fairly limited due to the low coherence and quality of the available textual data, which would require more extensive preprocessing or domain-specific models.

---

## Dataset Enrichment

Through text analysis, it was possible to:
- **Assign a gender** to items (M/F/N), with "N" used for ambiguous cases;
- **Recover information on brands, product categories, and styles** when missing from the metadata.

> This made it possible to observe that items with gender **F** show a higher likelihood of being sold.

---

## Quantitative Analysis

### Text Length
A significant relationship emerged between text length and the likelihood of sale:

| Text Type     | Ideal Length (in number of words) |
|---------------|-----------------------------------|
| Title         | 2–6 words                         |
| Description   | 4–12 words                        |

Texts that are too short or too long tend to correlate with lower sale rates.

---

## Semantic Analysis

### Key Expressions: “mai...” (“never...”)
Phrases starting with “mai...” (e.g., *mai indossato*, *mai usato* — "never worn", "never used") appear frequently and **have a positive impact** on sale rates.  
The only exception: for items already classified as *"new with tag"*, the effect is neutral; instead, **the effect is particularly positive for items classified as “satisfactory”**, suggesting a persuasive power in this phrasing.

---

## Explorative Predictive Models

Several models were tested to predict the likelihood of sale by combining structured and textual features:

- **Random Forest**
- **XGBoost**
- **LightGBM**
- **Neural Networks**

Text-derived features (e.g., embeddings, length, key expressions) proved to be **useful and complementary** to classical variables.

---

## Limitations and Observations

- The texts are **extremely heterogeneous** and often lack useful information: some users write minimal descriptions, others provide personal stories or calls to action;
- **Automatic topic extraction** proved ineffective due to the semantic inconsistency of the content;
- The language used is **exclusively Italian**, with wide stylistic variation and frequent use of informal or non-standard language.

---

## Suggestions for Future Developments

Some possible directions for improvement:
- Introduce **fine-tuning of LLMs** on similar content to obtain more robust extractions (brand, category, condition);

The resale platform could leverage these insights to implement a system for **automatic qualitative evaluation of texts**, suggesting to users how to improve their descriptions (e.g., in terms of length, clarity, or key terms) to increase sales.

---
