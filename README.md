# NBA MVP Prediction Project

## Introduction

This project focuses on predicting NBA MVP candidates using machine learning models. The goal is to identify and rank the top MVP candidates based on various player statistics.
We can train this model from analyzing 30+ seasons and 20+ different player statistics to figure out who is worthy of being crowned the next NBA MVP.

### Data

The dataset includes features such as:
- **Player Name**: Name of the player
- **Year**: NBA season year
- **MP**: Minutes Played
- **FG%**: Field Goal %
- **PTS**: Points
- **Losses**: Number of losses
- **TOV**: Turnovers

complete list of data points can be found at mvp_prediction_machine_learning.ipynb

## Experiments

### Evaluation Metrics

- **RMSE (Root Mean Square Error)**: Measures how accurately the model predicts player performance.
- **MAP@K (Mean Average Precision at K)**: Assesses the model's ability to rank the top 5 MVP candidates.

### Data Processing

- **PCA (Principal Component Analysis)**: Used to reduce the dimensionality of the data but did not improve model performance in this case. Models trained without PCA performed better.
- **Time-Series Cross-Validation**: Used to handle the temporal structure of the data, ensuring no data leakage.

### Results

#### Model Performance

The following table shows the performance of various models, both with and without PCA, using RMSE and MAP@K:

| Model                        | Train Score (GridSearchCV) | Valid Score (GridSearchCV) | MAP@K  | RMSE   |
|------------------------------|----------------------------|----------------------------|--------|--------|
| Random Forest with PCA       | 0.021934                   | 0.039515                   | 0.007273| 0.029964|
| Gradient Boosting with PCA   | 0.017573                   | 0.041427                   | 0.006993| 0.031851|
| XGB with PCA                 | 0.023754                   | 0.042037	                 | 0.006869| 0.029802|
| Adaboost DT with PCA         | 0.026489                   | 0.042167                   | 0.006869| 0.041514|
| Gradient Boosting            | 0.015139                   | 0.044027	                 | 0.006465| 0.034904|
| Random Forest                | 0.022301                   | 0.044927                   | 0.006465| 0.037445|
| Adaboost DT                  | 0.023977                   | 0.047309	                 | 0.006465| 0.052322|
| XGB                          | 0.021173                   | 0.048713	                 | 0.007677| 0.031351|
| ElasticNet                   | 0.055027                   | 0.055516                   | 0.004848| 0.053423|
| Lasso                        | 0.054929                   | 0.055604                   | 0.004444| 0.053460|
| Ridge                        | 0.054958                   | 0.055616                   | 0.004444| 0.053349|
| Ridge with PCA               | 0.058084                   | 0.057501                   | 0.004848| 0.055500|
| ElasticNet with PCA          | 0.057972                   | 0.057599                   | 0.004444| 0.055491|
| Lasso with PCA               | 0.057951                   | 0.057630                   | 0.004444| 0.055570|
| Baseline                     | 0.062202                   | 0.061709	                 | 0.000000| 0.058113|
| Baseline with PCA            | 0.062202                   | 0.061709	                 | 0.000000| 0.058113|

#### Takeaways

- **XGB without PCA**: Out of all the models had the best performence with a MAP@K of 0.007677 and a RMSE of 0.031351.
- There was slight variation between the models with PCA and the models without PCA some performed better while others performed similarity. Lasso performed the same while Random Forest with PCA performed better than Random Forest without PCA.

### Example Predictions

The XGB model without PCA made accurate predictions for the top MVP candidates:

- Nikola Jokić: Predicted 1st, Actual 1st
- Shai Gilgeous-Alexander: Predicted 2nd, Actual 2nd
- Luka Dončić: Predicted 4th, Actual 3rd
- Giannis Antetokounmpo: Predicted 3rd, Actual 4th

<img width="475" alt="image" src="https://github.com/user-attachments/assets/1422189f-3205-4b91-ad01-0af45832a0f0" />

## Conclusion

By using a lot of different machine learning algorithims we were able to get an accurate prediction of who the MVP might be. The models with the PCA did not necessarily outperform the models without PCA. I was able to learn how to graph many different data points at once and how to relate each data point together. As someone who just started watching the NBA more and trying to figure out who the best players were, this project allowed me to learn a lot about the sport and how one can measure how good a player is. Referring to mvp predictions from sources like the NBA itself and espn it is safe to say that this model puts the same group of people at the top of the MVP leaderboard.

Ways to improve would be using more recent data like from the most recent season since I am only using data that is up to the 2023-2024 season to get a more accurate result as to how these players are performing. Also take into account injuries and how many games a player might miss. Also showing more graphs would help for visual learners in some parts of the project there are a lot of numbers on the screen and it can be difficult to break down what these numbers mean.

## References
1. [WebScraping](https://www.youtube.com/watch?v=JGQGd-oa0l4)
2. [Predicting the NBA MVP with Machine Learning](https://www.samford.edu/sports-analytics/fans/2023/Using-Machine-Learning-to-Predict-the-NBA-MVP#:~:text=Model%20Explanation%20and%20MSE,a%20reliable%20and%20accurate%20prediction.)
3. [Different Machine Learning Algorithms](https://www.geeksforgeeks.org/machine-learning-algorithms/)
4. [Data](https://www.basketball-reference.com/)


