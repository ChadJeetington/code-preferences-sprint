# Prompt 5 (Free Choice / Task Overview)

**Category:** Debugging & Meta-Programming

**Sub-category:** Language-diverse Debugging > Solidity: Smart Contract Execution Tracing and Security Analysis
**Language:** Solidity

**Repo:** https://github.com/compound-finance/compound-protocol

**Prompt:**

We’re looking at integrating Compound into a liquidation automation setup, and I’m having trouble making sense about the liquidation path from start to end. The specific scenario that worries me is multiple liquidations hitting overlapping positions in the same block, like a MEV attack.

I want to understand the core flow: how interest accrual, collateral seizure, and debt repayment interact, and where ordering actually matters.

If there are parts of this that are genuinely hard to reason about without running a simulation, then I would like to know. Then also make a summary of the complex areas of implementation in laymans terms for me and my team top understand.