# Play Store ChatGPT Review Sentiment Analysis

## Project Overview

This project aims to analyze and classify user reviews of ChatGPT from the Play Store into positive, negative, and neutral sentiments. The analysis leverages Natural Language Processing (NLP) techniques and various machine learning models to gain insights into user feedback. The outcome of this project can help in enhancing customer satisfaction and guiding product development based on real user sentiments.

## Libraries Used

- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations.
- **Seaborn and Matplotlib**: For data visualization.
- **Re**: For regular expressions in text processing.
- **NLTK and SpaCy**: For text processing and NLP tasks.
- **WordCloud**: For generating word cloud visualizations.
- **PIL**: For image processing.
- **Scikit-learn**: For machine learning tasks.
- **Imbalanced-learn**: For handling imbalanced datasets.
- **XGBoost**: For advanced gradient boosting.

## Exploratory Data Analysis (EDA)

The dataset of ChatGPT reviews was loaded and inspected to understand its structure. EDA included:

- **Rating Distribution**: Visualizing the distribution of ratings to identify trends and patterns.
- **Missing Values Analysis**: Identifying and handling missing values.
- **Review Text Analysis**: Generating word clouds to visualize the most common words in the reviews.

## Data Preprocessing

1. **Combining Columns**: Combining review timestamp and review text into a single column for comprehensive analysis.
2. **Lowercasing**: Converting all text to lowercase to maintain uniformity.
3. **Removing Punctuation and Emojis**: Cleaning the text data by removing unnecessary characters.
4. **Stopwords Removal**: Eliminating common words that do not contribute significantly to the sentiment analysis.
5. **Lemmatization**: Reducing words to their base forms using SpaCy.
6. **Removing Specific Words**: Removing words specific to the app (e.g., 'chatgpt', 'app') to focus on sentiment-bearing words.

## Sentiment Mapping

The ratings were mapped to sentiments:
- **Positive**: Ratings > 3
- **Neutral**: Ratings = 3
- **Negative**: Ratings < 3

## Imbalanced Data Handling

The dataset was imbalanced, with a higher proportion of positive reviews. To address this, Synthetic Minority Over-sampling Technique (SMOTE) was used to balance the dataset by oversampling the minority classes.

## Feature Extraction

Text features were extracted using:
- **Count Vectorizer**: Converting text into a bag-of-words model.
- **TF-IDF Vectorizer**: Converting text into term frequency-inverse document frequency (TF-IDF) features.

## Model Training and Evaluation

### Train-Test Split

The data was split into training and testing sets using a 85-15 split with stratification to maintain the distribution of sentiments.

### Multinomial Naive Bayes

- **Training**: The Multinomial Naive Bayes model was trained on the processed data.
- **Evaluation**: The model's performance was evaluated using classification metrics, achieving a reasonable accuracy.

### Logistic Regression

- **Training**: A logistic regression model was trained on the balanced dataset.
- **Evaluation**: The model's performance was evaluated, showing competitive results.

### XGBoost

- **Training**: The XGBoost model was trained using the DMatrix API for efficient handling of the data.
- **Evaluation**: XGBoost achieved the highest accuracy of 92%, demonstrating superior performance compared to other models.

## Conclusion

The project successfully classified user reviews of ChatGPT from the Play Store into positive, negative, and neutral sentiments. XGBoost emerged as the best-performing model with an accuracy of 92%. This sentiment analysis provides valuable insights for businesses to understand user feedback, improve customer satisfaction, and make data-driven decisions for product enhancement.

Overall, the developed sentiment analysis model offers a robust tool for analyzing and understanding user sentiments in reviews, helping to enhance the quality and user experience of ChatGPT.