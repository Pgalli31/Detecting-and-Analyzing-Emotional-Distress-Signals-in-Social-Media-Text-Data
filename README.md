# Detecting-and-Analyzing-Emotional-Distress-Signals-in-Social-Media-Text-Data

## Overview
This repository contains the code and analysis for a Master's thesis focused on
detecting and analyzing emotional distress signals in social media text data.

The project applies data cleaning, sentiment analysis, topic modeling, 
TF-IDF analysis, and logistic regression modeling.

## Data
- Source: Reddit and Twitter (publicly available posts)
- Text field: `clean_post` (preprocessed)
- Notes:
  - All text was cleaned to remove URLs, mentions, emojis, and non-textual content
  - Very short or empty posts were excluded to ensure sufficient linguistic context
