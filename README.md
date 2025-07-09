# House-Price-Prediction
This project focuses on predicting house prices using supervised machine learning regression techniques. The dataset contains 75+ features(both numerical and categorical), requiring significant preprocessing, transformation, and feature selection. The end goal is find the best model for predicting house prices.

Workflow Summary

Data Exploration & Cleaning

• Loaded the dataset (data.csv), observed that all features were initially of type object.

• Converted features to appropriate types (e.g., float, int, category) as needed.

• Identified and visualized missing values.

Imputation

Applied SimpleImputer for both categorical and numerical features:

• Numerical: filled using mean/median.

• Categorical: filled using mode (most frequent).

Preprocessing

Used ColumnTransformer to handle separate transformation paths

• OneHotEncoding for categorical features.

• Scaling and imputation for numerical features.

Feature Selection

Narrowed down features using:

• LassoCV: A regularized regression method that helps select important features by shrinking coefficients of less relevant ones to zero.

• Started with ~80 features and reduced them significantly before model training.

Model Building Built and tested a variety of regression models

• Linear Regression

• K-Nearest Neighbors Regressor (KNN)

• Support Vector Regressor (SVR)

• Decision Tree Regressor

• Random Forest Regressor

• Gradient Boosting Regressor

• XGBoost Regressor

Model Evaluation Evaluated models using

• R² Score

• Mean Absolute Error (MAE)

• Root Mean Squared Error (RMSE)

• Relative Error

Hyperparameter Tuning

• GridSearchCV

• RandomizedSearchCV

Challenges Faced

Feature Selection Bottleneck:

• Reducing from 80+ features to the most impactful ones was time-consuming.

• Extracting and displaying feature names after selection using LassoCV inside pipelines caused multiple errors.

• Data Type Conversion: All columns initially read as object, requiring careful conversion for imputation, encoding, and modeling.

Key Insights

• LassoCV was highly effective in dimensionality reduction and overfitting control.

• XGBoost Regressor consistently outperformed others in terms of accuracy and generalization.

• Proper imputation and encoding significantly impacted model performance.

• Preprocessing pipelines improved modularity but added complexity when introspecting intermediate steps
