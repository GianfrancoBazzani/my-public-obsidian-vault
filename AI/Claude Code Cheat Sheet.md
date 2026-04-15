A distilled onboarding guide to [Claude Code](https://code.claude.com/docs/en/best-practices), Anthropic's agentic coding environment. Organized from ground-floor mechanics to deeper topics, stop reading when you've learned enough to be useful.

> Claude Code is not a chatbot. You describe what you want; it reads files, runs commands, and makes changes autonomously. The whole UX is built around managing that autonomy without it going off the rails.

---

# Cheat Sheet: Commands, Shortcuts, and Keywords

Everything in this part is something you type or press. Learn these first.

## Slash commands (type inside the prompt box)

| Command | What it does |
| --- | --- |
| `/init` | Scan your project and generate a starter `CLAUDE.md` (project instructions). Run once per new codebase. |
| `/clear` | Wipe the conversation context. Use between unrelated tasks; a long polluted session performs worse than a fresh one. |
| `/compact` | Summarise the conversation so far to free context. Add focus instructions: `/compact focus on the API changes`. |
| `/context` | See what's currently using space in the context window. |
| `/memory` | View or edit loaded `CLAUDE.md` files and auto-memory. |
| `/rewind` | Restore code, conversation, or both to an earlier checkpoint. |
| `/resume` | Pick a previous session from a searchable list. |
| `/rename <name>` | Give the current session a memorable name (e.g. `oauth-migration`). |
| `/btw <question>` | Ask a side question that **never enters conversation history**, good for quick lookups. |
| `/plan [description]` | Enter plan mode so Claude researches and plans before touching code. |
| `/ultraplan <prompt>` | Draft a plan in a browser ultraplan session, then run it remotely or pull it back here. |
| `/model` | Switch model (e.g. Sonnet, Opus) mid-session. |
| `/effort <level>` | Set reasoning effort: `low`, `medium`, `high`, `max`, or `auto`. |
| `/skills` | List available skills (reusable knowledge and workflows that extend Claude). |
| `/agents` | Manage subagents: isolated workers that explore or review in their own context. |
| `/mcp` | Manage connections to external tools (databases, Slack, Figma, etc.) via MCP servers. |
| `/cost` | Show token usage for the current session. |
| `/help` | List everything available in your current session. |

## In-prompt keywords

| Syntax            | Meaning                                                                       |
| ----------------- | ----------------------------------------------------------------------------- |
| `/`               | Open the slash-command menu (e.g. `/clear`). Type at the start of a prompt.   |
| `#`               | Save the message to a `CLAUDE.md` memory file — Claude asks which one.        |
| `@path/to/file`   | Attach a file's contents to your message (Claude reads it before responding). |
| `@path/to/folder` | Attach a directory listing.                                                   |

## CLAUDE.md file locations

`CLAUDE.md` is the project's persistent instruction file, Claude reads it every session.

Inside a `CLAUDE.md`, import other files with `@path/to/other.md`. Keep it under ~200 lines: longer files get diluted and ignored.

---

# Prompting Tips: How to Actually Get Good Results

Commands are mechanics. These are the habits that separate "Claude constantly missing the point" from "Claude just shipped the feature."

## Give Claude a way to verify its own work

The single highest-leverage habit. Bundle tests, expected outputs, or screenshots into your prompt so Claude can check itself:

> ❌ *"make the dashboard look better"*
> ✅ *"[screenshot attached] implement this design. Take a screenshot of the result, compare to the original, list the differences, and fix them."*

> ❌ *"the build is failing"*
> ✅ *"the build fails with this error: [paste]. Fix the root cause and verify the build succeeds — don't suppress the error."*

## Explore → Plan → Implement → Commit

For anything non-trivial, separate research from execution:

1. **Explore** (Plan Mode — press `Shift+Tab` twice): *"Read `src/auth/` and explain how sessions work."*
2. **Plan** (still Plan Mode): *"Create a plan to add Google OAuth. Which files change?"* Use `Ctrl+G` to edit the plan directly.
3. **Implement** (Normal Mode): *"Implement the plan. Write tests for the callback handler and run the test suite."*
4. **Commit**: *"Commit with a descriptive message and open a PR."*

Skip this for one-sentence changes (typos, renames). It's overhead when the scope is obvious.

## Be specific: scope, sources, patterns, symptoms

Claude can infer, but every inference is a coin flip:

- **Scope:** *"write a test for `foo.py` covering the logged-out edge case. Avoid mocks."*
- **Point to sources:** *"look through ExecutionFactory's git history and summarise how its API evolved."*
- **Reference patterns:** *"look at how `HotDogWidget.php` is built and follow the same pattern for a CalendarWidget."*
- **Describe symptoms:** *"login fails after session timeout. Check `src/auth/`, especially token refresh. Write a failing test that reproduces it, then fix."*

## Let Claude interview you for larger features

Start minimal and delegate the requirements-gathering itself:

> *"I want to build [brief description]. Interview me using the `AskUserQuestion` tool. Ask about technical implementation, UI/UX, edge cases, and tradeoffs. Don't ask obvious questions — dig into the hard parts I might not have considered. When we're done, write the spec to `SPEC.md`."*

Then `/clear` and start a fresh session to execute the spec.

## Course-correct early and often

- Notice something wrong? Press `Esc` immediately — don't let it compound.
- Two failed corrections on the same issue? `/clear` and rewrite the prompt with what you learned. A clean session with a better prompt beats a long cluttered one.
- Ask a sub-question without polluting the session: `/btw <question>`.

## Manage context aggressively

Context = the conversation window Claude is reasoning over. Full context = worse answers. Defensive habits:

- `/clear` between unrelated tasks.
- For investigation-heavy work, ask for **subagents**: *"use subagents to investigate how we handle token refresh."* Subagents work in their own context and report back a summary — yours stays clean.
- Reference files with `@` instead of pasting long blocks.
- Use `/compact focus on X` to summarise while preserving what matters.

## Avoid the five common failure patterns

| Pattern | Fix |
| --- | --- |
| **Kitchen sink session** — unrelated tasks pile into one conversation | `/clear` between tasks |
| **Correcting in circles** — same correction repeated | After two failed tries, `/clear` and write a better prompt |
| **Bloated CLAUDE.md** — rules get lost in the noise | Ruthlessly prune. If Claude already does it right, delete the rule |
| **Trust-then-verify gap** — plausible code that doesn't handle edge cases | Always provide verification. If you can't verify it, don't ship it |
| **Infinite exploration** — "investigate X" with no scope | Narrow the scope, or delegate to a subagent so exploration doesn't eat your context |

---

# Advanced Topics: Further Reading

Once you're comfortable with the basics, these are the rabbit holes. Each link is to Anthropic's official docs — all verified working at time of writing.

## Fundamentals

- **[How Claude Code works](https://code.claude.com/docs/en/how-claude-code-works)** — the agentic loop, built-in tools, sessions, context window.
- **[Common workflows](https://code.claude.com/docs/en/common-workflows)** — step-by-step recipes: refactoring, testing, PRs, images, worktrees.
- **[Best practices](https://code.claude.com/docs/en/best-practices)** — the source document this cheat sheet is distilled from.

## Extending what Claude can do

- **[Extend Claude Code (overview)](https://code.claude.com/docs/en/features-overview)** — decision tree for when to use what.
- **[CLAUDE.md / Memory](https://code.claude.com/docs/en/memory)** — persistent project instructions, rules, and auto-memory.
- **[Skills](https://code.claude.com/docs/en/skills)** — reusable knowledge and `/slash-command` workflows.
- **[Subagents](https://code.claude.com/docs/en/sub-agents)** — isolated workers that return summaries instead of cluttering your context.
- **[Hooks](https://code.claude.com/docs/en/hooks-guide)** — deterministic shell scripts that run on events (post-edit, pre-tool, etc.).
- **[MCP servers](https://code.claude.com/docs/en/mcp)** — connect Claude to external services (databases, Slack, Figma, GitHub).
- **[Plugins](https://code.claude.com/docs/en/plugins)** — bundle skills, hooks, subagents, and MCP servers for sharing.

## Controlling what Claude can run

- **[Permission modes](https://code.claude.com/docs/en/permission-modes)** — default, acceptEdits, plan, auto, dontAsk, bypassPermissions.
- **[Sandboxing](https://code.claude.com/docs/en/sandboxing)** — OS-level filesystem and network isolation for bash commands.
- **[Checkpointing](https://code.claude.com/docs/en/checkpointing)** — auto-snapshot and rewind file edits.

## Scaling beyond one session

- **[Agent teams](https://code.claude.com/docs/en/agent-teams)** *(experimental)* — multiple Claude sessions coordinating on a shared task list.
- **[Claude Code on the web](https://code.claude.com/docs/en/claude-code-on-the-web)** — run tasks on Anthropic-managed cloud VMs from `claude.ai/code` or mobile.
- **[Non-interactive mode / Agent SDK](https://code.claude.com/docs/en/headless)** — run Claude programmatically for CI, scripts, and automation (Python & TypeScript SDKs available).

## Integrations and UI

- **[Chrome integration](https://code.claude.com/docs/en/chrome)** — Claude opens tabs, reads DOM, automates forms.
- **[Status line](https://code.claude.com/docs/en/statusline)** — persistent bottom bar showing context usage, cost, git state.

