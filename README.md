# Air_Quality_Forecasting
### Problem Statement:
Beijing air pollution is a critical and long-term problem that existed over decades, driven by the predominance of rapid industrialization, economic development, heavy traffic, and adverse weather [1], [2]. These pollutants have PM2.5 which is a fine particle of contaminated air with a diameter of less than 2.5 micrometers is very dangerous to human beings due to its ability to penetrate deep into the lungs and blood system, causing severe cardiovascular and respiratory diseases [1], [3]. Within 6 years, since 2014 in Beijing only the average of maximum PM2.5 concentration was 74.4 µg/m³, well above national and international safety standards [1], [4]. Seasonal peaks of pollution, particularly during winter due to residential coal burning for heating and atmospheric inversions, add to the city's air quality crisis [2], [4].

Given the high economic and health risks associated with these issues, accurate forecasting of PM2.5 and overall air quality is highly critical. Regular forecasts enable city planners to issue public health warnings, stimulate personal protective actions (e.g., shortening outdoor stay), and guide government policies regarding emissions control and urban planning [1], [3]. Additional precise prediction enables long-term planning in the environmental sector, avoids economic losses (e.g., tourism loss), and, eventually, boosts the quality of life of millions of citizens.
#### Objective:
- Preprocess sequential air quality and meteorological data.
- Design and train RNN/LSTMs models to forecast PM2.5 levels.
- Fine-tune models by experimenting with different architectures and hyper-parameters.
- Evaluate model performance and submit predictions.

## Experimentation Table

| Experiment No. | Model Details                                                                                             | RMSE    |
|---------------|---------------------------------------------------------------------------------------------------------|---------|
| 1   | LSTM(32, relu), Dropout(0.2), Dense(1); lr=0.01; batch=64; optimizer=Adam                                 | 4821.070   |
| 2             | LSTM(64, relu), Dropout(0.3), Dense(1); lr=0.001; batch=32; Adam                                          | 5265.206    |
| 3             | LSTM(64, tanh), Dropout(0.3) *2, Dense(32), Dense(1); lr=0.005; batch=32; Adam                                       | 5028.105    |
| 4             | LSTM(64, tanh), Dropout(0.2), Dense(1); lr=0.01; batch=64; Epochs=10;RMSprop                                          | 4794.416   |
| 5             | LSTM(64, relu), Dropout(0.2), Dense(1); lr=0.01; batch=128; Epochs=10;RMSprop                                          | 4744.571    |
| 6             | LSTM(64, relu), Dropout(0.2), Dense(1); lr=0.005; batch=64; Epochs=15;Adam                                          | 5015.431    |
| ...           | ...                                                                                                       | ...     |
| 11             | GRU(64, relu), Dropout(0.2), Dense(1); lr=0.001; batch=32; Epochs=50;Adamax                                          | 4280.646    |


## **The Selected model of ```LSTM```**

After conducting multiple experiments with different architectures, the selected model
demonstrated superior performance in terms of minimizing RMSE while ensuring generalization to enhance performance of model was this one:

### LSTMs layers:

- First LSTM layer with 32 units, ReLU activation.

- Dropout layer (20%) for regularization.

#### **Dense layers:**

- Fully connected layer with 32 units, ReLU activation.

- Output layer with 1 unit for PM2.5 prediction.

- *Optimizer*: Adam with a learning rate of 0.01.

- *Loss function*: Mean Squared Error (MSE) which were **4821.070**.

#### **Training:**

- 35 epochs with a batch size of 64, with the use of Early stopping.

- Learner Regression was used as an Imputer predict method for dealing with missing values

## Why it is the best:
>Best-performing model was LSTM; it's the best since it learns temporal dependencies, and we use dropout to prevent overfitting, and we also used the adaptive Adam optimizer for quicker convergence and uses early stopping to prevent overtraining, hence is accurate and generalizable to time-series prediction like air quality forecasting the more we are dealing with currently.


## Project Structure (```Air_Quality_Forecasting```)
├── Data/                  # Dataset 

├── Output_Experiment/         # Attempt for experiment

├── README.md              # Project documentation


## *Setup*
To run the code, follow this instructions. 

- Clone this Repo: [Link to Repo](https://github.com/M-Pascal/Air_Quality_Forecasting.git)
- Review and Comment this [Jupyter Notebook](https://colab.research.google.com/drive/1-aPZeJn6ReAsq36e_1rso4nZHY0BrXz5?usp=sharing)

## Success of project:
* Effective handling of missing values using Imputor predictor (linear Regression)
* Strong generalization with minimal overfitting

## Challenge during the Project:
- Tuning hyperparameters for optimal results
- Managing noisy, seasonal data fluctuations
- Change of loss within different experiment some were high that Baseline(Best)

## Recommandation:
- Experiment with Bidirectional LSTMs or GRUs for richer context,<br>
- Add exogenous features like wind direction or holidays,<br>
- Explore ensemble methods combining LSTM with tree-based models for robustness


### **Contributors**
> Pascal Mugisha

<br>

# Reference List:
[1] K. Kaur, S. Das, and K. Singh, “Air Quality Prediction in Beijing: Machine and Deep Learning Analysis,” in ITM Web of Conferences, 2024. [Online]. Available: https://www.itm-conferences.org/10.1051/itmconf/20246801012

[2] M. Cărbureanu and M.-C. Vieru, “Machine Learning Methods Applied in Air Quality Prediction,” Romanian Journal of Petroleum & Gas Technology, 2024. [Online]. Available: https://www.semanticscholar.org/paper/4fbf8ed06d9bbefed6d55f8accdd1d6a812f08da

[3] D. Pandey, M. Dwivedi, J. Choubey, S. Kushwaha, and R. Saraf, “Harnessing Machine Learning for Enhanced Air Quality Prediction,” International Journal of Innovative Research in Science, Engineering and Technology, 2023. [Online]. Available: https://www.ijirset.com/upload/2023/march/139_Harnessing.pdf

[4] S. Kumar, R. V. Singh, and A. P. Singh, “Hybrid Machine Learning Models for Fine-grained Air Quality Forecasting,” International Journal for Multidisciplinary Research, 2024. [Online]. Available: https://www.semanticscholar.org/paper/e7b866bff15449fba79f7dffd6814c4c5b6065fa
