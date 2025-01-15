# WasteNot: Inventory Optimization for Reducing Food Waste

WasteNot is a machine learning-driven project aimed at addressing the issue of food waste in the restaurant industry. By analyzing historical sales data and leveraging predictive modeling, the project enables optimized inventory management to reduce excess food waste.

## Problem Statement

According to the UN Environment Programme (UNEP), over one billion tons of food are wasted annually, with 15% attributed to restaurants. Poor inventory management often leads to overstock and spoilage, creating economic and environmental consequences. WasteNot aims to mitigate this issue by predicting sales to improve inventory planning.

## Dataset

- **Source**: [Mendeley Data](https://data.mendeley.com/datasets/7s3ys9ntnz/1)
- **Description**: The dataset comprises two years of daily restaurant sales data from Stuttgart, Germany. It includes:
  - Sales for seven menu items: CALAMARI, FISCH, GARNELEN, HAEHNCHEN, KOEFTE, LAMM, STEAK.
  - Features like weekdays, holidays, special events, weather conditions, and historical sales data.

## Machine Learning Models

### 1. **Poisson Regression**
   - Predicts count data, such as the number of menu items sold daily.
   - Used as a baseline model for its ability to handle count-based outcomes.

### 2. **Tree-Based Models**
   - **Random Forest** and **XGBoost**: Capture complex nonlinear relationships in the data.
   - Handle high-dimensional features effectively.

### 3. **Time Series Models**
   - **SARIMA**: Models seasonal and non-seasonal patterns in sales data.
   - **VARMAX**: Incorporates exogenous variables like weather and holidays to enhance predictions.

## Methodology

1. **Data Preparation**
   - Dropped low-variance and highly correlated features.
   - Standardized features using `StandardScaler`.
   - Used time-series split for cross-validation.

2. **Feature Engineering**
   - Derived lagged demands, cumulative sales, and high-medium-low demand categories.
   - Incorporated exogenous factors such as weather conditions and holidays.

3. **Model Training and Tuning**
   - Evaluated models using metrics like Mean Squared Error (MSE).
   - Applied hyperparameter tuning (e.g., GridSearchCV) for optimal model performance.

4. **Time Series Analysis**
   - Stationarized non-stationary menu items using differencing.
   - Selected optimal SARIMA parameters using AIC minimization.

## Results

- **Poisson Regression**: Performed well for simpler categories but showed overfitting in some cases.
- **Tree-Based Models**:
  - XGBoost delivered the best results, with the lowest test MSE across most menu items.
  - Random Forest was prone to overfitting despite high flexibility.
- **Time Series Models**:
  - Weekly seasonality (m=7) provided better predictions than monthly seasonality.
  - Incorporating exogenous variables further improved forecast accuracy.

## Key Insights

- Optimizing inventory based on predicted sales can significantly reduce food waste.
- Weather and holidays are critical factors influencing restaurant sales trends.
- Reducing feature dimensionality helps mitigate overfitting, especially for tree-based models.

## Technologies Used

- **Programming Languages**: Python
- **Libraries**: Pandas, NumPy, Scikit-learn, Statsmodels, Matplotlib, XGBoost
- **Algorithms**: Poisson Regression, Random Forest, XGBoost, SARIMA, VARMAX

## Future Work

- Extend analysis to other industries facing inventory management challenges.
- Integrate real-time data for dynamic prediction updates.
- Develop a user-friendly interface for broader adoption by restaurant managers.


WasteNot demonstrates the potential of machine learning in solving critical societal challenges, aligning with values of sustainability and technological innovation.
