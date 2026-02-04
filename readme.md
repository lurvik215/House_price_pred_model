# House Price Prediction using Linear Regression
## 1. Introduction

This project implements a supervised machine learning approach to predict house prices using structured housing data. The objective is to model the relationship between multiple property-related features and the target variable SalePrice using a Linear Regression model.

The workflow includes data cleaning, preprocessing, feature transformation, model training, and evaluation using standard regression metrics.

## 2. Dataset Description

Dataset: HousePricePrediction.csv

Target Variable: SalePrice

Features include both:

Numerical variables (e.g., basement area, total area)

Categorical variables (e.g., zoning type, building type, exterior type)

The dataset was explored using:

df.head()

df.info()

df.describe()

df.isnull().sum()

## 3. Data Preprocessing
### 3.1 Handling Missing Values

Rows with missing values in selected features such as:

- MSZoning

- Exterior1st

- BsmtFinSF2

- TotalBsmtSF
were removed.

The variance of SalePrice was examined before and after filling missing values to analyze the effect of imputation.

Missing values in SalePrice were handled carefully:

Initially filled with mean to compare variance.

Finally, rows containing missing SalePrice values were dropped to prevent bias.

This ensured the integrity of the regression model.

### 3.2 Feature Transformation

Converted MSSubClass to string type since it represents categorical information.

Removed the Id column as it does not contribute to prediction.

Separated features and target variable:

X → Independent variables

y → Target variable (SalePrice)

Categorical and numerical columns were identified using:

select_dtypes(include=['object'])

select_dtypes(include=['int64','float64'])

## 4. Exploratory Data Analysis

Pairwise relationships were visualized using seaborn.pairplot().

Unique values of categorical features were examined to understand category distribution.

Basic statistical summaries were analyzed to understand central tendency and dispersion.

## 5. Model Development
### 5.1 Preprocessing Pipeline

A ColumnTransformer was used to apply:

StandardScaler to numerical features

OneHotEncoder to categorical features

drop='first' to avoid multicolarity

handle_unknown='ignore' to handle unseen categories

This ensures consistent preprocessing during both training and testing.

### 5.2 Machine Learning Model

The regression algorithm used:

Linear Regression

A complete pipeline was constructed:

Preprocessing (Scaling + Encoding)

Linear Regression Model

This approach prevents data leakage and ensures reproducibility.

## 6. Model Training

The dataset was split into:

80% Training data

20% Testing data

random_state = 42 for reproducibility

The model was trained using the training dataset and predictions were made on the test dataset.

## 7. Model Evaluation

The model performance was evaluated using:

Mean Absolute Error (MAE)

Mean Squared Error (MSE)

R-squared (R² Score)

These metrics measure:

Average prediction error

Squared error magnitude

Goodness of fit of the model

## 8. Tools and Libraries Used

- Python

- NumPy

- Pandas

- Matplotlib

- Seaborn

- Scikit-learn

- Jupyter Notebook

## 9. Conclusion

This project demonstrates a complete machine learning regression pipeline including:

Data cleaning

Handling missing values

Feature scaling

Categorical encoding

Pipeline-based modeling

Model evaluation

Linear Regression provides a baseline predictive model for house price estimation. The workflow can be extended using more advanced regression algorithms to improve performance.

Author:
Pokala Lurvik