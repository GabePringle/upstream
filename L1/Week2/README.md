# Week 2 Assignment - Traders@SMU Alpha Program

## Overview

This directory contains materials for Level 1, Week 2 of the Alpha Program.

## Learning Objectives

- Understand basic financial markets concepts
- Learn Python fundamentals for financial analysis
- Explore data sources and basic data manipulation

## Assignment Instructions

Complete the following tasks:

q1: stock_prices = [100.5, 102.3, 99.8, 103.7, 101.2]
daily_returns = []
for i in range(1, len(stock_prices)):
    daily_return = (stock_prices[i] - stock_prices[i-1]) / stock_prices[i-1]
    daily_returns.append(daily_return)
print(daily_returns)

q2: stock_prices = [100.5, 102.3, 99.8, 103.7, 101.2]
price_checks = []
for i in range(1, len(stock_prices)):
    price_checks.append(stock_prices[i] > 101.50)
print(price_checks)

q3: stock_prices = [100.5, 102.3, 99.8, 103.7, 101.2]
signals = []
for i in range(1, len(stock_prices)):
    daily_return = (stock_prices[i] - stock_prices[i - 1]) / stock_prices[i - 1]
    if daily_return > 0.02:
        signals.append("Buy")
    elif daily_return < -0.02:
        signals.append("Sell")
        print(signals)
        break
    else:
        signals.append("Hold")
else:
    print(signals)

    q4: stock_prices = [100.5, 102.3, 99.8, 103.7, 101.2]
def trading_strat(stock_prices):
    last_price = stock_prices[-1]
    daily_return = (stock_prices[-1] - stock_prices[-2]) / stock_prices[-2]
    short_avg = sum(stock_prices[-3:]) / 3
    signals = {
            "Last Price": last_price, 
            "Daily Return": daily_return, 
            "3-Day Average": short_avg
    }
    if last_price > 101 and daily_return > 0:
        signals["Recommendation"] = "Buy"
    elif short_avg < 100:
        signals["Recommendation"] = "Sell"
    else:
        signals["Recommendation"] = "Hold"

    return signals
print(trading_strat(stock_prices))

class MomentumStrategy:
    def __init__(self, stock_prices):
        self.stock_prices = stock_prices
        self.cash = 10000.0
        self.shares = 0
        self.signals = []
        self.trades = []

def run(self):
        for i in range(1, len(self.stock_prices)):
            daily_return = (self.stock_prices[i] - self.stock_prices[i - 1]) / self.stock_prices[i - 1]
            if daily_return >= 0.02:
                self.signals.append("Buy")
            elif daily_return <= -0.02:
                self.signals.append("Sell")
            else:
                self.signals.append("Hold")

            for i, signal in enumerate(self.signals):
            price = self.stock_prices[i + 1]
            if signal == "Buy":
                cost = 10 * price
                if cost <= self.cash:
                    self.cash -= cost
                    self.shares += 10
                    self.trades.append((price, "Buy", 10))
            elif signal == "Sell":
                if self.shares > 0:
                    proceeds = self.shares * price
                    self.cash += proceeds
                    self.trades.append((price, "Sell", self.shares))
                    self.shares = 0

        def summary(self):
        print("Momentum Strategy Summary:")
        
        signals_str = '[' + ','.join(f"'{s}'" for s in self.signals) + ']'
        print(f"Signals: {signals_str}")
        
        print(f"Trades: {self.trades}")

        print(f"Final Cash: {self.cash:.1f}")
        print(f"Shares Owned: {self.shares}")
        total_value = self.cash + self.shares * self.stock_prices[-1]
        print(f"Total Portfolio Value: ${total_value:.1f}")


if __name__ == "__main__":
    prices = [100.5, 102.3, 99.8, 103.7, 101.2]
    strategy = MomentumStrategy(prices)
    strategy.run()
    strategy.summary()



## Submission Guidelines

- Complete all tasks in this directory
- Submit your work by creating a pull request with branch name `L1-W2-submission`
- Deadline: [Date]

## Resources

- [Resource 1]
- [Resource 2]
- [Resource 3] 
