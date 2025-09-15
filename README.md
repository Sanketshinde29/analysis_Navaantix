# analysis_Navaantrix
This repo contains the anlysis part of predictive and descrptive analysis:

1.Data Cleaning & Preprocessing
The dataset contained empty columns (Status, unnamed1) and missing values in Amount.
Had to drop/clean irrelevant columns to make the dataset usable.
2.Handling Encoding Issues
Initially, pd.read_csv() failed with UnicodeDecodeError due to non-UTF-8 encoding.
Fixed by loading the file with encoding="latin1".
3.Feature Selection for Prediction
Not all columns were numeric or useful for prediction.
Needed to carefully select Age and Orders as features to train the regression model.
4.Building Predictive Model
Choosing a simple but effective model (Linear Regression).
Making sure the model was not overfitting by splitting data into train & test sets.
