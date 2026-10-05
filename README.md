# fone.me MCP server

**Reach anyone's AI agent at their fone.me link — from ChatGPT, Claude, Cursor, or any MCP client.**

[fone.me](https://www.fone.me) gives every person and business an AI agent at their own link (`fone.me/name`). The agent answers for them 24/7 — questions, bookings, quotes, leads — on the web, WhatsApp, calls and Telegram. This MCP server lets your AI assistant find those agents and talk to them.

- **URL:** `https://www.fone.me/mcp`
- **Transport:** Streamable HTTP
- **Auth:** none (public, like the links themselves)

## Demo

Claude looking up fone.me/samspearin and messaging that agent on someone's behalf: [demo.mp4](demo.mp4)

## Tools

| Tool | What it does |
|---|---|
| `find_agents` | Search fone.me for people's and businesses' agents by what they do — "hair salon", "real estate agent in Miami", "Spanish tutor". |
| `get_agent` | Who is behind a fone.me link and what their agent can help with. |
| `message_agent` | Send a message to the agent at a link and get its reply — ask a question, request a booking or quote, or leave a message. Conversations continue across calls; the owner sees them in their fone.me inbox ("Maria via ChatGPT"). |

## Add it

**ChatGPT:** Settings → Apps & Connectors → Advanced → Developer mode → Create → URL `https://www.fone.me/mcp`, no authentication.

**Claude:** Settings → Connectors → Add custom connector → `https://www.fone.me/mcp`.

**Cursor / VS Code / other clients** (`mcp.json`):

```json
{
  "mcpServers": {
    "fone.me": { "url": "https://www.fone.me/mcp" }
  }
}
```

## Try

- "Find a hair salon on fone.me and ask if they have a slot Saturday."
- "Message fone.me/samspearin and ask what he's working on."

## Agent-to-agent (A2A)

Every fone.me link also speaks [A2A](https://a2a-protocol.org): agent card at `https://www.fone.me/{link}/.well-known/agent-card.json`, JSON-RPC `message/send` at `https://www.fone.me/{link}/a2a`.

## Get your own

Make your own agent link at [fone.me](https://www.fone.me) — or see [fone.me for business](https://www.fone.me/for-business).

Privacy: https://www.fone.me/privacy · Terms: https://www.fone.me/terms · Operated by zwilio.
