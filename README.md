# Machine Learning Driven Dollar Neutral Equity Strategy With Volatility Targeting and Monte Carlo Significance Testing
<img width="1281" height="56" alt="image" src="https://github.com/user-attachments/assets/8a31be87-8b83-4674-bd6d-99c9f30edabb" />


Overview

This project develops and rigorously validates a cross sectional dollar neutral long short equity strategy using machine learning.

Rather than predicting exact stock returns, the framework focuses on ranking stocks by expected excess return. Portfolio performance is driven by relative ordering, not point forecasts.

The objective is to evaluate whether nonlinear machine learning can generate robust cross sectional alpha under realistic backtesting constraints.

Research Design
Rolling Out of Sample Framework

All performance is generated using strict rolling out of sample validation.

Fixed train, validation, and test windows

Chronological retraining

No look ahead bias

Reduced overfitting risk

Every return in the backtest is produced by a model that had not seen that month’s data during training.

Portfolio Construction

Each month:

Rank stocks by predicted excess return

Long top 10 percent

Short bottom 10 percent

Equal weight within each leg

Enforce dollar neutrality

Monthly portfolio return is defined as the return on the long leg minus the return on the short leg.

This isolates cross sectional ranking skill rather than exposure to market direction.

Volatility Targeting

To address time varying risk, the strategy applies portfolio level volatility targeting.

Trailing rolling volatility estimate

One month lag to avoid look ahead bias

Scaling to a constant annualized volatility target

Leverage cap to control risk

This ensures risk comparability across market regimes.

Signal Evaluation Framework

The strategy is evaluated using multiple cross sectional diagnostics:

Decile monotonicity testing

Information Coefficient analysis

Rolling Sharpe stability

Drawdown behavior

Out of sample R squared interpretation

Low out of sample R squared is expected in asset pricing contexts, as the objective is ranking accuracy rather than point return prediction.

Robustness Testing

A Monte Carlo based simulation framework is implemented to test whether observed performance characteristics could arise by chance.

Randomized return path simulations

Empirical null distribution construction

Tail probability evaluation

This provides a statistical robustness layer beyond traditional backtesting.

Key Contributions

End to end ML driven equity research pipeline

Strict out of sample validation design

Cross sectional portfolio construction framework

Risk controlled implementation via volatility targeting

Statistical robustness testing through Monte Carlo simulation

This repository demonstrates a structured approach to evaluating machine learning based equity strategies under realistic empirical constraints.
