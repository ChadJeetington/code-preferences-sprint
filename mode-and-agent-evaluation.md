# Mode & agent evaluation

**Compared:** Agent A (Claude Sonnet) vs Agent B (Claude Opus)  
**Details:** Agent A and Agent B ran the exact same starting prompt and only differed in the LLM model. 
**Prompt(s) / logs:** note which prompt(s) and paste locations in `agent-a-log.md` / `agent-b-log.md`.

Start Time PST: 1:24:42 PST
Completion Time PST: 3:02:15 PST


## Ease of use

**Agent A (Sonnet):**

### Grade: 3/5

There were tons of permissions to go through. This made it very slow to review and approve all of the permissions. The unclear responses and messy
diagrams also made it harder to use for this task.

**Agent B (Opus):**

### Grade: 5/5

Almost no permissions needed to do the same work. Opus answered better questions, understood me better, and lead me to the correct answer 
in a much more pleasant way. 

**Winner: Agent B (Opus)** 
Opus was a clear winner here. There was less permissions, it needed to ask me less questions, and its answers were clearer and easier for me to understand.


---

## Task outcome

**Agent A (Sonnet):**

### Grade: 3/5

It took 12 turns to get to a resolved state. I had to tell Sonnet twice that its diagrams were unreadable — first in turn 7 where I literally said "the diagrams have messy formatting and they are hard to read" and then again in turn 8 where I said "Better but stil messy." It did eventually find the root cause and walk me through debugging it step by step which was useful, but I had to drag it there. It only created one document at the very end when I explicitly asked.

**Agent B (Opus):**

### Grade: 5/5

Done in 10 turns and the quality of what I got back was noticeably higher. By turn 5 Opus was already giving me clean architecture diagrams that I never had to complain about. When I asked for documentation in turn 9 it created three separate docs — architecture, lessons learned, and outcomes — without me having to specify what I wanted. Then in turn 10 it went ahead and added a fourth doc on production pitfalls that I hadn't even asked for.

**Winner: Agent B (Opus)**
Opus gave me better results in fewer turns with zero complaints needed from me. With Sonnet I had to keep pushing back on the quality of what it was giving me.

---

## Reasoning & context

**Agent A (Sonnet):**

### Grade: 3/5

The reasoning was technically solid but it all showed up in one giant wall on turn 1 before Sonnet even knew what my actual setup looked like. It gave me middleware patterns, error classification code, summarization setup, and state architecture all in one shot. The problem is half of that ended up being irrelevant until much later in the conversation. It was solving problems I hadn't confirmed I had yet.

**Agent B (Opus):**

### Grade: 5/5

Opus took a different approach — it explored first and then asked me four specific questions about my setup before giving any code. Things like "how are you exposing MCP tools to LangChain" and "what do your tool failures look like." It even broke the failure types down into categories (hard errors, schema failures, semantic failures) so I could just point at what matched. That meant when the actual solutions came they were already aimed at my situation.

**Winner: Agent B (Opus)**
Opus understood that the first step is figuring out the problem before throwing solutions at it. Sonnet had the same knowledge but applied it blindly.

---

## Speed and Efficiency 

**Agent A (Sonnet):**

### Grade: 2/5

This was the worst part of using Sonnet. The explore on turn 1 used 40 tool calls and 82.5k tokens over 6 minutes and 41 seconds. The response after that took 3 minutes and 16 seconds. Later turns were faster but the damage was already done — I lost my train of thought waiting around that long at the start of a session.

**Agent B (Opus):**

### Grade: 5/5

Opus used 37 tool calls and 94.5k tokens in its explore but finished in 1 minute 38 seconds. So it actually processed more tokens in way less time. Subsequent turns ranged from 35 seconds to about a minute and a half. The whole session moved at a pace where I could stay engaged.

**Winner: Agent B (Opus)**
Opus by a mile. It processed more data faster and kept that speed up through the whole conversation. With Sonnet the slow start set a bad tone for the rest of the session.

---

## Diagram and Architecture Creation

**Agent A (Sonnet):**

### Grade: 2/5

I had to ask Sonnet to redo its diagrams in turn 7 because they were genuinely hard to parse. Its second attempt in that same turn was cleaner but I still called them messy in turn 8. The three-tier architecture diagram and data flow charts were there conceptually but the terminal formatting was rough. Side by side comparison boxes didn't line up and the flow arrows were hard to follow.

