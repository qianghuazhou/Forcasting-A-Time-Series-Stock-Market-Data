# Forcasting of a Time Series (Stock Market) Data in R
### *A Comparative Study by,* 

#### _Shreyashi Saha_ _and_ _Sagarnil Bose_
###### _Masters in Statistics_


![](Images/Intro.jpg)

### Contents

####  **Overview**  
  
####  **Introduction**  
  
####  **Dataset and Advanced Visualizations**  
  
####  **Methods**
 * *ARIMA*: &nbsp; *Autoregressive Integrating Moving Average Model
		   -Forecasting
		   -Arima Results*
 * *GARCH*: &nbsp; *Generalized Autoregressive Conditional Heteroscedastic Model
		   -Garch Forecasting
                   -Garch Results*
 * *Prophet-Prophet Forecasting-Prophet Results*
 * *K-NN regression time series forecasting*
 * *Feed Foward Neural network*  
 
 #### **Result**  
 
 #### **Conclusion**

### **Overview**
This project describes different time series and machine learning forecasting models applied to a real stock close price dataset. For this project we will start with a general idea of the stock price, including dataset analysis. Followed by a general description and analysis of the dataset, our objective is to apply different forecasting predictive models for “S&P500” stock daily close price. The models will be evaluated, analyzed and compared, following the main course project directions. The data will be prepared to predict the next 30 days’ close price from today. The results will be explained during the report along with concluding remarks.
### **Introduction**
A forecasting algorithm is an information process that seeks to predict future values based on past and present data. This historical data points are extracted and prepared trying to predict future values for a selected variable of the dataset. In this project approach we will focus on quantitative forecasting involving our variable to forecast (close price), its statistical analysis and advanced concepts applied to a given historical data.

Historically, there has been a continuous interest in trying to analyze market tendencies, behavior and random reactions. This continuous concern to understand what happens before it really happens motivates us to continue with this study. Some great market traders and economists says that is almost impossible to predict stock returns or prices referring to, independence between each other, the past movements or trends cannot be used to predict future values, explained by random walk theory, skewness, kurtosis and big random component. With the new different advanced models, we will try to go against the current, because, why not? As this is a data science project this forecasting models are not considered as oracles, but are really useful for analyzing the movements of stock prices with a statistical approach. The main objective of this research is to show the models fitted, compare them and encourage the use of them.

Let us firstly load the following libraries into the R environment
```R
#libraries
library(quantmod)
library(ggplot2)
library(forecast)
library(tseries)
library(rugarch)
library(prophet)
library(tsfknn)
```
If the libraries are not installed, install the required packages with `install.packages("library.name")`
### **Dataset and Advanced Visualizations**
Firstly, we take a glimpse into the data.
```R
getSymbols("^GSPC",src="yahoo",from="2015-01-01",to = "2020-06-04")
head(GSPC)
```
```
>Index        GSPC.Open   GSPC.High   GSPC.Low   GSPC.Close   GSPC.Volume   GSPC.Adjusted
 2015-01-02   2058.90     2072.36     2046.04    2058.20      2708700000    2058.20
 2015-01-05   2054.44     2054.44     2017.34    2020.58      3799120000    2020.58
 2015-01-06   2022.15     2030.25     1992.44    2002.61      4460110000    2002.61
 2015-01-07   2005.55     2029.61     2005.55    2025.90      3805480000    2025.90
 2015-01-08   2030.61     2064.08     2030.61    2062.14      3934010000    2062.14
 2015-01-09   2063.45     2064.43     2038.33    2044.81      3364140000    2044.81
```
Now, we try to visualize the close price data with the following graph
```R
chartSeries(GSPC,TA = NULL)
```
![](Images/plot_1.jpeg)


For a more advanced view, we add Bollinger Band chart, % Bollinger change, Volume Traded and Moving Average Convergence Divergence to the above graph.

![](Images/plot_2.jpeg)

For a more detailed code [visit here](https://github.com/Stat-Wizards/Forcasting-a-Time-Series-Stock-Market-Data)

![](Images/plot_3.jpeg)
![](Images/plot_4.jpeg)
![](Images/plot_5.jpeg)
![](Images/plot_6.jpeg)
![](Images/plot_7.jpeg)
![](Images/plot_8.jpeg)
![](Images/plot_9.jpeg)
![](Images/plot_10.jpeg)
![](Images/plot_11.jpeg)
![](Images/plot_12.jpeg)
![](Images/plot_13.jpeg)
![](Images/prophet.png)
![](Images/plot_14.jpeg)
![](Images/plot_15.jpeg)
![](Images/knn2.png)
![](Images/plot_16.jpeg)
![](Images/feed_forward.jpg)
![](Images/plot_17.jpeg)
