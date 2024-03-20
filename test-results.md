# ExpectedReturns Tests

0: **Pre-req**
[Prosper Loan Analysis](https://github.com/luca-miniati/ProsperLoanAnalysis)

1: **Easy**
Download/install went smoothly

2: **Intermediate**
Time-series-momentum.Rmd: Doesn't build because `ff.dates` does not match index of `data`.

3: **Harder**
Commodities-long-run.Rmd: 

- Analysis:
    - Disclaimer: I'm no finance expert (yet), but I did my best.
    - Macro Indicators
        - The regressions show statistical significance of the macroeconomic states in the
        short-term for an equally-weighted portfolio of commodities. This suggests that changes in
        macroeconomic factors have effects in the short-term, but fade over longer horizons.
        Additionally, since there wasn't statistical significance for the long-short portfolio,
        it's possible that the strategy intentionally adjusts for macroeconomic factors, which
        could explain the low statistical significance.
        - The time-series factor model showed alphas of 0.007% and 0.004% for equally-weighted and
        long-short portfolios. From what I can gather, this is a pretty small alpha, giving a tiny
        edge in the market. Lastly, the residual volatilities are low--about 0.05% for both
        portfolios. Thus, the model has captured most of the variation in asset returns.
    - Investment Styles
        - For the short term (horizon of 0 months), momentum was found to be very statistically
        significant. Momentum was also significant for an 11-month horizon using the long-short
        portfolio. For the other horizons of 11 and 59 months, however, no relationship was found.
        - Value did not show statistical significance for expected returns.
        - Carry showed statistical significance in the long term (horizon of 59 months) for the
        long-short portfolio, but not the equally-weighted portfolio.
- Repetitive code:
    - `lapply(unlist(macro.regs, recursive=FALSE), summary)` was used multiple times to provide
    summary statistics for multivariate regressions.
    - This could be a function called `multivariateRegression` to provide summary stats given the
    dependent/independent variables, horizons, and data.
