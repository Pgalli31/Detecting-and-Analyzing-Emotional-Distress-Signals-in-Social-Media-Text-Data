# Detecting-and-Analyzing-Emotional-Distress-Signals-in-Social-Media-Text-Data

## Notebook Overview
Two separate analyses were created using Twitter and Reddit data. The code for both
datasets are 

*The analyses for both datasets are separated. There are two folders named `twitter` and `reddit`*

### 1. `twitter_cleaning.ipynb` / `reddit_cleaning.ipynb`
**Purpose:**  
Cleans and prepares raw Twitter and Reddit text data for analysis and machine learning

**Inputs:**  
- `twitter_data.csv`
- `reddit.csv`

**What it does:**  
- Removes URLs, mentions, emojis, and special characters  
- Converts text to lowercase and removes stop words 
- Creates the `clean_post` column used throughout the project  

**Outputs:**  
- Cleaned csv files ready for analyses and ML models
- `twitter_clean_data.csv`
- `reddit_clean_data.csv`
---

### 2. `sentiment_analysis.ipynb`
**Purpose:**  
Generates polarity score and classifies each post as positive, neutral, or negative based on threshold

**Inputs:**  
- Cleaned text (`clean_post`) from preprocessing notebook

**What it does:**  
- Applies polarity score to each clean post using VADER Python package
- Classifies each post as positive, neutral, and negative 
- Splits classifications into non-negative affect or high negative affect
- Creates and adds new columns `polarity`, `sentiment`, `affect_label`, and `label_name` to datasets  

**Outputs:**  
- Full datasets with added features
- `twitter_data_full.csv`
- `reddit_data_full.csv` 

---

### 3. `LDA.ipynb`
**Purpose:**  
Generate topics using Latent Dirichlet Allocation

**Inputs:**  
- Cleaned text (`clean_post`)

**What it does:**  
- Lemmatization for each text
- Creates 10, 20, and 30 topics
- Evaluates performance using coherence and perplexity scores
- Visualizes topics using PyLDavis  

**Outputs:**  
- Visualizations of 10, 20, and 30 topics using PyLDavis
- `10_twitter_lda_visualization.html`
- `10_reddit_lda_visualization.html`
- `20_twitter_lda_visualization.html`
- `20_reddit_lda_visualization.html`
- `30_twitter_lda_visualization.html`
- `30_reddit_lda_visualization.html`

---

### 4. `tf-idf.ipynb`
**Purpose:**  
Generate TF-IDF scores and display terms with highest TF-IDF scores along with the post they appear in

**Inputs:**  
- Cleaned text (`clean_post`)

**What it does:** 
- Filters out posts containing less than 5 terms
- Constructs document–term matrices  
- Constructs dataframe consisting of post index, term, and TF-IDF score
- Filters dataframe to TF-IDF scores less than 0.990

**Outputs:**  
- Returns top 5 terms with highest TF-IDF score along with post index and post text  

---

### 5. `log_regression_1.ipynb` / `log_regression_2.ipynb`
**Purpose:**  
Builds and evaluates a logistic regression model to determine the top indicators of high negative affect and non-negative affec.

**Inputs:**  
- TF-IDF terms as X variable
- Affect label 0 or 1 as Y variable 

**What it does:**   
- Trains a logistic regression classifier  
- Evaluates performance using accuracy, ROC-AUC, and confusion matrices  
- Interprets model coefficients to identify top indicators  

**Outputs:**  
- Trained classification model  
- Evaluation metrics  
- Interpretable indicator results  

