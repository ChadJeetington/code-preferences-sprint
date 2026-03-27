# Prompt 2

**Category:** Debugging & Meta-Programming

**Sub-category:** Language-diverse Debugging > Python/JavaScript: Performance Bottlenecks

**Language:** JavaScript / Python

**Repo:** https://github.com/ccxt/ccxt

**Prompt:**

We run a multi-exchange stack on top of ccxt and latency has gotten bad enough to matter on shorter timeframes. The rate limiter is the main suspect — during volatility it feels like it’s serializing us into throttling exactly when we need throughput. My guess is it’s treating global and per-endpoint limits the same, or the burst window logic is too conservative, but I’d rather confirm it in the code than just assume.

There’s also something weird with the WebSocket order-book feeds where we see what looks like backpressure even when the consumer should be keeping up. Haven’t figured out if that’s ccxt’s WS layer, something in our handler, or the exchange being slow on its end.

Basically I want to understand where time is actually going on the order placement path. Signing, HTTP roundtrip, queueing behind the limiter, retries — which of those is actually the bottleneck? Is sub-100ms on REST even realistic with this architecture or is that a ceiling we can’t get past?
