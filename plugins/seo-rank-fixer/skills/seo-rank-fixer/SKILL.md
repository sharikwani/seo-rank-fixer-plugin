---
name: seo-rank-fixer
description: Use when the user asks about their website's Google rankings, Search Console clicks or impressions, traffic drops, keywords, SEO fixes, page titles or meta descriptions, or how a page shows up in Google, ChatGPT or other AI answers. Uses the SEO Rank Fixer tools to answer with the user's real data.
---

# SEO Rank Fixer

SEO Rank Fixer reads the user's Google Search Console data and ranks SEO fixes by the extra clicks each could win. Its tools are on the `seo-rank-fixer` MCP server. If they are missing or say the user is signed out, tell the user to run `/mcp`, pick **seo-rank-fixer** and sign in with their SEO Rank Fixer account (free at https://seorankfixer.com).

## Tools

| Tool | Use it for | Plan |
| --- | --- | --- |
| `list_sites` | Site ids, sync status, the plan. **Call first.** | Free |
| `site_performance` | Clicks, impressions, CTR, position vs the previous period | Free (28 days); longer ranges Starter |
| `top_fixes` | The 5 fixes worth the most clicks, with why and steps | Free |
| `scan_page` | Score any public URL for SEO, answer-engine and AI-crawler issues | Free |
| `opportunities` | Every open fix, filterable by site and type | Starter |
| `search_report` | Top queries or pages; countries and devices | Starter; countries/devices Pro |
| `write_fix` | AI-written titles, meta descriptions, content briefs, answer blocks | Pro (uses AI credits) |

## Rules

- Quote only numbers the tools return. Never estimate traffic yourself.
- Say which date range the numbers cover.
- When a tool says a feature needs another plan, pass that on in one line with the upgrade link it gives. Don't push upgrades otherwise.
- Lead with the fix worth the most clicks, in plain words, then the steps.
- `write_fix` spends AI credits: call it only when the user wants the fix written, one fix at a time.
- When the site's source code is open in this session, offer to apply a fix (title tag, meta description, headings, content) to the right file, and show the diff before saving.
