<h1 style="color:grey;text-align:center"> 
Time Series analysis of Product's Sales using Arima 
</h1>    

Jupyter notebook is used for performaing Exploratory Data Analysis, Statistical test and Arima Time Series model

<h2>Problem Statement </h2>
<p> We have to predict the sales of an item for the next 3 months using Time series technique. In this model we are using ARIMA for performing forecasting method along with  Exploratory data Analysis and Statistical tests for measuring the data Quality 
</p>


<h2>Dataset: </h2>

<p> The dataset contains data of 5 years of store-item sales data, and asked to predict 3 months of sales for 50 different items at 10 different stores.
  https://www.kaggle.com/c/demand-forecasting-kernels-only/overview/description </p>
  
  
  <h2>Exploratory Data Analysis: </h2>

<p>Before performing Statistical Analysis and Arima time series, it is a good practise toundersatnd the data and try to gather as many insights from it. Some of the Exploratory Data Analysis plot are <strong>Histogram</strong> ( Graphically method to summarise the distribution of a univariate dataset), <strong>Barplot</strong>( A chart or graph that presents categorical data with rectangular bars with heights or lengths proportional to the values that they represent) and <strong>LinePlot</strong> to plot the time series plot of the sales Data with datetime as x-axis</p>

![barplot](https://user-images.githubusercontent.com/57468338/120264747-6f083f00-c26c-11eb-9e50-49d2fbd137e5.png)
![histo1](https://user-images.githubusercontent.com/57468338/120264770-7a5b6a80-c26c-11eb-9e0d-e0393cbc6960.png)
![timeseries](https://user-images.githubusercontent.com/57468338/120264773-7cbdc480-c26c-11eb-80e5-27b5626d6bc2.png)


<h2>Decompose Time Series into Trend and Seasonality</h2>

<p>
A Time Series consists of three systematic components which are as follows:
  <ul>
    <li><strong>Level: </strong>The Average value in the series</p>
      <li><strong>Trend: </strong>The increasing or decreasing value in the value</p>
        <li><strong>Seasonality: </strong>The repeating short-term cycle in the series</p>
          <li><strong>Noise: </strong>The random variation in the series</p>
    </ul>

The components of the time series can be <strong>Additive</strong> and <strong>Multiplicative</strong>
<h3>Additive Model : </h3> <p> An additive model is a linear where changes over time are consistently made by same amount.</p>

y(t)->Level + Trend + Seasonality + Noise
<h3>Multiplicative Model : </h3> <p> An multiplicative suggests that the components are multiplied together</p>
y(t)->Level x Trend x Seasonality x Noise
</p>

![decompose](https://user-images.githubusercontent.com/57468338/120268763-6e73a680-c274-11eb-9e68-3aa971303fb7.png)

<h2>Autocorrelation Function</h2>
<p> Autocorrelation and partial correlation plots are heavily used in time series analysis and forecasting. A plot of the autocorrelation of the time series by lag is called the Autocorrelation Function. ACF is an auto-correlation function which gives us the values of the auto-correlation of any series with its lagged values<p>

![image](https://user-images.githubusercontent.com/57468338/120377090-a9b0bc80-c2ea-11eb-8f9f-1fd7b7ef9aeb.png)

<h2>Check for stationary using Ad Fuller Hypothesis test</h2>

<p>
  The null hypothesis of the test is that the time series can be represented by a unit root, that it is not stationary (has some time-dependent structure). The alternate hypothesis (rejecting the null hypothesis) is that the time series is stationary.

<strong>Null Hypothesis (H0):</strong> If failed to be rejected, it suggests the time series has a unit root, meaning it is non-stationary. It has some time dependent structure.<br>
<strong>Alternate Hypothesis (H1):</strong> The null hypothesis is rejected; it suggests the time series does not have a unit root, meaning it is stationary. It does not have time-dependent structure.
We interpret this result using the p-value from the test. A p-value below a threshold (such as 5% or 1%) suggests we reject the null hypothesis (stationary), otherwise a p-value above the threshold suggests we fail to reject the null hypothesis (non-stationary).

<strong>p-value > 0.05:</strong> Fail to reject the null hypothesis (H0), the data has a unit root and is non-stationary.

<strong>p-value <= 0.05:</strong> Reject the null hypothesis (H0), the data does not have a unit root and is stationary.
  
  </p>

![image](https://user-images.githubusercontent.com/57468338/120379130-4e33fe00-c2ed-11eb-81cc-3475071b344b.png)

  <p>The more negative this statistic, the more likely we are to reject the null hypothesis</p>
  
  
  <h2>Arima Model(Autoregressive Integrated Moving Average) </h2>
  <p>When we combine differencing with autoregression and a moving average model, we obtain a non-seasonal ARIMA model.
  The predictors on the right hand side include both lagged values of yt and lagged errors denoted as ARIMA(p,d,q)
model
<ul>
  <li>p: order of the autoregression part</li>
  <li>q: degree of first differencing involved</li>
  <li>q: order of the moving average part</li>
  </ul>
  
For selecting p,d,q value we used Information Criteria known as AIC(Akaike Information Criterion) which is useful in selecting predictors for regression, also use to determine the order of an ARIMA model <br>
<strong>Good model are obtained by minimising the AIC, AICc or BIC</strong></p>

![image](https://user-images.githubusercontent.com/57468338/120388073-a91f2280-c2f8-11eb-96b8-eb3ab6ed4b20.png)

<h2>Metrics</h2>
 <p> We spilt the dataset into 88% training dataset and 12%  test dataset. Then we caculated the final root mean squared error score <strong> RMSE </strong> for the predictions  </p>. A line plot is then  plotted showing the expected value compared with the forecast predictions. We can see the values show some trend and are in the correct scale.
<br>
<strong>RMSE: 5.970 </strong></p> 

 ![image](https://user-images.githubusercontent.com/57468338/120389530-8857cc80-c2fa-11eb-89fb-d1c9f295789b.png)
 
  ![image](https://user-images.githubusercontent.com/57468338/120389837-f3090800-c2fa-11eb-973d-4d444a9b896f.png)
