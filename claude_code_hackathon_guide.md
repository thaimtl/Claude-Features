# Claude Code: Hackathon Development Workflow

## Setup

After `git init`, install the **Superpowers** plugin pack. It bundles the skills needed to build features end to end. Not sure what skills or plugins are? Ask Claude directly, or check the Claude Code documentation at [docs.claude.ai](https://docs.claude.ai).

---

## The Workflow

### 1. Plan Your Project

Press **Shift+Tab** to enter Plan Mode. Think through your idea with Claude before writing a single line of code. This phase matters more than most people realize. Discuss the problem, the user, the constraints, and what success looks like. Do not rush it.

### 2. Generate Your Foundation Files

Once your team agrees on scope, ask Claude to generate two files:

- **PRD.md** — your product requirements document. Read it carefully. Make sure it reflects what you actually want to build.
- **README.md** — an executive summary of the project.

Then run `/init`. Claude will generate or update **CLAUDE.md**, which acts as persistent memory across sessions. Read it, ask questions, and edit it until it accurately reflects your project.

### 3. Build Your Issue Backlog (Teams)

Ask Claude to generate an `issues_backlog.md`. Copy each issue into GitHub Projects as individual tickets. Assign owners and note dependencies or blockers before anyone starts coding.

### 4. Start Development

Each team member opens a new Claude Code session and picks up an issue.

### 5. Dev Loop (Per Issue)

1. Run `/init` to refresh Claude's memory.
2. Enter Plan Mode. Review Claude's plan. Adjust it until you understand every step.
3. Run `execute-plan` from the Superpowers plugin. Claude will begin executing.
4. Build the feature together with Claude.
5. When done, ask Claude to run a code review. The `code-reviewer` agent will flag issues before you commit.
6. Create a branch, commit, and push. Open a PR and merge. If you have the GitHub plugin, Claude handles this automatically.

---

## Tips

**Context management.** Plugins consume context fast. Reserve them for mid-to-complex tasks.

**Model selection.** For complex tasks, use Opus. Type `/model` to switch.

**Compact often.** After each sub-feature, run `/compact` to compress the conversation and preserve your context window.

**Resume sessions.** Use `/resume` to pick up a previous conversation.

---

> This is a personal workflow, not an official Anthropic guide. Plugins are optional. Adapt this to fit your team and your stack.
