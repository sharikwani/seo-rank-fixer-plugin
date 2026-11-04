---
name: seo-rank-fixer
description: Use when the user asks about their website's Google rankings, Search Console clicks or impressions, traffic drops, keywords, SEO fixes, page titles or meta descriptions, or how a page shows up in Google or AI answers. Answers with the user's real Search Console data from SEO Rank Fixer.
---

# SEO Rank Fixer

SEO Rank Fixer reads the user's Google Search Console data and ranks SEO fixes by the extra clicks each could win.

## Start here

1. Call `list_sites` first to get site ids.
2. If there are no sites, tell the user to add one at https://seorankfixer.com/dashboard after connecting Google Search Console.
3. For "how is my site doing", call `site_performance`. For "what should I fix", call `top_fixes`. For any public URL, call `scan_page`.

## Tools

| Tool | Use it for |
| --- | --- |
| `list_sites` | Site ids and sync status |
| `site_performance` | Clicks, impressions, CTR, position vs the previous period |
| `top_fixes` | The fixes worth the most clicks, with why and steps |
| `scan_page` | Score any public URL for SEO, answer-engine and AI-crawler issues |
| `index_status` | Which pages are in Google's index, and why the others are not (URL Inspection) |
| `site_audit` | Latest crawl of a site: health score out of 100, errors, warnings and notices, and the problems most worth fixing first with how to fix each. Read-only, never starts a crawl |
| `listing_plan` | Checklist of trusted places to list a site for backlinks (directories, profiles, review sites), with the user's progress |
| `opportunities` | Every open fix, filterable by site and type |
| `search_report` | Top queries or pages; countries and devices |
| `write_fix` | Suggested titles, meta descriptions, content briefs, answer blocks |

## Rules

- Quote only numbers the tools return, and say which date range they cover.
- When a tool says a feature is not included in the user's current plan, say so in one plain line. Do not promote plans, prices or upgrades.
- Call `write_fix` only when the user wants a fix written, one fix at a time.
- SEO Rank Fixer never changes the user's website. Give the user the exact text to paste.
