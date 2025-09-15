# analysis_Navaantrix
*This repo contains the anlysis part of predictive and descrptive analysis of Diwali sales:

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

* web scraping facing challenges:
1.Many e-commerce sites  Amazon and Flipkart load product details dynamically using JavaScript.
  This made it difficult to scrape using only requests and BeautifulSoup.
  
2.Frequent Changes in HTML Structure
 Used more stable attributes like data-component-type in Amazon and added error handling with try/except.

3.Data Cleaning Issues
 Extracted price and rating values often contained unwanted symbols or missing values.
Solution:Cleaned the data using Pandas string operations and replaced missing values with "N/A".

4.Saving Data into Excel
 Ensuring that all scraped data was structured properly before saving.
Solution: Converted data into a Pandas DataFrame and exported with df.to_excel().

*CRUD cgallenges:
1.Appending New Records (Create)
In older versions of Pandas, DataFrame.append() was commonly used, but in Pandas 2.0 it was removed.
This caused errors when adding new rows.
Solution: Switched to pd.concat() with ignore_index=True for adding records.

2.Updating Records
Updating specific rows required careful use of conditions with .loc[].
If conditions were not precise, multiple rows could be updated by mistake.
Solution: Used strict filtering with multiple conditions (e.g., product + region) before updating.

3.Deleting Records
Deletion using filtering sometimes caused confusion because Pandas does not modify the DataFrame in place unless reassigned.
Solution: Reassigned the DataFrame (df = df[df['Quantity'] != 2]) to ensure rows were actually removed.


