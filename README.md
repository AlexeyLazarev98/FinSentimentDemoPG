# FinSentimentDemoPG

Compares sentiment predictions from three transformer models on a dataset of
financial market news:

- [`ProsusAI/finbert`](https://huggingface.co/ProsusAI/finbert)
- [`cardiffnlp/twitter-roberta-base-sentiment-latest`](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment-latest)
- [`yiyanghkust/finbert-tone`](https://huggingface.co/yiyanghkust/finbert-tone)

## Usage

Open `sentiment_comparison.ipynb` (e.g. in Google Colab) and run the cells
top to bottom:

1. Install dependencies.
2. Set the config cell — by default it points at the Google Drive folder
   provided for this project; update `TEXT_COLUMN` / `LABEL_COLUMN` if
   auto-detection doesn't match your file's schema.
3. Run the download, inference, and save steps.

The notebook writes `sentiment_comparison_results.csv`: the original data
plus, for each model, a predicted label, its top score, and the full
per-class probability distribution.
