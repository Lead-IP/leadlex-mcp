# LeadLex MCP server

Connect Claude, ChatGPT, Cursor or any MCP client to your [LeadLex](https://www.leadlex.com) workspace. LeadLex is a CRM built for law firms and IP practices.

This is a remote server. There is nothing to install.

```
https://mcp.leadlex.com/mcp
```

Transport: streamable HTTP. Sign in with OAuth 2.1 (dynamic client registration, PKCE), or send a workspace API key in the `X-API-Key` header.

## What you can do

- Capture a meeting in one request: company, contact, meeting, note, deal and follow-up task are created and linked together.
- Search and update contacts, companies, deals, tasks, meetings and notes.
- Import contacts from pasted rows or a CSV or XLSX file.
- Source new prospects, then reveal emails and save them as contacts once you confirm who you want.
- Draft email campaigns and manage their steps. Sending needs your explicit instruction and a workspace setting.
- Read synced email and run pipeline, activity and response-time reports.
- Look up patent portfolio activity for companies linked to the IP register.

99 tools. Every call runs inside the workspace of the account that signed in. Read-only connections get no write tools, and delete tools require an explicit confirmation flag.

## Connect

**Claude:** Customize → Connectors → **+ Add**, then paste the URL above. On Team and Enterprise plans an organization Owner adds it first under Organization settings → Connectors.

**Claude Code:**

```bash
claude mcp add --transport http leadlex https://mcp.leadlex.com/mcp
```

**ChatGPT** (Business, Enterprise and Edu, on the web): Plugins → **+** → **Add custom MCP server**, paste the URL under Connection and choose OAuth.

**Cursor and other clients:**

```json
{
  "mcpServers": {
    "leadlex": {
      "url": "https://mcp.leadlex.com/mcp"
    }
  }
}
```

Full setup guides and the tool reference: [docs.leadlex.com/mcp-server/overview](https://docs.leadlex.com/mcp-server/overview)

## Example prompts

1. "Just met with Alex Tan at Banana Legal, trademark pilot, follow up next week."
2. "Which deals have gone quiet in the last six weeks?"
3. "Find 20 patent attorneys in pharma and show me who they are."
4. "Did Anna reply to my pitch?"
5. "Create a follow-up campaign called Q3 Nordlicht and add the Nordlicht prospects."

## Limits and pricing

MCP is included on every LeadLex plan. Each OAuth connection or API key can make 60 tool calls a minute.

## Support

[support@leadlex.com](mailto:support@leadlex.com) · [Privacy](https://www.leadlex.com/privacy) · [Terms](https://www.leadlex.com/terms)

This repository holds documentation and the registry manifest only. The server itself is operated by Lead IP.
