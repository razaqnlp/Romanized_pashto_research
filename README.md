# Romanized Pashto NLP Research

A progressive research program focused on Romanized Pashto, Pashto natural language processing, and the challenges of working with multilingual and code-mixed text.

## Research Program

The projects move from understanding the data to developing models and identifying future research directions:

1. [Dataset Quality Analysis](01-Dataset-Quality-Analysis/README.md) - What is wrong, missing, or unique about the available data?
2. [Romanized Pashto Detection](02-Romanized-Pashto-Detection/README.md) - Can Romanized Pashto be reliably identified in noisy multilingual text?
3. [Sentiment Analysis](03-Sentiment-Analysis/README.md) - Can NLP models understand sentiment in Romanized Pashto?
4. [Code-Mixed Pashto](04-Code-Mixed-Pashto/README.md) - What happens when Pashto is mixed with other languages?
5. [Future Research](05-Future-Research/README.md) - Which advanced methods and research questions should come next?

## Shared Project Structure

Each active project uses the same layout:

```text
data/raw/          Original, immutable datasets
data/processed/    Cleaned and model-ready datasets
notebooks/         Exploratory analysis and experiments
src/               Reusable research code
results/tables/    Generated tables
results/figures/   Generated figures
results/metrics/   Evaluation metrics
results/reports/   Analysis reports
paper/             Paper drafts and supporting materials
```
