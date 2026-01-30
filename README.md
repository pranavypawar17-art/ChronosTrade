# Chronos Trade 📈  
### Multi-Modal Stock Market Prediction using ARIMA, LSTM, and Sentiment Analysis

Chronos Trade is a stock price prediction project that combines **traditional time-series models**, **deep learning**, and **NLP-based sentiment analysis** to build a robust, multi-modal forecasting system.  
The project demonstrates how integrating **historical price data** with **market sentiment from news headlines** improves prediction performance, especially during volatile periods.

---

## 📌 Project Overview

Stock prices are influenced not only by historical trends but also by **news, public perception, and market psychology**.  
This project compares and extends:

- **ARIMA** – a statistical time-series forecasting model  
- **LSTM** – a deep learning model for sequential data  
- **Sentiment-Augmented LSTM** – a multi-modal model combining price data and sentiment scores  

The final system predicts stock closing prices more effectively by capturing both **numerical patterns** and **textual sentiment signals**.

---

## 🧠 Models Used

### 1. ARIMA (AutoRegressive Integrated Moving Average)
- Requires stationary data
- Uses differencing to remove trends
- Parameters: ARIMA(p, d, q)
- Final model used: **ARIMA(0,1,0)**

### 2. LSTM (Long Short-Term Memory)
- Recurrent Neural Network for time-series
- Captures long-term dependencies
- Handles non-linear patterns
- Uses sliding window technique and normalized inputs

### 3. LSTM with Sentiment Analysis (Final Model)
- Combines:
  - Historical stock prices
  - Daily aggregated sentiment scores
- Multi-feature input sequence
- Improves responsiveness to news-driven price movements

---

## 📰 Sentiment Analysis Pipeline

1. **Text Data Collection**
   - Financial news headlines related to the stock

2. **Text Preprocessing**
   - Lowercasing  
   - Stop-word removal  
   - Tokenization  
   - Lemmatization  

3. **Sentiment Scoring**
   - Classified as:
     - Positive
     - Negative
     - Neutral
   - Converted into numerical sentiment scores

4. **Daily Aggregation**
   - Multiple headlines aggregated into a single daily sentiment value

---

## 🔗 Feature Fusion

The final model uses **feature-level fusion**:

- Price sequence:  
  `[Price(t−n), ..., Price(t−1)]`
- Sentiment sequence:  
  `[Sentiment(t−n), ..., Sentiment(t−1)]`

These combined inputs allow the LSTM to learn interactions between **market movement** and **public sentiment**.

---

## 📊 Key Observations

- ARIMA performs reasonably for short-term forecasting but struggles with volatility
- LSTM produces smoother and more adaptive predictions
- **Sentiment-augmented LSTM outperforms price-only models**
- Improved prediction during:
  - News-driven volatility
  - Strong positive or negative sentiment periods

---

## 🛠️ Technologies & Tools

- Python
- NumPy, Pandas
- Matplotlib
- Statsmodels (ARIMA)
- TensorFlow / Keras (LSTM)
- NLP libraries for text preprocessing
- Yahoo Finance (price data source)

---

## 📈 Visualizations Included

- Stock price vs time
- ARIMA vs LSTM predictions
- Residual analysis
- Training vs validation loss curves
- Actual vs predicted prices (with sentiment)

---

## 🚀 Future Improvements

- Use transformer-based sentiment models (e.g., **FinBERT**)
- Weight sentiment based on news source credibility
- Incorporate social media sentiment (Twitter, Reddit)
- Build a real-time prediction dashboard
- Experiment with attention-based LSTM architectures

---

## 👤 Author

**Pranav Pawar**  
WiDS | ID: 24B2503  

---

## 📄 License

This project is for academic and learning purposes.
