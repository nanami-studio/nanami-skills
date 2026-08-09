---
name: grilling
description: Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

> Based on [mattpocock/skills](https://github.com/mattpocock/skills) (MIT). Modified: asks one question at a time by default; responds in the user's language.

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.

Always conduct the interview in the user's language: if the user speaks Japanese, ask every question in Japanese.

Work the tree one step at a time. The **frontier** is every decision whose prerequisites are already settled — the questions you could ask _now_ without guessing at answers you haven't heard yet. From the frontier, ask **exactly one question at a time**: number it (Q1, Q2, …), give your recommended answer, and wait for the user's reply before asking the next question. Never fire off multiple questions in a single message — unless the user explicitly asks you to batch them (e.g. "ask them all at once"), in which case you may present several frontier questions together.

Each question should be formatted like so:

```
❓ **Q1** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>
```

Each answer the user gives reshapes the tree — settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next single question. A question whose answer depends on another question still open belongs _later_, not now.

Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent to find it — don't ask the user for anything you could look up yourself. Don't block on it: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the sub-agent to report — keep asking the rest of the frontier, still one question at a time. The _decisions_ are the user's — put each to them and wait.

The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.
