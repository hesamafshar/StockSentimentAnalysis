# Stock Sentiment Analysis with Historical Price Correlation

This project explores the relationship between news sentiment and stock prices using a combination of data wrangling, feature engineering, natural language processing (NLP), and machine learning modeling. The main goal is to extract financial news, perform sentiment analysis, and correlate it with historical stock price movements to predict trends or understand market behavior.

---

## 📂 Project Structure

```
StockSentimentAnalysis/
│
├── Data_Wrangling.ipynb              # Cleaning and preparing raw news and stock data
├── Extact News.ipynb                 # Extracting and formatting news content
├── Feature_Extraction.ipynb         # Generating textual and numerical features
├── Modelling.ipynb                   # Machine learning pipeline for prediction
│
├── historical_stock_data/           # CSV files of historical stock prices
│   └── Foolad_stock.csv
│
├── raw_news_data/                   # Raw financial news categorized by topic
│   ├── EghtesadOnline-currency-400-403.csv
│   ├── EghtesadOnline-energy-400-403.csv
│   └── ...
│
└── sentiment_outputs/               # Sentiment results with probabilities
    └── sentiment_results_with_probs.csv
```

---

## 📊 Features

- Automated financial news extraction from categorized CSVs.
- Sentiment analysis using NLP models with probability outputs.
- Historical stock price processing and visualization.
- Feature engineering to match temporal aspects of news with stock data.
- Predictive modeling to identify relationships between news and market trends.

---

## 🧰 Tech Stack

- Python
- Jupyter Notebooks
- pandas, NumPy
- scikit-learn
- nltk / spaCy / transformers (for NLP)
- Matplotlib / Seaborn

---

## 📜 License

This project is for educational and research purposes.

