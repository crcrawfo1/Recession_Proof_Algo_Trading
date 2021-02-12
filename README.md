# The Impact of the 2008 Recession and the COVID Recession on Five Industries
### Coded by CONNOR CRAWFORD, HENNA SINGH, MEAGAN RATHJEN, JOHN GASCHLER, OGUZHAN ACIL

## How the code works:
The only code you will have to run in order to produce our dashboard is the jupyter notebook called 'Plots'. This file draws on CSV's that were created by our two DataCleaner files. If you care to see how the CSV's were created, feel free to peruse those notebooks. The weight optimization notebook details how we were able to decide on the optimal weights for each portfolio in each time period. You can see code that we had originally used but became redundant in our 'Old' subfolder within the 'notebooks' folder. The 'Data' folder contains the csvs that the DataCleaner notebooks produced. The Photos folder contains pngs of the plots contained within the dashboard.

# The Project Itself:

## Project Proposal
Given the tumultuous economic year we are closing out, we took a closer look at recessions to see how different industries and portfolios of stocks performed throughout these recessions. We compared 5 different portfolios of stocks comprised from 5 different industry verticals to see how they were impacted in both the 2008 recession and COVID recession. The analysis also included how the individual portfolios could have been weighted to beat the market. 

Our goal was to answer these questions:
Comparing the 2008 recession and the recent COVID recession, how did various portfolios based in 5 different industries perform both prior to and during their respective economic downturns?
How did the industries perform in comparison to the market as a whole both prior to and during the recessions?
What were the optimal portfolio weights prior to each recession to reduce downside risk?
Determine the risk and volatility associated with each industry portfolio and how correlated were the industry portfolios to the S&P 500?

Date Ranges for Data Pulls:
- Prior to 2008 (7/1/2005-7/1/2007)
- During 2008 Recession (7/1/2007-7/1/2009)
- Prior to COVID (11/1/2017-11/1/2019)
- During COVID Recession (11/1/2019-11/1/2020)


Industry Portfolios:
- Entertainment: Imax Corporation, Disney, Netflix, Comcast, Sony
- Fast Food: McDonald’s, Wendy’s, Yum! Brands Inc., Domino’s Pizza, Jack in the Box Inc.
- Tech: Amazon, Apple, Microsoft, Google, Intel Corp.
- Travel/Transportation: Expedia Inc, Booking, American Airlines, Delta Airlines, SouthWest Airlines
- Energy: Exxon Mobil, BP, ConocoPhillips, Chevron, Total SE


## Finding Data & Data Cleanup & Analysis
Data was originally pulled using Alpaca, however, we found out that Alpaca's data only goes back as far as January 1st, 2008. We then pivoted to use Yahoo Finance via Pandas DataReader to pull the adjusted close data.
In order to better understand the impact of the 2008 recession and the COVID recession on the industries, we calculated Sharpe Ratios, Correlations, Rolling Averages, Variance, Covariance, and Beta for the four date ranges previously specified.

Findings about our studies are as follows.

