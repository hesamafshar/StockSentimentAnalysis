# Stock Price Prediction Using Financial News Sentiment

I built this project to check whether sentiment in Persian financial news could add useful information to stock-price prediction. The case study is Foolad (Mobarakeh Steel) in the Tehran Stock Exchange.

I did not start from a ready-made dataset. I collected financial news from EghtesadOnline for the Persian calendar years 1400--1403, grouped the articles by topic, and combined them with historical Foolad stock data. I then processed the Persian text and used a ParsBERT sentiment model to get positive, negative, and neutral sentiment scores for the news.

For price prediction, I used a Temporal Convolutional Network (TCN). I trained the same forecasting setup once with the sentiment features and once without them so I could directly compare the two cases. Most of the work was done from the beginning: collecting the data, finding suitable NLP and time-series methods, implementing them, and comparing the results.

## Repository files

- `Extact News.ipynb` -- collection and organization of Persian financial news
- `Data_Wrangling.ipynb` -- cleaning and alignment of the news and stock data
- `Feature_Extraction.ipynb` -- Persian text preprocessing and sentiment feature extraction with ParsBERT
- `Modelling.ipynb` -- TCN-based stock-price modeling and comparison with/without sentiment features
- `raw_news_data/` -- collected news data from different financial categories
- `Foolad_stock.csv` -- historical Foolad stock data
- `sentiment_results_with_probs.csv` -- extracted sentiment probabilities

## Notes

The sentiment model was used for inference rather than trained from scratch. The main modeling experiment and the comparison between the two forecasting settings are available in `Modelling.ipynb`.
