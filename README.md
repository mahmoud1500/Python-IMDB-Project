📊 IMDB & Metacritic Movie Analysis with MongoDB and Sentiment NLP
This project showcases a complete data analysis pipeline built with Python, Pandas, MongoDB, and NLP for sentiment analysis. It focuses on retrieving movie data from IMDB (via Excel), uploading and cleaning the data in MongoDB, merging it with Metacritic records, and performing linear regression analysis to understand factors affecting movie revenue.

Key components include:

📥 Data Ingestion: Load IMDB data from Excel and upload it to MongoDB.

🧹 Data Cleaning & Transformation: Filter and process movie data using pandas, especially focusing on films released in the year 2000.

🔗 Data Integration: Merge IMDB and Metacritic datasets based on movie titles.

📈 Regression Modeling: Apply linear regression with statsmodels to analyze relationships between variables like budget, rating, and gross sales.

💬 Sentiment Analysis: Use transformers pipelines with pre-trained models (DistilBERT, XLM-Roberta) to analyze movie descriptions and extract sentiment features.

🧠 Feature Engineering: Create new columns, including custom sentiment scores, to enhance the dataset for deeper analysis.

The analysis is performed in a Jupyter Notebook and connected securely to MongoDB using a credentials.json file (excluded from version control for security).

This project demonstrates data engineering, statistical modeling, and natural language processing (NLP) in action for entertainment industry insights.

