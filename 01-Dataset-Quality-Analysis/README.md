# 01: Dataset Quality Analysis

# Romanized Pashto Sentiment Dataset – Analysis Report (AI-Generated Data)

## Full Analysis Article
A detailed write-up of these tests and findings is available here:  
→ [Exploring AI-Generated Romanized Pashto Data: Does It Really Resemble Human Language?](https://www.linkedin.com/pulse/exploring-ai-generated-romanized-pashto-data-does-really-abdul-razaq-7m7lf)

---

This repository contains the results of a systematic data quality, statistical, and linguistic analysis performed on a Romanized Pashto sentiment corpus. The dataset appears to consist primarily of **AI-generated** short-form text (chat-style / social-media style) labeled for sentiment.

## Dataset Overview

| Metric | Value |
|--------|-------|
| Total records | 8,239 |
| Columns | `text` (Romanized Pashto), `label` (sentiment) |
| Original label distribution (before mapping) | `0`: 1,850 · `1`: 1,677 · `2`: 1,812 · `Negative`: 888 · `Neutral`: 1,283 · `Positive`: 729 |
| Final label mapping | `0` = Positive · `1` = Negative · `2` = Neutral |
| Final label counts | `0`: 2,579 · `1`: 2,565 · `2`: 3,095 |

### Cleaning Summary
- Missing text values: **0**
- Empty / whitespace-only text: **0**
- Leading/trailing whitespace: cleaned
- Invalid / unexpected labels: **0** (after mapping)
- Exact duplicate rows (`text` + `label`): **2,015** (24.46%)
- Duplicate texts (regardless of label): **2,029** rows (885 unique texts appearing more than once)

> **Note**: A substantial portion of the data is duplicated. This is typical of many AI-generated or heavily augmented corpora and should be handled carefully before model training.

## Sentence Length Characteristics

**Words per sentence**
- Mean: 7.82  
- Median: 8.00  
- Min / Max: 1 / 19  
- 75th percentile: 9 · 90th: 11 · 99th: 15

**Characters per sentence**
- Mean: 32.49  
- Min / Max: 1 / 100

The corpus consists almost exclusively of **short, chat-style messages**.

## Vocabulary & Lexical Diversity

| Metric | Value |
|--------|-------|
| Total tokens | 64,389 |
| Unique tokens (vocabulary size) | 3,882 |
| Type-Token Ratio (TTR) | 0.0603 |
| Root TTR (Guiraud’s R) | 15.30 |
| Corrected TTR (Herdan’s C) | 0.7463 |
| Hapax Legomena | 1,479 (38.1% of vocabulary) |

**Most frequent tokens** are dominated by punctuation and high-frequency function words (`pa`, `da`, `ke`, `wo`, `wa`, `na`, `kho`, etc.).

The low TTR and high lexical repetition are consistent with AI-generated or highly formulaic text.

## Character-Level Statistics

| Character type | Percentage |
|----------------|------------|
| Alphabetic     | 78.43% |
| Spaces         | 14.57% |
| Punctuation    | 6.69% |
| Emojis         | 0.18% |
| Numbers        | 0.10% |
| Other          | 0.03% |

## Character N-gram Patterns
- Unique bigrams: 1,243  
- Unique trigrams: 5,795  
- Unique 4-grams: 17,052  
- Unique 5-grams: 33,626  

Frequent n-grams reflect common Romanized Pashto particles and word boundaries (`a `, ` k`, `e `, `wa`, `kh`, `da`, `pa`, etc.).

## Spelling Variation Analysis
- Vocabulary size analyzed: 3,882  
- Words with ≥1 potential variant (Levenshtein ≤ 2 or Jaccard ≥ 0.6 on trigrams): **3,099** (~80%)  
- Highest variation observed on short function words (`sa`, `ra`, `wa`, `ai`, `la`, `da`, …)

Spelling variation is extremely high — a known characteristic of Romanized Pashto and of AI-generated text that has not been normalized.

## Key Observations & Recommendations

1. **Heavy duplication** – Remove or deduplicate before training to avoid inflated performance metrics.
2. **Short-text domain** – Models should be designed for short, informal messages.
3. **Low lexical diversity + high spelling variation** – Subword tokenization (BPE / WordPiece / SentencePiece) is strongly recommended.
4. **AI-generated nature** – The combination of short sentences, high repetition, and systematic spelling variation is consistent with synthetic data. Human evaluation of a sample is advised before using the corpus for production systems.
5. **Label balance** – After mapping, the three classes are reasonably balanced (≈31% / 31% / 38%).

## How to Reproduce
The full analysis pipeline is contained in the accompanying Jupyter notebook. It includes:
- Loading & mounting
- Text & label validation / cleaning
- Duplicate detection
- Length statistics
- Vocabulary & Zipf analysis
- Character n-gram extraction
- Automated spelling-variant detection

---

**Disclaimer**: This report is derived exclusively from automated statistical and surface-level linguistic tests. No human annotation quality check or native-speaker validation of the Romanized Pashto text or labels was performed.
