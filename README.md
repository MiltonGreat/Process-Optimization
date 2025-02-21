# Manufacturing Process Optimization

## Overview

This project focuses on analyzing data from a multi-stage continuous manufacturing process. The goal is to identify bottlenecks in the production pipeline, predict output measurements, and suggest process optimizations to enhance overall production efficiency. By leveraging machine learning models and examining various process stages, this analysis aims to improve production flow and reduce inefficiencies.

### Problem Statement

Manufacturing processes often face bottlenecks that disrupt the smooth flow of operations, leading to reduced output and wasted resources. Identifying these bottlenecks and predicting output measurements at various stages is crucial for optimizing the production line and ensuring timely deliveries.

This project uses machine learning to analyze and predict measurements from two stages of the manufacturing process, helping identify inefficiencies and optimize resource allocation.

### Data

The dataset includes sensor and output measurements from a continuous manufacturing process, where multiple machines operate in parallel and series. Key data points include:

- Input Features: Properties from five machines, including raw material characteristics, temperatures, pressures, and other machine-specific environmental conditions.
- First Stage Outputs: Measurements from the first stage of the process after three machines operate in parallel.
- Second Stage Outputs: Measurements from the second stage after two machines operate in series.

Dataset Size: 14,088 records

### Workflow

1. Data Preprocessing
- Handling Missing Values: Imputed missing values using the median for numerical features.
- Feature Extraction: Extracted time-based features (hour, minute) to observe trends over time.
- Feature Selection: Dynamically identified relevant input and output columns based on naming conventions.

2. Model Building
- First Stage: Built a RandomForestRegressor to predict the first stage outputs from the input features.
- Second Stage: Built another RandomForestRegressor to predict the second stage outputs, incorporating both input features and first-stage outputs.

3. Evaluation Metrics
- MAE (Mean Absolute Error): Measures the average magnitude of errors in predictions.
- RMSE (Root Mean Squared Error): Penalizes larger errors more heavily.
- R² (Coefficient of Determination): Represents the proportion of the variance in the dependent variable that is predictable from the independent variables.

### Results

First Stage Model Evaluation
- MAE: 0.4367
- RMSE: 1.2550
- R²: 0.6201

Second Stage Model Evaluation
- MAE: 0.4223
- RMSE: 1.3155
- R²: 0.7439

Both stages performed well, with the second stage model showing slightly higher predictive accuracy. This highlights the benefits of combining features from multiple stages for better overall prediction.

Quality Control
- Precision: 0.958
- Recall: 0.954
- F1-Score: 0.956
- ROC-AUC: 0.992

Optimal Inputs
- Identified optimal input configurations to maximize output quality.

### Key Findings

1. Stage 1 Predictions:

- The Random Forest model for Stage 1 achieved moderate performance, with an R² of 0.618, indicating that it explains 61.8% of the variance in the output measurements.
- The MAE (0.436) and RMSE (1.804) suggest that the model's predictions are reasonably accurate, though there is room for improvement. Larger errors (as indicated by RMSE) may be due to outliers or complex patterns in the data.

To further enhance Stage 1 predictions, additional feature engineering, hyperparameter tuning, or more advanced models (e.g., gradient boosting or neural networks) could be explored.

2. Stage 2 Predictions:

- The model for Stage 2 outperformed Stage 1, achieving an R² of 0.744, which indicates a stronger ability to explain the variance in the output measurements.
- The MAE (0.422) and RMSE (1.818) are slightly better than Stage 1, suggesting that the inclusion of Stage 1 outputs as inputs for Stage 2 provides additional predictive power.
- This improvement highlights the interconnected nature of the two stages and the importance of leveraging intermediate outputs for downstream predictions.

3. Quality Control:

- The quality control model demonstrated exceptional performance, with a precision of 0.958, recall of 0.954, and an F1-score of 0.956. These metrics indicate that the model is highly reliable for identifying high-quality outputs.
- The ROC-AUC score of 0.992 further confirms the model's strong ability to distinguish between high-quality and low-quality outputs.
- This model can be effectively used to automate quality control and provide early warnings for suboptimal production outcomes.

4. Process Optimization:

- The analysis identified optimal input configurations (e.g., machine settings, raw material properties) that maximize output quality. These configurations can be used to fine-tune the production process.
- Positive and negative values in the optimal inputs indicate whether increasing or decreasing specific features improves output quality, while the magnitude reflects their relative importance.
- Mapping these optimal inputs back to the original feature names will provide actionable insights for process optimization.


### Future Directions

- Predictive Analytics: Integrating predictive models to forecast future bottlenecks and dynamically adjust production settings.
- Real-Time Monitoring: Leverage real-time data from IoT sensors to provide actionable insights for immediate adjustments in the production process.
- Advanced Modeling: Explore the use of more advanced algorithms such as XGBoost or deep learning models for better predictions and further optimization.

### Source

https://www.kaggle.com/datasets/supergus/multistage-continuousflow-manufacturing-process
