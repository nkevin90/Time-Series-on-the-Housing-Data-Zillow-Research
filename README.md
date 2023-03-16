# Time-Series-on-the-Housing-Data-Zillow-Research
![image](https://user-images.githubusercontent.com/116062465/225610397-429d89cb-2e0f-4c22-9621-199c97f3cac9.png)

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

## 5.Modelling
For this project  auto arima was used to find the best p,d,q for the model then we did fit the ARIMA model on the training series.
![image](https://user-images.githubusercontent.com/116062465/225685554-b62cea0f-2ab3-4856-a43d-b8631bc864fc.png)
![image](https://user-images.githubusercontent.com/116062465/225685818-bd1483f8-72c4-4be8-870f-d6cedd59579b.png)  
The qq- plot on the bottom left showed that the residuals followed a linear trend line hence  normally distributed.The correlogram plot on the bottom left showed there were low correlations with their lagged version. There wasn't seasonality in our series.The histogram had a bell curve showing that the residuals are normally distributed which was a good thing.

## 6.CONCLUSIONS 
![image](https://user-images.githubusercontent.com/116062465/225711356-0ecfd169-e3fe-4fd6-b4b0-d066b82b4d0d.png)
- The Highest Growing Zipcode: 2 is expected to grow by 57.31%
- All the Zipcodes have an encouraging predicted price seeing as they are in the positive apart from the 85035 zipcode 
- 
## 7.RECOMMENDATIONS
- The investor can then decide to invest in any of the top 5 zipcodes that have the highest ROI Forecast.

## 8.REPOSITORY GUIDE
- The data set used can be found [here](https://github.com/learn-co-curriculum/dsc-phase-4-choosing-a-dataset/tree/main/time-series)
- The data report can be found [here](https://docs.google.com/document/d/1SwijdmULcyr92pvaWKuVQyIZFxTCL23Jb0qcMRnpK_E/edit)
- The notebook can be found [here](https://github.com/nkevin90/Time-Series-on-the-Housing-Data-Zillow-Research/blob/main/index.ipynb)
- The Presentation Slides can be found [here](https://www.canva.com/design/DAFdMH34Hbo/f9KjfY-RSlMXAnzjBnluGg/edit?utm_content=DAFdMH34Hbo&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
