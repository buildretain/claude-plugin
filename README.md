# Retain — Claude Code plugin

Connect Claude Code (or Codex, or any MCP client) to your [Retain](https://www.buildretain.com) workspace so it can read, draft, and schedule your questions and lessons.

```
export RETAIN_API_KEY=rtn_...        # from Retain → Settings → Agent access (MCP)
/plugin marketplace add buildretain/claude-plugin
/plugin install retain@retain
```

Codex:

```bash
codex mcp add retain --url https://www.buildretain.com/mcp --bearer-token-env-var RETAIN_API_KEY
```

See [`plugins/retain/README.md`](plugins/retain/README.md) for what the tools can do. Agent-created content is saved as a draft unless your key has publish permission and you ask for it.
