# Telecom Customer Churn Analysis

## Project Overview
This project analyzes customer churn in a telecom company using machine learning techniques. The goal is to predict which customers are likely to churn and identify the key factors influencing customer retention.

## Files in this Project
- `Telecom_Churn_Analysis.ipynb`: Jupyter notebook containing the main analysis
- `requirements.txt`: List of Python packages required for this project
- `.gitignore`: Specifies intentionally untracked files to ignore

## Dataset
The dataset contains customer information including demographics, services used, account information, and churn status. It consists of 5634 samples and 7072 features.

## Methodology
1. Data Preprocessing
   - Handling missing values
   - Encoding categorical variables
   - Feature scaling

2. Feature Selection
   - Removing constant features
   - Selecting top 100 features using SelectKBest

3. Model Building
   - Logistic Regression with hyperparameter tuning

4. Model Evaluation
   - Classification report (Precision, Recall, F1-Score)
   - ROC-AUC score
   - Confusion Matrix

## Key Findings
- The model achieved an accuracy of 80% in predicting customer churn.
- ROC-AUC score of 0.85, indicating good discriminative ability.
- Top features influencing churn:
  1. Contract Type (Month-to-Month contracts have higher churn)
  2. Tenure (Shorter tenure correlates with higher churn)
  3. Total Charges (Higher charges associated with increased churn)
  4. Internet Service (Fiber optic users more likely to churn)
  5. Payment Method (Electronic check users show higher churn rates)

## Visualizations
- Feature Importance Plot: Highlights the top factors influencing churn
- Confusion Matrix Heatmap: Illustrates model performance in predicting churn
- ROC Curve: Demonstrates the model's ability to distinguish between churners and non-churners

## Conclusions and Recommendations
- Conclusions:
1. Month-to-month contracts are a significant risk factor for churn.
2. Customers with shorter tenure are more likely to churn.
3. Higher total charges correlate with increased churn risk.
4. Fiber optic internet service users have higher churn rates.
5. Customers using electronic checks as a payment method are more prone to churning.

- Recommendations:
1. Offer incentives for longer-term contracts to reduce month-to-month churn.
2. Implement a robust onboarding program for new customers to increase early engagement and tenure.
3. Review pricing strategies, especially for high-value customers, to ensure competitive rates.
4. Investigate and improve the quality and support for fiber optic internet services.
5. Encourage customers to switch to more stable payment methods like direct debit.
6. Develop targeted retention campaigns for high-risk segments identified by the model.
7. Implement a proactive customer service approach for customers showing early signs of dissatisfaction.

## Future Work
- Experiment with other machine learning algorithms (e.g., Random Forest, XGBoost)
- Perform more in-depth feature engineering
- Conduct a cost-benefit analysis of retention strategies
- Develop a real-time churn prediction system
- Analyze the impact of customer retention efforts over time

## Tools and Technologies Used
- Python 3.x
- Libraries: pandas, numpy, scikit-learn, matplotlib, seaborn

## How to Run
1. Ensure you have Python 3.x installed
2. Install required packages: `pip install -r requirements.txt`
3. Open and run the Jupyter Notebook: `Telecom_Churn_Analysis.ipynb`

## Contact Me
Raveena Sarwal - https://www.linkedin.com/in/raveena-sarwal-data-governance-analysis-visualization/

## License
This project is open-source and available under the MIT License.
