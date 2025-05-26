# Air_Quality_Forecasting
### Problem Statement:
Beijing air pollution is a critical and long-term problem that existed over decades, driven by the predominance of rapid industrialization, economic development, heavy traffic, and adverse weather. These pollutants have PM2.5 which is a fine particle of contaminated air with a diameter of less than 2.5 micrometers is very dangerous to human beings due to its ability to penetrate deep into the lungs and blood system, causing severe cardiovascular and respiratory diseases. Within 6 years, since 2014 in Beijing only the average of maximum PM2.5 concentration was 74.4 µg/m³, well above national and international safety standards. Seasonal peaks of pollution, particularly during winter due to residential coal burning for heating and atmospheric inversions, add to the city's air quality crisis.

Given the high economic and health risks associated with these issues, accurate forecasting of PM2.5 and overall air quality is highly critical. Regular forecasts enable city planners to issue public health warnings, stimulate personal protective actions (e.g., shortening outdoor stay), and guide government policies regarding emissions control and urban planning. Additional precise prediction enables long-term planning in the environmental sector, avoids economic losses (e.g., tourism loss), and, eventually, boosts the quality of life of millions of citizens.
#### Objective:
- Preprocess sequential air quality and meteorological data.
- Design and train RNN/LSTMs models to forecast PM2.5 levels.
- Fine-tune models by experimenting with different architectures and hyper-parameters.
- Evaluate model performance and submit predictions.

## Experimentation Table

| Experiment No. | Model Details                                                                                             | RMSE    |
|---------------|---------------------------------------------------------------------------------------------------------|---------|
| 1   | LSTM(32, relu), Dropout(0.2), Dense(1); lr=0.01; batch=32; optimizer=Adam                                 | 4991.478   |
| 2             | LSTM(64, relu), Dropout(0.3), Dense(1); lr=0.005; batch=32; Adam                                          | 9.87    |
| 3             | 2x LSTM(64, relu), Dropout(0.3), Dense(1); lr=0.005; batch=32; Adam                                       | 9.42    |
| 4             | LSTM(64, tanh), Dropout(0.3), Dense(1); lr=0.005; batch=32; Adam                                          | 9.56    |
| ...           | ...                                                                                                       | ...     |

