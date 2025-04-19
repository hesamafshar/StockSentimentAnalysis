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

- **`Foolad_stock.csv`**  
  Historical stock price data file located in the root directory.

- **`sentiment_results_with_probs.csv`**  
  Sentiment analysis result file located in the root directory.

- **`fine_tuned_model/`**  
  Contains the pre-trained Persian BERT model used for sentiment classification.

- **`raw_news_data/`**  
  Categorized financial news files scraped from EghtesadOnline:
  - `EghtesadOnline-currency-400-403.csv`
  - `EghtesadOnline-energy-400-403.csv`
  - `EghtesadOnline-industry-400-403.csv`
  - `EghtesadOnline-interior-economy-400-403.csv`
  - `EghtesadOnline-stock-market-400-403.csv`

---

## 📥 Data Collection

### 📰 Financial News

News articles were scraped from **[EghtesadOnline](https://www.eghtesadonline.com/)** — a Persian-language financial news agency — spanning Persian calendar years **1400 to 1403**. Articles were categorized by topic and saved as CSV files.

Each entry includes:
- Date of publication
- Title
- Full article text

The sentiment for each article was evaluated using a fine-tuned BERT model from [this repository](https://github.com/marzinouri/persian-sentiment-analysis/blob/main/downsampled-minimalReportIncluded.ipynb). This model is stored locally in the `fine_tuned_model/` directory and used for inference only.

### 📈 Stock Price Data

Stock price data for **Foolad (فولاد مبارکه)** was collected from public financial sources like Codal.ir or TSETMC.com and includes:
- Date
- Opening/closing prices
- High/low
- Volume

The sentiment and price data were aligned by date for training and evaluation.

---

## 🧠 Models Used

### 🗣️ Sentiment Model

A pre-trained BERT model fine-tuned on Persian sentiment data was used to classify news articles into categories like positive, neutral, or negative. It is not retrained here — only used for inference from the `fine_tuned_model/` folder.

### 📈 Price Prediction Model

The final features (including sentiment and price history) were fed into a machine learning model (e.g., Random Forest, Gradient Boosting) to predict future stock trends. This is handled in `Modelling.ipynb`.

---

## 📒 Notebook Descriptions

- **`Extact News.ipynb`** – Scrapes and extracts raw news articles.
- **`Data_Wrangling.ipynb`** – Cleans and aligns stock/news data.
- **`Feature_Extraction.ipynb`** – Applies sentiment model and builds features.
- **`Modelling.ipynb`** – Trains models and evaluates results.
