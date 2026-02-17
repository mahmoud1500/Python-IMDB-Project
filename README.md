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

**Key Finding:** The model achieved an **
