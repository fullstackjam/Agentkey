# AgentKey — Setup fallback: clients not on the auto-list

Load this when `npx -y @agentkey/cli --auth-login` could **not** write the user's
client config — i.e. the user's agent is **Codex / OpenCode / Gemini CLI / Linux
Claude Desktop / Hermes / Manus / any other client** the CLI doesn't auto-configure.
Guide a manual install:

1. Tell the user to grab a key at https://console.agentkey.app/
2. Show them this JSON to paste into their agent's MCP config (path varies per agent):
   ```json
   {
     "mcpServers": {
       "agentkey": {
         "type": "http",
         "url": "https://api.agentkey.app/v1/mcp",
         "headers": { "Authorization": "Bearer ak_..." }
       }
     }
   }
   ```
3. Restart the agent.

If you don't know the user's agent, ask: "Which agent / client are you using? (Claude Code, Claude Desktop, Cursor, Codex, …)"
