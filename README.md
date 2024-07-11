# OLD-CAR-PRICE-PREDICTION-MODEL

## Abstract

This project focuses on developing a predictive model to determine the selling price of used cars using various regression techniques. The study leverages a comprehensive dataset encompassing multiple attributes of used cars, such as manufacturing year, kilometers driven, fuel type, seller type, transmission type, ownership history, mileage, engine capacity, maximum power, and seating capacity.

The primary objectives include data cleaning, feature extraction, and exploratory data analysis to identify key trends and correlations within the dataset. Significant steps in the process include the removal of null values, elimination of duplicates, numerical encoding of categorical variables, and transformation of text-based columns into numerical values for better analysis.

Key findings from the exploratory data analysis indicate that factors such as engine capacity, maximum power, and the age of the car significantly influence the selling price. Higher engine capacity and maximum power are positively correlated with higher selling prices, while older cars tend to sell for less.

The project concludes with the implementation of a Random Forest regression model, evaluated using metrics like Mean Squared Error (MSE), Mean Absolute Error (MAE), and R-squared (R²) values, to predict the selling price of used cars. The insights derived provide a robust foundation for understanding price determinants in the used car market, potentially aiding buyers, sellers, and market analysts in making informed decisions.

## Introduction

This report presents a comprehensive analysis of a dataset containing details about used cars, including attributes such as manufacturing year, selling price, kilometers driven, fuel type, seller type, transmission type, ownership history, mileage, engine capacity, maximum power, and seating capacity. The objective is to explore and understand the factors influencing the selling price of used cars. Through data cleaning, transformation, and exploratory data analysis, key trends and correlations are identified, providing insights into the used car market. This analysis serves as a foundation for predictive modeling and further statistical analysis to better understand price determinants in the used car market.

## Importing Libraries

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from datetime import datetime
import numpy as np
from sklearn.feature_selection import SelectKBest, f_regression
from sklearn import metrics
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score
```

## Dataset Used

The dataset contains information about used cars, with attributes such as the car's name, manufacturing year, selling price, kilometers driven, fuel type, seller type, transmission type, ownership history, mileage, engine capacity, maximum power, and number of seats.

## Data Overview

### Data Cleaning and Preparation

1. **Removing Null Values**: We identified and removed null values present in the mileage, engine, max power, and seats columns.
2. **Handling Duplicates**: We detected and eliminated duplicate records to ensure the dataset's integrity.

### Extracting Useful Features

- **No. of Years Used**: A new column, "no_year", was created to represent the number of years a car has been used, calculated by subtracting the manufacturing year from the current year (2024).

### Encoding Categorical Variables

- **Numerical Encoding**: Fuel type, seller type, transmission type, owner type, and car brand names were encoded as numerical values for better analysis and model training.

### Data Transformation

- **Modifying Mileage, Engine, and Max Power**: These columns originally contained text values with units. We extracted the numerical part of these values for analysis.
- **Brand Name Extraction**: The car brand was extracted from the name column and encoded into numerical values.

## Exploratory Data Analysis

### Distributions

- **Selling Price**: The distribution is right-skewed, indicating that most cars are sold at a lower price.
- **Kilometers Driven**: This distribution is also right-skewed, with most cars having fewer kilometers driven.
- **Mileage**: There is a wide range in mileage, but a significant number of cars offer moderate mileage.
- **Engine Capacity**: The distribution shows a concentration of cars with smaller engine sizes.
- **Max Power**: Most cars have lower maximum power values.
- **Number of Years Used**: The distribution shows a mix of newer and older cars.

### Box Plots

Box plots were used to identify outliers in the dataset. Significant outliers were present in the selling price, kilometers driven, mileage, engine capacity, and max power columns.

### Correlation Analysis

A correlation matrix was generated to understand the relationships between numerical variables.

- **Positive Correlations**:
  - Selling price is positively correlated with engine capacity and max power.
  - Engine capacity and max power also show a strong positive correlation.
- **Negative Correlations**:
  - Selling price is negatively correlated with the number of years used, indicating that older cars tend to sell for less.
  - Mileage has a negative correlation with engine capacity and max power.

## Insights

- **Factors Influencing Car Prices**: Engine capacity, max power, and the age of the car are significant factors affecting the selling price. Cars with higher engine capacity and max power tend to sell for more, while older cars generally fetch lower prices.
- **Model Training**: Implemented Random Forest regression model to predict the selling price and evaluate their performance using metrics like Mean Squared Error (MSE), Mean Absolute Error (MAE), and R-squared (R²) values.

## Conclusion

This project successfully developed a predictive model for estimating the selling price of used cars using regression techniques. Through thorough data cleaning and preparation, including the handling of missing values and duplicates, and the encoding of categorical variables, the dataset was effectively transformed for analysis. The exploratory data analysis provided valuable insights into the factors influencing car prices, with key determinants identified as engine capacity, maximum power, and the age of the car. Higher engine capacity and maximum power were found to be positively correlated with higher selling prices, while older cars tended to have lower prices.

The implementation of a Random Forest regression model demonstrated the model's capability in predicting car prices with reasonable accuracy, as evidenced by evaluation metrics such as Mean Squared Error (MSE), Mean Absolute Error (MAE), and R-squared (R²) values. These findings highlight the potential of regression models in providing reliable price estimates, benefiting both buyers and sellers in making informed decisions. Overall, this project underscores the importance of key car attributes in price determination and showcases the application of data science techniques in addressing real-world problems, providing a solid foundation for further research and improvement in used car price prediction models.
