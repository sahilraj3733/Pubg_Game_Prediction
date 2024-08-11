# PUBG Game Prediction
## Project Overview
This project aims to predict the outcomes of PlayerUnknown's Battlegrounds (PUBG) matches using machine learning techniques. By analyzing various in-game features and player statistics, the model predicts whether a player or team will win or lose a match. The project utilizes a dataset containing 29 features that represent different aspects of a player's performance and behavior in the game.

## Features
The dataset includes the following 29 features:
- DBNOs - Number of enemy players knocked.

- assists - Number of enemy players this player damaged that were killed by teammates.
- boosts - Number of boost items used.
- damageDealt - Total damage dealt. Note: Self inflicted damage is subtracted.
- headshotKills - Number of enemy players killed with headshots.
- heals - Number of healing items used.
- Id - Player’s Id
- killPlace - Ranking in match of number of enemy players killed.
- killPoints - Kills-based external ranking of player. (Think of this as an Elo ranking where only kills matter.) If there is a value other than -1 in rankPoints, then any 0 in killPoints should be treated as a “None”.
- killStreaks - Max number of enemy players killed in a short amount of time.
- kills - Number of enemy players killed.
- longestKill - Longest distance between player and player killed at time of death. This may be misleading, as downing a player and driving away may lead to a large longestKill stat.
- matchDuration - Duration of match in seconds.
- matchId - ID to identify match. There are no matches that are in both the training and testing set.
- matchType - String identifying the game mode that the data comes from. The standard modes are “solo”, “duo”, “squad”, “solo-fpp”, “duo-fpp”, and “squad-fpp”; other modes are from events or custom matches.
- rankPoints - Elo-like ranking of player. This ranking is inconsistent and is being deprecated in the API’s next version, so use with caution. Value of -1 takes place of “None”.
- revives - Number of times this player revived teammates.
- rideDistance - Total distance traveled in vehicles measured in meters.
- roadKills - Number of kills while in a vehicle.
- swimDistance - Total distance traveled by swimming measured in meters.
- teamKills - Number of times this player killed a teammate.
- vehicleDestroys - Number of vehicles destroyed.
- walkDistance - Total distance traveled on foot measured in meters.-
- weaponsAcquired - Number of weapons picked up.
- winPoints - Win-based external ranking of player. (Think of this as an Elo ranking where only winning matters.) If there is a value other than -1 in rankPoints, then any 0 in winPoints should be treated as a “None”.
- groupId - ID to identify a group within a match. If the same group of players plays in different matches, they will have a different groupId each time.
- numGroups - Number of groups we have data for in the match.
- maxPlace - Worst placement we have data for in the match. This may not match with numGroups, as sometimes the data skips over placements.
winPlacePerc - The target of prediction. This is a percentile winning placement, where 1 corresponds to 1st place, and 0 corresponds to last place in the match. It is calculated off of maxPlace, not numGroups, so it is possible to have missing chunks in a match.

## Machine Learning Workflow
### 1. Data Preprocessing
   - Cleaned and preprocessed the dataset to handle missing values, outliers, and feature scaling.
   - Converted categorical variables into numerical formats using techniques like one-hot encoding.
### 2. Feature Engineering
   - Performed feature selection to identify the most impactful features on the game outcome.
   - Created new features based on existing ones to enhance model performance.
### 3. Model Training
   - Implemented the CatBoost model, which is particularly effective for handling categorical features and provides robust performance.
   - Split the dataset into training and testing sets to evaluate model performance.
### 4. Model Evaluation
   - Used accuracy, precision, recall, F1 score, and ROC-AUC to evaluate the CatBoost model.
   - Achieved superior performance metrics with CatBoost compared to traditional models.
### 5. Hyperparameter Tuning
   - Performed hyperparameter tuning on the CatBoost model using Grid Search and Random Search to optimize performance.
### 6. Prediction and Insights
   - Generated predictions on the test set and provided insights into the factors most influential in determining the outcome of PUBG matches.

## Results
- Achieved a high accuracy in predicting the outcome of PUBG matches(RMSE of 0.08 and an R² of 0.93).
- Identified key factors such as kill count, damage dealt, survival time, and headshot rate as critical predictors of match outcomes.

## Tools & Technologies
- Programming Language: Python
- Libraries: Pandas, Scikit-learn, CatBoost, Matplotlib, Seaborn
- Environment: Jupyter Notebook

## Contributor
- Sahil Raj
