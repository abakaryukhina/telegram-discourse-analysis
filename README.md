# 📊 Diachronic Discourse Analysis of Russian Milblogger Telegram Channels (2024–2026)

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![spaCy](https://img.shields.io/badge/NLP-spaCy-09A3D5.svg)](https://spacy.io/)
[![pandas](https://img.shields.io/badge/Data-pandas-150458.svg)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Academic Disclaimer:** This repository contains code and empirical data created for academic research in computational linguistics and discourse analysis. The analyzed texts do not reflect the author's political views.

---

## 📌 Overview
This project investigates diachronic narrative shifts and lexical dynamics in the discourse of pro-Russian war correspondents (*Milbloggers*), focusing on the channel **🎙КОГДА ЗАПЕЛИ ПУШКИ | КЗП** (`@cs_association_0`). 

While initially embedded in state-aligned war propaganda, independent nationalist channels increasingly exhibit critical stances toward the Russian military command and political establishment.

* **Corpus Size:** 5,819 Telegram posts
* **Timeframe:** March 2024 – July 2026
* **Primary Objective:** Tracking diachronic changes in topic salience, sentiment markers, and co-occurrence patterns.

---

## 🛠️ Data Pipeline & Methodology

[Telegram API] ➔ [JSON Export] ➔ [Pandas Preprocessing & Emoji Removal]
                       ➔ [Deep Translator (spaCy Sentence Fallback)]
                       ➔ [Lemmatization & Filtering (spaCy de_core_news_lg)]
                       ➔ [IPM / Relative Frequency Calculation]
                       ➔ [Dynamic Co-occurrence Networks (vis-network)]
1. Extraction: Automated retrieval of raw post archives via telegram-download-chat.
2. Text Normalization: Removal of emojis (emoji package) and formatting artifacts, aggregation into monthly corpus slices.
3. Translation & Tokenization: Machine translation into German using deep_translator with sentence-level segmentation fallbacks for long texts.
4. Frequency & Co-occurrence Analysis: Calculation of relative frequencies and Instances Per Million (IPM) for content lemmata, filtering stop words and punctuation.
5. Network Visualization: Generation of interactive bigram graphs with vis-network (HTML output).

## 🔍 Key Findings
The empirical analysis reveals a shift across four distinct phases:
Phase 1 (Spring 2024) – Historical Legitimization: Dominance of historical conflicts (Chechnya, Bosnia, Kosovo, Afghanistan) to frame the invasion within past military traditions.
Phase 2 (Summer 2024 – Winter 2024) – Disillusionment & Radicalization: Critical retrospective on the origins of the 2014 conflict (Minsk agreements, Girkin), marked by high connectivity around the lemma verstehen.
Phase 3 (Spring 2025 – Late 2025) – Internal Friction & Institutional Critique: Rise of discourse concerning mutinies (Lunin, Aufstand), prison battalions (Tulenkov), and monetary frustration targeting state institutions (Zentralbank, Nabiullina, Gulag).
Phase 4 (2026) – Frontline Reality & Demystification: Rejection of official propaganda (Verleugnung, Realität), open acknowledgement of retreats (RUSSEN FLIEHEN), and focus on drone attrition warfare (Drohne, Sicherheitszone).

## ⚠️ Methodological Limitations
- Hapax Legomena: Due to monthly segmentation, many terms in the top-50 spectrum exhibit a frequency of N=1.
- Aggregation: Future iterations will aggregate data quarterly to enhance statistical robustness.
- High risk of a pragmatic misinterpretation (f.e. in case of irony).

## 🚀 Quickstart

# Clone repository
git clone [https://github.com/abakaryukhina/telegram-discourse-analysis.git](https://github.com/abakaryukhina/telegram-discourse-analysis.git)
cd telegram-discourse-analysis

# Install dependencies
pip install -r requirements.txt

# Run analysis
jupyter notebook Studienleistung_2.ipynb
