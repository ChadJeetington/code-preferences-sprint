# Prompt 2

**Category:** Debugging & Meta-Programming

**Sub-category:** Language-diverse Debugging > Python/JavaScript: Performance Bottlenecks

**Language:** JavaScript / Python

**Repo:** https://github.com/ccxt/ccxt

**Prompt:**

We run a multi-exchange stack on top of ccxt and latency has gotten bad enough to matter on shorter timeframes. The rate limiter is the main suspect. During volatility it feels like it’s serializing us into throttling exactly when we need throughput. My guess is it’s treating global and per-endpoint limits the same. I’d rather confirm it in the code than just assume.

There’s also something weird with the WebSocket order-book feeds where we see what looks like backpressure even when the consumer should be keeping up. I want to understand where time is actually going on the order placement path and where the potential bottle necks are. Is sub-100ms on REST even realistic with our current architecture? If not, show me the ideal architecture.
