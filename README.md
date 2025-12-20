# Detecting-and-Analyzing-Emotional-Distress-Signals-in-Social-Media-Text-Data

## Notebook Overview
Two separate analyses were created using Twitter and Reddit data. The code for both
data are 

### 1. `twitter_cleaning.ipynb` / `reddit_cleaning.ipynb`
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

### 2. `sentiment_analysis.ipynb`
**Purpose:**  
Generates polarity score and classifies each post as positive, neutral, or negative based on threshold

**Inputs:**  
- Cleaned text (`clean_post`) from preprocessing notebook

**What it does:**  
- Applies polarity score to each clean post 
- Classifies each post as positive, neutral, and negative 
- Splits classifications into non-negative affect or high negative affect based on threshold -0.05. 
- Creates and adds new columns `polarity`, `sentiment`, `affect_label`, and `label_name` to datasets  

**Outputs:**  
- Full datasets with added features
- `twitter_data_full.csv`
- `reddit_data_full.csv` 

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

