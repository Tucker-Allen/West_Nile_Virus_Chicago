# README

This readme was used as a collaborative notebook between contributors:

Tucker Allen
Youn Hee Pernling Frodin
David Hoffman
Andrew Carl

---

## Original_Data Download (Tucker)

'mapdata_copyright_openstreetmap_contributors.txt' was not uploaded, because it is too large for GitHub (it's 40.9MB). You will have to download this from https://www.kaggle.com/c/predict-west-nile-virus/data if you need it (I think it is a different format of the same information contained in the .rds file of the same name)

## Info about about the data (Youn Hee)
Spray data - Years: 2011, 2013
Weather data - Years: 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014
Training data - Year: 2007, 2009, 2011, 2013
Test data - Year: 2008, 2010, 2012, 2014

## What data to use (...work in progress)
Since we only have spray data for the training years (odd years) and not the test years (even years) we have 
decided that we are not going to use the spray data. 

We chose to remove station 2 from the weather data.

We also divided the weather data into 2 data frames, odd and even years. This is to make it easier to merge the weather data into the test and training data. 


## Info about the cleaned Weather/Spray output CSV files (Youn Hee)
Weather 
- Datetime format is not kept when you turn the data into a CSV and then read the CSV. So you need to do it again when you read in the CSV-file.
- The column named Unnamed: 24 acually do not have a name, it was just empty in the CodeSum column when the dummies were greated.
- Drop column CodeSum. You do not want to use CodeSum and dummies together. (was not done in the cleaning process)
- Change Sunrise and Sunset if they are going to be used. They are strings of time right now, like '0415'. (was not done in the cleaning process)

Spray 
- Datetime format is not kept when you turn the data into a CSV and then read the CSV. So you need to do it again when you read in the CSV-file.

## Info about the cleaned Train/Test output CSV files (Tucker)

Train/Test
- The following features have been dropped in X_train_clean.csv and X_test_clean.csv. Let me know if you'd like any of them reincorporated for any reason.
	- Date: Information recreated in features 'Year_x', 'Month_x' and 'Day_x'
	- Address: Information recreated in 'Latitude', 'Longitude' and 1-hot encoded zip codes
	- Species: Information recreated in 1-hot encoded species
	- Street: Duplicate information of Address
	- AddressNumberAndStreet: Duplicate information of Address
	- AddressAccuracy: Erroneous information from geocoder
	- Zipcode: Information recreated in 1-hot encoded zipcodes

- The following features have been dropped in weather_odd.csv and weather_even.csv.
	- CodeSum: Information recreated i 1-hot encoded weather features
	- Year_y: Duplicate information from X_train/X_test
	- Month_y: Duplicate information from X_train/X_test
	- Day_y: Duplicate information from X_train/X_test
	- Unnamed: 24: Erroneous information

---

## Logistic regression model (David)
The notebook named logreg_model is the logistic regression model document. (could be cleaned and commented more)
The sub1.csv is the submission document that was submitted to kaggel.