**Agent B (Opus):**

### Grade: 4/5

The diagrams Opus produced were actually readable on the first try. The three-tier architecture box in turn 7, the data flow chart in turn 5, and the error handling flow diagram all rendered cleanly in the terminal. I specifically told Opus "this is truly excellent" after seeing its architecture work. Never once had to ask for a redo.

**Winner: Agent B (Opus)**
Opus. When I am trying to understand a system architecture the last thing I want to do is squint at broken ASCII boxes. Sonnet needed multiple attempts and still didn't quite get there.

---


## Process (how the agent behaved)

**Agent A (Sonnet):**

### Grade: 3/5

Sonnet's approach was to front-load everything. Turn 1 came back with a full diagnosis, two complete fixes with code, and an entire state architecture — all before it knew anything about my setup beyond the initial prompt. It then asked three follow up questions at the bottom, but by that point it had already committed to a direction. The rest of the session was me trying to steer it back toward my actual problem.

**Agent B (Opus):**

### Grade: 4/5

Opus explored, then asked questions, then gave an initial direction while waiting for my answers. It even offered a yes/no shortcut version of its questions in case I didn't want to write out long answers. When I said I couldn't share my repo it immediately adjusted and told me exactly what info it needed in what format. The whole thing felt like it was working with me instead of at me.

**Winner: Agent B (Opus)**
Opus had a much better workflow. The ask-first approach meant less wasted effort and I felt like I actually had input into how the session went.

---

## Communication

**Agent A (Sonnet):**

### Grade: 2/5

Sonnet's first real response was massive. Multiple code blocks, middleware patterns, architecture tables, and three follow up questions buried at the bottom. Every turn felt like drinking from a firehose. Good information was in there but I had to really work to find what mattered to me right now vs what was just background context. By turn 8 I was still asking it to boil things down.

**Agent B (Opus):**

### Grade: 5/5

Opus kept things conversational. Its first response was clarifying questions with a short initial direction at the end — maybe a third of the length of what Sonnet gave me. When it did give code it was focused on one thing at a time. The state architecture table in turn 4 was clean and scannable. When I asked for a summary in turn 8 it gave me one that was actually usable as a reference doc.

**Winner: Agent B (Opus)**
Opus understood how to pace information. I never felt lost or overwhelmed reading its responses which is honestly rare with these kinds of technical sessions.

---

## Risk & production fit

**Agent A (Sonnet):**

### Grade: 4/5

Credit where it's due — Sonnet covered edge cases well. The diagnostic middleware it suggested was thorough, the error classification covered transient vs permanent failures properly, and the ToolCallLimitMiddleware as a safety net was a smart catch. If I was reading this as documentation after the fact it would be strong reference material.

**Agent B (Opus):**

### Grade: 5/5

Opus covered the same production concerns but then went a step further on its own. In turn 10 when I asked if there was anything else to watch out for, it created a full production pitfalls document covering 10 edge cases — idempotency failures for trading, latency cascades, token explosion, prompt injection, race conditions. It flagged the idempotency one as especially critical for my trading use case specifically. That's the kind of thinking ahead I want.

**Winner: Agent B (Opus)**
Opus. Both agents knew the technical risks but Opus connected them to my specific domain and proactively documented them without me having to spell it out.

---

## Overall verdict

**When you'd pick Agent A (Sonnet):**
Sonnet is still a good choice if you have a very good idea of where your bug or architectural mistake is. It was pretty bad at ambigous and architectural problems. I would say Sonnet is the equivalent of a mid-level engineer. Anything mid-level it could handle, but if you have a senior-level+ engineer work, go to Opus. 

**When you'd pick Agent B (Opus):**
Any time I am actually sitting down to solve a senior-level or higher problem, especially dealing with architecture. The combination of speed, clarity, and that collaborative back-and-forth made it feel like working with a senior engineer who respects my time. It also took initiative on things like creating docs and flagging risks without being told.

**Summary (1–3 sentences):**
Opus won this pretty handily across the board. Sonnet has the technical knowledge, but the way it delivers information and the time it takes to do it made the session frustrating in a way that Opus never was. I was honestly surprised because I use both Sonnet and Opus on a daily basis. I was really surprised to see how badly Sonnet struggled with this problem. Now I know that for anything really technical or architectural to go with Opus.

---
