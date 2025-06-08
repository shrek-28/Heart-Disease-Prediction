# Heart Disease Prediction using Logistic Regression

## Introduction
This repository contains the code for execution of a logistic regression model, for prediction of heart disease presence from a variety of features related to heart health. Libraries such as ```scikit-learn```, ```pandas```, ```numpy```, ```matplotlib``` and ```seaborn``` for model development, data analysis and data visualization. ```LIME``` was utilized for model explainability. 

## Dataset:
The dataset used was the Long Island dataset from the UCI ML Repository: https://archive.ics.uci.edu/dataset/45/heart+disease

The dataset's features can be described from this dataset:
| Feature     | Biological Relevance                                                                 |
|-------------|----------------------------------------------------------------------------------------|
| age         | Age is a major risk factor for heart disease; the risk increases with age.           |
| sex         | Males generally have a higher risk of heart disease compared to females.             |
| cp          | Chest pain type indicates different types of angina, a key symptom of heart issues.  |
| trestbps    | High resting blood pressure can strain the heart and arteries, increasing risk.      |
| chol        | High serum cholesterol is linked to plaque buildup in arteries (atherosclerosis).    |
| fbs         | Elevated fasting blood sugar may indicate diabetes, which is a risk factor.          |
| restecg     | Abnormal ECG results can indicate underlying heart conditions.                       |
| thalach     | Lower maximum heart rate during exercise can indicate compromised heart function.    |
| exang       | Exercise-induced angina signifies reduced blood flow to the heart under stress.      |
| oldpeak     | ST depression can reflect ischemia or reduced blood flow to the heart muscle.        |
| slope       | The slope of the ST segment helps assess the severity of ischemia during exercise.   |
| ca          | Number of vessels colored by fluoroscopy indicates the extent of coronary blockage.  |
| thal        | Thalassemia test results (e.g., fixed defect, reversible defect) indicate blood flow problems. |


## Methodology:

1. The data was first explored, using ```df.describe()``` and ```df.info()```, to identify the basic statistical details of the different features of the data, and analyze the data types of the different features.
2. Basic Data Visualization operations are conducted:
* Visualization of target class imbalance
* Feature-based bivariate relationships between the different variables
* Clustermap to visualize the complete correlation between all the variables in the dataset
3. The data was split into train and test datasets, with a ratio of 90%-10%, and scaling was done utilized ```StandardScaler()```.
4. Logistic regression was utilized with cross validation, to get superior results.

## Results:
The model performed extremely well, with 26 true values and 5 false values predicted, out of the test dataset which had 31 values. 

The classification report obtained is as follows:
| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.86      | 0.80   | 0.83     | 15      |
| 1     | 0.82      | 0.88   | 0.85     | 16      |

| Metric       | Value |
|--------------|--------|
| Accuracy     | 0.84   |
| Macro Avg    | 0.84   |
| Weighted Avg | 0.84   |

The model was explained using SHAP, where cp, ca, and sex were observed to be the main influencing factors. 

## Future Improvements:
1. Model deployment by containerization
2. Streamlit app for direct usage of model. 
