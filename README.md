# Project H1 - HISTORICAL FLIGHT PRICES
Authors: Kerreth Arula, Nazar Zavrin, Oliver Albert Hallik

## Goals and motivation of the project

Flight prices change frequently and are affected by many different factors such as the airline, route, season and how close the departure is. This makes a purchasing decision difficult for a traveller, who might hope that the price drops in the future. <br>

The goal of our project is to give some basis to those travellers to make that decision on. We decided to build regression models to predict the price of a flight ticket from information only available to a traveller during booking time using a dataset that contains over 20 million flight listing observations. We want to try different models and compare them to simple baselines using the MAE metric in euros to see, if we could get a result that is worth using. We also want to study the relationship between different attributes of a flight and how they drive the price of a ticket.

Our main motivation is to see, if we can create a model a traveller can actually rely on to make a decision whether to buy now or wait for a drop.

## The dataset
The dataset is too large to add into Github. 
Please download it from Kaggle and add it to the root of the project: https://www.kaggle.com/datasets/daniilchuhai/flights-test/data?fbclid=IwY2xjawVYOkVleHRuA2FlbQIxMABwZG9mBWJyaWQRMHN2cXVzTTdkVUZGOGh4NW1zcnRjBmFwcF9pZBAyMjIwMzkxNzg4MjAwODkyAAEfZnUXsTbFOStBFIVm44VlM8B04assrmY_cs2ESU-br1wO3XEH1tmqKKQZHsM_aem_6-_PBuVtJObj14H58YXKdg
There is only one file needed: flights_clean.parquet

## How to navigate the repository

Here are the files and their main content:

- IDS2026_HW07.ipynb: This file contains our first exploration of the data, understanding the data as well as the business aspect, setting some goals and identifying problems. We checked the columns, data types, data quality and tried to make our first few plots. This was the starting point.
- Introduction_to_Data_Science_project.ipynb: This file contains the initial cleaning of the raw dataset and checking some correlations to help with modelling in the future.
- feature_building_preprocessing.ipynb: This file contains further cleaning of the data, engineering many new columns from existing data, deciding the train/val/test split, identifying outliers, optimizing data types and creating a full dataset ready for modelling with a sample dataset.
- modelling.ipynb: This file contains all the modelling work: splitting the data, removing outliers, establishing baselines, removing unneeded columns or ones that can potential leak the target, training Ridge and Lasso regression models as well as a LightGBM model and finding the best parameters for them, comparing the models and baselines by MAE and RMSE, identifying the feature importance and the final evaluation of the models as well as conclusions
- plotting.ipynb: - This file contains further exploration of the data and especially the new engineered features. There are many plots comparing features to price and also grouping them to different ranges and paired with other features. 
- IDS2026_HW10.ipynb: Reporting our work so far during HW10.


## How to replicate our work?
- Clone our repository and download the dataset from the link above. Add it to the root of the project.
- Run the IDS2026_HW07.ipynb notebook, then Introduction_to_Data_Science_project.ipynb. This gives us the initially cleaned dataset called 'cleaned_flights_for_modelling.parquet'.
- Run feature_building_preprocessing.ipynb. This uses the file created in the last step and creates 'features.parquet' which contains all the engineered features and the sample 'features_sample.parquet' which contains about 10% of the rows for experiments. Run this notebook before the modelling one.
- Run modelling.ipynb. This notebook does all the modelling. There is a switch at the top to either use the sample or full dataset. All the modelling results come from here. Note: training the models took hours, so using the sample is better advised. The full dataset gives the full results, but takes a very long time to run.
- Run plotting.ipynb: this notebook contains the further exploration of the constructed features.ipynb dataset and finds different interesting relationships between attributes and plots them. You can run this before the modelling notebook as well.
