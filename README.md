# Vasicek Interest Rate Model

Modeling Mexican interest rates using the Vasicek stochastic process, maximum likelihood estimation, and Monte Carlo simulation.
---

## 🔍 Overview

This project studies the behavior of interest rates through the Vasicek model, a mean-reverting stochastic process widely used in quantitative finance and fixed income modeling.

The model is applied to Mexican CETES data in order to:
- Estimate model parameters.
- Analyze long-term behavior.
- Compare simulated dynamics against observed market data.

This repository was developed as an undergraduate thesis project in Actuarial Science.

---
## 🧮 Methodology

The project begins with the theoretical foundations of stochastic calculus, including Brownian motion and Itô stochastic integrals, which provide the mathematical framework for continuous-time interest rate modeling.

The Vasicek process is defined through the stochastic differential equation:

$dr_t = a(b-r_t)dt+\sigma dB_t$

Where:
* $a$: Speed of mean reversion.
* $b$: Long-term equilibrium level.
* $\sigma$: Volatility parameter.
* $W_t$: Wiener Process 

The explicit solution of the process allows the derivation of its statistical properties, including mean reversion behavior, conditional expectation, variance dynamics, and stationary distribution.

For estimation purposes, the continuous-time model is transformed into its discrete recursive representation:

$r_{t+\Delta}=u+vr_t+\eta_t$

This representation is equivalent to an AR(1) process, allowing parameter estimation through Maximum Likelihood Estimation (MLE) and Ordinary Least Squares (OLS).

After recovering the continuous-time parameters, the model is used to simulate future interest rate trajectories and analyze its ability to represent observed market dynamics.

---

## 📚 Documentation and Implementation

**Theory and Mathematical Development**  
Available in the `thesis` directory.

**Python Implementation and Simulations**  
Available in the `notebooks` directory.


---

## 📈 Results and Model Analysis

### Historical Interest Rates

The historical CETES series exhibits clear changes in volatility across different economic periods, including high-rate environments and more stable low-volatility regimes.

![Historical Rates](figures/historical_rates.png)


### Parameter Estimation

The estimated Vasicek parameters suggest the presence of mean-reverting dynamics in CETES interest rates.

- Mean reversion speed: $\hat{a}=0.3607$
- Long-term equilibrium level: $\hat{b}=0.0587$
- Volatility parameter: $\hat{\sigma}= 0.0178$

The estimated parameters capture the essential dynamics of 28-day CETES interest rates. The mean reversion speed, ( $\hat{a} = 0.3607$ ), suggests a moderate adjustment toward equilibrium after external shocks. The long-term mean, ( $\hat{b} = 5.87%\$ ), reflects the average interest rate level under stable inflation conditions, while the estimated volatility, ( $\hat{\sigma} = 0.0178$ ), indicates that stochastic fluctuations remain consistent with the model’s long-run mean-reverting behavior.

### Simulated Interest Rate Paths

Using the estimated parameters, multiple stochastic trajectories were simulated under the Vasicek framework.

The simulations reproduce the mean-reverting behavior predicted by the model while illustrating possible future interest rate scenarios.

![Simulation Paths](figures/simulated_paths.png)

The simulations successfully reproduce the general behavior of the observed CETES series, suggesting that the estimated parameters provide an adequate representation of the underlying interest rate dynamics. In particular, a noticeable concentration of trajectories around the interval $(0.05, 0.06)$ can be observed, indicating convergence toward the estimated long-term equilibrium level of the process.


---

## Validation 

**Moment Validation

![Moments Validation](figures/comp.png)
