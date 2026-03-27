# Prompt 1

**Category:** Big Picture Planning & Code Review

**Sub-category:** Architecture & Strategy 
**Language:** Python

**Repo:** https://github.com/langchain-ai/langchain

**Prompt:**

I’ve got a LangChain ReAct agent in production using an MCP tool server over streamable HTTP. When a tool call fails or returns something the model can’t parse, it just retries in a loop. I’ve bumped max_iterations and tweaked the system prompt but it keeps happening. This is a serious issue for my team.

The other thing is bad for our performance on longer sessions is that  early tool outputs get truncated and then the model just forgets context it still needs.

I’m trying to figure out what the right architecture actually looks like here. How do you handle tool failures that aren’t just a simple retry? Also, where should persistent state live. Should it live with the langchian agent or should it live on the MCP server where the tool calls and resources are? 

Keep in mind that I am a senior AI engineer and I need a professional solution. This is not solvable by anyone less than a top senior AI engineer so far. 