# Predictive Time Series Modelling for Real Estate Investment using Zillow Research Data
![image](https://github.com/nkevin90/Time-Series-on-the-Housing-Data-Zillow-Research/blob/main/cover.png)

This repository contains the code and analysis for developing a predictive time series model for real estate investment using Zillow research data. The project's goal is to provide Naruto Investment firm with solid recommendations for the top 5 best zip codes to invest in.

## 1.Introduction
Real estate is a significant component of most people's wealth, and this is especially true for American homeowners. However, the real estate market is influenced by various variables that can make it challenging for investors to choose the right investment opportunities. To help investors in this process, Naruto Consultants aims to develop a predictive time series model.

## 2. Business Understanding
### Problem Statement
Naruto Consultants aim to simplify the buying process for their clients by developing a predictive time series model that can identify lucrative real estate investment opportunities.

### Main Objective
The main objective of this project is to develop a time series model that can predict the future prices of houses for Naruto Investments to invest in.

## 3. Notebook Structure
The Python notebook is structured as follows:
- Data cleaning
- External Data Validation
- Exploratory Data Analysis
- Data Preprocessing
- Data Modelling and Evaluation
- Conclusion and Recommendations

## 4. Data Understanding
The Data
The data used in this project was downloaded from GitHub and provided by researchers at Zillow. It consists of 14,723 rows and contains a small series of categorical features, as well as a large number of columns, each containing the median value of homes in a zipcode for a certain month. The months range from April 1996 to April 2018. The dataset includes features such as RegionID, RegionName (Zip code), City, State, Metro, CountyName, and SizeRank.

## 5. Data Preparation
To prepare the data for modeling and exploration, the pd.melt function was applied to transform the dataset from a wide format to a long format, resulting in a dataset with 3,901,595 rows and 11 columns. The data cleaning process involved handling missing values and checking for duplicates.

## 6. Exploratory Data Analysis
Exploratory Data Analysis (EDA) was performed to uncover various patterns. The most popular state, city, and average profit margin per state were determined. Mean %ROI by zipcode and house value were also examined.

## 7. Data Preprocessing
During EDA, we noticed that the dataset as provided by Zillow comes in "wide format" and for our time series models to run, we had to convert it to "long format." A function was provided to do this. The top 5 zip codes based on %ROI were filtered, and data was grouped by date and zipcode, calculating the mean price for each group selecting from 2012. Home prices and monthly returns of each zipcode were plotted.

## 8. Data Modelling and Evaluation
The data was modeled using statistical time series models, such as ARIMA and SARIMA. The model's performance was evaluated using several metrics, such as Mean Squared Error (MSE) and Return on Investment (ROI).

## 9. Conclusion and Recommendations
The ARIMA and SARIMA models were evaluated using MSE and ROI%, and the top 5 zip codes to invest in were identified. The findings of this project can be used by Naruto Investments to make informed investment decisions in the real estate market.
