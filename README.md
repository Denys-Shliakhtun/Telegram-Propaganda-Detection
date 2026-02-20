# Telegram Propaganda Detection using NLP & Distributed Computing

This project focuses on the development and implementation of a scalable system for the automated detection and analysis of propaganda content in the Telegram messenger. It utilizes distributed computing and advanced Natural Language Processing (NLP) to process massive datasets in a bilingual environment (Ukrainian and Russian).

## Key Features
* **Scalable ETL Pipeline:** Implemented automated collection, cleaning, and preprocessing of Telegram records.
* **Multilingual Processing:** Native support for Ukrainian and Russian languages via **SpaCy** and automated language detection.
* **Advanced Feature Extraction:**
    * **Stylometric Metrics:** Lexical complexity analysis using Type-Token Ratio (TTR).
    * **Psycholinguistic Markers:** Analysis of "We/They" dichotomy (polarization) and subjectivity levels.
    * **Network Analysis:** Detection of coordinated inauthentic behavior using the **MinHashLSH** algorithm to find near-duplicate content across channels.
* **Machine Learning:** Applied **Positive-Unlabeled (PU) Learning** with a **Random Forest** classifier to effectively identify propaganda markers amidst a large volume of unlabeled news flow.

## Tech Stack
* **Frameworks:** Apache Spark (PySpark), Spark MLlib.
* **NLP:** Spark NLP, SpaCy, langdetect.
* **Models:** XLM-RoBERTa (Transformer for sentiment/verdict analysis), Random Forest, LDA (Topic Modeling).
* **Environment:** Python, Jupyter Notebook / Google Colab.

## 📊 Performance & Results
The system was evaluated using a balanced dataset, where the Random Forest model demonstrated superior stability and generalization on noisy data compared to Gradient Boosted Trees.

| Model | AUC-ROC | Accuracy | F1-Score |
| :--- | :---: | :---: | :---: |
| **Random Forest** | 0.7104 | 0.6453 | 0.6365 |
| **GBT Classifier** | 0.6450 | 0.6017 | 0.5947 |

### Key Indicators of Propaganda:
1.  **Subjectivity (25.7% impact):** High emotional loading and biased language.
2.  **Pronoun Usage (~39% combined impact):** Frequent use of collective ("we") and hostile ("they") pronouns.
3.  **Lexical Diversity (TTR):** Propaganda sources tend to use repetitive clichés and slogans, resulting in lower lexical richness.

## Aggregated Analysis
Beyond single-post classification, the system performs aggregated analysis at the channel level. This approach effectively separated known propaganda sources from neutral news resources with nearly perfect accuracy.

## Academic Context
This project was developed as a Coursework for the "Processing of Large Datasets" discipline at the **Igor Sikorsky Kyiv Polytechnic Institute (KPI)**.

**Author:** [Denys Shlyakhtun](https://www.linkedin.com/in/denys-shliakhtun/) 
