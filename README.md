# Customer Lifetime Value Classification – EcomX Retailers

## Overview  
**Objective**: Predict which customers are likely to be high-value, so the business can focus marketing and retention resources effectively.  
**Business Context**: EcomX Retailers is an e-commerce company seeking to optimize its customer segmentation strategy. By predicting CLV classes, they aim to personalize outreach, reduce churn, and increase ROI from customer-facing initiatives.

---

## Target Label Creation: CLV Classes  
To simplify the prediction task, Customer Lifetime Value (CLV) was calculated per customer and binned into three classes using the **quartile method**:
- **Low**: CLV < $1,724.13 (bottom 25%)  
- **Medium**: $1,724.13 ≤ CLV < $7,036.56 (middle 50%)  
- **High**: CLV ≥ $7,036.56 (top 25%)  

This classification supports strategic targeting of customer segments based on spend and engagement behavior.

---

## Key Insight  
Behavioral and transactional features — especially **total spend**, **site engagement**, and **email interaction** — were strong predictors of high-value customers. Random Forest achieved the best performance across classification metrics.

---

## General Logic of the Code

1. **Data Integration**  
   - Combined `customers`, `transactions`, `engagements`, and `marketing` datasets using `customer_id`.

2. **Feature Engineering**  
   - Aggregated total spend and number of transactions.  
   - Merged in engagement metrics like site visits and email interactions.  
   - Created binary indicators for marketing campaign response.

3. **Target Creation**  
   - Computed total CLV per customer.  
   - Used quartiles to categorize CLV into Low, Medium, and High classes.

4. **Preprocessing**  
   - Handled missing values and scaled numeric features.  
   - Encoded categorical variables using LabelEncoder and OneHotEncoder.

5. **Modeling & Evaluation**  
   - Trained multiple classifiers: Logistic Regression, KNN, Random Forest, Naive Bayes.  
   - Evaluated models using **accuracy**, **F1-score**, **precision**, and **recall**.  
   - Random Forest outperformed other models, especially for high-value customer identification.

---

## Tools & Technologies Used  
- **Languages & Libraries**: Python, pandas, numpy, seaborn, matplotlib, scikit-learn  
- **Models**: K-Nearest Neighbors  
- **Techniques**: Feature engineering, classification, quartile-based binning, model evaluation

---

## Files in This Repository  

| File Name                 | Description |
|--------------------------|-------------|
| `customers_final.csv`    | Customer demographic and purchase history metadata |
| `transactions_final.csv` | Full purchase transactions with amount and category |
| `engagements_final.csv`  | Customer-level behavioral metrics (clicks, visits, opens) |
| `marketing_final.csv`    | Campaign interaction history |
| `final_code.ipynb`       | Main notebook containing full analysis and model building |
| `README.md`              | This documentation file |

