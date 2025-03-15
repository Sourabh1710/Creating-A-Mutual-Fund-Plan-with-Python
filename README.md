# Creating a Mutual Fund Plan with Python

A mutual fund plan is created by selecting the stocks where an investor can benefit in the long term. Here’s the process I followed to create a mutual fund plan:

## Steps to Create a Mutual Fund Plan

1. **Gather Historical Stock Data**: I collected closing prices and growth trends over time.
2. **Calculate Key Metrics**: I calculated the Return on Investment (ROI) and volatility (risk) to understand how each stock has performed historically.
3. **Select Stocks Based on ROI and Risk**: I chose stocks with a high ROI and low volatility to balance risk and reward.
4. **Calculate Future Value of Investments**: I estimated the future value of monthly investments based on the expected ROI of selected stocks.

---

## Importing Necessary Libraries and Dataset

I started by importing the required Python libraries and the [dataset](https://statso.io/mutual-funds-bucket-case-study/). Then, I converted the date column into a datetime data type:

```python
data['Date'] = pd.to_datetime(data['Date'])
```

Next, I checked for null values in the dataset:

```python
print(data.isnull().sum())
```

### Handling Missing Values

There were 24 null values in the closing prices of HDFC. I filled these null values using the forward fill method:

```python
data.fillna(method='ffill', inplace=True)
```

---

## Stock Price Trends

Below is a visualization of the stock price trends of all companies in the dataset:

![Stock Price Trends](https://github.com/Sourabh1710/Creating-A-Mutual-Fund-Plan-with-Python/blob/main/images/Stock%20Price%20Trends%20of%20All%20Indian%20Companies.png)

---

## Identifying High-Risk Companies

To understand the risk factor, I analyzed companies with the highest volatility:

![High-Risk Companies](https://github.com/Sourabh1710/Creating-A-Mutual-Fund-Plan-with-Python/blob/main/images/Companies%20with%20High%20Risk%20for%20Investing.png)

---

## Identifying High-Growth Companies

Next, I examined companies with the highest growth rates:

![High Growth Companies](https://github.com/Sourabh1710/Creating-A-Mutual-Fund-Plan-with-Python/blob/main/images/Companies%20with%20highest%20growth%20rate%20for%20investing.png)

---

## Identifying Companies with Highest ROI

Finally, I identified companies with the highest return on investments:

![Highest ROI Companies](https://github.com/Sourabh1710/Creating-A-Mutual-Fund-Plan-with-Python/blob/main/images/Companies%20with%20highest%20rate%20of%20ROI.png)

---

## Creating a Mutual Fund Plan Based on High ROI and Low Risk

To create a strategy for selecting companies with high ROI and low risk, I used a combination of ROI and volatility (standard deviation) metrics. The goal was to find companies that offer a high return on investment while minimizing risk.

### Steps:

1. **Define ROI and Volatility Thresholds**: I set thresholds for ROI and volatility to select companies that provide good returns with lower risks.
2. **Rank Companies by ROI and Volatility**: I ranked all companies based on their ROI and volatility scores.
3. **Assign Investment Ratios**: I allocated more investment to companies with higher ROI and lower volatility.

### Selected Companies

The following companies met the criteria of high ROI and low volatility:

- **ICICI Bank** (ROI: 13.48%)
- **IndusInd Bank** (ROI: 7.16%)
- **JSW Steel** (ROI: 7.02%)
- **Axis Bank** (ROI: 6.59%)
- **HDFC Bank** (ROI: 6.32%)
- **Sun Pharma** (ROI: 5.63%)
- **Kotak Bank** (ROI: 5.47%)
- **Cipla** (ROI: 4.85%)
- **NTPC** (ROI: 4.36%)

### Investment Allocation Based on Inverse Volatility

To balance the investment, I used an inverse volatility ratio for allocation. Companies with lower volatility received a higher weight:

| Company      | Investment Ratio |
|-------------|-----------------|
| NTPC        | 28.08%          |
| JSW Steel   | 15.99%          |
| Axis Bank   | 9.22%           |
| HDFC Bank   | 8.93%           |
| Cipla       | 8.48%           |
| Kotak Bank  | 7.66%           |
| IndusInd Bank | 7.44%        |
| Sun Pharma  | 7.26%           |
| ICICI Bank  | 6.93%           |

---

## Analyzing the Mutual Fund Plan

To evaluate my mutual fund plan, I compared it with the high-performing companies in the stock market.

### Risk Comparison

I compared the risks (volatility) of the mutual fund companies versus high-growth companies:

![Risk Comparison](https://github.com/Sourabh1710/Creating-A-Mutual-Fund-Plan-with-Python/blob/main/images/Risk%20Comparison-%20Mutual%20Fund%20vs%20Growth%20Rate%20Companies.png)

### ROI Comparison

Then, I compared the ROI of both groups:

![ROI Comparison](https://github.com/Sourabh1710/Creating-A-Mutual-Fund-Plan-with-Python/blob/main/images/Expected%20ROI%20Comparison%20Mutual%20Fund%20vs%20Growth%20Rate%20Companies.png)

The comparison between the risk (volatility) and expected ROI for mutual fund companies (in blue) and growth rate companies (in green) shows a clear trade-off. Mutual fund companies offer lower volatility, meaning they are less risky, but also provide lower expected returns. In contrast, growth rate companies demonstrate higher volatility, indicating more risk, but they offer much higher potential returns, especially companies like Bajaj Auto and Bajaj Finserv. 

This highlights a common investment dilemma: lower risk comes with a lower reward, while higher risk could yield higher returns. 

For long-term investments, the goal is typically to find companies that offer a balance of stable returns and manageable risk. The companies in my mutual fund exhibit low volatility, meaning they are less risky, and their moderate returns make them solid choices for long-term, stable growth. They are well-suited for conservative investors who want steady returns without significant fluctuations in value.

---

## Calculating Expected Returns

I calculated the expected returns if an investor contributes ₹5000 every month.

### Steps:

1. Assume the investor deposits ₹5000 monthly.
2. Use the expected ROI from mutual fund companies to simulate the growth over time.
3. Compute the compounded value of the investments for each period (1 year, 3 years, 5 years, and 10 years).
4. Visualize the accumulated value over these periods.

![Expected Returns Over Time](https://github.com/Sourabh1710/Creating-A-Mutual-Fund-Plan-with-Python/blob/main/images/Expected%20Value%20of%20Investments%20of%20%E2%82%B9%205000%20Per%20Month%20(Mutual%20Funds).png)

After 1 year, the accumulated value is around ₹62,000, and by 5 years, it grows to over ₹300,000. The long-term benefit is evident, with the investment growing to nearly ₹860,000 over 10 years, which emphasizes the value of consistent investing and compounding over time for long-term investors.

---

## Summary

This project demonstrates how a mutual fund plan is designed by investment companies for long-term investors. Mutual funds pool money from multiple investors to purchase a diversified portfolio of stocks, bonds, and other securities, managed by professional fund managers.

---

## Author
Sourabh Sonker <br>
Data Scientist
