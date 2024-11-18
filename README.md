# Manufacturing Process Optimization Project

# Overview

This project focuses on analyzing data from a multi-stage continuous manufacturing process to identify bottlenecks, predict output measurements, and suggest process optimizations. The dataset used includes measurements from machines operating in parallel and series, providing insights into the overall manufacturing efficiency.

#### Project Objectives

1. Primary Goal: Predict the measurements of output from the first stage of the manufacturing process.

2. Secondary Goal: Predict the measurements of output from the second stage of the manufacturing process.

3. Analysis Focus:
- Identify bottlenecks in the manufacturing pipeline.
- Analyze process inefficiencies and suggest potential optimizations.
- Provide feature importance insights to guide decision-making.

### Dataset Overview

- Source: A continuous factory process dataset extracted from a manufacturing line in Detroit, Michigan.
- continuous_factory_process.csv: Contains sensor and output measurements.
- notes_on_dataset.txt: Provides context and metadata about the data.

### Key Features:

- Input Features: Properties from Machines 1 to 5, including raw material properties, temperatures, pressures, and environmental conditions.
- First Stage Outputs: Measurements recorded after the first stage, where three machines operate in parallel.
- Second Stage Outputs: Measurements recorded after the second stage, where two machines operate in series.

### Methodology

Data Preprocessing:
- Handled missing values by imputing with the median for numerical columns.
- Extracted time-based features (hour, minute) from timestamps for trend analysis.
- Dynamically identified input and output columns based on naming conventions.

Model Building:
- First Stage: Built a RandomForestRegressor to predict outputs from the first stage using input features.
- Second Stage: Built another RandomForestRegressor to predict outputs from the second stage using both input features and first-stage outputs.

Evaluation Metrics:
- Mean Absolute Error (MAE): Measures average prediction error.
- Root Mean Square Error (RMSE): Penalizes larger prediction errors.
- R² Score: Explains variance captured by the model.

### Results

First Stage Model Evaluation:
- MAE: 0.4343
- RMSE: 1.2391
- R²: 0.6864

Second Stage Model Evaluation:
- MAE: 0.4213
- RMSE: 1.3119
- R²: 0.7460

The models performed well, with the second stage demonstrating higher predictive accuracy. The results highlight the importance of combining input features with first-stage outputs for better predictions in the second stage.

### Visualizations

- Bar plots showcasing the most critical input features for both stages.
- Time-series plots illustrating trends in machine temperatures and output measurements.
- Revealed relationships between input and output variables.

### Source

https://www.kaggle.com/datasets/supergus/multistage-continuousflow-manufacturing-process
