<h1>S&P 500 Trading Predictor Model</h1>



<h2>Description</h2>
This project aims to develop a prediction model for the S&P 500 index to forecast whether its price will increase or decrease on the following trading day. The goal is to create a reliable tool that can assist in making informed stock trading decisions.
<br />
<h3>Step Overview</h3>
<b>Data Cleaning</b>
This step involved the cleaning of data, removing unnecessary columns like “Dividend” and “Stock Splits”. To ensure the model’s reliability, old market data before the 1990s is excluded from the dataset as it greatly differs from the current market conditions. Old market data is generally an unreliable indicator of whether a stock in the modern age will increase or decrease and can lead to false predictions. Hence, the dataset is cleaned to only include S&P 500 data past 1990-01-01.
<br />
<b>Target and Predictors</b>
The target for our model is set to whether the S&P 500 price will increase or decrease the following trading day. The predictors are also set, which will be the values we analyze to formulate a prediction. The predictors used are: Close, Open, Volume, High, Low, rolling average ratio, rolling average trend.  
<br />
<b>Machine Learning Model</b>
<br />
To train the machine learning model, we use RandomForestClassifier, which is a type of decision tree algorithm. Random Forest trains a variety of individual decision trees using randomized parameters, and then taking an average from those decision trees. Random Forest was chosen because of several reasons. Firstly, it is able to pick up non-linear relationships, which is extremely important when predicting stock prices. This is because stock prices are never linear, and treating them as such would yield unreliable predictions. Second, they do not take too long to run, which is beneficial in training and obtaining fast results. Lastly, due to the way Random Forest works, it is resistant to overfitting when compared to other models. 
<br />
<b>Backtesting</b>
<br />
To verify our results, we create a backtest method. The backtest method trains the first model with 10 years of data, equivalent to 2500 days as there are 250 trading days in a calendar year. We then use a step of 250 days (1 year), which trains each following model over the course of the total elapsed time, which is now 11 years. We then take another step of 250 days, which trains the following model over the total elapsed time of 12 years. This process continues until we reach the present day. This means that the training set will be all years prior to the current year in question, and the test set is the current year. We then call the predict method within the backtest method to generate our predictions. The predictions will then be stored in a list.
<br />
<b>Ways to improve accuracy</b> 
<br />
In order to improve the accuracy of our predictions, I incorporated the use of rolling averages. The rolling averages calculate the mean close price over several specific timeframes: past 2 days, past trading week, past 3 trading months, past trading year, past 4 trading years. We use this information to create new columns in the dataframe, displaying the trend and other ratios that would improve our accuracy. 
<br />
Other methods to improve accuracy could be to increase the threshold of success for predictions. The default setting causes the model to predict an increase if there is greater than a 50 percent chance of an increase. If we increase the threshold to 60 percent, it would provide us with more concrete predictions, as the model has to be more than 60 percent sure that the price will increase, instead of 50 percent. We can therefore be more confident of the model’s predictions.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 

<h2>Environments Used </h2>

- <b>Jupyter Notebook</b> 

<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
