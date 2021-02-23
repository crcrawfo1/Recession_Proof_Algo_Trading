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
* Reasoning: The reason we chose to use Random Forest is because it is a strong classification modeler.  Our intention was to train the model to generate indicators to buy and sell based on several features that will be discussed later. Since this is a long only model, entry and exit times are especially critical. In our backtesting, we were able to further mitigate any potential losses by implementing a self-designed stop loss.
* Exploration & Cleanup was fairly straightforward because our team recycled the code we used for Project 1 which allowed us to focus most of our efforts on the model and its attributes. 
* Problems with Training the Model: Getting the stop loss to work correctly, adding features that improved the model, and the buy/sell indicator would occasionally be flipped in the visualization
* Overall Training Process: The model takes into account the returns, volatility, and the trend in volume (similar to simple moving average, but focused on volume rather than price) to anticipate buy/sell behavior. The most time-consuming part of the model was the data cleanup prior to the model training; the model training was fairly straightforward.  


## Findings and PostMortem Analysis

- Our findings were generally in line with expectations as to how each industry performed throughout each recession. 
- The gains and losses in 2008 were much greater than in COVID. Both recessions caused a good degree of volatility. 
- S&P 500 generally performs in a less volatile and risky manner compared to individual market sectors

 Some of our findings are as follows

 ![DISNEY 2008](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/OVERALL.PNG)
 

  **DISNEY 2008 Recession**

 According to our algorithm for disney has more trade in profit. Especially in the first and last months. 

   ![DISNEY 2008](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DIS2008all.PNG)

 If we look at the performance values of our algorithm for 2008 recession Disney trade. Our Annual return 0.11 and sharpe Ration 0.47. Our accurancy is 0.48

   ![DISNEY 2008 Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DIS2008Perf.PNG)

  **DISNEY Current**

 Our current trades are much more successful and positive and have made very good profits.
    
   ![DISNEY Current](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DISCurrentall.PNG)

 If we look at the performance values of our algorithm for Current Disney trade. Our Annual return 0.19 and sharpe Ration 1.47. Our accurancy is 0.52
   
   ![DISNEY Current Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/DISCurrentPerf.PNG)
  
  **TOTAL 2008 Recession**

 According to our algorithm, although we have lost money until September, after that traded with some profits.Looking at the overall graph, our algorithm seems to have made losses for 2008 recession.

   ![Total 2008](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/TOT2008all.PNG)

 If we look at the performance values of our algorithm for 2008 recession Total trade. Our Annual return -0.11 and sharpe Ration 0.69. Our accurancy is 0.47.

   ![Total 2008 Perf](https://github.com/crcrawfo1/Project2/blob/main/Photos/Project2/TOT2008Perf.PNG)
 
  **Total Current**

 For the Current Total trade performance seems to have made good profits.Although some of our trading transactions seem to have lost money, we have positive gains in total, as there are more transactions with large profits.

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
