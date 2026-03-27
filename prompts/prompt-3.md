# Prompt 3

**Category:** Debugging & Meta-Programming

**Sub-category:** Language-diverse debugging
**Language:** Python

**Repo:** https://github.com/freqtrade/freqtrade

**Prompt:**

We have 15+ signal strategies and a backtester, but regressions are mostly caught by full backtests and eyeballing. Our core issue is that the backtest are normally fine but the bugs should up in a live trading environment. 

I want a concrete backtesting strategy that is comporable to a live trading environment. I would like the following to be achieved. 

- Backtesting that is identical to a live trading environment, like a testnet that uses real transactions. 
- Something more pro-active when live trading to catch bugs as they happen.
- Compatable with Python environments and libraries. 
- Professional-tier debugging, setup, and architecture 