![Dashboard](https://github.com/crcrawfo1/Project1/blob/main/Photos/dashboardgif.gif)


 - **Expected Returns**

    Prior 2008: Travel/Airlines is the most volatile, offered the highest expected return but also had the most downside risk. Entertainment also had some downside risk in this period, but without as much upside. Everything else is relatively similar in terms of standard deviation and correlation to S&P 500. 

    ![ER PRIOR 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/returns/returns_before_2008.PNG)

    During 2008 Recession: Travel/Airlines was once again the most volatile and had the highest gains. Every other sector moved in correlation with the S&P 500.

    ![ER During 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/returns/returns_during_2008.PNG)
   
    Prior COVID: There was not as much volatility compared to 2008. Fast Food had the highest upside data point in early 2019. Tech (along with the entire market) fluctuated up and down quite a bit at the end of 2018. 

    ![ER PRIOR COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/returns/returns_before_covid.PNG)

    During COVID: Every industry experienced drastic market fluctuations in March through May of 2020. Energy and Fast Food had the highest volatility on both ends of the spectrum. Surprisingly, Tech was not volatile at all during this timeframe relative to the S&P and other industries.

    ![ER During COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/returns/returns_during_covid.PNG)
    


 - **Annual Risk Findings**
 
    Prior 2008: Transportation had the highest risk, while Entertainment had the lowest risk of industry specific portfolios. The S&P 500 had lower risk than all portfolios.

    ![AR PRIOR 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/annual_risk/annual_risk_before_2008.PNG)

    During 2008: Transportation still had the highest risk however every other industry became more risky. Fast Food actually had less risk than the S&P. 
    
    ![AR During 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/annual_risk/annual_risk_during_2008.PNG)
    
    Prior COVID: Transportation had the highest risk followed closely by Energy and Tech. The S&P was the lowest risk. 

    ![AR PRIOR COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/annual_risk/annual_risk_before_covid.PNG)
    
    During COVID: Unsurprisingly, Energy, Transportation, Tech and Fast Food  had the four highest risk factors as people dealt with the lockdowns by not traveling or going outside which led to little demand for these services. Surprisingly, Entertainment had lower annual risk than the S&P 500 for this period. 

    ![AR During COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/annual_risk/annual_risk_during_covid.PNG)



-  **21 Day Rolling Risk Analysis**

    Prior 2008: Tech and Transportation had higher risk fluctuations and did not move in a correlated manner with the S&P 500. The rest of the industries did move with the market as a whole. 

    ![RR PRIOR 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/21_day_rolling_risk/21_day_rolling_risk_pre_2008.PNG)

    During 2008: During the actual crash in 2008 between 9/2008 and 1/2009, all of the industries mirrored the movements of the S&P 500.

    ![RR During 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/21_day_rolling_risk/21_day_rolling_risk_during_2008.PNG)

    Prior COVID: Leading up to COVID, these industries were not always moving in synch with the S&P 500 except for ~Q4 of 2018 and the beginning of Q1 2019. 

    ![RR PRIOR COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/21_day_rolling_risk/21_day_rolling_risk_pre_covid.PNG)

    During COVID: Energy had higher fluctuations in risk and other industries measured moved in a nearly identical pattern to the S&P 500.

    ![RR During COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/21_day_rolling_risk/21_day_rolling_risk_during_covid.PNG)


- **Sharpe Ratios**

    Prior 2008: Transportation had the highest Sharpe Ratio (2.04). The lowest by far was Energy (1.261) excluding the S&P 500. 

    ![SR PRIOR 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/sharpe_ratios/sharpe_ratios_pre_2008.PNG)
    
    During 2008: The S&P 500 fell to a Sharpe Ratio of -0.532 during this period. The Energy portfolio was also slightly negative. Interestingly enough, the Entertainment portfolio which had the lowest Sharpe Ratio leading up to the 2008 recession, had the highest ratio during the recession of 0.264.

    ![SR During 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/sharpe_ratios/sharpe_ratios_during_2008.PNG)
    
    Prior COVID: Tech had the highest Sharpe Ratio at 1.289 while the S&P 500 sat in the middle with a 0.656 ratio. The Energy portfolio was the lowest at 0.375. 

    ![SR PRIOR COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/sharpe_ratios/sharpe_ratios_pre_covid.PNG)
    
    During COVID: The Energy portfolio (-0.623) and the Transportation portfolio were the only negative Sharpe Ratios. The Tech portfolio had the highest ratio of 1.2. Entertainment was the second highest at 0.5. 

    ![SR During COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/sharpe_ratios/sharpe_ratios_during_covid.PNG)



- **Correlation**

    Prior 2008: Limited correlation between the portfolios, no correlation was higher than 0.447. Specifically in regards the correlation with the S&P 500, Entertainment had the highest correlation at 0.823. 

    ![Cor PRIOR 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/correlations/corr_pre_2008.PNG)

    During 2008: Strong correlations are more abundant in this time period. Energy and the S&P 500 had a 0.975 correlation. Energy and Entertainment as well as Energy and the S&P 500 both had correlations of ~0.95 as well. 

    ![Cor During 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/correlations/corr_during_2008.PNG)

    Prior COVID: Entertainment and Tech had the highest correlation to the S&P 500 in this period. Both portfolios also had the highest correlations with the other portfolios as well. 

    ![Cor PRIOR COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/correlations/corr_pre_covid.PNG)

    During COVID: The S&P 500 was positively correlated with each portfolio at a minimum of 0.951 (Transportation) and at a maximum of 0.983 (Entertainment). 
    
    ![Cor During COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/correlations/corr_during_covid.PNG)


- **Beta**

    Prior 2008: Not a surprise given the previous remarks on risk, but Tech had by far the highest Beta in this timeframe. Its highest point registered at ~2.29 and had a median Beta of 1.45. The remaining 4 portfolios all had similar median Beta’s ranging between 0.95 (Fast Food) and 1.22 (Transportation). This period had the widest range of Betas out of the four timeframes we analyzed.  

    ![B PRIOR 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/beta_variability/variability_beta_pre_2008.PNG) 

    During 2008: Betas are more scattered during than before the 2008 recession, but still relatively in line with each other. Tech and Transportation had the highest two median Betas (1.02 and 1.26 respectively). Fast Food had the lowest median Beta at 0.784.

    ![B During 2008](https://github.com/crcrawfo1/Project1/blob/main/Photos/beta_variability/variability_beta_during_2008.PNG) 

    Prior COVID: Betas are even more spread apart than during the 2008 recession. A consistent theme with this time frame continues with Tech and Energy having the two highest median Betas at 1.42 and 1.02, respectively. 

    ![B PRIOR COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/beta_variability/variability_beta_pre_covid.PNG)

    During COVID: Betas are less spread out (not surprising if the entire market decreases rather than only a few sectors). Seeing as the Energy portfolio was the most volatile from a returns perspective, it isn’t surprising that Energy had the highest median Beta of 1.388.

    ![B During COVID](https://github.com/crcrawfo1/Project1/blob/main/Photos/beta_variability/variability_beta_during_covid.PNG) 


## Result

- Our findings were generally in line with expectations as to how each industry performed throughout each recession. 
- The gains and losses in 2008 were much greater than in COVID. Both recessions caused a good degree of volatility. 
- S&P 500 generally performs in a less volatile and risky manner compared to individual market sectors

## Resource

https://finance.yahoo.com/

https://stackoverflow.com/
