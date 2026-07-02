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

The notebook processes the data in resumable chunks (checkpointed to Google
Drive as Parquet shards, so Colab disconnects don't lose work) and writes
`sentiment_comparison_results.parquet` to your Drive: the original data
plus, for each model, a predicted label, its top score, and the full
per-class probability distribution. Start with `SAMPLE_N = 100_000` to
validate the pipeline, then set it to `None` for the full ~7M-row run.
