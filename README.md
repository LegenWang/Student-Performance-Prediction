## Student-Performance-Prediction
This project is done by Shiyi Li, Shilong Wang, Supeng Yu

## Introduction 
Student performance is a multifaceted issue influenced by a combination of personal, familial, and institutional factors, with exam scores serving as a critical indicator of individual achievement.​ We aim to identify the factors that significantly impact exam scores and compare the predictive accuracy (MSE on test set) and R-squared value (the fraction of variance explained by the model) of different modeling approaches in evaluating these factors.​

## Models and Tools
- Multiple Linear Regression Model
- Random Forest 
- Hyperparameter Tuning
- SHAP

## Preprocess the Dataset
1. Get rid of rows with missing value (6378 remaining)
2. Convert categorial variable variable into numerical format using one-hot-encoding (40 predictor variables including dummy variables)
3. Standardize numerical to ensure all features contribute equally to model performance and to minimize issues caused by varying scales of data
4. Split the data set into a train set with 80% observations and a test set with 20% observations (train set: 5102 observations, test set: 1276 observations).​
<img width="184" alt="Screenshot 2025-04-05 at 19 14 16" src="https://github.com/user-attachments/assets/0900842e-303d-49d5-b49a-83d7c9daa4fd" />

## Multiple Linear Regression (Best model for this dataset)
1. Use the stepwise regression method to select the "best" subset of predictors
2. Use Ordinary Least Squares (OLS) to estimate the parameters of the MLR model by minimizing the sum of the squared residuals (differences between observed and predicted values).​
3. R-squared: 0.7364870905041896
4. MSE on test set: 5.526956754131496
<img width="377" alt="Screenshot 2025-04-05 at 19 15 13" src="https://github.com/user-attachments/assets/ff5c2065-fc8d-4788-b109-3594380e2e2b" />

## Exahustive Hyperparameter Tuning 
Final best result
- max_features=19,​
- n_estimators=650,​
- max_depth=15,​
- min_samples_leaf=1,​
- bootstrap=True
- Test MSE: 6.39789
- R^2 on Train: 0.61411
<img width="392" alt="Screenshot 2025-04-05 at 19 19 21" src="https://github.com/user-attachments/assets/f01796e9-bdac-4f51-b422-7e804c43febb" />


## SHAP
- Use SHAP Summary Plot to provide a comprehensive view of how each feature contributes to the model's predictions.
<img width="276" alt="Screenshot 2025-04-05 at 19 20 26" src="https://github.com/user-attachments/assets/2fae13b6-35d1-4a1b-a139-fc1b5b289bf6" />

- Use SHAP Interaction Plot to show the correlation between twos feartures in the dataset and how they are impacting the student performance together 
<img width="314" alt="Screenshot 2025-04-05 at 19 19 10" src="https://github.com/user-attachments/assets/292377a8-afc7-495f-9250-a21231d440da" />

