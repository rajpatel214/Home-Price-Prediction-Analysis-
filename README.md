# Home-Price-Prediction-Analysis
## Overview
This project focuses on predicting home prices using **Linear Regression** and other machine learning models based on real estate data. The dataset contains various features such as the number of bedrooms, bathrooms, car parking spaces, land size, and region information, among others.

The project involves:
1. **Data Preprocessing** – Handling missing values and feature encoding
2. **Exploratory Data Analysis (EDA)** – Visualizing key trends in the data
3. **Feature Engineering** – One-Hot Encoding categorical variables
4. **Model Training & Evaluation** – Deploying regression models and assessing their performance

---
## Dataset
- The dataset consists of home listings with attributes such as:
  - **Rooms**: Number of rooms in the property
  - **Bedroom2**: Number of bedrooms
  - **Bathroom**: Number of bathrooms
  - **Car**: Number of car parking spaces
  - **Landsize**: Size of the land
  - **BuildingArea**: Size of the building
  - **YearBuilt**: Year the property was built
  - **Lattitude & Longtitude**: Geographic location of the property
  - **Regionname**: Region in which the property is located
  - **Price**: Target variable (house price in dollars)

---
## Data Preprocessing
### Handling Missing Values
Many features had missing values, so we handled them as follows:
- **Numerical Features**: Replaced missing values with their median.
- **Categorical Features**: Used the mode to fill missing values.

### Feature Encoding
- **One-Hot Encoding**: Applied to categorical columns (e.g., `Regionname`)
- **Feature Scaling**: Used **RobustScaler** to scale numerical features

---
## Exploratory Data Analysis (EDA)
### 1. Distribution of Room Counts
A count plot of rooms showed that most properties have **2 to 4 rooms**.

### 2. Property Type Distribution
A pie chart analysis revealed the majority of properties are **houses**, followed by **apartments** and **townhouses**.

### 3. Bedrooms and Bathrooms Distribution
- The most common properties had **2-4 bedrooms**.
- The number of bathrooms varied, but **1-2 bathrooms** were the most common.

### 4. Car Parking Availability
- The dataset indicated that most properties provided **1-2 parking spaces**.

### 5. Region-wise Property Distribution
- **Reservoir, Bentleigh East, and Richmond** had the highest number of listings.
- Price varied significantly by region.

### 6. Property Distance from City Center
- Properties closer to the city center had **higher prices**.
- A violin plot of `Regionname` vs. `Price` revealed a skewed distribution.

### 7. Property Count vs. Price
- More available properties in a region correlated with **lower average prices**.

---
## Model Training & Evaluation
We tested several models to predict home prices:

### 1. Linear Regression
- Simple model, achieved an **R² score of 0.28**.

### 2. Decision Tree Regressor
- Improved performance with **R² score of 0.38**.

### 3. Random Forest Regressor
- Performed better with hyperparameter tuning:
  - `max_depth=50`
  - `max_features=10`
  - `min_samples_split=20`
  - **R² score = 0.45**

### 4. Voting Regressor (Ensemble of LR, RF, DT, KNN)
- **R² score = 0.45**

### 5. Bagging Regressor (with RandomForestRegressor)
- Best performing model with **R² score = 0.46**

### 6. XGBoost Regressor
- **R² score = 0.43**, slightly lower than bagging but still competitive.

#### Error Metrics
- **Mean Absolute Error (MAE)** and **Mean Squared Error (MSE)** were consistent across models, indicating stable but not highly accurate predictions.

---
## Conclusion & Insights
- **More available properties in a region led to lower property prices**.
- **Properties closer to the city center were more expensive**.
- **The number of rooms, land size, and building area were strong price indicators**.
- **Random Forest and Bagging Regressors performed the best in predicting house prices**.

Future improvements could include:
- **Feature Engineering**: Adding more location-based variables.
- **Hyperparameter Tuning**: Further optimizing the best models.
