# Time-Series-on-the-Housing-Data-Zillow-Research
![image](https://user-images.githubusercontent.com/116062465/225610397-429d89cb-2e0f-4c22-9621-199c97f3cac9.png)

This repository contains the code and analysis for developing a predictive time series model for real estate investment using Zillow research data. The goal of this project is to provide solid recommendations to Naruto Investment firm for the top 5 best zip codes to invest in.

## 1. Introduction
Real estate is a major component of most people's wealth, and this is particularly true for many American homeowners. The real estate market is influenced by various variables, such as governmental regulations, demographics of prospective buyers, affordability, disparities in housing access, location, cash flows, liquidity, and the overall status of the economy. To help investors choose which real estate possibilities to pursue, Naruto Consultants are working to develop a predictive time series model.

## Dependencies

This project requires the installation of the following libraries:

- pandas: data manipulation and analysis library
- numpy: numerical computing library
- seaborn: data visualization library based on matplotlib
- matplotlib: plotting library for the Python programming language
- statsmodels: library for statistical modeling and analysis
- pmdarima: library for ARIMA modeling and forecasting
- sklearn: machine learning library

## 2. Business Understanding
### The Problem statement
Naruto consultants aim to simplify the buying process for their clients by developing a predictive time series model that can identify lucrative real estate investment opportunities, despite the complex array of variables that can make this task tedious for buyers.
### Main Objective
Our main objective for this project is to develop a time series model that would predict the future prices of houses for Naruto Investments to invest in.

## 3. Notebook Structure  
The notebook is [here](https://github.com/nkevin90/Time-Series-on-the-Housing-Data-Zillow-Research/blob/main/index.ipynb)  

The python notebook is structured as follows:
1.Data cleaning
2.External Data Validation
3.Exploratory Data Analysis
4.Data Preprocessing
5.Data Modelling and evaluation
6.Conclusion and Recommendation

## 4. Data Understanding
### The Data
The data used in this project was downloaded from [Github](https://github.com/learn-co-curriculum/dsc-phase-4-choosing-a-dataset/tree/main/time-series) 
The data provided came from the researchers at Zillow and consisted of 14,723 rows. The dataset included a small series of categorical features and a large number of columns, each of which contained the median value of homes in a zipcode for a certain month. The months ranged from April 1996 to April 2018.These were some of the features:
- RegionID: ID
I initially was not sure if this column was a zip code or an ID  
- RegionName: This was the column for zip codes.60657 is a Chicago ZipCode
- City
- State
- Metro: What Metropolitan Area the zip code is nearest to.
- CountyName: Name of the county the zip code resides within.
- SizeRank: Rank of Urbanization (The closer to 1, the more urbanized).


### Data Preparation
To prepare the data for modeling and exploration, we applied a pd.melt function to transform the dataset from a wide format to a long format. This resulted in a dataset with 3901595 rows and 11 columns, which made it easier to read and work with.

The data cleaning process involved the following steps:

a.Handling missing values:
- Identified missing values in the Metro, %ROI, and ROI price columns. Filled the null values in the Metro column with "Missing". The remaining two columns were handled in the preprocessing stage.

b.Checking for duplicates:
- Checked the dataset for duplicates and found that there were none. This ensured that our analysis was based on unique and accurate data.

### Exploratory Data Analysis
By carrying out EDA , various patterns were discovered.
We found the most popular state,city and average Profit Margin per State
![image](https://user-images.githubusercontent.com/116062465/225703861-6af4f9f9-9285-4fab-adc9-d8e581ffd6c1.png)
![image](https://user-images.githubusercontent.com/116062465/225704174-7d5f9f11-d987-47ee-aed6-a7772db8c25c.png)
Mean %ROI by Zipcode  
![image](https://user-images.githubusercontent.com/116062465/225704385-d62599fe-d0d8-49ef-a1cf-bf258e90dd94.png)
House value  
![image](https://user-images.githubusercontent.com/116062465/225708965-3afa9145-b971-445d-b30f-3b90b9602f60.png)

### Data Preprocessing
During EDA, we noticed that the dataset as provided by Zillow comes in "wide format" and for our time series models to run, we had to convert it to "long format". Luckily a function to do this was provided to us along with the dataset. We filtered the top 5 zipcodes based on %ROI and grouped data by date and zipcode, and calculate the mean price for each group selecting from 2012.
Plotting home prices by zipcodes
![image](https://user-images.githubusercontent.com/116062465/225606702-55f4ebe6-151f-4af6-9e9e-d91544a888cd.png)
Monthly returns of each zipcode
![image](https://user-images.githubusercontent.com/116062465/225606904-d54a3737-3e5a-4c86-8026-b8f54017c1ec.png)  
A Dicky-fuller test was performed to test for stationarity

## 5. Modelling
For this project  auto arima was used to find the best p,d,q for the model then we did fit the ARIMA model on the training series.
![image](https://user-images.githubusercontent.com/116062465/225685554-b62cea0f-2ab3-4856-a43d-b8631bc864fc.png)
![image](https://user-images.githubusercontent.com/116062465/225685818-bd1483f8-72c4-4be8-870f-d6cedd59579b.png)  
The qq- plot on the bottom left showed that the residuals followed a linear trend line hence  normally distributed.The correlogram plot on the bottom left showed there were low correlations with their lagged version. There wasn't seasonality in our series.The histogram had a bell curve showing that the residuals are normally distributed which was a good thing.

## 6. Conclusions 
![image](https://user-images.githubusercontent.com/116062465/225711356-0ecfd169-e3fe-4fd6-b4b0-d066b82b4d0d.png)
- The Highest Growing Zipcode: 2 is expected to grow by 57.31%
- All the Zipcodes have an encouraging predicted price seeing as they are in the positive apart from the 85035 zipcode 

## 7. Recommendations
- Investors are encouraged to consider investing in the top five recommended zip codes, as they are expected to have a positive ROI. However, it is important to note that additional factors beyond predicted price should also be considered before making an investment decision. Factors such as the availability of facilities like schools and hospitals, the level of security, and historical performance of real estate investments in the area should also be taken into consideration.

## 8. Repository guide
- The data set used can be found [here](https://github.com/learn-co-curriculum/dsc-phase-4-choosing-a-dataset/tree/main/time-series)
- The data report can be found [here](https://docs.google.com/document/d/1SwijdmULcyr92pvaWKuVQyIZFxTCL23Jb0qcMRnpK_E/edit)
- The notebook can be found [here](https://github.com/nkevin90/Time-Series-on-the-Housing-Data-Zillow-Research/blob/main/index.ipynb)
- The Presentation Slides can be found [here](https://www.canva.com/design/DAFdMH34Hbo/f9KjfY-RSlMXAnzjBnluGg/edit?utm_content=DAFdMH34Hbo&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
