# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:** The model takes in historical stock price data, including daily prices, opening prices, high prices, low prices, trading volumes, and percentage changes. Additionally, it requires data on the FTSE 100 index and the United Kingdom 3-month and 6-month bond yields, which serve as proxies for the market and risk-free rate, respectively. 

**Output:** The model outputs an efficient frontier, which is a set of optimal portfolios offering the highest expected return for a given level of risk. It also provides the optimal asset allocation weights for each portfolio on the efficient frontier, as well as the portfolio with the maximum Sharpe ratio.

**Model Architecture:** The model follows the principles of Modern Portfolio Theory (MPT) and the Markowitz model. It calculates the expected returns, volatilities, and covariances of the stocks based on historical data. These values are then used to formulate and solve the Markowitz optimization problem, which aims to minimize portfolio variance subject to budget, non-negativity, and return constraints. The optimization problem is solved using the Sequential Least Squares Programming (SLSQP) method from the SciPy library.

## Performance

The performance of the model is evaluated through backtesting on historical data. The notebook provides visualizations of the efficient frontier and compares the performance of various portfolios, including the optimal portfolio (maximum Sharpe ratio), equal-weighted portfolio, and the FTSE 100 index. The performance metrics include annualized returns, annualized volatility, Sharpe ratios, and maximum drawdowns. 
The notebook analyzes data from April 2021 to May 2024, which may not be representative of future market conditions.

## Limitations

1. Data Quality: The model's performance heavily relies on the quality and accuracy of the historical data used. Any errors or anomalies in the data can lead to inaccurate calculations and suboptimal portfolio allocations.
2. Assumptions: The model makes several assumptions, such as the normality of returns, constant volatility, and the absence of transaction costs and taxes. These assumptions may not hold true in real-world scenarios, potentially affecting the model's performance.
3. Static Asset Universe: The model considers a fixed set of assets (stocks) and does not account for the possibility of adding or removing assets from the portfolio over time.
4. Parameter Estimation: The model uses historical data to estimate expected returns, volatilities, and covariances. These estimates may not accurately reflect future market conditions, leading to suboptimal portfolio allocations.
5. Computational Complexity: As the number of assets increases, the computational complexity of the optimization problem grows significantly, potentially making the model impractical for large asset universes.

## Trade-offs

1. Risk-Return Trade-off: The model aims to find the optimal balance between risk (volatility) and expected return. However, portfolios with higher expected returns generally carry higher risk, and vice versa. Investors must carefully consider their risk tolerance and investment objectives when selecting a portfolio from the efficient frontier.
2. Diversification vs. Concentration: The model may suggest highly concentrated portfolios for certain target returns, especially at the higher end of the efficient frontier. While these portfolios may offer higher expected returns, they also come with increased risk due to lack of diversification.
3. Model Complexity vs. Interpretability: While more complex models may potentially improve performance, they can become less interpretable and harder to explain to stakeholders or decision-makers.
4. Data Frequency: The model uses weekly stock return data, which may not capture intra-week volatility or other high-frequency market dynamics. Using higher-frequency data (e.g., daily) could potentially improve the model's performance but at the cost of increased computational complexity.
