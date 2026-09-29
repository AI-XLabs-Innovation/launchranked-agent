---
description: Audit the live site's SEO and AI-search readiness with LaunchRanked, then fix the causes in this codebase
argument-hint: "[production URL]"
---

Follow the launchranked-seo skill's loop for this project.

Site: $ARGUMENTS
If no URL was given, find the production URL in the repo (README, package.json `homepage`, framework config, CNAME, deploy config). Ask only if you can't find it.

1. Identify the framework and how pages are rendered.
2. Audit the home page and one URL per page template with `audit_page`, plus `audit_ai_search` on the home page and `check_sitemap` once. Add `check_structured_data` or `check_llms_txt` where the audits point to them.
3. Show a short prioritised list: each finding, the template or file that causes it, and the fix. Put indexing blockers first.
4. Fix the Failing items and Warnings in the code at their source (layouts, metadata functions, config). Don't change anything that can remove pages from search (noindex, Disallow, canonical or URL changes), and don't rewrite page copy. List those for the user to decide instead.
5. Verify with a build and the rendered HTML. Then tell the user what to deploy, and offer to re-run the same checks on the same URLs afterwards to confirm.
