# Detecting-and-Analyzing-Emotional-Distress-Signals-in-Social-Media-Text-Data

## Notebook Overview

### 1. `twitter_cleaning.ipynb` / 'reddit_cleaning.ipynb'
**Purpose:**  
Cleans and prepares raw Twitter and Reddit text data for analysis and machine learning.

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

### 2. `02_tfidf_analysis.ipynb`
**Purpose:**  
Transforms cleaned text into numerical features using TF-IDF and identifies the most distinctive words and phrases.

**Inputs:**  
- Cleaned text (`clean_post`) from preprocessing notebook

**What it does:**  
- Builds a TF-IDF matrix using unigrams and bigrams  
- Removes extremely common and extremely rare terms  
- Identifies top TF-IDF term–document pairs  
- Displays full cleaned posts alongside high TF-IDF terms for interpretability  

**Outputs:**  
- TF-IDF feature matrix  
- Tables of top TF-IDF terms with contextualized text examples  

---

### 3. `03_sentiment_analysis.ipynb`
**Purpose:**  
Quantifies emotional polarity in posts to complement lexical features.

**Inputs:**  
- Cleaned text (`clean_post`)

**What it does:**  
- Applies sentiment analysis (e.g., VADER / TextBlob)  
- Computes polarity and subjectivity scores  
- Analyzes sentiment distributions across posts  

**Outputs:**  
- Sentiment score columns added to the dataset  
- Visualizations summarizing sentiment trends  

---

### 4. `04_topic_modeling.ipynb`
**Purpose:**  
Identifies latent themes in mental-health-related text using topic modeling.

**Inputs:**  
- Lemmatized tokens from preprocessing  

**What it does:**  
- Constructs document–term matrices  
- Fits an LDA topic model  
- Extracts and interprets dominant topics  
- Assigns topic probabilities to documents  

**Outputs:**  
- Topic–word distributions  
- Document-level topic probabilities  
- Topic interpretation tables  

---

### 5. `05_logistic_regression.ipynb`
**Purpose:**  
Builds and evaluates a classification model to identify mental-health-related posts.

**Inputs:**  
- TF-IDF features  
- Sentiment scores  
- Topic probabilities  
- Target labels (if applicable)

**What it does:**  
- Combines linguistic and semantic features  
- Trains a logistic regression classifier  
- Evaluates performance using accuracy, ROC-AUC, and confusion matrices  
- Interprets model coefficients to identify predictive terms  

**Outputs:**  
- Trained classification model  
- Evaluation metrics and figures  
- Interpretable feature importance results  

