# Final_Proyect

## Predict Fare of Airlines Tickets 
The idea of the project is to create a model capable of predicting the price of airline tickets.

## Dataset
For this project I have used a kaggel dataset consisting of 10683 rows and 11 columns.
Columns:
  - Airline: with the different airlines
  - Date_of_Journey: with the travel date
  - Source: with the origin of the place of departure
  - Destination: with the destination
  - Route: with the airport route that follows
  - Dep_Time: with departure time
  - Arrival_Time: with arrival time
  - Duration: The duration of the trip in hours
  - Total_Stops: the number of stops on the trip
  - Additional_Info: Separate information such as how many bags you have checked in, the class ...
  - Price: the price of the trip and our target variable

## Data wranling 
The original dataset had several problems in its columns.
First convert the columns Date_of_Journey, Dep_Time, Arrival_Time to data type time.
From there I started to work on the data that were interesting from those columns:
  - From the Date_of_Journey column create two new ones with the month and the day the trips were made
  - With the columns of 'Dep_Time', 'Arrival_Time' I separate them in hours and minutes and that it returns zero value if there are no hours or minutes
  - Separate the values of the 'Route' column by eliminating the '→' symbol that you had as a separator
  - Transform and correct the written values different from the column 'Additional info'

## Data Cleaning
Luckily the dataset only had a couple of null values of origin plus those that had been created in the new columns of the Route column.
For null data I decided to do a dropna of the original columns and a fillna with zero value of the path columns.

## Handle Categorical columns
To handle categorical data use label encoder on the columns 'Route_1', 'Route_2', 'Route_3', 'Route_4', 'Route_5' created from separating the route column above.
For the rest of the categorical columns use a onehot encoder.

## Train, validation, test split, model
  - Training set: 80 percent of the data
  - Validation set: 10% of the data
  - Test set: 10% of the data
  - model: After trying different models I decided to use the RandomForestRegressor since it is the one that gave me the best results.

## Cross-Validation and Hyperparameter Tuning
After creating, training the model and seeing the initial predictions, I proceed to perform Cross-Validation and Hyperparameter Tuning on it, improving the model.

## Result
Our model is close to 80 percent accuracy
