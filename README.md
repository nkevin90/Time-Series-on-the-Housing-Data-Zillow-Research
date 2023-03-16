# Time-Series-on-the-Housing-Data-Zillow-Research
![image](https://user-images.githubusercontent.com/116062465/225610397-429d89cb-2e0f-4c22-9621-199c97f3cac9.png))

## 1.Introduction
Real estate investments can provide both short-term and long-term returns through rental income, property appreciation, and value-added investments such as renovations and developments.Real estate represents a significant portion of most people's wealth, and this is especially true for many homeowners in the United States. A number of factors drive the real estate market including government policies, demographics of the potential buyers,affordability, disparity in housing access, location, cash flows and liquidity as well as the current economic climate. 

## 2. BUSINESS PROBLEM
### The Problem statement
The many variables can make the process tedious for the buyers. Naruto consultants hope to create a predictive time series model that can help to determine which real estate opportunities to invest in.
### Main Objective
Our main objective for this project is to develop a time series model that would predict the future prices of houses for Naruto Investments to invest in.

## 3. NOTEBOOK STRUCTURE  
The notebook is [here](https://github.com/nkevin90/Time-Series-on-the-Housing-Data-Zillow-Research/blob/main/index.ipynb)  

The python notebook is structured as follows:
1.Data cleaning
2.External Data Validation
3.Exploratory Data Analysis
4.Data Preprocessing
5.Data Modelling and evaluation
6.Conclusion and Recommendation

## 4. DATA UNDERSTANDING
### The Data
The data used in this project was downloaded from [Github](https://github.com/learn-co-curriculum/dsc-phase-4-choosing-a-dataset/tree/main/time-series) 
The data provided came from the researchers at Zillow and consisted of 14,723 rows. The dataset included a small series of categorical features and a large number of columns, each of which contained the median value of homes in a zipcode for a certain month. The months ranged from April 1996 to April 2018.These were some of the features:
- RegionID: ID
I initially was not sure if this column was a zip code or an ID but after a cursory search It was discovered that 84654 is from Utah and not Chicago, 
- RegionName: This was the column for zip codes.60657 is a Chicago ZipCode
- City
- State
- Metro: What Metropolitan Area the zip code is nearest to.
- CountyName: Name of the county the zip code resides within.
- SizeRank: Rank of Urbanization (The closer to 1, the more urbanized).


### Data Preparation
The data was checked for missing values and some columns were found to have null values.There were no duplicates in the dataset.

### Exploratory Data Analysis
By carrying out EDA , various patterns were discovered.
We found the most popular state,city and average Profit Margin per State
![image](![image](https://user-images.githubusercontent.com/116062465/225603513-3a79eb45-74d3-447d-910e-832ee93c1a99.png))
![image](https://user-images.githubusercontent.com/116062465/225603647-bb7fc5e5-77eb-4349-928c-67602a4b785a.png)  
![image](https://user-images.githubusercontent.com/116062465/225604010-05e11d35-7a1d-49af-8d32-efabc52e1966.png)


### Data Preprocessing
During EDA, we noticed that the dataset as provided by Zillow comes in "wide format" and for our time series models to run, we had to convert it to "long format". Luckily a function to do this was provided to us along with the dataset. We filtered the top 5 zipcodes based on %ROI and grouped data by date and zipcode, and calculate the mean price for each group selecting from 2012.
Plotting home prices by zipcodes
![image](https://user-images.githubusercontent.com/116062465/225606702-55f4ebe6-151f-4af6-9e9e-d91544a888cd.png)
Monthly returns of each zipcode
![image](https://user-images.githubusercontent.com/116062465/225606904-d54a3737-3e5a-4c86-8026-b8f54017c1ec.png)
A Dicky-fuller test was performed to test for stationarity

## 5.Modelling
For this project  a SARIMA model was used  with time series data to forecast the next 10 years of ROI for 5 zip codes to help real estate investors know which zip codes were best to invest in.




## 6.CONCLUSIONS 

- 
## 6.RECOMMENDATIONS
-

## 7.REPOSITORY GUIDE
- The data set used can be found [here](https://github.com/Wachira-2030/used-car-price-prediction/blob/main/Car%20details%20v3.csv)
- The data report can be found [here](https://docs.google.com/document/d/1B9I0-xRG8lxLWqaBFGVek-dTkqbagRHvYpjNrPdN8tU/edit#heading=h.k2dex7ijg0)
- The notebook can be found [here](https://github.com/Wachira-2030/used-car-price-prediction/blob/main/index.ipynb)
- The Presentation Slides can be found [here](https://www.canva.com/design/DAFXiNjCN-o/oBZXk_wvi-jTLk2v5q-sKw/view?utm_content=DAFXiNjCN-o&utm_campaign=designshare&utm_medium=link&utm_source=publishsharelink)
