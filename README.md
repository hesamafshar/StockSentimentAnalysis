# Stock Price Prediction Using Financial News Sentiment

I built this project to examine whether sentiment in Persian financial news can add useful information to stock-price prediction. The case study is Foolad (Mobarakeh Steel) in the Tehran Stock Exchange.

The work started with data collection rather than a ready-made dataset. I collected financial news from EghtesadOnline for the Persian calendar years 1400--1403, grouped the articles by topic, and combined them with historical Foolad stock data. I then processed the Persian text and used a ParsBERT sentiment model to obtain positive, negative, and neutral sentiment scores for the news.

For the forecasting part, I used a Temporal Convolutional Network (TCN). I trained the forecasting setup both with and without the sentiment features so I could compare whether the news information changed the prediction results. The main point of the project was the full research pipeline: collecting the data, finding a suitable NLP and time-series approach, implementing the models, and comparing the two settings.

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
