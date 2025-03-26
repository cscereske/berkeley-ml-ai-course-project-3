# Bank Marketing Campaign Analysis

## Project Overview
This project analyzes a dataset from a Portuguese banking institution containing the results of multiple marketing campaigns. The goal is to predict whether a client will subscribe to a term deposit based on various client, campaign, and economic features.

## Methodology
The analysis follows the CRISP-DM (Cross-Industry Standard Process for Data Mining) methodology:

1. **Business Understanding**: The bank wants to optimize its marketing campaigns by identifying clients who are more likely to subscribe to term deposits.

2. **Data Understanding**: The dataset contains 41,188 records with 20 input features and 1 target variable. Features include client demographics, campaign details, and economic indicators.

3. **Data Preparation**: 
   - Renamed variables using snake_case for better readability
   - Handled 'unknown' values in categorical features
   - Detected and handled outliers using IQR method and winsorizing
   - Encoded categorical variables using one-hot encoding
   - Scaled numerical features
   - Split data into training and testing sets

4. **Modeling**: Evaluated multiple classifiers:
   - Logistic Regression
   - K-Nearest Neighbors
   - Decision Tree
   - Support Vector Machine

5. **Evaluation**: Compared models using accuracy, ROC AUC, and other metrics while considering training time.

6. **Deployment**: Provided business recommendations based on model insights.

## Key Findings
- The best performing model is Support Vector Machine with an accuracy of 90.36%.
- Most important factors in predicting term deposit subscriptions:
  - employment_var_rate (economic indicator)
  - consumer_price_idx (economic indicator)
  - pdays (days since last contact from previous campaign)
  - num_employees (economic indicator)
  - consumer_conf_idx (economic indicator)

## Business Recommendations
1. **Target Marketing**: Focus marketing efforts on clients during periods of favorable economic conditions, particularly when employment_var_rate and consumer_price_idx show patterns associated with higher subscription rates.
2. **Campaign Timing**: Contact clients who haven't been contacted for a moderate amount of time. October appears to be a more favorable month for campaigns.
3. **Contact Method**: The telephone contact method appears to be an important feature in predicting subscription outcomes, suggesting different response patterns compared to cellular contacts.
4. **Economic Considerations**: Macroeconomic indicators are the strongest predictors of campaign success. Consider reducing campaign intensity during unfavorable economic periods.

## File Structure
- `bank_classifier_analysis.ipynb`: Jupyter notebook containing the complete analysis
- `data/`: Directory containing the dataset
- `README.md`: This file summarizing the project

## Usage
To run the analysis:
1. Ensure you have Python and the required libraries installed (pandas, numpy, scikit-learn, matplotlib, seaborn)
2. Open the Jupyter notebook `bank_classifier_analysis.ipynb`
3. Run all cells to reproduce the analysis

## Conclusion
This analysis demonstrates how machine learning can be applied to optimize bank marketing campaigns. By targeting clients with a higher likelihood of subscribing to term deposits, the bank can allocate its resources more efficiently and improve the return on investment for its marketing efforts. The findings suggest that economic conditions play a crucial role in the success of marketing campaigns, which should inform the timing and targeting of future efforts.