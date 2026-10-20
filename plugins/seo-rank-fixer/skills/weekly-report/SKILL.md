---
name: weekly-report
description: A short "what changed in Google this week and what to fix" summary across all the user's sites. Use when the user asks for a weekly SEO report, an update, or how their sites are doing.
---

# Weekly SEO report

1. Call `list_sites`. Skip sites whose status is not synced and mention them at the end.
2. For each site (at most 5), call `site_performance` with range `7d`, then `top_fixes` for that site. On the Free plan the tool returns the last 28 days instead and says so: report those, label them "last 28 days", and don't call them weekly.

Write one short block per site:

- **example.com:** clicks for the period and the change against the period before, impressions and the change, average position and how many places it moved.
- **Fix this week:** the single fix worth the most clicks, with its estimated extra clicks a month and its first step.

Finish with one line naming the biggest win or drop across all sites. Use only the numbers the tools return, and keep the whole report readable in under a minute.
