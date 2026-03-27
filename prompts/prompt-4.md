# Prompt 4

**Category:** Infrastructure & DevOps

**Sub-category:** CI/CD Pipeline Debugging and Optimization

**Language:** TypeScript

**Repo:** https://github.com/NomicFoundation/hardhat

**Prompt:**

Our Hardhat setup has rotted. Flaky integration tests, shared global state, suites that only pass in a certain order — failures I genuinely can’t reproduce locally half the time. Deploy scripts are so manual that getting a clean environment is always a project. And proxy upgrade testing is basically "cross your fingers before prod."

I’m not looking for individual tips, I want to rethink the structure:

- Some fixture model that actually isolates chain state between tests without redeploying everything for every `it()`. What we have doesn’t scale.
- Deployments that are deterministic and have real dependency ordering. Factories probably, but I’m not sure what the right shape is.
- Parallel test runners without them stepping on each other’s nonces or snapshots.
- Repeatable upgrade tests — storage layout checks, UUPS vs transparent gotchas, initializer replay issues. Something that could actually block a bad upgrade in CI.

Small team, no patience for abstractions that only make sense to whoever wrote them.
