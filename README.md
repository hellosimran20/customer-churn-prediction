## Customer Churn Prediction
A machine learning project that predicts whether a telecom customer is likely to
churn (leave the service), using Logistic Regression, Decision Tree and Random
Forest models, with a Streamlit web app for real-time predictions.

## Problem Statement
- Customer churn directly hurts revenue, and retaining a customer costs less than acquiring a new one.
- This project predicts churn from customer demographics, services used, contract type and billing details.
- Businesses can use the predictions to find at-risk customers and target retention efforts.

## Dataset
- Telecom customer data, one row per customer. [fill in: name and source, e.g. Telco Customer Churn on Kaggle]
- Size: [fill in rows × columns]
- Target variable: `Churn` (Yes/No → 1/0)
- Input features (19):
  - Demographics: `gender`, `SeniorCitizen`, `Partner`, `Dependents`
  - Account info: `tenure`, `Contract`, `PaperlessBilling`, `PaymentMethod`
  - Services: `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`,
    `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`
  - Charges: `MonthlyCharges`, `TotalCharges`
    
## Workflow
1. Data loading and cleaning [fill in: e.g. fixing `TotalCharges` type, handling missing values]
2. Exploratory data analysis (EDA) [fill in: key findings, e.g. month-to-month contracts churn more]
3. Preprocessing: encoding of categorical features and scaling of numeric features [confirm steps]
4. Train/test split [fill in ratio]
5. Model training and comparison
6. Evaluation and selection of the best model
7. Saving the trained model with `joblib`
8. Deployment as a Streamlit app

##  Models Used
- Logistic Regression
- Decision Tree
- Random Forest

##  Results
| Model               | Accuracy | Precision | Recall   | F1-score |-
|---------------------|----------|-----------|----------|----------|-
| Logistic Regression |[0.802416]|[0.602094] |[0.614973]|[0.608466]|      
| Decision Tree       |[0.789623]|[0.644578] |[0.572193]|[0.606232]|     
| Random Forest       |[0.792466]|[0.637584] |[0.508021]|[0.565476]|

- Best model: [Random Forest], saved as `models/customer_churn_model.pkl`

##  Web App (Streamlit)
- `app.py` loads the saved model and provides a form for entering customer details.
- The user clicks **Predict Churn** and the app shows whether the customer is
  likely to churn (red alert) or stay (green message).
- The saved model accepts raw customer inputs directly, so preprocessing is part
  of the saved pipeline.

##  Project Structure
customer-churn-prediction/
├── data/            # Dataset
├── notebooks/       # EDA, preprocessing and model training notebooks
├── models/          # Saved trained model (customer_churn_model.pkl)
├── app.py           # Streamlit app for predictions
├── requirements.txt # Python dependencies
├── .gitignore
└── README.md

##  Tech Stack
- Python
- pandas, NumPy: data handling
- scikit-learn: modelling and evaluation
- matplotlib, seaborn: visualization
- joblib: model saving/loading
- Streamlit: web app

##  Installation and Usage
1. Clone the repository
   git clone https://github.com/hellosimran20/customer-churn-prediction.git
   cd customer-churn-prediction
2. (Optional) Create a virtual environment
   python -m venv venv
   source venv/bin/activate      # Windows: venv\Scripts\activate
3. Install dependencies
   pip install -r requirements.txt
4. Run the app
   streamlit run app.py
5. To retrain the model, run the notebook in `notebooks/`.

##  Future Improvements
- Try XGBoost / LightGBM and hyperparameter tuning
- Handle class imbalance (SMOTE or class weights)
- Add feature importance / SHAP explanations
- Show churn probability instead of only a yes/no result
- Deploy on Streamlit Cloud and add a live demo link

##  Author
Simran ([@hellosimran20](https://github.com/hellosimran20))
