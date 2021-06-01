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

<p>Before performing Statistical Analysis and Arima time series, it is a good practise toundersatnd the data and try to gather as many insights from it. Some of the Exploratory Data Analysis plot are **Histogram** ( Graphically method to summarise the distribution of a univariate dataset), **Barplot**( A chart or graph that presents categorical data with rectangular bars with heights or lengths proportional to the values that they represent) and **LinePlot** to plot the time series plot of the sales Data with datetime as x-axis</p>


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
