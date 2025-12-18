# Employee Sentiment Analysis

## Project Overview
This project focuses on analyzing employee email communications to understand overall sentiment and engagement levels using **Natural Language Processing (NLP)** and **statistical analysis**.  
Since the provided dataset was unlabeled, sentiment for each message was automatically determined using the **VADER sentiment analysis technique**.

The project covers the complete pipeline including sentiment labeling, exploratory data analysis, employee sentiment scoring, ranking, flight risk detection, and predictive modeling.

---

## Dataset Information
- **File Name**: `test.csv`
- **Data Type**: Internal employee email communications

### Key Columns Used:
- `from` – Employee identifier (email address)
- `Subject` – Subject line of the email
- `body` – Main content of the message
- `date` – Timestamp of when the email was sent

---

## Sentiment Labeling Method
- **Tool Used**: VADER Sentiment Analyzer
- **Sentiment Categories**:
  - Positive
  - Neutral
  - Negative

### Classification Logic (Compound Score):
- **≥ 0.05** → Positive  
- **≤ -0.05** → Negative  
- **Between -0.05 and 0.05** → Neutral  

### Sentiment Distribution:
- **Positive**: 1545 messages  
- **Neutral**: 382 messages  
- **Negative**: 264 messages  

---

## Monthly Employee Sentiment Scoring
Each email message was assigned a numerical value based on its sentiment:
- Positive → +1  
- Negative → -1  
- Neutral → 0  

Scores were aggregated **monthly for each employee**, with sentiment scores resetting at the beginning of every new month.

---

## Employee Ranking
For every month:
- The **Top 3 Positive Employees** were identified based on the highest sentiment scores.
- The **Top 3 Negative Employees** were identified based on the lowest sentiment scores.
- In case of ties, employees were sorted alphabetically by their identifier.

This ranking highlights both highly engaged employees and those expressing dissatisfaction.

---

## Flight Risk Detection
An employee is classified as a **flight risk** if:
- They have sent **4 or more negative messages within any rolling 30-day period**.
- Monthly boundaries are ignored, ensuring continuous monitoring.

This approach helps detect consistent negative sentiment patterns at an early stage.

---

## Predictive Modeling
- **Model Used**: Linear Regression
- **Target Variable**: Monthly sentiment score

### Features Included:
- Number of messages sent per month
- Average message length
- Total message length
- Count of negative messages

### Key Model Observations:
- Negative message count has the strongest adverse impact on sentiment score.
- Higher communication frequency often aligns with more positive sentiment.
- Message length can indicate emotional depth or intensity.

---

## Key Insights & Recommendations

### Insights:
- Most employee communications show positive sentiment, indicating generally healthy engagement.
- A small group of employees consistently displays negative sentiment and requires attention.
- Message frequency and negativity significantly influence sentiment scores.

### Recommendations:
- Proactively track employees flagged as flight risks.
- Encourage transparent communication to address recurring negative sentiment.
- Use sentiment analysis as a continuous feedback and engagement monitoring tool.

---

## Repository Structure
Employee-Sentiment-Analysis/
├── data/
│ └── test.csv
├── notebooks/
│ └── employee_sentiment_analysis.ipynb
├── visualizations/
└── README.md


---

## Author
**Soham M. Tare**
