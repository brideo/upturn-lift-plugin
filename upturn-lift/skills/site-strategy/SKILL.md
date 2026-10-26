---
name: site-strategy
description: "Write a site-level marketing strategy in Upturn Lift from the brief, every page audit, the SEO crawl, Google Analytics and Search Console: ranked priorities, a channel plan, quick wins, a 90-day plan and the KPIs to watch. Use when the owner asks for a \"marketing strategy\", \"channel plan\", \"priorities\", \"quick wins\", \"90-day plan\", \"where should I focus\" or \"refresh my strategy\"."
allowed-tools: Read, WebFetch, WebSearch
---

# Marketing strategy

1. Pick the site (`list_sites`), then call `get_run_order` with `purpose: check`. If the strategy step is **locked**, say what's locking it (usually the brief or pending audits) and offer that step instead (**site-brief** or **page-audit**).
2. Call `get_site_strategy_inputs`. It returns the brief, research pack, every page's scores and review verdicts, the open tasks with ids, the previous strategy and the method. **Follow that method.**
3. If the SEO crawl matters to a priority, read `get_seo_audit` so technical SEO ranks against everything else.
4. Write it against the brief's commercial goal, as a growth strategist. Cite scan and task ids so the owner can click through.
5. Save with `save_site_strategy`. Each save is a new version on the site's **Marketing Strategy** tab.
6. Summarise the top three priorities and the first quick win in a few lines. Then offer "what should I do first?" (**task-plan**).
