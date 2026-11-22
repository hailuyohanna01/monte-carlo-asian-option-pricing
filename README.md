# Monte Carlo Asian Option Pricing
## Project Overview

This project implements a Monte Carlo simulation framework to estimate the theoretical value of arithmetic-average Asian call options using Geometric Brownian Motion (GBM).

The project investigates how market volatility, strike prices, and simulation size influence theoretical option valuation and numerical uncertainty.

## Technologies

- Python
- NumPy
- pandas
- Matplotlib
- SciPy
- Google Colab

## Methodology

1. Simulate stock-price paths using the exact discrete-time solution of GBM.
2. Calculate the arithmetic average stock price along each simulated path.
3. Calculate the Asian call payoff as the maximum of the average stock price minus the strike price and zero.
4. Discount simulated payoffs using the risk-free interest rate.
5. Average discounted payoffs to estimate the theoretical option premium.
6. Calculate Monte Carlo standard errors and approximate 95% confidence intervals.

## Baseline Parameters

| Parameter | Value |
|---|---|
| Initial stock price | $500 |
| Strike price | $510 |
| Annual volatility | 15% |
| Risk-free rate | 3.83% |
| Time to maturity | 1 year |
| Trading-day steps | 252 |
| Monte Carlo simulations | 10,000 |

The arithmetic average includes the initial stock price and 252 simulated daily observations.

## Key Results

**Baseline option valuation**

- Estimated premium: $16.99
- Standard error: $0.2665
- Approximate 95% confidence interval: $16.46–$17.51
- Simulated zero-payoff frequency: 52.25%

**Volatility sensitivity**

Increasing annual volatility from 10% to 30% increased the estimated option premium from $11.28 to $34.11, an increase of approximately 202.5%.

**Strike-price sensitivity**

Increasing the strike price from $490 to $550 reduced the estimated option premium from $27.89 to $4.86.

## Model Validation

The model was evaluated using:

- Zero-volatility deterministic benchmark
- Positive-payoff deterministic benchmark
- Nonnegative option-value test
- Strike-price monotonicity test

All four validation checks passed.

## Limitations

The model assumes constant volatility and interest rates, zero dividend yield, and GBM stock-price dynamics. Results are theoretical risk-neutral estimates rather than predictions of realized market option prices.

The confidence intervals quantify Monte Carlo sampling uncertainty and do not account for model misspecification or parameter-estimation uncertainty.

## Future Improvements

- Calibrate volatility using historical market data
- Compare Asian option values with European option values
- Implement variance-reduction techniques
- Evaluate additional payoff structures and averaging conventions
- Add an interactive pricing dashboard

## Conclusion

This project demonstrates the application of stochastic simulation, numerical analysis, derivatives valuation, and financial risk modeling to the pricing of path-dependent options.
