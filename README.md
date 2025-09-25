
# Spooky Author Identification - Spark NLP Pipeline
![Banner](images/header.png)

> Kaggle's Spooky Author Idetification competition walktrough

[![Kaggle Competition](https://img.shields.io/badge/Kaggle-Competition-F2FA98)](https://www.kaggle.com/competitions/spooky-author-identification)
[![PySpark](https://img.shields.io/badge/PySpark-3.5.3-8FB4FF)](https://spark.apache.org/)
[![Python](https://img.shields.io/badge/Python-3.12-FAA698)](https://spark.apache.org/)
**Competition Website:** https://www.kaggle.com/competitions/spooky-author-identification <br>

Kaggle provide two files:
- a labelled train.csv (id, text, author)
- an unlabelled test.csv (id, text)

## How to Run Locally
**Setup**
### 1. Create new project folder
```bash
mkdir spooky-author-project
cd spooky-author-project
```
### 2. Download main notebook
- For Windows
```bash
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/lauraFortune/kaggle-spooky-author/main/notebooks/spooky-author-identification.ipynb" -OutFile "spooky-author-identification.ipynb"
```
- For Mac/Linux:
```bash
curl -O https://raw.githubusercontent.com/lauraFortune/kaggle-spooky-author/main/notebooks/spooky-author-identification.ipynb
```
### 3. Install dependencies
```bash
pip install pyspark==3.5.3 matplotlib wordcloud pandas jupyter
```

### 4. Setup Data
```bash
mkdir data
```
- Download train.csv and test.csv and place in data folder: <br>
https://www.kaggle.com/competitions/spooky-author-identification/data 

### 5. Run notebook
- jupyter notebook spooky-author-identification.ipynb <br>

**Key Project Files:**
- `notebooks/spooky-author-identification.ipynb` - Local PySpark notebook
- `notebooks/spooky-author-identification-databricks.ipynb` - Original Databricks version
- `data/` - Kaggle training and test datasets
- `output` - Kaggle submission (predictions CSV)

