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
- Duplicate texts (regardless of label): **2,029** rows (885 
