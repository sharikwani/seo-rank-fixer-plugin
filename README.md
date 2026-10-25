# SEO Rank Fixer: SEO MCP server for Claude and ChatGPT (Google Search Console)

[![M8ven Score](https://m8ven.ai/badge/mcp/sharikwani-seo-rank-fixer-plugin-3guueu?v=0dd7b74c3ec5f582d298115e657ba84e)](https://m8ven.ai/mcp/sharikwani-seo-rank-fixer-plugin-3guueu?s=readme)

[SEO Rank Fixer](https://seorankfixer.com) is an SEO MCP server and Claude and ChatGPT plugin that connects your Google Search Console data to your AI assistant, so website owners and developers can ask what to fix and get answers ranked by the extra Google clicks each fix could win. It also runs a site audit and page scans, all through one remote MCP endpoint: `https://seorankfixer.com/api/mcp`.

<p>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/top-fixes-dark.png">
    <img src="assets/screenshots/top-fixes-light.png" alt="SEO Rank Fixer in Claude: a card listing the SEO fixes worth the most extra Google clicks, ranked from your Search Console data" width="720">
  </picture>
</p>

## What it does

SEO Rank Fixer reads your Google Search Console data and ranks every fix (pages stuck on page two, titles that rank but don't get clicked, pages competing with each other for the same search) by the extra clicks it could win. This repo is the plugin and connector listing that brings that into [Claude Code, Claude.ai, ChatGPT and other MCP clients](https://seorankfixer.com/connectors).

With it you can ask, in plain words:

- How did my site do in Google over the last 28 days, compared with the period before?
- What is the one SEO fix worth the most clicks right now?
- Which queries and pages bring the most traffic, and which are losing it?
- Which of my pages are not in Google's index, and why?
- What are the biggest problems found by a site audit (broken pages and links, redirects, titles, duplicates, indexing)?
- Is this page ready for Google, answer engines and AI crawlers?
- Where can I list my site to earn its first backlinks?

In Claude Code it can also apply a fix to your site's code, and you approve the diff before anything is saved.

## Install in Claude Code

```
/plugin marketplace add sharikwani/seo-rank-fixer-plugin
/plugin install seo-rank-fixer@seo-rank-fixer
```

Then run `/mcp`, pick **seo-rank-fixer** and sign in with your SEO Rank Fixer account. The free plan is enough to start: no card needed.

| Command | What it does |
| --- | --- |
| `/seo-rank-fixer:audit example.com` | Full review: performance against the last period, the three fixes worth the most clicks, losing queries and a homepage scan |
| `/seo-rank-fixer:weekly-report` | What changed across all your sites and the one fix to make this week |
| `/seo-rank-fixer:fix-page https://example.com/page` | Scans a page, finds its fixes and applies them to your code (you approve the diff first) |

You can also just ask, for example *"Why did my clicks drop last week?"*, and Claude uses the tools below to answer from your real data.

Prefer not to use the plugin? In Claude Code you can add the server directly:

```
claude mcp add --transport http seo-rank-fixer https://seorankfixer.com/api/mcp
```

## Claude.ai and Claude desktop connector

No plugin needed: go to Settings, Connectors, Add custom connector and enter `https://seorankfixer.com/api/mcp`. Sign in with your SEO Rank Fixer account when asked. Fixes, performance and page scans show up as interactive cards in the chat.

To give Claude the same SEO know-how the plugin has, upload [`claude-ai-skill/seo-rank-fixer.zip`](claude-ai-skill/seo-rank-fixer.zip) under Settings, Capabilities, Skills.

<p>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/performance-dark.png">
    <img src="assets/screenshots/performance-light.png" alt="Google Search Console performance in an AI chat: clicks, impressions, CTR and average position against the previous period, with a trend chart" width="720">
  </picture>
</p>

## ChatGPT

In ChatGPT, open Settings, Apps & Connectors, Advanced settings, turn on Developer mode, then Create a connector with the URL `https://seorankfixer.com/api/mcp` and OAuth as the authentication. Sign in with your SEO Rank Fixer account and allow access. This repo also carries the [ChatGPT plugin manifest](chatgpt/plugin.json) and its [skill](chatgpt/skills/seo-rank-fixer/SKILL.md).

## Other MCP clients: Cursor, VS Code and more

SEO Rank Fixer is a remote MCP server over streamable HTTP with OAuth sign-in, so any MCP client that supports remote servers can use it. The URL is:

```
https://seorankfixer.com/api/mcp
```

**Cursor** (`.cursor/mcp.json`, or `~/.cursor/mcp.json` for all projects):

```json
{
  "mcpServers": {
    "seo-rank-fixer": {
      "url": "https://seorankfixer.com/api/mcp"
    }
  }
}
```

**VS Code** (`.vscode/mcp.json`):

```json
{
  "servers": {
    "seo-rank-fixer": {
      "type": "http",
      "url": "https://seorankfixer.com/api/mcp"
    }
  }
}
```

Your client will open a browser window to sign in. Step-by-step guides for each app are at [seorankfixer.com/connectors](https://seorankfixer.com/connectors). The server is also described in [`server.json`](server.json) for MCP registries.

## MCP tools

| Tool | What it returns | Plan |
| --- | --- | --- |
| `list_sites` | Your sites, sync status, your plan, AI credits left and renewal date. Called first | Free |
| `site_performance` | Clicks, impressions, CTR and average position against the previous period | Free (28 days); longer ranges Starter |
| `top_fixes` | The SEO fixes worth the most extra clicks, with why they matter and the steps | Free (top 3 fixes); paid plans top 5 |
| `scan_page` | Scores any public URL out of 100 for SEO, answer-engine and AI-crawler problems | Free (3 scans a day, first 3 findings in full); paid plans every finding, no daily limit |
| `site_audit` | The latest site audit crawl: health score out of 100 and its trend, errors, warnings and notices, what is new or fixed, and the problems most worth fixing first. Read-only, never starts a crawl | Free (top 3 problems with steps); paid plans every problem |
| `listing_plan` | A checklist of trusted places to list a site for backlinks (Google Business Profile, Bing, social profiles, review sites, directories) with your progress. Read-only | Free (top 5 essentials); paid plans the full list |
| `index_status` | Which pages are in Google's index and why others are not (not indexed, blocked by robots.txt, noindex, a different URL) | Free (summary and 3 example pages); Starter and up every problem page |
| `site_profile` | Your own description of the business behind a site (offers, audience, voice, spelling) so AI-written copy stays on-brand | Free |
| `opportunities` | Every open SEO opportunity, best first, filterable by site and type | Starter |
| `search_report` | Top queries or pages against the previous period; countries and devices | Starter (queries and pages); Pro (countries and devices) |
| `write_fix` | AI-written title and meta description options, content refresh briefs, answer blocks and plans for competing pages. Uses AI credits | Pro and up |

When the server's search data provider is enabled, it also offers `competitor_gap` (searches a competitor ranks for in Google's top 20 that you do not; Pro and up), `rank_tracking` (daily Google positions of the searches you track; Starter and up) and `ai_answers` (how AI assistants answered the customer questions you saved, and whether they name or cite your site; Pro and up). All tools are read-only except `write_fix`, which only writes text for you and changes nothing on your site. The server also offers ready-made prompts: `audit_site`, `biggest_win`, `weekly_review`, `fix_page` and `content_ideas`.

<p>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/screenshots/page-scan-dark.png">
    <img src="assets/screenshots/page-scan-light.png" alt="SEO page scan result in chat: a score out of 100 and each finding with its severity and what to change" width="720">
  </picture>
</p>

## Example prompts

- "Which sites do I have in SEO Rank Fixer?"
- "What should I fix first on example.com to get more Google clicks?"
- "Why did my clicks drop last week?"
- "Which search queries bring example.com the most clicks?"
- "Run through the latest site audit for example.com and tell me what to fix first."
- "Scan https://example.com/pricing for SEO and AI-crawler problems."
- "Which of my pages aren't indexed by Google, and why?"
- "Where should I list example.com to get my first backlinks?"
- "Write a better title and meta description for my slowest-growing page." (Pro)

## Free vs paid

You can start on the free plan with no card. It covers one site and gives you a working preview: the last 28 days of performance, your top 3 fixes, an index summary, the top 3 problems from the site audit, the top 5 essential listings and 3 page scans a day. Each answer says what the rest would add up to and which plan includes it.

| | Free | Starter | Pro and up |
| --- | --- | --- | --- |
| Performance, top fixes, index status, site audit, listing plan, page scans | Preview | Full | Full |
| Ranges beyond 28 days, every opportunity, top queries and pages | | Yes | Yes |
| Countries and devices, AI Fixer (`write_fix`) | | | Yes |

Current plans and prices are on [seorankfixer.com](https://seorankfixer.com).

## Privacy and permissions

SEO Rank Fixer only reads your data. It never changes your website or your Search Console settings, and the assistant cannot change your plan or billing. You sign in with OAuth and approve access on seorankfixer.com, and you can disconnect any time under Settings, Connected AI apps. This repo holds no code that runs on your machine: the plugin points your assistant at `https://seorankfixer.com/api/mcp` and adds instructions. Read the [privacy policy](https://seorankfixer.com/privacy) and [terms](https://seorankfixer.com/terms).

## FAQ

### Is there a Google Search Console MCP server?

Yes. SEO Rank Fixer is a remote MCP server at `https://seorankfixer.com/api/mcp` that reads your Search Console data (clicks, impressions, CTR, position, indexing) and turns it into ranked SEO fixes. You connect your Google Search Console to your SEO Rank Fixer account first, then your AI assistant to SEO Rank Fixer.

### Can Claude read my Search Console data?

Yes, through this plugin or the Claude.ai connector. Claude asks SEO Rank Fixer's tools and answers from your real numbers, within what your plan includes. It cannot see sites you have not connected.

### Does it work with ChatGPT?

Yes. Add it as a custom connector in ChatGPT with Developer mode, using the URL above and OAuth. See the [ChatGPT section](#chatgpt).

### Can I use it in Cursor or VS Code?

Yes, any MCP client that supports remote servers can use the URL `https://seorankfixer.com/api/mcp`. Config examples for Cursor and VS Code are above.

### Is it free?

There is a free plan with no card needed, which gives a preview of the main tools. Deeper reports and the AI Fixer need a paid plan. See [Free vs paid](#free-vs-paid).

### Can it change my website or Search Console?

No. The tools are read-only. `write_fix` writes suggested text, and in Claude Code you can ask Claude to apply it to your code, but you see and approve the diff first.

### Is it a site audit MCP, or only Search Console?

Both. `site_audit` returns the latest crawl of your site (health score, broken pages and links, redirects, titles, duplicates, indexing) and `scan_page` checks any single public URL. `site_audit` only reads the latest audit; it does not start a crawl from the assistant.

## Support

Email support@seorankfixer.com or see [seorankfixer.com/connectors](https://seorankfixer.com/connectors).

## License

[MIT](LICENSE)
