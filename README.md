# Link Crypt MCP server

<!-- mcp-name: com.getlinkcrypt/linkcrypt -->

Connect Claude, ChatGPT, Copilot and other AI assistants to [Link Crypt](https://getlinkcrypt.com),
so you can search, save, and tidy your saved links by asking in plain English.

Link Crypt is a bookmark library that keeps a copy of every page you save, so search
finds words in the page itself, not just its title.

**Server URL:** `https://mcp.getlinkcrypt.com/mcp`

This is a hosted (remote) server. There is nothing to install. You sign in to your Link Crypt
account and approve the connection; no API keys to copy.

## What you can ask

- "What did I save this week?"
- "Find the article I saved about sourdough starters."
- "Save this link and tag it recipes."
- "Which tags am I using most?"
- "Do I have any duplicate links? Merge them."
- "Write me a digest of what I've been reading this month."

## Connect

**Claude** (Claude.ai, Desktop, mobile): Settings → Connectors → Add custom connector →
`https://mcp.getlinkcrypt.com/mcp`, then sign in and approve.

**ChatGPT**: Settings → Apps & Connectors → Advanced settings → Developer mode on → Create →
`https://mcp.getlinkcrypt.com/mcp`, Authentication: OAuth.

**Claude Code**

```bash
claude mcp add --transport http linkcrypt https://mcp.getlinkcrypt.com/mcp
```

**VS Code (GitHub Copilot)**: `.vscode/mcp.json`

```json
{
  "servers": {
    "linkcrypt": { "type": "http", "url": "https://mcp.getlinkcrypt.com/mcp" }
  }
}
```

**Cursor**: `~/.cursor/mcp.json`

```json
{
  "mcpServers": {
    "linkcrypt": { "url": "https://mcp.getlinkcrypt.com/mcp" }
  }
}
```

Full setup guide, including Grok, Hermes and Muse: https://getlinkcrypt.com/integrations/mcp

## Tools

**Read your library**
`get_overview`, `search_links`, `list_links`, `get_link`, `list_tags`, `generate_digest`,
`find_duplicates`, `search`, `fetch`

**Changes** (turned off when you connect read-only)
`save_link`, `update_link`, `tag_link`, `update_tag`, `delete_link`, `delete_tag`,
`merge_duplicates`

Read tools are marked read-only. `delete_link`, `delete_tag` and `merge_duplicates` are marked
destructive and need explicit confirmation.

## Security and privacy

- Sign-in is OAuth 2.1 with PKCE. You approve each connection on getlinkcrypt.com and choose
  whether the assistant may make changes. Disconnect any time from Preferences → Connected
  AI assistants, and access stops immediately.
- A connection sees only your own library, with the same limits as your plan.
- The server reads only what each tool is asked for. It does not see your chat history.
- Privacy policy: https://getlinkcrypt.com/privacy

## Support

privacy@objectivelabs.com
