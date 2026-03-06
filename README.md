# Wine Quality Prediction – Classification vs Regression

Machine Learning final project exploring two different approaches for predicting wine quality using the **Wine Quality dataset**.

The project compares **classification models** and **regression models** to determine which approach better fits the characteristics of the dataset.

Dataset source:  
https://archive.ics.uci.edu/dataset/186/wine+quality

---

# Project Structure
```text
wine-quality-ml-project/
│
├── wine_quality_analysis.ipynb
├── requirements.txt
└── README.md
```


---

# Project Overview

The goal of the project is to analyse the **Wine Quality dataset** and build machine learning models capable of predicting wine quality based on physicochemical properties.

The analysis follows three main stages:

1. Exploratory Data Analysis  
2. Classification task  
3. Regression task

The results of both approaches are compared to determine which modeling strategy is more suitable for the dataset.

The project uses the **white wine dataset** from the UCI Machine Learning Repository. :contentReference[oaicite:0]{index=0}

---

# Dataset

The dataset contains several physicochemical measurements of wines, including:

- fixed acidity  
- volatile acidity  
- citric acid  
- residual sugar  
- chlorides  
- free sulfur dioxide  
- total sulfur dioxide  
- density  
- pH  
- sulphates  
- alcohol  

The target variable is **wine quality**, which is originally expressed as an integer score between **3 and 9**.

---

# Exploratory Data Analysis

The first step of the project focuses on understanding the structure of the dataset.

Key questions explored during EDA include:

- whether the dataset is **balanced or imbalanced**
- how features are **distributed**
- whether **features are correlated**
- whether there is a **linear relationship between features and the target**

The dataset was found to be **imbalanced**, meaning some quality levels appear much more frequently than others. To address this in the classification task, the quality score was transformed into a binary label representing **good vs. not-good wines**. :contentReference[oaicite:1]{index=1}

Correlation analysis also showed that most features have **weak relationships with the target variable**, suggesting that simple linear models may struggle to capture the underlying patterns.

---

# Classification Task

The first modeling approach treats the problem as a **classification task**.

Wine quality scores are converted into two classes:

- **Good wine**
- **Not-good wine**

## Models Used

Two classification algorithms were implemented:

- Logistic Regression
- K-Nearest Neighbours (KNN)

## Training Process

The workflow includes:

- train/test split with **stratification**
- **feature scaling** using `StandardScaler`
- initial training using default hyperparameters
- **hyperparameter tuning with GridSearchCV**
- **k-fold cross-validation** for model evaluation

The main evaluation metrics used were:

- Accuracy
- Precision
- Recall
- F1-score

The **F1-score** was especially important because the dataset is imbalanced.

## Results

Logistic Regression achieved solid performance but was limited by the fact that the classes are not linearly separable.

KNN performed better overall because its **distance-based approach can capture more complex decision boundaries**, which helped identify high-quality wines more effectively. :contentReference[oaicite:2]{index=2}

---

# Regression Task

The second approach reframes the problem as a **regression task**, predicting the **continuous wine quality score**.

## Models Used

Two regression models were implemented:

- Ridge Regression
- KNN Regression

## Training and Evaluation

The regression models were trained using the same workflow:

- train/test split
- feature scaling
- hyperparameter tuning with GridSearchCV
- cross-validation

Evaluation metrics included:

- MAE (Mean Absolute Error)
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)
- R² score

## Results

Ridge Regression performed poorly because it assumes a **linear relationship between features and the target**, which was not strongly present in the dataset.

KNN Regression performed significantly better due to its ability to capture **nonlinear relationships between variables**. :contentReference[oaicite:3]{index=3}

---

# Comparison of Approaches

Although nonlinear models performed better in both cases, the project concludes that **classification is more appropriate for this dataset**.

The main reason is that the wine quality score is **not truly continuous**. Instead, it is an **integer rating assigned by human evaluators**, making it more natural to model the task as a classification problem.

---

# Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib / Seaborn
- Scikit-learn
- Jupyter Notebook

---

# Running the Project

### Install dependencies
`pip install -r requirements.txt`
### Run the notebook
`jupyter notebook`
### Open and run:
`wine_quality_analysis.ipynb`


---

# Dataset

Wine Quality Dataset (UCI Machine Learning Repository)

https://archive.ics.uci.edu/dataset/186/wine+quality

