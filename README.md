# OSINTverse for Claude Code

A Claude Code plugin that connects the [OSINTverse](https://osintverse.com) remote MCP server and adds an investigation skill: quote before you spend, stay inside a budget, file results into Cases, pivot deliberately, and report findings without overstating them.

## Install

```text
/plugin marketplace add OSINTVerseHQ/osintverse-agent-plugin
/plugin install osintverse@osintverse
```

Then run `/mcp` and sign in to OSINTverse. On the consent screen pick the wallet to bill and set a daily cap. New connections start in sandbox mode (sample data, nothing charged) until you switch them to live from Dashboard → API keys → Agents.

From a shell:

```bash
claude plugin marketplace add OSINTVerseHQ/osintverse-agent-plugin
claude plugin install osintverse@osintverse
```

## What you get

- **MCP server** `osintverse` at `https://osintverse.com/mcp` (OAuth 2.1; an `ov_` API key also works). Tools for providers and prices, quotes, single and bulk searches, Cases, and your balance. Paid tools ask for confirmation.
- **Skill** `/osintverse:osint-investigation`, which Claude also picks up on its own when you ask it to look something up.
- **Prompts** from the server: `/osintverse:investigate_email`, `investigate_username`, `investigate_domain`, `investigate_phone`, `investigate_wallet`, plus `summarise_case` and `pivot_case` for an existing case.

## Other agents

The skill is plain Markdown at [`plugins/osintverse/skills/osint-investigation/SKILL.md`](plugins/osintverse/skills/osint-investigation/SKILL.md). Copy it into any agent that reads skills or instructions (Claude Agent SDK, Cursor rules, `AGENTS.md`). Setup for other clients: https://osintverse.com/docs/mcp/setup and https://osintverse.com/docs/mcp/frameworks.

Use OSINTverse only for lawful investigations. Provider results are third-party data; treat them as untrusted input.

Support: hi@osintverse.com · MIT licensed.
