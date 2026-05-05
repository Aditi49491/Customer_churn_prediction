Customer Churn Prediction — Telecom Dataset
Predicting which customers are likely to leave a telecom provider using machine learning, with a focus on handling class imbalance and delivering actionable business insights.

Problem Statement
Customer churn is one of the most costly problems in the telecom industry. Acquiring a new customer costs significantly more than retaining an existing one. This project builds a classification model to identify at-risk customers before they churn, enabling targeted retention strategies.

Dataset

Source: Telco Customer Churn — Kaggle
Size: 7,043 records, 20 features
Target variable: Churn (Yes / No)
Key features: Contract type, tenure, monthly charges, internet service, payment method


Project Workflow
Data Loading & Exploration
        ↓
Exploratory Data Analysis (EDA)
        ↓
Data Preprocessing & Feature Engineering
        ↓
Handling Class Imbalance (SMOTE)
        ↓
Model Training & Cross-Validation
        ↓
Model Evaluation & Comparison
        ↓
Feature Importance & Business Insights
        ↓
Model Export (Pickle)

Key Findings

Contract type is the strongest churn predictor — month-to-month customers churn at 3x the rate of annual contract holders
Tenure matters — customers in their first 12 months are at highest risk
Monthly charges above ₹65 correlate with significantly higher churn
Customers without tech support or online security are more likely to leave


Models & Results
ModelAccuracyRecall (Churn)F1 ScoreDecision Tree78%0.710.69XGBoost83%0.760.74Random Forest ✅84%0.790.77
Random Forest selected as the final model based on highest accuracy and recall on the minority (churn) class.
Why SMOTE?
The dataset was imbalanced (~73% No Churn, ~27% Churn). Without correction, models bias toward predicting "No Churn" and miss actual churners. SMOTE (Synthetic Minority Oversampling Technique) was applied to the training set to balance classes and improve recall on the churn class.

Tech Stack
ToolPurposePythonCore languagePandas, NumPyData manipulationMatplotlib, SeabornVisualisationScikit-learnML models, cross-validationImbalanced-learnSMOTEXGBoostGradient boosting modelPickleModel serialisation

Project Structure
customer-churn-prediction/
│
├── churn_prediction.ipynb     ← Main notebook (EDA + modeling)
├── model.pkl                  ← Saved Random Forest model
├── requirements.txt           ← Dependencies
└── README.md

How to Run

Clone the repository

bashgit clone https://github.com/your-username/customer-churn-prediction.git
cd customer-churn-prediction

Install dependencies

bashpip install -r requirements.txt

Open the notebook

bashjupyter notebook churn_prediction.ipynb

Business Recommendations
Based on model insights, a telecom company could:

Target month-to-month customers in months 1–12 with loyalty discounts
Offer contract upgrades to high-charge customers showing early churn signals
Bundle tech support with high-value plans to reduce churn risk


Author
Aditi Sachdeva
B.Sc Computer Science, SSCBS — University of Delhi
