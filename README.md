# CHALLENGE_5
# Background
You decided to start a FinTech consultancy firm, and you want to make a difference by working on projects with high social impact in local communities. You just won your first contract to help one of the biggest credit unions in your area. They want to create a tool that helps their members enhance their financial health. The Chief Technology Officer (CTO) of the credit union asked you to develop a prototype application to demo in the next credit union assembly.
The credit union board wants to allow the union's members to assess their monthly personal finances, and also be able to forecast a reasonably good retirement plan based on cryptocurrencies, stocks, and bonds.
In this homework activity, you will use all the skills you have learned until now - focusing on using APIs as part of the technical solution - to create two financial analysis tools.
The first will be a personal finance planner that will allow users to visualize their savings composed by investments in shares and cryptocurrencies to assess if they have enough money as an emergency fund.
The second tool will be a retirement planning tool that will use the Alpaca API to fetch historical closing prices for a retirement portfolio composed of stocks and bonds, then run Monte Carlo simulations to project the portfolio performance at 30 years. You will then use the Monte Carlo data to calculate the expected portfolio returns given a specific initial investment amount.

# Instructions

# Part 1 - Personal Finance Planner
In this section of the challenge, you will create a personal finance planner application. To develop the personal finance planner prototype, you should take into account the following assumptions:
* The average household income for each member of the credit union is $12,000.
* Every union member has a savings portfolio composed of cryptocurrencies, stocks and bonds:
* Assume the following amount of crypto assets: 1.2 BTC and 5.3 ETH.
* Assume the following amount of shares in stocks and bonds: 50 SPY (stocks) and 200 AGG (bonds).
  
## Collect Crypto Prices Using the requests Library
* Create two variables called my_btc and my_eth. Set them equal to 1.2 and 5.3, respectively.
* Use the requests library to fetch the current price in US dollars (USD) of bitcoin (BTC) and ethereum (ETH) using the Alternative Free Crypto API endpoints provided in the starter notebook.
* Parse the API JSON response to select only the crypto prices and store each price in a variable.
Hint: Be aware of the particular identifier for each cryptocurrency in the API JSON response - the bitcoin identifier is 1 whereas ethereum is 1027.
* Compute the portfolio value of cryptocurrencies and print the results.

<img width="626" alt="Screenshot 2024-01-23 at 12 54 12 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/4197b54a-aa59-4098-9f72-8bbaafa73218">


## Collect Investments Data Using Alpaca: SPY (stocks) and AGG (bonds)
Important: Remember to create a .env file in your working directory to store the values of your Alpaca API key and Alpaca secret key.

* Create two variables named my_agg and my_spy and set them equal to 200 and 50, respectively.
* Set the Alpaca API key and secret key variables, then create the Alpaca API object using the tradeapi.REST function from the Alpaca SDK.
* Format the current date as ISO format. You may change the date set in the starter code to the current date.
* Get the current closing prices for SPY and AGG using Alpaca's get_bars() function. Transform the function's response to a Pandas DataFrame and preview the data.
* Pick the SPY and AGG close prices from the Alpaca's get_bars() DataFrame response and store them as Python variables. Print the closing values for validation.
* Compute the value in dollars of the current amount of shares and print the results.

<img width="656" alt="Screenshot 2024-01-23 at 1 00 19 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/4ce6dec8-8c25-4dd7-9b40-962e6598b980">

<img width="987" alt="Screenshot 2024-01-23 at 1 00 51 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/49a6e868-77a5-4c6d-b051-55ea1b64e91b">

<img width="664" alt="Screenshot 2024-01-23 at 1 03 01 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/7788ae5e-3e9a-4c4b-b1a7-636f8ddee471">

## Savings Health Analysis
In this section, you will assess the financial health of the credit union's members.
1. Create a variable called monthly_income and set its value to 12000.
2. To analyze savings health, create a DataFrame called df_savings with two rows. Store the total value in dollars of the crypto assets in the first row and the total value of the shares in the second row.
Hint: The df_savings DataFrame should have one column named amount and two rows where crypto and shares are the index values:

<img width="533" alt="Screenshot 2024-01-23 at 1 07 26 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/c0925ef4-38ad-4f3c-bd8e-aa3043129228">


3. Use the df_savings DataFrame to plot a pie chart to visualize the composition of personal savings.
   
<img width="821" alt="Screenshot 2024-01-23 at 1 07 37 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/0cdb9a49-3e3d-4f85-9a2d-b0710442761c">

