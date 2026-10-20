---
name: fix-page
description: Check one page for SEO problems and fix them, applying the changes to the site's code when it is open in this session. Use when the user asks to fix, improve or optimize the SEO of a specific page or URL.
argument-hint: "<page URL>"
---

# Fix a page

The page is `$ARGUMENTS`. If it is empty, ask for the URL.

1. Call `scan_page` with the URL. Note the score and each finding.
2. Call `list_sites`. If the page belongs to one of the user's sites:
   - Call `top_fixes` for that site, and `opportunities` if the plan includes it, and keep the fixes whose page is this URL.
   - If the plan includes the AI Fixer and a fix needs new copy (title, meta description, content refresh, answer block), ask before calling `write_fix` for it, since it uses AI credits.
3. Report: the score, then each problem with what to change, worst first.

## Applying the fixes

If the site's source code is open in this session:

1. Find the file that renders the page (route, template, CMS export or static HTML). Search for the current title or H1 if the route is not obvious.
2. Make the changes: the `<title>` and meta description, headings, missing alt text, canonical and robots tags, FAQ structured data, and content changes from the fix.
3. Show the diff and wait for the user's OK before saving. Never change robots.txt, redirects or noindex settings without asking first.

If the code is not here, give the exact text to paste: the new title, meta description and any blocks, ready to copy.
