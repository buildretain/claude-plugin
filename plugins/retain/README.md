# Retain for Claude Code

Lets Claude read, draft, and schedule the questions and lessons in your Retain workspace.

## Setup

1. In Retain, go to **Settings → Agent access (MCP)** and create a key (default permissions: read + drafts).
2. Put the key in your shell environment:

   ```bash
   export RETAIN_API_KEY=rtn_...
   ```

   (Add it to `~/.zshrc` or `~/.bashrc` to keep it.)
3. In Claude Code:

   ```
   /plugin marketplace add arjaythedev/retain-plugin-plugin
   /plugin install retain@retain
   ```

Run `/mcp` to confirm the `retain` server is connected.

## What Claude can do

- **Read**: workspace info, topics, questions, lessons, the daily-question calendar
- **Draft** (default): create and edit questions (multiple choice, matching, ordering), topics, and slide-deck lessons with comprehension checks
- **Publish / schedule** (opt-in on the key): publish, schedule the daily question, unschedule
- **Archive** (opt-in on the key): archive questions and lessons

Agent-created content is saved as a **draft** unless the key has publish permission and you ask for it.

## Codex

```bash
codex mcp add retain --url https://www.buildretain.com/mcp --bearer-token-env-var RETAIN_API_KEY
```
