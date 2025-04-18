# Stock Sentiment Analysis with Historical Price Correlation

This project explores the relationship between news sentiment and stock prices using a combination of data wrangling, feature engineering, natural language processing (NLP), and machine learning modeling. The main goal is to extract financial news, perform sentiment analysis, and correlate it with historical stock price movements to predict trends or understand market behavior.

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

### 📈 Stock Price Data

Stock data was retrieved from publicly available sources (such as Codal.ir or TSETMC.com) and stored in CSV format. In this version of the dataset, only the **Foolad (فولاد مبارکه)** stock price is included (`Foolad_stock.csv`), which contains:
- Date
- Opening and closing prices
- Daily highs and lows
- Volume and trade count

This data was used to align sentiment from financial news with actual market performance on corresponding days.

---

## 📊 Features

- Automated financial news extraction from categorized CSVs.
- Sentiment analysis using NLP models with probability outputs.
- Historical stock price processing and visualization.
- Feature engineering to match temporal aspects of news with stock data.
- Predictive modeling to identify relationships between news and market trends.



