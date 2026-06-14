# Telecom Customer Intelligence Using Machine Learning

This repository contains the group project for `36106 - Machine Learning Algorithms and Applications` in the Master of Data Science and Innovation at the University of Technology Sydney.

The project explores how a telecom company can use customer data to support better decisions across retention, revenue planning, upselling, and customer support. The work is based on customer details, address, usage, satisfaction, and subscription data.

## Project Overview

The telecom company had customer transaction and service data but needed practical ways to turn it into business insight. This project applies four modelling approaches:

| Area | Business Question | Main Method |
| --- | --- | --- |
| Regression | Which customers are likely to have higher lifetime value? | Random Forest Regressor |
| Classification | Which customers are likely to churn in the next 3 months? | Random Forest, XGBoost |
| Clustering | Which customer groups are suitable for digital service upselling? | KMeans, KMeans with PCA, DBSCAN |
| Anomaly Detection | Which customers show unusual spending or usage behaviour? | Isolation Forest, Local Outlier Factor |

## Repository Contents

| File | Description |
| --- | --- |
| `36106_25AU_AT3_25585973_eda_customer_details.ipynb` | EDA for customer details |
| `36106_25AU_AT3_25585973_regression.ipynb` | Customer lifetime value regression model |
| `36106-25AU-AT3-group-24-13417454-eda-customer-address.ipynb` | EDA for customer address data |
| `36106-25AU-AT3-group-24-13417454-2-eda-customer-satisfaction.ipynb` | EDA for customer satisfaction data |
| `36106_25AU_AT3_Group_24_13417454_classification.ipynb` | Customer churn classification model |
| `36106-25AU-AT3-group_24_25934391_eda-customer_subscriptions.ipynb` | EDA for customer subscription data |
| `36106-25AU-AT3-group_24_25934391_clustering.ipynb` | Customer segmentation and upselling analysis |
| `36106_25AU_AT3_24647024_4_eda_customer_usage.ipynb` | EDA for customer usage data |
| `36106_25AU_AT3_24647024_4_anomaly.ipynb` | Anomaly detection for spending and usage behaviour |

## Methods and Results

### 1. Customer Lifetime Value Prediction

The regression model predicts Customer Lifetime Value (CLTV). This can help the business identify high value customers, plan retention campaigns, forecast revenue, and allocate marketing budget more effectively.

Key steps:

- Removed personal identifiers and fields that were not useful for modelling.
- Handled missing values and duplicate records.
- Engineered features such as tenure category, churn status, and additional services level.
- Used feature selection to reduce noise before modelling.
- Trained a Random Forest Regressor with hyperparameter tuning.

Result:

- Test MAE: `0.761953`
- Test RMSE: `0.897445`
- Key contributing features included `month_tenure`, `total_charges`, and `total_revenue`.

### 2. Customer Churn Prediction

The classification model predicts whether a customer is likely to churn within the next 3 months. This supports early customer support action and focused retention work.

Models tested:

- Random Forest Classifier
- XGBoost Classifier

Result:

- Best F1 score: `0.8702`
- The Random Forest model was selected as a strong option because it performed well and is simpler to deploy than XGBoost.

### 3. Customer Segmentation for Upselling

The clustering work groups customers by behaviour, engagement, and service usage. The goal is to help the Product Team target digital service offers more accurately.

Models tested:

- KMeans
- KMeans with PCA
- DBSCAN

Result:

- DBSCAN performed best.
- Silhouette Score: `0.514`
- Davies-Bouldin Index: `1.050`

The DBSCAN model was useful because it could find dense customer groups while separating noisy or low engagement customers.

### 4. Anomaly Detection in Customer Behaviour

The anomaly detection work identifies unusual customer spending or usage patterns. These cases may point to fraud, billing issues, customer dissatisfaction, or churn risk.

Models tested:

- Isolation Forest
- Local Outlier Factor

Key steps:

- Selected financial and usage related features.
- Created features such as `charge_per_tenure`, `international_to_monthly_ratio`, and `premium_service_count`.
- Applied log transformation and scaling.
- Used a 5 percent contamination setting to flag likely anomalies.

Result:

- Isolation Forest flagged `4515` anomalies.
- Local Outlier Factor flagged `4571` anomalies, equal to about `5.00%` of the prepared data.

## Main Business Value

- Identify high value customers for retention and service improvement.
- Predict churn so support teams can act earlier.
- Build customer groups for better upselling campaigns.
- Detect unusual usage or spending patterns before they become larger issues.
- Support marketing, product, finance, and customer support teams with clearer customer insights.

## Tools and Libraries

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- Altair
- Plotly

## How to Run

1. Clone this repository.
2. Open the notebooks in Jupyter Notebook, JupyterLab, or Google Colab.
3. Add the required course dataset files to the paths expected by each notebook.
4. Run the EDA notebooks first, then run the modelling notebooks.

The raw dataset files are not included in this repository. They were provided for the subject assessment.

## Ethical Considerations

The project considered customer privacy and responsible use of customer data. Personal identifiers such as names, emails, phone numbers, and address details were removed where they were not needed for modelling. The report also discusses fairness, transparency, and the need for human review before using model outputs in real customer decisions.

## Team

Group 24:

| Name | Student ID | Main Responsibility |
| --- | --- | --- |
| Sahaj Gupta | 25585973 | EDA for customer details and regression |
| Yuyang Chen | 13417454 | EDA for address and satisfaction data, classification |
| Shreyash Narayane | 25934391 | EDA for customer subscriptions and clustering |
| Philopatir Bebawy | 24647024 | EDA for customer usage and anomaly detection |

## License

This repository is intended for educational and portfolio use.
