# Sentiment Analysis on Amazon Product Reviews

## 📌 Project Overview
This project performs **Sentiment Analysis** on Amazon product reviews using **Python**. The goal is to analyze customer feedback and classify reviews as **positive, neutral, or negative** based on their sentiment polarity.

## 📂 Dataset
- **Source**: [Amazon Product Reviews](https://www.kaggle.com/datasets/saurav9786/amazon-product-reviews)
- **Size**: 34,660 reviews
- **Key Features**:
  - `reviews.text`: The actual review text.
  - `reviews.rating`: Star rating given by the customer.
  - `sentiment`: Assigned sentiment label (Positive, Neutral, Negative).

## 🔧 Technologies Used
- **Python** 🐍
- **Pandas** for data manipulation
- **TextBlob** for sentiment analysis
- **Seaborn & Matplotlib** for data visualization

## 🚀 Project Workflow
1. **Data Preprocessing**: Handle missing values, clean text data.
2. **Sentiment Analysis**: Apply TextBlob to analyze sentiment polarity.
3. **Sentiment Categorization**: Label reviews as Positive, Neutral, or Negative.
4. **Data Visualization**: Plot sentiment distribution.

## 📊 Sample Code
```python
import pandas as pd
from textblob import TextBlob
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv("1429_1.csv")
df = df.dropna(subset=['reviews.text'])
df['reviews.text'] = df['reviews.text'].astype(str)

# Sentiment Analysis
df['sentiment_polarity'] = df['reviews.text'].apply(lambda text: TextBlob(text).sentiment.polarity)
df['sentiment'] = df['sentiment_polarity'].apply(lambda score: 'positive' if score > 0 else ('negative' if score < 0 else 'neutral'))

# Visualization
sns.countplot(x=df['sentiment'], palette='coolwarm')
plt.title('Sentiment Analysis of Customer Reviews')
plt.show()
```

## 📈 Results
- **Positive Reviews**: Majority of the customers had a great experience.
- **Neutral Reviews**: Some reviews were mixed or lacked strong sentiment.
- **Negative Reviews**: A small portion of customers expressed dissatisfaction.

## 🎥 Video Demo
(*Include a link to your sample video once created*)

## 📜 License
This project is open-source and available under the **MIT License**.

## 🤝 Contributing
Feel free to fork this repository and contribute! Suggestions and pull requests are welcome.

## 📬 Contact
For any inquiries, reach out via **[sajiaashfaq@gmail.com](mailto:sajiaashfaq@gmail.com)** or connect on **LinkedIn** (*add your profile link*).

---
🚀 Happy Coding! 😊

