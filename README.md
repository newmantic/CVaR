# CVaR

Conditional Value at Risk (CVaR), also known as Expected Shortfall (ES), is a risk measure used in finance to assess the potential loss in a portfolio under extreme market conditions. Unlike Value at Risk (VaR), which only provides a threshold for the worst expected loss at a certain confidence level, CVaR gives the expected average loss given that this threshold has been exceeded.


Value at Risk (VaR): Value at Risk is defined as the threshold loss level such that the probability of experiencing a loss greater than this level is equal to a specified confidence level.
VaR_alpha = -inf { L : P(L <= VaR_alpha) = alpha }
Where:
VaR_alpha is the Value at Risk at confidence level alpha.
L represents the potential losses in the portfolio.
P(L <= VaR_alpha) is the probability that the loss L does not exceed VaR_alpha.
alpha is the confidence level (e.g., 0.95 for 95% confidence).

Conditional Value at Risk (CVaR): CVaR is the expected loss given that the loss exceeds the VaR threshold. It provides a measure of the tail risk of the loss distribution.
CVaR_alpha = E[L | L >= VaR_alpha]
Where:
CVaR_alpha is the Conditional Value at Risk at confidence level alpha.
E[L | L >= VaR_alpha] represents the expected value of losses L given that they exceed VaR_alpha.


Risk Threshold (VaR): VaR provides a cut-off point for losses at a certain confidence level. For example, if the VaR at the 95% confidence level is $1 million, this means that there is a 95% probability that the loss will not exceed $1 million.

Beyond the Threshold (CVaR): CVaR takes the analysis further by calculating the average loss in the worst 1-alpha percent of cases. Continuing with the above example, CVaR would tell us the average loss expected if the loss does exceed $1 million.

Mathematical Interpretation: To calculate CVaR, we first calculate VaR, and then compute the expected loss over all scenarios where the loss exceeds this VaR.

Mathematically, CVaR is expressed as:
CVaR_alpha = (1 / (1 - alpha)) * integral_{alpha}^{1} F_L^{-1}(u) du
Where:
F_L^{-1}(u) is the inverse of the cumulative distribution function of the losses.
The integral calculates the average over the tail of the loss distribution, which corresponds to the worst-case scenarios.


CVaR is used by financial institutions to manage and limit the potential losses in their portfolios, especially under extreme market conditions. In portfolio optimization, CVaR can be minimized to achieve a portfolio that has a lower risk of extreme losses compared to one optimized based on VaR alone. CVaR is useful in stress testing scenarios to understand the impact of rare but significant adverse market movements on a portfolio.
