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

### Solution Approach

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

### Key Findings

- Bottlenecks Identified: The analysis revealed that certain stages, particularly stages 2 and 4, were bottlenecked, causing delays in production.

- Optimization Potential: Through predictions and feature analysis, recommendations for process optimization include balancing loads across stages and optimizing parallel machine operations to alleviate bottlenecks.

- Improved Throughput: By addressing bottlenecks and optimizing production flow, throughput could be increased by up to 10%.

- Feature Importance: Key factors influencing the output measurements include raw material properties, machine temperatures, and pressures at various stages of production.

### Future Directions

- Predictive Analytics: Integrating predictive models to forecast future bottlenecks and dynamically adjust production settings.
- Real-Time Monitoring: Leverage real-time data from IoT sensors to provide actionable insights for immediate adjustments in the production process.
- Advanced Modeling: Explore the use of more advanced algorithms such as XGBoost or deep learning models for better predictions and further optimization.

### Source

https://www.kaggle.com/datasets/supergus/multistage-continuousflow-manufacturing-process
