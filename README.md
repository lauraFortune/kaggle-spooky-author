
# Kaggle: Spooky Author Identification
![Banner](images/header.png)

> Kaggle's Spooky Author Identification competition using PySpark MLlib. Originally developed on Databricks as part of a 'Programming for Big Data' assignment, and later converted for local Spark development. This project served as an introduction to machine learning, focusing on exploring text classification techniques and the ML pipeline, rather than optimisation for Kaggle submission.


[![Kaggle](https://img.shields.io/badge/Kaggle-Competition-F2FA98)](https://www.kaggle.com/competitions/spooky-author-identification)
[![PySpark](https://img.shields.io/badge/PySpark-MLlib-8FB4FF)](https://spark.apache.org/mllib/)

## Project Overview
**Competition:** Spooky Author Identification <br>
**Problem:** Predict the author of excerpts from horror stories by Edgar Allan Poe, Mary Shelley, and HP Lovecraft.<br>
**Task:** Train a model on the labelled training set to accurately attribute each text excerpt to its author in the unlabelled test set. <br>
**Log Loss:** The evaluation model favours highly confident correct predictions, resulting in lower log loss scores. While correct predictions that are also low in confidence can incur greater penalties than incorrect predictions. Consequently, confidence probability estimates are far more important than pure accuracy. <br>
**Technology:** PySpark ML library, Python, Jupyter Notebook <br>
**Pipeline:** Tokenizer --> Stopword Removal --> CountVectorizer --> IDF (TF-IDF) --> Classifier --> Predictions <br>
**Classifiers:** Logistic Regression (best), Multinominal Naive Bayes, Random Forest. <br>

### Results 
| Model | Log Loss | Best Params |
| :---- |:-------- |:----------- |
| **Logistic Regression** | **0.49** | regParam: 0.08, vocabSize: 11500, elasticNetParam: 0.0 |
| Naive Bayes | 0.59 |  |
| Random Forest | 0.92 |  |

**Kaggle Submission Score:** 0.46689 (Logistic Regression)

## How to Run

**Prerequisites:** Python 3.8+, Java 11+ (required for PySpark)

```bash
# 1. Project setup
mkdir spooky-author-project && cd spooky-author-project 
mkdir data

# 2. Download Kaggle datasets and place in data folder:
# https://www.kaggle.com/competitions/spooky-author-identification/data 

# 3. Download notebook (Windows)
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/lauraFortune/kaggle-spooky-author/main/notebooks/spooky-author-identification.ipynb" -OutFile "spooky-author-identification.ipynb"

# OR Download notebook (Mac/Linux)
curl -O https://raw.githubusercontent.com/lauraFortune/kaggle-spooky-author/main/notebooks/spooky-author-identification.ipynb

# 4. Install dependencies
pip install pyspark==3.5.3 matplotlib wordcloud pandas jupyter

# 5. Run notebook
jupyter notebook spooky-author-identification.ipynb
```

**Key Project Files:**
- `notebooks/spooky-author-identification.ipynb` - Local PySpark notebook
- `notebooks/spooky-author-identification-databricks.ipynb` - Original Databricks version
- `data/` - Kaggle training and test datasets
- `output` - Kaggle submission (predictions CSV)
