# LaunchRanked for AI agents

SEO and AI search for your codebase, in Claude Code, Cursor, Codex, OpenClaw and other agents. LaunchRanked checks the **live site**. Your agent fixes the cause in **your code**, then checks again after you deploy.

This repo is a Claude Code plugin (`.claude-plugin/`) and an [Agent Plugins](https://agent-plugins.org) plugin (`plugin.json`) in one. It contains:

- The LaunchRanked MCP server, `https://launchranked.com/mcp`. You sign in with your LaunchRanked account (free); no API key needed.
- The `launchranked-seo` skill: the audit, fix and verify playbook, with framework-specific fixes.
- Two Claude Code commands: `/launchranked:seo-audit [url]` (audit and fix) and `/launchranked:launch-plan [product]` (directory and launch plan, with listing copy).

## Tools

- `audit_page`: on-page SEO audit with a score and a fix for every failing check
- `audit_ai_search`: readiness for ChatGPT, Perplexity, Claude and Google AI Overviews
- `check_page_speed`, `check_structured_data`, `check_sitemap`, `check_llms_txt`, `check_links`
- `domain_rating`: Domain Rating by Ahrefs for up to 25 domains
- `find_directories`: startup directories ranked by fit for your product, with link type and pricing
- With an Autopilot site: `get_account`, `ai_visibility_report`

## Install

### Claude Code

```text
/plugin marketplace add AI-XLabs-Innovation/launchranked-agent
/plugin install launchranked@launchranked
```

Then run `/mcp`, choose **launchranked** and sign in. Try `/launchranked:seo-audit`.

### Cursor

[Add the server to Cursor](https://cursor.com/install-mcp?name=launchranked&config=eyJ1cmwiOiJodHRwczovL2xhdW5jaHJhbmtlZC5jb20vbWNwIn0%3D). Cursor opens the sign-in the first time it connects. Then add the skill:

```sh
npx skills add AI-XLabs-Innovation/launchranked-agent -a cursor
```

### Codex

```sh
codex mcp add launchranked --url https://launchranked.com/mcp
npx skills add AI-XLabs-Innovation/launchranked-agent -a codex
```

Codex opens the sign-in when you add the server. If it doesn't, run `codex mcp login launchranked`.

### OpenClaw

```sh
openclaw mcp set launchranked '{"url":"https://launchranked.com/mcp","transport":"streamable-http","auth":"oauth"}'
openclaw mcp login launchranked
openclaw skills install @piyushgit011/launchranked-seo --global
```

### Other agents

Add `https://launchranked.com/mcp` to your agent's MCP settings; it opens the sign-in. `npx skills add AI-XLabs-Innovation/launchranked-agent` installs the skill into most agents. For scripts or CI, create an API key at https://launchranked.com/app/account and send it as `Authorization: Bearer lrk_...`.

ChatGPT and Claude on the web: see https://launchranked.com/docs/mcp.

## Limits

The checks have the same per-minute fair-use limits as the free tools on launchranked.com, and no daily cap. Domain Rating lookups are counted per day: 25 domains on a free account, 250 on Autopilot. Failed lookups don't count.

## Privacy

The server receives the URLs, domains and product descriptions your agent sends. What we keep, and for how long: https://launchranked.com/privacy#ai-assistants

## License

MIT
