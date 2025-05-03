# PORTFOLIO OPTIMIZATION FOR WEALT MANAEMENT FIRMS
## Project Overview

Wealth management firms play a critical role in growing client wealth while carefully managing market risk. However, many firms still rely on traditional portfolio construction methods—often static and rigid—which results in missed opportunities and increased volatility during market shifts.

This project introduces a data-driven portfolio optimization model using Modern Portfolio Theory (MPT) to help wealth managers maximize returns for a given level of risk or minimize risk for a desired return. The goal is to create personalized, adaptable portfolios that outperform naive strategies.


## Problem Statement

Static portfolio strategies do not account for market volatility or changing correlations between assets. As a result:

- Portfolios may be overexposed to risk
- Returns may be inconsistent with market behavior
- Client dissatisfaction may increase due to underperformance


## Proposed Solution

The solution leverages Modern Portfolio Theory (MPT) and a simulation-based optimization approach to identify optimal asset weightings that offer the best risk-adjusted return (Minimize Risk), measured using the Sharpe Ratio(to maximize returns with minimal risk).

We do this by:

- Collecting historical data for multiple stocks
- Calculating individual and portfolio returns and volatilities
- Simulating thousands of random portfolios to explore the feasible space
- Identifying the optimal portfolio from the simulation

This approach allows wealth managers to construct customized investment portfolios based on risk appetite and market conditions.


## Tools & Libraries Used

### 1. Pandas & NumPy

These core data manipulation libraries were used for:

- Importing and cleaning the financial data
- Computing daily returns, portfolio metrics, and statistical summaries

### 2. Matplotlib & Seaborn

Used to visualize:

- The spread of portfolio simulations (risk vs. return)
- Optimal portfolio highlighting
- Asset allocation via bar charts

### 3. yfinance

The Yahoo Finance API was used to fetch historical stock prices for:

- Apple (AAPL), Microsoft (MSFT), Google (GOOGL), Amazon (AMZN), Tesla (TSLA)
- Covering the time period from 2018 to 2024


## Methodology

### Step 1: Data Collection

We use `yfinance` to download historical daily closing prices of selected stocks. We work specifically with the 'Close' price as it reflects the most common trading metric for investors.

### Step 2: Data Cleaning & Return Calculation

- Extract the 'Close' price from the multi-indexed DataFrame
- Calculate daily returns using the formula:
  \(R_t = \frac{P_t - P_{t-1}}{P_{t-1}}\)

Note: All calculations using formula were computed using Python libraries NumPy and Pandas, but the underlying functionality are mathematical & statistical formulas which are shown in this documentation for the sake of clarity for those who may not understand the code

### Step 3: Portfolio Simulation with Random Weights

Before finding the optimal portfolio, we simulate thousands of random portfolios. This is crucial because:

- It allows us to visualize the Efficient Frontier
- We explore a wide range of combinations to avoid local optima
- We better understand the trade-off between risk and return

Each simulated portfolio has:

- Random asset weightings summing to 1 (all individual weights must be between 0 and 0.9, and total sum of all weights must sum up to 1)
- Computed expected return (weighted sum of individual returns)
- Computed volatility using the covariance matrix of returns
- Sharpe Ratio: \(SR = \frac{R_p - R_f}{\sigma_p}\) (assuming risk-free rate R\_f = 0)

### Step 4: Finding the Optimal Portfolio

After the simulation:

- Identify the portfolio with the highest Sharpe Ratio
- Extract and visualize the asset allocation and performance metrics


## Results & Visualization

- Over **10,000 random portfolios** were simulated
- The optimal portfolio showed:
  - Improved Sharpe Ratio
  - Balanced risk-return profile
  - Diversified weights across assets

### Example Output

- Sharpe Ratio: 1.23
- Expected Annual Return: 18.4%
- Annual Volatility: 12.3%

Visualizations included:

- Risk vs Return scatter plot
- Optimal portfolio highlight
- Bar chart of optimal asset weights


## Business Value

### Key Outcomes

- Better risk-adjusted returns using Sharpe Ratio maximization
- Personalized portfolio strategies for each investor profile
- Improved adaptability to changing market dynamics

### Business Impact

- Enhanced client satisfaction & retention
- Competitive edge through smarter portfolio engineering
- Lowered legal risk due to data-backed decisions


## How to Run

```bash
git clone https://github.com/blaqjacquez/Data-Science-Portfolio/portfolio-optimization.git
cd portfolio-optimization

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook "Portfolio Optimization Model.ipynb"



## Author

Michael Otu
Data Scientist | Finance & AI Enthusiast
[LinkedIn](https://www.linkedin.com/in/michaelotu/) | [Email](mcotu08@gmail.com)

