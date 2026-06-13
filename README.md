# 🎮 Marvel's Spiderman Sentiment Analysis

## Project Overview

This project analyzes user reviews collected from Steam to understand player sentiment and predict whether a review recommends a game or not.

The workflow combines **web scraping, natural language processing (NLP), exploratory data analysis (EDA), sentiment analysis, and machine learning** to extract meaningful insights from real-world gaming reviews.

---

## Objectives

- Collect real Steam reviews automatically.
- Analyze player opinions and review behavior.
- Measure sentiment using NLP techniques.
- Identify factors influencing positive and negative feedback.
- Build machine learning models to predict review recommendations.

---

## Technology Stack

- Python
- Selenium
- Pandas
- NumPy
- Matplotlib
- Seaborn
- NLTK
- Scikit-Learn
- XGBoost

---

# Project Workflow

## 1 Data Collection (`scrap.ipynb`)

### Steam Review Scraping

Reviews were collected directly from Steam using Selenium.

### Process

- Automated browser interaction using Selenium WebDriver.
- Handled dynamic content loading and infinite scrolling.
- Extracted:
  - Review text
  - Recommendation status (Recommended / Not Recommended)
  - Playtime hours
  - Review posting date
- Stored the collected dataset for further analysis.

### Output

- steam_reviews_final.csv


---

## 2 Data Cleaning & Exploratory Data Analysis (`analysis.ipynb`)

### Data Preprocessing

The raw dataset was cleaned and standardized by:

- Removing missing values
- Renaming columns for consistency
- Converting playtime data into numerical format
- Standardizing review dates
- After preprocessing, the dataset was saved as `cleaned_reviews.csv`

### Exploratory Data Analysis

Performed analysis on:

- Review length distribution
- Playtime distribution
- Positive vs Negative review ratio
- Correlation between review length, playtime, and feedback
- Review trends over time
- Weekly and monthly review patterns

### Key Visualizations

- Bar Charts
- Histograms
- Box Plots
- Scatter Plots
- Correlation Heatmaps
- Time-Series Analysis

---

## 3 Natural Language Processing

### Text Preprocessing

Implemented NLP preprocessing using NLTK:

- Lowercasing
- URL removal
- Punctuation removal
- Tokenization
- Stop-word removal
- Lemmatization

### Sentiment Analysis

Applied **VADER (Valence Aware Dictionary and Sentiment Reasoner)** to generate sentiment scores for each review.

Generated:

- Compound sentiment score
- Sentiment distribution analysis
- After sentiment analysis, the dataset was saved as `Final_Reviews.csv`

## 4 Recommendation Prediction (`prediction.ipynb`)

### Feature Engineering

Created numerical features using:

- VADER sentiment score
- Review length

### Machine Learning Models

Trained and evaluated multiple classification models:

- Logistic Regression
- Random Forest Classifier
- XGBoost Classifier

### Evaluation Metrics

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

### Prediction Capability

The trained model can predict whether a new review is likely to be:

- Recommended
- Not Recommended

based on its textual sentiment characteristics.

---

# Key Insights

### Player Sentiment

- Most reviews were positive, indicating strong player satisfaction.
- Positive reviews generally showed higher sentiment scores.

### Review Behavior

- Review length and playtime exhibited significant right-skewed distributions.
- Highly engaged players tended to write longer reviews.

### Temporal Trends

- Review activity varied across weeks and months.
- Review spikes may indicate game updates, promotions, or seasonal sales.

### Predictive Findings

- Sentiment score proved to be a strong indicator of recommendation behavior.
- Machine learning models successfully classified user feedback using sentiment-based features.

---

# Project Structure

```text
├── notebooks/
│   ├── scrap.ipynb
│   ├── analysis.ipynb
│   └── prediction.ipynb
├── steam_reviews_final.csv
├── Cleaned_Reviews.csv
├── Final_Reviews.csv
└── README.md
```

---

# How to Run

## 1. Clone Repository

```bash
git clone https://github.com/Rahul-dev-P/steam-marvel-spiderman-sentiment-analysis.git
```

## 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn nltk selenium scikit-learn xgboost
```

## 3. Download NLTK Resources

```python
import nltk

nltk.download("stopwords")
nltk.download("wordnet")
nltk.download("punkt")
nltk.download("vader_lexicon")
```

## 4. Run Notebooks

Execute the notebooks in the following order:

```text
1. scrap.ipynb
2. analysis.ipynb
3. prediction.ipynb
```

---

# Future Improvements

- Deep learning models such as LSTM and BERT.
- Interactive dashboard using Streamlit.
- Multi-game sentiment comparison.
- Real-time Steam review monitoring.
- Model deployment through a web application.

---

## Learning Outcomes

Through this project, I have learned:

- Web scraping with Selenium
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Natural Language Processing (NLP)
- Sentiment Analysis using VADER
- Machine Learning Classification
- Model Evaluation and Performance Analysis

---
