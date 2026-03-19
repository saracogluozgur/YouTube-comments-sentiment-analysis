# NLP Analysis of YouTube Comments on Streaming and Piracy

## Overview
This project applies natural language processing (NLP) techniques to a dataset of YouTube comments discussing streaming services, subscription prices, and piracy from the video https://youtu.be/ObL2xm5NrCk?si=G23n3GAu2yIbilhF titled "Why the era of cheap streaming is over" from Vox. The analysis explores how viewers react to changes in the streaming market by cleaning comment text, extracting topics, visualizing frequent terms, and measuring sentiment. The project combines text preprocessing, TF-IDF vectorization, topic modelling, and sentiment analysis in Python.

## Dataset
The dataset contains **2,120 YouTube comments** and **4 variables**:

- `comment_id`
- `comment_text`
- `like_count`
- `published_at`

## Files
- `nlp_ytcomments_ozgursaracoglu.ipynb` — main Jupyter Notebook containing the full analysis
- `youtube_comments.csv` — dataset used in the project

## Objectives
The main goals of this project are to:

- preprocess raw YouTube comment text for analysis
- identify the most common themes in viewer discussions
- visualize important words and expressions
- measure sentiment in comments using VADER
- compare sentiment patterns across discovered topics

## Methods Used

### 1. Data Exploration
The project begins by loading and inspecting the dataset, checking its structure, and exploring the `comment_text` field.

### 2. Text Preprocessing
The comments are cleaned through several NLP preprocessing steps:

- lowercase conversion
- URL removal
- punctuation removal
- number removal
- tokenization
- stopword removal
- lemmatization
- removal of very short tokens

A cleaned version of the text is then rebuilt into a final corpus for modelling.

### 3. Document Vectorization
The processed comments are converted into numerical form using **TF-IDF vectorization**.  
The resulting document-term matrix has shape **(2120, 801)**.

### 4. Word Cloud
A word cloud is generated to highlight the most frequent and important words in the YouTube comments.

### 5. Topic Modelling
The project uses **Non-Negative Matrix Factorization (NMF)** with **5 topics** to identify the dominant themes in the discussion.

Examples of extracted topic keywords include:

- **Topic 0:** streaming, service, watch, free, pay, netflix, show
- **Topic 1:** pirate, life, free, use
- **Topic 2:** piracy, back, people, video
- **Topic 3:** sea, sail, high, back, pay
- **Topic 4:** torrent, back, bring, old

These topics suggest strong discussion around:
- streaming service costs
- free alternatives
- piracy culture and references
- torrent-related language

### 6. Sentiment Analysis
The notebook applies **VADER sentiment analysis** to compute four sentiment scores for each comment:

- positive
- neutral
- negative
- compound

Average sentiment scores across all comments are:

- **Positive:** 0.1108
- **Neutral:** 0.8365
- **Negative:** 0.0507
- **Compound:** 0.1467

This suggests that the overall conversation is mostly **neutral**, with mild positive and negative variation.

### 7. Statistical Testing
The project also tests whether sentiment differs across the discovered topics using:

- **ANOVA**
- **Tukey HSD post-hoc comparisons**

The ANOVA results show statistically significant differences across topics for:

- positive sentiment
- negative sentiment
- neutral sentiment
- compound sentiment

This means that some topics are discussed in a more positive, negative, or neutral tone than others.

## Tools and Libraries
This project uses:

- Python
- Pandas
- NumPy
- NLTK
- Scikit-learn
- Matplotlib
- WordCloud
- SciPy
- Statsmodels

## Key Takeaways
- Viewer comments strongly reflect frustration with the fragmentation and pricing of streaming services.
- Piracy-related language appears frequently, showing that many users compare legal streaming costs with free alternatives.
- Topic modelling reveals distinct discussion clusters around streaming services, piracy, torrents, and consumer dissatisfaction.
- Sentiment is mostly neutral overall, but statistical testing shows that emotional tone differs significantly by topic.

## How to Run
1. Open the notebook in Jupyter Notebook or JupyterLab.
2. Make sure the required Python libraries are installed.
3. Keep `youtube_comments.csv` in the same folder as the notebook.
4. Run the notebook cells in order.

## Author
**Ozgur Saracoglu**
