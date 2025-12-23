# 🚗 NEV-Opinion-Mining
### A Hybrid Topic–Semantic Framework Based on LDA and Large Language Models

![Status](https://img.shields.io/badge/Status-Research_Design-blue)
![Methodology](https://img.shields.io/badge/Methodology-LDA%2BLLM-green)
![Domain](https://img.shields.io/badge/Domain-Decision_Science-orange)
![License](https://img.shields.io/badge/License-MIT-grey)

## 1. Motivation
Understanding user sentiment in the New Energy Vehicle (NEV) market presents unique challenges. User-generated reviews are highly unstructured, noisy, and rich in domain-specific expressions.

While Large Language Models (LLMs) excel at semantic understanding, fully replacing statistical models with LLM-based classification often sacrifices **comparability, transparency, and structural interpretability**.

**The Research Question:**
> *Can LLMs be used not as black-box classifiers, but as semantic operators that enhance traditional topic models while preserving their statistical structure?*

## 2. Research Objective
The core objective is to design a hybrid opinion mining framework that enables:
1.  **Structurally interpretable** topic modeling.
2.  **Fine-grained semantic interpretation** of latent topics.
3.  **Comparative analysis** between **BEV** (Battery Electric Vehicle) and **PHEV** (Plug-in Hybrid Electric Vehicle) user groups.

Rather than predicting sentiment alone, the framework aims to uncover structural differences in user concerns (e.g., Intelligence experience vs. Range anxiety) to support data-driven business decisions.

## 3. Methodological Positioning
This framework positions itself between **Classical Unsupervised Learning** (LDA) and **Generative AI** (LLMs).

| Approach | Pros | Cons |
| :--- | :--- | :--- |
| **Pure LDA** | Probabilistic structure, Stable | Low semantic interpretability, Sensitive to noise |
| **Pure LLM** | High semantic understanding | High cost, Black-box nature, Hard to quantify structurally |
| **Our Hybrid Framework** | **Interpretable + Semantic-aware** | Complex pipeline design |

**Design Philosophy:**
*   **LDA** provides the probabilistic backbone for topic stability.
*   **LLMs** act as "Semantic Operators" for noise filtering and meaning extraction.

## 4. Core Innovations

### 4.1 LLM-Driven Noise Modeling
Inspired by recent computational social science literature (e.g., *"Jobless Growth"*), we leverage LLMs to identify recurrent noise patterns in raw UGC and automatically generate high-precision **Regular Expressions**. This "Human-in-the-loop" approach enables scalable cleaning that surpasses manual keyword matching.

### 4.2 LLM-Assisted Semantic Interpretation
Traditional LDA outputs unordered keyword lists. In this framework, LLMs serve as interpreters to bridge probabilistic outputs with human understanding, automatically generating coherent topic labels.

### 4.3 Comparative Topic–Sentiment Analysis
Unlike generic sentiment analysis, this framework explicitly designs for **Group-Level Comparison** (BEV vs. PHEV), identifying asymmetric pain points across different powertrain technologies.

## 5. System Architecture
The project follows a hybrid pipeline:
1.  **Data Acquisition**: Multi-source scraping from Chinese automobile platforms.
2.  **LLM-Enhanced Preprocessing**: Noise pattern discovery & Regex generation.
3.  **Topic Modeling**: Gensim-based LDA with Coherence optimization.
4.  **Semantic Enrichment**: LLM-based topic labeling & sentiment interpretation.
5.  **Comparative Analysis**: BEV vs. PHEV topic distribution visualization.

## 6. Research Stage Clarification ⚠️
**Current Status: Methodological Design & Prototyping**

This repository currently serves as a **Research Proposal** and **System Design** demonstration. 
*   The pipeline architecture is fully specified.
*   Core algorithms (LDA + LLM interaction logic) are defined in the `src/` directory.
*   Large-scale quantitative evaluation is planned for the next phase.

## 7. Directory Structure
```text
NEV-Opinion-Mining/
├── data/                # Raw and processed datasets
├── src/
│   ├── scraper.py       # Data collection scripts
│   ├── preprocessor.py  # LLM + Regex cleaning logic (Core Innovation)
│   ├── lda_model.py     # Topic modeling core
│   └── llm_agent.py     # LLM interface for semantic interpretation
├── notebooks/           # Experimental designs
├── requirements.txt     # Dependencies
└── README.md            # Project documentation
