# Recession Proofing an AlgoTrading Model
### Coded by CONNOR CRAWFORD, HENNA SINGH, MEAGAN RATHJEN, JOHN GASCHLER, OGUZHAN ACIL, FRANCIOS M BYRCH, MAURICIO RODRIGUEZ ALAS

## How the code works:
UPDATE 

# The Project Itself:

## Project Proposal
Similar to Project 1, our team wanted to expand on the idea of making portfolios recession proof - so we decided to build an AlgoTrader that would learn based on the 2008 Recession, and apply that trading model to the most recent COVID Recession to see if the Algorithmic Trading Model could outperform what normal human beings would’ve done, especially during periods of high economic volatility. 

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


## Findings and PostMortem Analysis

- Our findings were generally in line with expectations as to how each industry performed throughout each recession. 
- The gains and losses in 2008 were much greater than in COVID. Both recessions caused a good degree of volatility. 
- S&P 500 generally performs in a less volatile and risky manner compared to individual market sectors

## Resource

https://finance.yahoo.com/

https://stackoverflow.com/
