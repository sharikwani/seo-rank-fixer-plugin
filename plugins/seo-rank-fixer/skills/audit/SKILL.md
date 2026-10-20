---
name: audit
description: Full SEO review of one of the user's sites from its Search Console data, with the fixes ranked by the clicks they could win. Use when the user asks for an SEO audit, review or health check of their site.
argument-hint: "[site, e.g. example.com]"
---

# SEO audit

Audit the site the user named in `$ARGUMENTS` (or ask which one if they have several and named none).

1. Call `list_sites`. Match the site by domain. If it is not there, say so and point them to https://seorankfixer.com/dashboard to add it.
2. Call `site_performance` for the site (28 days, and 3 months too if the plan allows).
3. Call `top_fixes` for the site. If the plan includes them, also call `opportunities` (limit 25) and `search_report` for `query` with `filter: "losing"`.
4. Call `scan_page` on the site's homepage.

Then write the audit:

- **Snapshot:** clicks, impressions, CTR, average position, each with the change against the previous period, and the date range.
- **Fix first:** the three fixes worth the most clicks, each with the estimated extra clicks a month, why, and the steps.
- **Losing ground:** queries or pages that dropped, if you have them.
- **Homepage scan:** the score and the high-severity findings.
- **Next step:** one sentence on what to do this week.

Keep it under 400 words. Use only the numbers the tools return. If a step needs a higher plan, say so once at the end with the link the tool gave.
