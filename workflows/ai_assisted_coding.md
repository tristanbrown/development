# Strategies for AI-Assisted Coding

## 1. Iterative Copy-Paste
- Plan with ChatGPT
  - GPT-4o follows instructions best
  - GPT-5 has more robust and creative solutions
- Copy relevant files into chat. Copy code outputs back into codebase.
- Tip: Ask GPT-4o and GPT-5 to generate independent solutions and review each other's code.

#### Pros
- High degree of user control
- Can refine code very precisely
- Remembers historical context and prior plans

#### Cons
- Context only comes through manual copy-paste
  - Unsustainable with large, interconnected codebases
- Historical context can get out of date
- Juggles several different chats for each task

#### Use-Cases
- Works well for isolated changes, single files
- Coding where I know exactly what I want
- Can get a good feedback loop going, creating momentum on a project
- Becomes difficult as the codebase grows

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

#### Use-Cases
- Simple, brainless, repo-wide updates (mostly boilerplate)
- Avoid for tasks requiring any degree of human judgement: Often frustrating
- I spend time and mental health arguing with the model and requesting reversions

## 3. Plan With Chat, Implement With Codex
- Use method #1 to generate an instructional `plan.md` document
- Feed `plan.md` into method #2 to guide implementation
- Not sure which model to use for implementation (gpt-5-codex-medium?)

#### Pros
- Gets the context and instructions-following advantages of Method #1 with the hands-off implementation of Method #2.

#### Cons
- Repo context still only comes from manual copy-paste.
- ChatGPT-4o does not seem to be good at generating `plan.md`. It describes too much step-by-step implementation detail, while failing to summarize the high-level concepts decided in planning. 

#### Use-Cases
- Possibly addresses the shortcomings of Method #2
- Cases where the planning and design decisions are crucial
- Will only work if I can find better ways to generate `plan.md` files

## 4. Codex Cloud
- Set up an environment
- Plan with chat mode
- Request feature implementation with Code mode (with up to 4 attempts)

#### Pros
- Explictly choose chat mode vs code mode
- Full repo context in both read and write
- Automated multiple attempts (up to 4)
- Easy to apply changes independently to different parallel branches
- Doesn't use tokens?
- Can install the package and run tests in the containerized environment

#### Cons
- In single-shot generation of 4 attempts, the different attempts don't learn from each other.
- Not as much refinement control as Method #1
- Messy to compare different attempt versions
- No control over model choice?
- Slower than local

#### Use-Cases
- Implementing major features or refactors
- Cases were the concept is simple, but the engineering may be complex
- Need to find faster, more effective ways to diff and review the attempt versions
- Use ChatGPT to help compare attempt versions?
- Not sure yet of the effectiveness or code quality
