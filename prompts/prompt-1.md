# Prompt 1

**Category:** Debugging & Meta-Programming

**Sub-category:** Language-diverse Debugging > Python: Data Pipeline Errors and Performance Bottlenecks

**Language:** Python

**Repo:** https://github.com/langchain-ai/langchain

**Prompt:**

I’ve got a LangChain ReAct agent in production hitting an MCP tool server over streamable HTTP. When a tool call fails or returns something the model can’t parse, it just retries in a loop until it hits max_iterations and dies. I’ve bumped the limit and tweaked the system prompt but that’s not fixing it.

I need you to dig into the LangChain source and find where this retry behavior actually lives — the agent executor loop, how tool errors propagate, where the decision to retry vs stop is made. Once we’ve traced it, I want to implement proper error classification: transient failures that should retry with backoff, hard failures that should surface a structured error and stop, and bad tool outputs that should be handled differently from connection failures.

There’s a second issue too — on longer sessions, early tool outputs get truncated from context and the model starts making decisions without them. I want to understand where message trimming happens in the chain and whether there’s a way to pin critical tool outputs or move them to a memory layer that doesn’t get dropped.

Start by mapping out the relevant code paths in the repo before touching anything.
