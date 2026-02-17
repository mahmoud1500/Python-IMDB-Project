# 🎬 IMDB & Metacritic Data Analysis (2000)

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![MongoDB](https://img.shields.io/badge/Database-MongoDB%20Atlas-green.svg)](https://www.mongodb.com/atlas)
[![Scikit-Learn](https://img.shields.io/badge/ML-Scikit--Learn-orange.svg)](https://scikit-learn.org/)

A data science project analyzing movie performance, financial ROI, and critic sentiment for films released in the year 2000. This project integrates data from **IMDB** and **Metacritic** via **MongoDB Atlas** to perform statistical modeling and NLP-driven sentiment analysis.

---

## 📌 Project Overview

This project explores what makes a movie successful. By merging IMDB's financial and user data with Metacritic's professional scores, we analyze:
* **Predictive Modeling:** Using OLS Regression to find the strongest drivers of Gross Sales.
* **Feature Engineering:** Calculating ROI and applying log-transformations to skewed financial data.
* **NLP Sentiment Analysis:** Using **Transformers (DistilBERT)** to analyze movie descriptions and correlate "hype" with actual user ratings.

## 🛠️ Tech Stack

* **Database:** MongoDB Atlas (PyMongo)
* **Data Manipulation:** Pandas, NumPy
* **Statistics:** Statsmodels (OLS Regression)
* **Machine Learning:** Scikit-Learn (StandardScaler)
* **NLP:** Hugging Face Transformers (DistilBERT)
* **Visualization:** Matplotlib, Seaborn

---

## 🚀 Key Analysis Phases

### 1. Data ETL & Cleaning
Data is pulled from MongoDB, filtered for the year 2000, and unified.
* **Regex Cleaning:** Titles are normalized (lowercase, stripped, special characters removed) to ensure high-accuracy merging between IMDB and Metacritic.
* **Currency Conversion:** Automated removal of symbols (`$`, `,`) and conversion to numeric types for budget and sales.

### 2. Statistical Modeling (OLS Regression)
We modeled **Log-transformed Gross Revenue** against budget, user ratings, and runtime.

$$log\_gross \sim budget\_new + user\_rating + runtime + votes$$

**Key Finding:** The model achieved an **Adj. R-squared of 0.329**. Analysis showed that **Budget** is a statistically significant predictor ($P < 0.001$) of revenue, while user ratings and runtime had less impact on commercial success for this specific year.

### 3. AI Sentiment Analysis
Using a pre-trained `distilbert-base-uncased-finetuned-sst-2-english` model, we converted movie descriptions into a sentiment score range $[-1, 1]$. This allows us to see if the "tone" of a movie's description aligns with its eventual user rating.



---

## 📊 Visualizations

The project includes several diagnostic and exploratory plots:
* **Correlation Heatmap:** To identify multicollinearity between features.
* **Residual Plot:** To validate the OLS model assumptions (homoscedasticity).
* **Log-Distribution:** Visualizing revenue to justify the use of log-scaling.



---

## 📥 Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/imdb-metacritic-analysis.git](https://github.com/yourusername/imdb-metacritic-analysis.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas pymongo certifi statsmodels scikit-learn transformers matplotlib seaborn torch
    ```
3.  **Setup Credentials:**
    Create a `credentials.json` file in the root directory:
    ```json
    {
      "mongodb": "your_mongodb_atlas_connection_string"
    }
    ```

## 📝 Results Summary
* **Significant Features:** Budget and Vote Count.
* **ROI Analysis:** Created a specific ROI metric to identify "sleeper hits" vs. "big-budget flops."
* **Regression Diagnostics:** The residual plot suggests the model is well-specified, though external factors (marketing, competition) likely account for the remaining variance.

---

**Author:** Mahmoud Faisal  
**License:** MIT
