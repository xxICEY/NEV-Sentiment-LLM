# 🚗 NEV-Opinion-Mining: A Hybrid Analysis Framework Based on LDA & LLMs

![Status](https://img.shields.io/badge/Status-Work_in_Progress-yellow)
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Method](https://img.shields.io/badge/Method-LDA%2BLLM-green)
![License](https://img.shields.io/badge/License-MIT-grey)

## 📖 Introduction
**NEV-Opinion-Mining** is a novel text mining framework designed to analyze user sentiment in the Chinese **New Energy Vehicle (NEV)** market. 

By integrating **Latent Dirichlet Allocation (LDA)** with **Large Language Models (LLMs)**, this project addresses the limitations of traditional topic modeling—specifically, the lack of semantic interpretability and the difficulty in handling unstructured UGC (User Generated Content) noise.

The core objective is to conduct a comparative analysis between **Battery Electric Vehicles (BEV)** and **Plug-in Hybrid Electric Vehicles (PHEV)**, revealing structural differences in user concerns regarding "Intelligence," "Range," and "Service."

## 💡 Core Innovations

### 1. LLM-Driven Data Preprocessing 🛠️
Inspired by the methodology in recent economic literature, we utilize **LLMs (e.g., GPT-5/Gemini 3Pro)** to automatically generate high-precision **Regular Expressions**. This allows for efficient, low-cost cleaning of massive, noisy datasets, far surpassing traditional keyword matching methods.

### 2. Enhanced Topic Interpretability 🧠
Traditional LDA models often output ambiguous keyword lists. We employ LLMs as a **Semantic Interpreter** to automatically generate coherent, context-aware labels for each topic cluster derived from LDA, bridging the gap between statistical probability and human understanding.

### 3. Fine-Grained Comparative Analysis 📊
Unlike generic sentiment analysis, this framework distinguishes between **BEV** and **PHEV** user groups, providing granular insights into how different powertrain technologies influence user satisfaction and pain points.

## 🏗️ Architecture

The project follows a "Human-in-the-loop" hybrid pipeline:

1.  **Data Acquisition**: Scraping multi-source reviews (Autohome/Dongchedi).
2.  **Preprocessing (The Hybrid Engine)**: 
    *   LLM identifies noise patterns -> Generates Regex -> Batch Cleaning.
    *   LLM constructs domain-specific stop-word lists.
3.  **Topic Modeling**: Gensim-based LDA training with Coherence Score optimization.
4.  **Semantic Enrichment**: LLM agents interpret topics and assign sentiment scores.
5.  **Visualization**: Interactive charts (pyLDAvis) and comparative radar plots.

## 🗓️ Roadmap

- [ ] **Phase 1: Infrastructure & Data**
    - [ ] Initialize repository structure.
    - [ ] Develop multi-threaded scrapers (Selenium).
    - [ ] Collect 10k+ raw review samples.
- [ ] **Phase 2: LLM-Enhanced Preprocessing**
    - [ ] Implement the "LLM-to-Regex" cleaning logic.
    - [ ] Build a specialized NEV domain dictionary.
- [ ] **Phase 3: Modeling & Interpretation**
    - [ ] Train LDA models and determine optimal *K* topics.
    - [ ] Integrate LLM API for automated topic labeling.
- [ ] **Phase 4: Analysis & Reporting**
    - [ ] Calculate fine-grained sentiment scores.
    - [ ] Generate BEV vs. PHEV comparative reports.

## 📂 Directory Structure

```text
NEV-Opinion-Mining/
├── data/                  # Raw and processed datasets
├── src/
│   ├── scraper.py         # Data collection scripts
│   ├── preprocessor.py    # LLM+Regex cleaning logic
│   ├── lda_model.py       # Topic modeling core
│   └── llm_agent.py       # API interface for LLM interpretation
├── notebooks/             # Jupyter notebooks for experiments
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
