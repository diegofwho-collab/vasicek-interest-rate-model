# Vasicek Interest Rate Model

Modeling Mexican interest rates using the Vasicek stochastic process, maximum likelihood estimation, and Monte Carlo simulation.
---

## Overview

This project studies the behavior of interest rates through the Vasicek model, a mean-reverting stochastic process widely used in quantitative finance and fixed income modeling.

The model is applied to Mexican CETES data in order to:
- estimate model parameters,
- simulate future interest rate paths,
- analyze long-term behavior,
- and compare simulated dynamics against observed market data.

This repository was developed as an undergraduate thesis project in Actuarial Science.

## Vasicek Model

The short-term interest rate dynamics are modeled through the stochastic differential equation:

$$dr_t = a(b - r_t)dt + \sigma dW_t$$

Donde:
* $a$: Speed of mean reversion.
* $b$: Long-term equilibrium level.
* $\sigma$: Volatility parameter.
* $W_t$: Wiener Process 

The model assumes that interest rates fluctuate randomly while tending to revert toward a long-run average level.
