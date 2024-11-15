# Telecom Customer Churn Analysis

## Project Overview
This project analyzes customer churn in a telecom company using machine learning techniques. The goal is to predict which customers are likely to churn and identify the key factors influencing customer retention.

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
- [Add your key findings here]
- Top features influencing churn: [List top features]
- Model Performance: [Add your best model's performance metrics]

## Visualizations
- Feature Importance Plot
- Confusion Matrix Heatmap
- ROC Curve

## Conclusions and Recommendations
- [Add your main conclusions]
- [List your recommendations for reducing churn]

## Future Work
- Experiment with other machine learning algorithms (e.g., Random Forest, XGBoost)
- Perform more in-depth feature engineering
- Conduct a cost-benefit analysis of retention strategies

## Tools and Technologies Used
- Python 3.x
- Libraries: pandas, numpy, scikit-learn, matplotlib, seaborn

## How to Run
1. Ensure you have Python 3.x installed
2. Install required packages: `pip install -r requirements.txt`
3. Open and run the Jupyter Notebook: `Telecom_Churn_Analysis.ipynb`

## Author
[Your Name]

## License
This project is open-source and available under the MIT License.
