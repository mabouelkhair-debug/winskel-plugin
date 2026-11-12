# Winskel Space plugin

Winskel Space is one shared memory for a team and its AI agents. A Space holds the project's files, the decisions people and agents made (with the reason and what they replaced), handoffs between agents, and conversations. This plugin connects your AI app to Winskel's hosted MCP server so it can read and add to your Spaces.

One package, five apps:

| App | Manifest | MCP config |
| --- | --- | --- |
| Claude Code | `.claude-plugin/plugin.json` | `.mcp.json` |
| ChatGPT and Codex | `.codex-plugin/plugin.json` | `.mcp.json` |
| Cursor | `.cursor-plugin/plugin.json` | `mcp.json` |
| Gemini CLI and Antigravity CLI | `gemini-extension.json` | inline (`httpUrl`) |

All of them point at the same server: `https://space.winskel.com/api/mcp`. Sign in happens with OAuth in your browser the first time a tool runs. No API key or token is stored in this package.

## What you need

- A Winskel account (free plan available) at https://space.winskel.com
- Access to at least one Space

## Install

- **Claude:** add the Winskel connector from the Claude connectors directory. In Claude Code:

  ```
  /plugin install winskel --marketplace mabouelkhair-debug/winskel-plugin
  ```
- **ChatGPT and Codex:** install Winskel Space from the plugin directory.
- **Cursor:** install Winskel from the Cursor marketplace.
- **Gemini CLI:** `gemini extensions install https://github.com/mabouelkhair-debug/winskel-plugin`

Then ask your AI: "Use Winskel to catch me up on my Space."

## What it can do

- Read a Space's files, decisions, latest handoffs and conversations
- Save documents and record handoffs (what was done, what is open, which checks ran)
- Ask a teammate's assistant about the shared work, or ask a person for a decision
- Request a review or a build from a teammate's connected agent

Every tool is annotated as read only or write, so your app asks before any write.

## Privacy Policy

Full policy: https://winskel.com/privacy

- **What we collect:** your name, email and profile picture from Google sign in, and what you or your authorized apps publish to a Space (files, decisions, handoffs, messages).
- **How it is used and stored:** to run your Spaces and control who can see them. Records are stored with Supabase and the service runs on Vercel.
- **Sharing:** Space content is visible only to the Space's members and the apps they authorize. The AI app you connect processes what it reads through this plugin. Payments go through Stripe. We do not sell your data.
- **Retention:** records are kept while your account exists. You can ask for deletion; some records may be kept for security or legal reasons.
- **Contact:** ahmed@winskel.com (Winskel, Ontario, Canada).

## Support

https://winskel.com/contact or ahmed@winskel.com
