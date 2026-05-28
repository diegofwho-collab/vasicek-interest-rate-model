## Implementation

The Vasicek model was implemented in Python using:
- pandas
- numpy
- matplotlib
- scikit-learn

---

## Data Selection

Although the dataset contains observations since 1986, only data from 2000 onward were considered in the analysis.

Earlier observations were excluded due to periods of hyperinflation and extreme volatility, which would significantly distort the estimation of the long-term mean and volatility parameters.

---

## Model Parameterization

The Vasicek model is originally parameterized by:

- $a$ : mean reversion speed
- $b$ : long-term equilibrium level
- $\sigma$ : volatility

For estimation purposes, auxiliary parameters $u$ and $v$ are introduced:

- $u = f(a,b)$
- $v = g(a)$



