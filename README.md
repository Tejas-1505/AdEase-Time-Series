# AdEase-Time-Series
My Case studies with Scaler Academy

## About AdEase

Ad Ease is an ads and marketing based company helping businesses elicit maximum clicks @ minimum cost. AdEase is an ad infrastructure to help businesses promote themselves easily, effectively, and economically. The interplay of 3 AI modules - Design, Dispense, and Decipher, come together to make it this an end-to-end 3 step process digital advertising solution for all.

You are working in the Data Science team of Ad ease trying to understand the per page view report for different wikipedia pages for 550 days, and forecasting the number of views so that you can predict and optimize the ad placement for your clients. You are provided with the data of 145k wikipedia pages and daily view count for each of them. Your clients belong to different regions and need data on how their ads will perform on pages in different languages.


## Dataset:

**Data Dictionary:**

There are two csv files given

**train_1.csv:** In the csv file, each row corresponds to a particular article and each column corresponds to a particular date. The values are the number of visits on that date.

The page name contains data in this format:

SPECIFIC NAME _ LANGUAGE.wikipedia.org _ ACCESS TYPE _ ACCESS ORIGIN

having information about the page name, the main domain, the device type used to access the page, and also the request origin(spider or browser agent)


Exog_Campaign_eng: This file contains data for the dates which had a campaign or significant event that could affect the views for that day. The data is just for pages in English.

There’s 1 for dates with campaigns and 0 for remaining dates. It is to be treated as an exogenous variable for models when training and forecasting data for pages in English



## Concepts Tested:

Exploratory data analysis

Time Series forecasting- ARIMA, SARIMAX, and Prophet

## Results

- There are **7 known language** pages in the dataset - **English, Japanese, German, French, Chinese, Russian** and **Spanish**
- **English** has the maximum number of pages, **16.62%**. This is excpected as the maximum people speak English
- **Decomposition** helps in understanding the underlying **trend**, **seasonality** and **error**(residual) in the time series data.
- As per the analysis done on English language time series data, a differencing of 1 gives a stationary series. This is also tested using Augmented Dickey-Fuller test
- As per the exogenous variable given, the visits to the English page has an **unusual peak** whenever the **exogenous variable is 1**
- The performance of AdEase will be effected by events or campaings. AdEase can use the **Prophet model** along with **exogenous** variable to **improve** their **predictions**
- Without the exogenous variable, it becomes impossible to make accurate predictions. This is demonstarted by the plots of other languages which do not have exogneous variable
- The main difference between ARIMA, SARIMA and SARIMAX is:
  - ARIMA is used for modeling non-seasonal time series data with trends and autocorrelations
  - SARIMA extends ARIMA by explicitly modeling seasonality in the time series. It’s useful when the time series exhibits seasonal patterns (e.g., monthly or yearly cycles).
  - SARIMAX is an extension of SARIMA that includes exogenous variables (external factors) in the model. It models both seasonal and non-seasonal components, while also incorporating the effect of other external (exogenous) variables that may influence the time series.
