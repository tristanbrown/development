# Strategies for AI-Assisted Coding

## 1. Iterative Copy-Paste
- Plan with ChatGPT
  - GPT-4o follows instructions best
  - GPT-5 has more robust and creative solutions
- Copy relevant files into chat. Copy code outputs back into codebase.
- Tip: Ask GPT-4o and GPT-5 to generate independent solutions and review each other's code.

#### Pros
- High degree of user control
- Works well for isolated changes, single files
- Can refine code very precisely
- Remembers historical context and prior plans

#### Cons
- Context only comes through manual copy-paste
  - Unsustainable with large, interconnected codebases
- Historical context can get out of date
- Juggles several different chats for each task

## 2. Local Codex Edits
- Ask Codex to implement features and make changes
- Model choices:
  - **gpt-5-medium (or lower):** Opinionated and often wrong.
  - **gpt-5-high:** Overthinks, overengineers, doesn't follow instructions.
  - **gpt-5-codex-medium (or lower):**
  - **gpt-5-codex-high:**

#### Pros
- Full repo context
- Operates autonomously (very hands-off)
- Just one chat window

#### Cons
- Uses tokens
- Does not allow for easy planning. Jumps the gun too much.
- Does not always follow instructions or respect AGENTS.md rules.
- Difficult to refine different versions
- No environment; can't run tests

## 3. Plan With Chat, Implement With Codex
- Use method #1 to generate an instructional `plan.md` document
- Feed `plan.md` into method #2 to guide implementation
- Not sure which model to use for implementation (gpt-5-codex-medium?)

#### Pros
- Gets the context and instructions-following advantages of Method #1 with the hands-off implementation of Method #2.

#### Cons
- Repo context still only comes from manual copy-paste.
- ChatGPT-4o does not seem to be good at generating `plan.md`. It describes too much step-by-step implementation detail, while failing to summarize the high-level concepts decided in planning. 


