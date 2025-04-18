# Stock Sentiment Analysis with Historical Price Correlation

This project explores the relationship between financial news sentiment and stock prices using a combination of data wrangling, feature engineering, natural language processing (NLP), and machine learning modeling. The primary goal is to evaluate how sentiment extracted from Persian-language news articles affects the behavior of stock prices, particularly for the Foolad (فولاد مبارکه) stock.

---

## 📂 Project Structure

- **`Data_Wrangling.ipynb`**  
  Preprocesses and cleans the raw news and stock price data.

- **`Extact News.ipynb`**  
  Extracts financial news data and organizes it for analysis.

- **`Feature_Extraction.ipynb`**  
  Converts textual and numerical data into features for modeling.

- **`Modelling.ipynb`**  
  Builds and trains predictive models using sentiment and price data.

- **`historical_stock_data/`**  
  Contains CSV files with historical stock prices.  
  └── `Foolad_stock.csv`

- **`raw_news_data/`**  
  Categorized financial news files scraped from EghtesadOnline across various sectors:
  - `EghtesadOnline-currency-400-403.csv`: News articles related to currencies.
  - `EghtesadOnline-energy-400-403.csv`: News about the energy sector (e.g., oil, gas).
  - `EghtesadOnline-industry-400-403.csv`: Industry and production-focused news.
  - `EghtesadOnline-interior-economy-400-403.csv`: Domestic economic affairs and policies.
  - `EghtesadOnline-stock-market-400-403.csv`: News related to stock market movements and trends.

- **`sentiment_outputs/`**  
  Contains the results of sentiment analysis performed on the news articles.  
  └── `sentiment_results_with_probs.csv`

---

## 📥 Data Collection

### 📰 Financial News

The news articles were manually scraped from **[EghtesadOnline](https://www.eghtesadonline.com/)** — a Persian-language financial news agency — over the Persian calendar years **1400 to 1403**. News was categorized based on the original section of the website:

- **Currency**: Coverage of foreign exchange markets and central bank decisions.
- **Energy**: Articles about oil, gas, and power generation sectors.
- **Industry**: Manufacturing, production, and heavy industry news.
- **Interior Economy**: General domestic economic policies, inflation, subsidies, etc.
- **Stock Market**: Reports and analyses on stock market trends and key companies.

Each news item includes:
- Date of publication
- Title
- Full text content

The scraped articles were cleaned and formatted into CSV files using Python scripts (see `Extact News.ipynb` and `Data_Wrangling.ipynb`).

The sentiment for each article was evaluated using a fine-tuned BERT model provided by [this GitHub repository](https://github.com/marzinouri/persian-sentiment-analysis/blob/main/downsampled-minimalReportIncluded.ipynb). This project uses the model for inference only and does not retrain or modify it.

### 📈 Stock Price Data

Stock data was retrieved from publicly available sources (such as Codal.ir or TSETMC.com) and stored in CSV format. In this version of the dataset, only the **Foolad (فولاد مبارکه)** stock price is included (`Foolad_stock.csv`), which contains:
- Date
- Opening and closing prices
- Daily highs and lows
- Volume and trade count

This data was used to align sentiment from financial news with actual market performance on corresponding days.

---

## 🧠 Models Used

### 🗣️ Sentiment Analysis Model

The sentiment of each news article is evaluated using a fine-tuned BERT model specifically trained for Persian-language sentiment classification. The model was sourced from [this repository](https://github.com/marzinouri/persian-sentiment-analysis/blob/main/downsampled-minimalReportIncluded.ipynb), and it is used here only for inference — not retrained.

The model classifies news headlines or full-text articles into sentiment categories (e.g., positive, negative, neutral) along with their associated probabilities.

### 📈 Stock Movement Prediction Model

After preprocessing and feature extraction, sentiment scores are combined with historical stock price data. These features are used to train a regression or classification model (such as Random Forest or Gradient Boosting) to predict future stock movements or price changes. The predictive modeling pipeline is implemented in the `Modelling.ipynb` notebook.

---

## 📒 Notebook Descriptions

- **`Extact News.ipynb`**  
  Scrapes and extracts financial news articles. Outputs categorized CSV files.

- **`Data_Wrangling.ipynb`**  
  Cleans the scraped news and stock data, standardizes date formats, and aligns both sources.

- **`Feature_Extraction.ipynb`**  
  Applies the pre-trained BERT sentiment model to generate sentiment scores. Combines these with temporal and numerical features.

- **`Modelling.ipynb`**  
  Trains a machine learning model to predict stock movement based on the engineered features. Includes training, validation, and results visualization.
