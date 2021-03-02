# Recession Proofing an AlgoTrading Model
### Coded by CONNOR CRAWFORD, HENNA SINGH, MEAGAN RATHJEN, JOHN GASCHLER, OGUZHAN ACIL, FRANCIOS M BYRCH, MAURICIO RODRIGUEZ ALAS

## How the code works:
We split our code into 2 notebooks: 
* One that cleans the data, formats it to then export it to our model. 
* One where we read in the data from the other notebook, test, train, run and evaluate the model using different portfolio evaluation metrics. 

This allowed us to get the biggest part of the process out of way, to then, in the second notebook, focus on picking and adding features to the model making it as profitable as we could.

# The Project Itself:

## Project Proposal
Similar to Project 1, our team wanted to expand on the idea of making portfolios recession proof - so we decided to build an AlgoTrader that would learn based on the 2008 Recession, and apply that trading model to the most recent COVID Recession to see if the Algorithmic Trading Model could outperform what normal human beings would’ve done, especially during periods of high economic volatility. We chose the 5 highest performing stocks in each of the 5 industry portfolios and used the model on these 5. 

Our initial hypothesis was that given the right features and buy/sell learning, the model could anticipate the best time to buy and sell, ultimately recession proofing a bot using the two most recent recessions.

Some questions that we wanted to answer:
* What signals are important in generating an AlgoTrader that performs well during periods of high economic volatility?
* What should the individual bands be and how can they be used to mitigate risk? 
* Is it even possible to create a profitable AlgoTrader during recessions? 
* How many signals improve an AlgoTrader? Is there such a thing as too many or too little?

## Model Evaluation and Analysis 
* Predictive Model Used: Random Forest Classifier
* Reasoning: The reason we chose to use Random Forest was because we wanted to classify the model into two categories - buy or sell. Since we did not want to make a one-sided model (i.e. long only), using Random Forest to classify the securities into buy/sell allowed us to train the model to sell prior to big losses.
* Exploration & Cleanup was fairly straightforward because our team recycled the code we used for Project 1 which allowed us to focus most of our efforts on the model and its attributes. 
* Problems with Training the Model: Getting the stop loss to work correctly, adding features that improved the model, and the buy/sell indicator would occasionally be flipped in the visualization
* Overall Training Process: The model takes into account the returns, volatility, and the trend in volume (similar to simple moving average, but focused on volume rather than price) to anticipate buy/sell behavior. The most time-consuming part of the model was the data cleanup prior to the model training; the model training was fairly straightforward.  

## Feature Engineering
* EWMA - Short-term window of 5, long-term window of 50, used this over SMA since it more heavily weights recent data (Unused)
* Volatility - Similar to EWMA, short-term window of 5, long-term of 50. Focuses on the EWMA of the daily return rather than that of the Adjusted Close (Used)
* Bollinger bands - Used a window of 20, when the close price crossed upper or lower bands, indicated to sell and buy respectively (Used)
* Volume - Short-term window of 5, long-term window of 15, when the short term volume exceeded the long-term window the model was signaled to buy (Used)
* ATR - When True Range fell below 0.7, a signal to buy was generated, conversely when True Range was above 0.9, a signal to sell was generated (Unused)


## Findings and PostMortem Analysis

- Our findings were generally in line with expectations as to how each industry performed throughout each recession. 
- The gains and losses in 2008 were much greater than in COVID. Both recessions caused a good degree of volatility. 
- S&P 500 generally performs in a less volatile and risky manner compared to individual market sectors

 Some of our findings are as follows

The model is not overfitting or underfitting which is good. Using another type of model other than random forest could performance better which we could work on in future iterations. We calculated the AUC and GINI index using Disney in the graph that you can see here. 

 ![OVERALL ](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/OVERALL.PNG)
 

  **DISNEY 2008 Recession**

  Our cumulative returns for Disney between June of 2008 and June of 2009 were 9% despite the stock dipping 23% in that date range. It seems that the total of positive and negative trades were fairly similar in number the positive trades.This is some part can be attribute to our stoploss, which we had set at a negative 5% day over day change. 

   ![DISNEY 2008](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DIS2008all.PNG)

  The bollinger signal was most predictive followed closely by the volatility Trend and further behind was the volume signal. Cumulative return was right around 9% , annual volatility was arround 24% and we had a Sharpie ratio of 0.48 which could definitely use work in a sortina ratio od 0.69 which is closer to being acceptable but again could be better. The accurancy score was right around 0.52 and f1 score is 0.58


   ![DISNEY 2008 Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DIS2008Perf.PNG)

  **DISNEY Current**

  We see market that more accurately reflects leading up to the crash of 2008. Our cumulative returns for Disney between 2017 and to the current day we are at 87% and the annual return of 19%. Percent model doesn't do a good as good of a job of beating the natural rise of the stock.Since the stock did rise 83%. During this period ever we still did beat it narrowly.if you look at the net profit and loss of each trade you can see that the positive trade beat the negative trade in both volume and value per trade 
    
   ![DISNEY Current](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DISCurrentall.PNG)

  You can see again the bollinger signal is weighted the most important. Our sharpie ratio and our sortino ratio are much better in this time period.If we look at the performance values of our algorithm for Current total trade. Our Annual return 0.09 and sharpe Ration .51. Our accurancy is 0.51.

   
   ![DISNEY Current Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DISCurrentPerf.PNG)
  
  **TOTAL SE 2008 Recession**

  According to our algorithm, although we have lost money until September, after that traded with some profits.Looking at the overall graph, As you can see we actually had negative returns over the 2008 recession.

   ![Total 2008](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/TOT2008all.PNG)

  We had an annual return of -11% and cumulative return -12%.The bollinger signal and the volatility trend signal where the most important features that this model.

   ![Total 2008 Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/TOT2008Perf.PNG)
 
  **TOTAL SE Current**

  Current time frame of 2017 till 2021, this stock performed much better, which is what we would have expected. In terms of the weighted net profit and losses of each trade. Overall we did have positive returns with Total SE.

   ![Total Current](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/TOTCurrentall.PNG)

  If we look at the performance values of our algorithm for Current booking trade. Our Annual return 0.09 and sharpe Ration .51. Our accurancy is 0.51.

   ![Total Current Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/TOTCurrentPerf.PNG)

   **APPLE 2008 Recession**
  
  According to our algorithm for apple seem more balanced sometimes we loss money sometimes we made a profit. But totally we made a little profit.

   ![Apple 2008](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/AAPL2008.PNG) 

  If we look at the performance values of our algorithm for 2008 recession Apple trade. Our Annual return 0.02 and sharpe Ration .10. Our accurancy is 0.48.

   ![Apple 2008 Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/AAPL2008Perf.PNG)

  **APPLE Current**

  However, current, it seems to have made good profit.Especially in the last months performance has very good. 

   ![Apple Current](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/AAPLCurrent.PNG)

  If we look at the performance values of our algorithm for Current Apple trade. Our Annual return 0.35 and sharpe Ration 1.2. Our accurancy is 0.54.

   ![Apple Current Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/AAPLCurrentPerf.PNG)


## Resource

https://finance.yahoo.com/

https://stackoverflow.com/
