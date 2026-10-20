---
name: seo-rank-fixer
description: Use when the user asks about their website's Google rankings, Search Console clicks or impressions, traffic drops, keywords, SEO fixes, page titles or meta descriptions, or how a page shows up in Google or AI answers. Answers with the user's real Search Console data from SEO Rank Fixer.
---

# SEO Rank Fixer

SEO Rank Fixer reads the user's Google Search Console data and ranks SEO fixes by the extra clicks each could win.

## Start here

1. Call `list_sites` first to get site ids and the user's plan.
2. If there are no sites, tell the user to add one at https://seorankfixer.com/dashboard after connecting Google Search Console.
3. For "how is my site doing", call `site_performance`. For "what should I fix", call `top_fixes`. For any public URL, call `scan_page`.

## Tools

| Tool | Use it for | Plan |
| --- | --- | --- |
| `list_sites` | Site ids, sync status, the plan | Free |
| `site_performance` | Clicks, impressions, CTR, position vs the previous period | Free (28 days); longer ranges Starter |
| `top_fixes` | The 5 fixes worth the most clicks, with why and steps | Free |
| `scan_page` | Score any public URL for SEO, answer-engine and AI-crawler issues | Free |
| `opportunities` | Every open fix, filterable by site and type | Starter |
| `search_report` | Top queries or pages; countries and devices | Starter; countries and devices Pro |
| `write_fix` | AI-written titles, meta descriptions, content briefs, answer blocks | Pro (uses AI credits) |

## Rules

- Quote only numbers the tools return, and say which date range they cover.
- When a tool says a feature needs another plan, pass that on in one line with the link it gives.
- Call `write_fix` only when the user wants a fix written, one fix at a time, because it uses AI credits.
- SEO Rank Fixer never changes the user's website. Give the user the exact text to paste.
