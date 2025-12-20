# Detecting-and-Analyzing-Emotional-Distress-Signals-in-Social-Media-Text-Data

## Notebook Overview
Two separate analyses were created using Twitter and Reddit data. The code for both
datasets are 

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