4. Use if conditional statements to validate if the current savings are enough for an emergency fund. An ideal emergency fund should be equal to three times your monthly income.
* If total savings are greater than the emergency fund, display a message congratulating the person for having enough money in this fund.
* If total savings are equal to the emergency fund, display a message congratulating the person on reaching this financial goal.
* If total savings are less than the emergency fund, display a message showing how many dollars away the person is from reaching the goal.
  
<img width="967" alt="Screenshot 2024-01-23 at 1 07 43 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/858cc2d8-041a-40d2-bb8c-d7152d657c98">

# Part 2 - Retirement Planning
In this section, you will use the Alpaca API to fetch historical closing prices for a retirement portfolio and then Use the MCForecastTools toolkit to create Monte Carlo simulations to project the portfolio performance at 30 years. You will then use the Monte Carlo data to answer questions about the portfolio.
Follow the steps outlined in the starter notebook to complete the following:

## Monte Carlo Simulation
1. Use the Alpaca API to fetch five years historical closing prices for a traditional 40/60 portfolio using the SPY and AGG tickers to represent the 60% stocks (SPY) and 40% bonds (AGG) composition of the portfolio. Make sure to convert the API output to a DataFrame and preview the output.
Note: In Monte-Carlo Simulation, getting data as far back as possible matters, because if we simulate using only small amounts of data during a recent time when markets are booming, or instead falling precipitously, a Monte-Carlo Analysis will inadvertently extrapolate this temporary market movement too far into the future. Getting data over a longer time period mitigates this effect.

<img width="591" alt="Screenshot 2024-01-23 at 1 10 33 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/7f453b30-b492-44d8-bde4-312707b1a767">

<img width="627" alt="Screenshot 2024-01-23 at 1 12 06 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/7710cbde-f5da-4c4c-9c96-fe80a75e74aa">

<img width="516" alt="Screenshot 2024-01-23 at 1 12 12 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/80473fdb-652b-4365-a8e7-ad0359c3b09c">

2. Configure and execute a Monte Carlo Simulation of 500 runs and 30 years for the 40/60 portfolio.
   
<img width="621" alt="Screenshot 2024-01-23 at 1 18 48 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/1b8b8075-ad6e-4b8f-9a59-2303fc7be420">

3. Plot the simulation results and the probability distribution/confidence intervals.
   
<img width="948" alt="Screenshot 2024-01-23 at 1 18 18 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/09b7a506-196a-4cea-b59c-eb482f2ea13d">

<img width="917" alt="Screenshot 2024-01-23 at 1 20 44 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/7104e562-b22e-4965-bea6-46329ac6cf06">


# Retirement Analysis
1. Fetch the summary statistics from the Monte Carlo simulation results.

<img width="527" alt="Screenshot 2024-01-23 at 1 22 13 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/b88dfca0-014b-42f9-bf6c-5d12c8a5f57c">

2. Given an initial investment of $20,000, calculate the expected portfolio return in dollars at the 95% lower and upper confidence intervals.

<img width="990" alt="Screenshot 2024-01-23 at 1 22 43 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/5b39e090-10c7-4521-a421-999f7f123a22">


3. Calculate the expected portfolio return at the 95% lower and upper confidence intervals based on a 50% increase in the initial investment.

<img width="991" alt="Screenshot 2024-01-23 at 1 22 52 PM" src="https://github.com/kimrodriguezFINTECH/CHALLENGE_5/assets/152752672/53730c02-7df4-4734-911d-d206b203a54b">


# Resources 
## In Class Activites 
* https://git.bootcampcontent.com/University-of-California---Berkeley/UCB-VIRT-FIN-PT-12-2023-U-LOLC/-/blob/main/05-APIs/Class_2_Activities/04-Ins_Alpaca_Demo/Solved/alpaca-demo.ipynb?ref_type=heads
* https://git.bootcampcontent.com/University-of-California---Berkeley/UCB-VIRT-FIN-PT-12-2023-U-LOLC/-/blob/main/05-APIs/Class_2_Activities/05-Stu_Investment_Value/Solved/investment-value.ipynb?ref_type=heads

## The documentation for these APIs can be found via the following links:
* Free Crypto API Documentation: https://alternative.me/crypto/api/
* AlpacaDOCS: https://docs.alpaca.markets/docs/getting-started

## Tutors & Peers 
### Tutor Meetings through FINTECH Bootcamp:
* Vijaya
- Tuesday 1/23/2024

### Tutor Meetings External Resources:
* Edward R.
* Website: https://www.edwardrees.info
- Sunday 1/21/2024
 
### Study Partner taking FINTECH Bootcamp (Same Class):
* German Romero
- Helped eachother fix code errors
- Cross Referenced work to help eachother understand why we are using a specific code and understand what the question is asking us for

















