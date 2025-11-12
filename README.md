# Ecommerce Customer Yearly Amount Spent Prediction Model

## Project Overview
This project aims to build a Linear Regression model to predict the yearly amount spent by customers of an e-commerce platform. By analyzing various customer attributes and their interactions with the platform, the model provides insights into factors influencing customer spending and can be used to forecast future expenditure.

## Data Source
The model was trained on the `Ecommerce Customers.txt` dataset, which contains customer information including:
- `Email`
- `Address`
- `Avatar`
- `Avg. Session Length`: Average session of in-store style advice sessions.
- `Time on App`: Average time spent on App in minutes.
- `Time on Website`: Average time spent on Website in minutes.
- `Length of Membership`: How many years the customer has been a member.
- `Yearly Amount Spent`: Total amount spent by that customer per year (Target Variable).

## Objective
The primary objective is to predict `Yearly Amount Spent` based on customer engagement metrics. This can help the e-commerce company understand customer behavior, optimize marketing strategies, and improve customer retention.

## Methodology
The project followed these key steps:
1.  **Data Loading and Initial Inspection**: Loaded the dataset and performed basic checks (`.head()`, `.info()`, `.describe()`, `.isnull().sum()`).
2.  **Data Preprocessing**: Dropped irrelevant features (`Email`, `Address`, `Avatar`).
3.  **Exploratory Data Analysis (EDA)**:
    *   Generated scatter plots to visualize relationships between numerical features and `Yearly Amount Spent`.
    *   Created box plots by binning numerical features to see how `Yearly Amount Spent` varies across different quartiles.
    *   Computed and visualized a correlation matrix to understand linear relationships between features.
    *   Generated a pair plot for a comprehensive view of all numerical feature distributions and relationships.
4.  **Data Splitting**: Separated features (X) from the target variable (y) and split the data into training (80%) and testing (20%) sets.
5.  **Model Training**: Trained a Linear Regression model on the training data.
6.  **Model Evaluation**: Evaluated the model's performance using Mean Squared Error (MSE) and R-squared ($R^2$).
7.  **Prediction Functionality**: Implemented a function to take user input for prediction.

## Model Details
### Model Used
**Linear Regression**

### Coefficients
- `Avg. Session Length`: `25.596`
- `Time on App`: `38.785`
- `Time on Website`: `0.310`
- `Length of Membership`: `61.897`

These coefficients indicate the change in 'Yearly Amount Spent' for a one-unit increase in the corresponding feature, holding all other features constant.

### Intercept
`-1044.257`

### Performance Metrics (on Test Data)
-   **Mean Squared Error (MSE)**: `109.86`
-   **R-squared ($R^2$)**: `0.978`

The high R-squared value indicates that approximately 97.8% of the variance in `Yearly Amount Spent` can be explained by the independent variables in the model, suggesting a good fit.

## Usage
To use the trained model for prediction, you can utilize the `predict_user_input()` function. This function prompts for user input for the four key features and provides a predicted 'Yearly Amount Spent'.

```python
predict_user_input()
```

**Example Interaction:**
```
enter the details for prediction:
average session length:33.0
time on app:12.0
time on website:37.0
length of membership:4.0
predicted yearly amount spent: $540.XX
```

## Dependencies
-   `pandas`
-   `numpy`
-   `matplotlib`
-   `seaborn`
-   `scikit-learn`
-   `joblib`
