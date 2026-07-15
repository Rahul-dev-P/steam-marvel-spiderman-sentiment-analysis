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

### Feature Distribution

Playtime (skew: 7.70) and review length (skew: 6.30) were both heavily right-skewed — most players write short reviews, but a small group of power-users pulls the tail way out. Feedback itself was left-skewed (-1.64), meaning the dataset leans strongly positive overall.

### Verbosity Vs Polarity

Review length had a weak negative correlation (-0.15) with positive feedback — frustrated players write longer, more detailed complaints. Interestingly, playtime and review length were basically uncorrelated (-0.02), so grinding more hours doesn't mean writing more.

### The late-June spike

Review volume surged in late June 2025 while average playtime and review length dropped — a pretty clear signature of a sale bringing in a wave of casual new players.

### What people actually talk about

Positive reviews center on "story," "game," "great." Negative ones are almost entirely technical — "optimization," "glitch," "performance," "frame" — pointing to a rough PC port experience.

### Where VADER breaks down

A lot of negative reviews open with praise (story, traversal) before pivoting hard into complaints about crashes and performance. That mixed sentiment confuses a lexicon-based scorer like VADER, which is exactly why I fed those scores into ML classifiers instead of trusting VADER's raw output alone.

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
