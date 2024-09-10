# Solar Power Generation Analysis and Forecasting

This Jupyter notebook provides a comprehensive analysis of solar power generation data. It focuses on data exploration, identifying performance issues, and forecasting daily yield using machine learning models, specifically LSTM (Long Short-Term Memory) networks.

## Key Objectives

- Explore the solar plant data to identify trends, correlations, and potential faults.
- Implement fault detection mechanisms to spot periods of abnormal performance.
- Develop and evaluate forecasting models for predicting daily solar yield using LSTM networks.

## Data Exploration & Visualization

Several visualizations were created to explore the dataset and highlight key performance metrics:

- **Correlation Heatmap**: Explored relationships between variables like DC/AC power, irradiation, and temperature.
- **Daily Yield & Power Plots**: Analyzed seasonal and daily patterns of solar power output.
- **Inverter Performance**: Conducted inverter-wise analysis to identify underperforming units.
- **Temperature Impact**: Examined the effect of temperature on the performance of solar modules.

### Findings:

- **Strong correlations** were found between DC power, AC power, irradiation, and temperature.
- **Outliers** indicated potential issues with panels or inverters.
- **Two distinct groups of inverters** were identified with different total yield patterns, suggesting performance inconsistencies.
- **Data quality concerns** were raised regarding decreasing daily yield on some days, which may indicate operational issues.

## Fault Detection

A fault detection mechanism was implemented to identify periods of abnormal inverter operation during daylight hours. The analysis highlights:

- Days and inverters exhibiting the most faults.
- Potential periods of non-operation or underperformance.

## Forecasting with LSTM Models

Two LSTM models were developed using a sliding window approach to forecast daily solar yield. The models were trained, validated, and evaluated using Root Mean Squared Error (RMSE), Mean Squared Error (MSE), Mean Absolute Error (MAE), and R² Score.

### Model Summaries:

#### Model 1:

- **Architecture**:
  - LSTM layer with 32 units.
  - Dense layers with 8 units and 1 unit for output.
  - Dropout layer for regularization.
  
- **Parameters**:
- Total params: 13,877
- Trainable params: 4,625
- Non-trainable params: 0

- **Results**:
- Mean Squared Error (MSE): 923.9586
- Root Mean Squared Error (RMSE): 30.3967
- Mean Absolute Error (MAE): 20.6171
- R² Score: 0.7520

#### Model 2:

- **Architecture**:
- Two LSTM layers with 128 and 64 units respectively.
- Dense layers with 32 and 1 unit for output.
- Dropout layers for regularization.


- **Parameters**:
- Total params: 354,245
- Trainable params: 118,081
- Non-trainable params: 0

- **Results**:
- Mean Squared Error (MSE): 97.4694
- Root Mean Squared Error (RMSE): 9.8727
- Mean Absolute Error (MAE): 1.6435
- R² Score: 0.9738

### Key Insights

- **Inverter Issues**: Inverters 1BY6WEcLGh8j5v7 and bvBOhCH3iADSZry exhibited signs of underperformance.
- **Non-Operational Periods**: Detected potential technical issues or the impact of temperature fluctuations on module performance.
- **Forecasting Accuracy**: Model 2 achieved superior forecasting performance with a significantly lower RMSE (9.8727) and higher R² Score (0.9738), indicating better generalization compared to Model 1.

## Conclusion

This notebook offers a comprehensive analysis of solar plant performance, pinpointing key issues and providing robust LSTM-based yield forecasting models. While Model 2 showed improved accuracy, further analysis and refinement of the models could improve performance even more, enabling better predictive maintenance and operational efficiency.

## Data Source
The data used for this analysis can be accessed from "https://www.kaggle.com/datasets/anikannal/solar-power-generation-data"

