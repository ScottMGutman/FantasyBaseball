# FantasyBaseball
This is a learning project that takes in real baseball data from FanGraphs, calculates fantasy relevant results, and creates a machine learning model that gives predictions for player quality in the next year's fantasy season.

The training methodology:
1) Make data is a clean and consistent format
2) Standardize all features using StandardScaler in sklearn
3) Calculate a target variable through a simple average of all relevant stats (Runs, RBIs, Stolen Bases, AVG, and HR for batters)
4) Shift targets so that each year of data is pared with the next year's target
5) Do a PCA reduction, more than havling the number of features and taking care of the large amount of multicollinearity
6) Train a linear regression model with each player year acting as a datapoint

The prediction methodology:
1) Clean/standardize features
2) Sepparate players by position
3) Predict 2023 performance target value with 2022 data by position
4) Adjust targets for in-position performance (i.e. players that outperform other players at their own position will do better overall)
5) Combine positions together to create a single ranking list
