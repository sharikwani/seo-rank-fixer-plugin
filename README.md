# SEO Rank Fixer for Claude

Your Google Search Console data and the SEO fixes worth the most clicks, inside Claude.

[SEO Rank Fixer](https://seorankfixer.com) reads your Search Console data and ranks every fix (pages stuck on page two, titles that don't get clicked, pages competing with each other) by the extra clicks it could win. This plugin brings that into Claude Code and Claude, so you can ask about your rankings in plain words and apply fixes straight to your site's code.

## Install in Claude Code

```
/plugin marketplace add sharikwani/seo-rank-fixer-plugin
/plugin install seo-rank-fixer@seo-rank-fixer
```

Then run `/mcp`, pick **seo-rank-fixer** and sign in with your SEO Rank Fixer account. The free plan is enough to start: no card needed.

## What you get

| Command | What it does |
| --- | --- |
| `/seo-rank-fixer:audit example.com` | Full review: performance against the last period, the three fixes worth the most clicks, losing queries and a homepage scan |
| `/seo-rank-fixer:weekly-report` | What changed across all your sites and the one fix to make this week |
| `/seo-rank-fixer:fix-page https://example.com/page` | Scans a page, finds its fixes and applies them to your code (you approve the diff first) |

You can also just ask: *"Why did my clicks drop last week?"* or *"What should I fix first on example.com?"* Claude uses SEO Rank Fixer's tools to answer from your real data.

## Tools

| Tool | Plan |
| --- | --- |
| `list_sites`, `site_performance`, `top_fixes`, `scan_page` | Free |
| `opportunities`, `search_report` (queries and pages), ranges beyond 28 days | Starter |
| `search_report` (countries and devices), `write_fix` (AI Fixer) | Pro |

## Claude (web and desktop) and ChatGPT

No plugin needed: add the connector.

- **Claude:** Settings → Connectors → Add custom connector → `https://seorankfixer.com/api/mcp`
- **ChatGPT:** Settings → Apps & Connectors → Advanced settings → Developer mode → Create → `https://seorankfixer.com/api/mcp`, OAuth

Both show your fixes, performance and page scans as interactive cards. To give Claude the same SEO know-how the plugin has, upload [`claude-ai-skill/seo-rank-fixer.zip`](claude-ai-skill/seo-rank-fixer.zip) under Settings → Capabilities → Skills.

Full setup for every app: https://seorankfixer.com/connectors

## Privacy

The plugin holds no code that runs on your machine: it points Claude at `https://seorankfixer.com/api/mcp` and adds instructions. You sign in with OAuth and approve access on seorankfixer.com, and you can disconnect at any time under Settings → Connected AI apps. See the [privacy policy](https://seorankfixer.com/privacy).

## Support

mail2sharik@gmail.com

## License

MIT
