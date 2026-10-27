---
name: router
description: "The front door to Upturn Lift. Works out where a site is in its run order and sends the owner to the one skill that fits right now, including the projects lifecycle (plan, scope, build, test). Use when the owner asks \"what can Upturn Lift do\", \"what should I do next\", \"what's next for my site\", \"help me grow my site\", \"catch up on Upturn Lift\", \"run whatever is pending\", types /lift:router, or makes any open-ended website, marketing or conversion request that doesn't clearly match one skill."
allowed-tools: Read
---

# Upturn Lift router

You route; the other skills do the work. Pick the **single best** next step, not a menu.

## Step 1: Where is the site?

Call `list_sites` and pick the site. If there's more than one and the owner hasn't said which, ask. If the connector isn't signed in, or no site has a confirmed brief and no scans, hand over to **onboard** (`/lift:onboard`).

Then call `get_run_order` with the `site_id` and `purpose: check`.

## Step 2: Route

| The owner says something like… | Route to |
|---|---|
| "set me up", "get started", "connect my site" | **onboard** |
| "set up a new site", "add a site", "add https://… to Upturn Lift", a site that isn't in `list_sites` | **onboard** (it adds the site, then sets it up) |
| "what is this site for", "research the brief", "what's the commercial goal" | **site-brief** |
| "set team goals", "set goals for my teams", "set up the goals" | **onboard**, its team-goals step only (or the one team's skill if they name a team) |
| "audit this page", "full audit for scan 42", "audit my pending pages", "review the latest scan" | **page-audit** |
| "catch up", "run whatever is pending", "do my weekly run" | **page-audit** in catch-up mode (`get_run_order` with `purpose: run`) |
| "marketing strategy", "channel plan", "priorities", "quick wins", "90-day plan" | **site-strategy** |
| "what should I do first", "most important tasks", "to-do list", "plan of work" | **task-plan** |
| "fix the tasks", "do the developer tasks" (in Claude Code) | **task-plan**, do mode |
| "test the fixes", "did that work", "verify the shipped tasks" | **task-plan**, test mode |
| "what should we work on next", "plan projects", "turn the reports into projects", "what are the big bets" | **projects** (the CEO) |
| "scope P-3", "scope the project" | **project-scope** |
| "build P-3", "action P-3", "create a PR for the project" (in Claude Code, in the site's repo) | **project-build** |
| "test the project", "test P-3", "is the project working" | **project-test** |
| "proposal", "quote", "pitch", "scope of work for a client" | **client-proposal** |
| A marketing goal ("grow organic traffic", "more sales or enquiries", "improve our Google Ads", "bring customers back", "what should marketing do this quarter"), or the marketing team | **marketing-team** |
| A shop-floor goal ("sell more from the store", "fix our product pages", "improve the feed", "what should we merchandise"), or the ecommerce team | **ecommerce-team** |
| A technical goal ("make the site safer", "make the site faster", "what should my developer fix"), or the technical team | **technical-team** |
| A product goal ("what should we build next", "improve activation", "more sign-ups using the product"), or the product team | **product-team** |
| "refresh the brief and the plan", "keep the work on the goal", or client services / the account team | **client-services-team** |
| Any other broad goal, or "run a team" without naming one | the team whose goals fit (from `list_departments`), or ask which as multiple choice |
| "product strategy", "product roadmap", "what should we build next", pricing and packaging, product-market fit, reaching mainstream customers | **product-strategy** (or **product-team** for the whole team) |
| "security audit", "vulnerability or CVE check", "is my store secure", "security report for my developers" | **security-audit** |
| Broken links, redirects, titles, canonicals, anything site-wide | `get_seo_audit` directly; offer **site-strategy** after |
| "how do we rank", "which terms moved", "track this keyword" | `get_rankings` directly (`save_tracked_keywords` to add or remove terms); offer **site-strategy** after |
| "keyword research", "what do competitors rank for", "keyword gap", "who links to my competitors", backlinks | `get_keyword_data` directly (kind `gap`, `ranking`, `links` or `link_gap`; Growth and Agency plans); offer to track the best gap terms with `save_tracked_keywords`, then **site-strategy** |

For an open request ("help me grow sales"), follow the run order: route to the first step that's **ready**. If a step is **locked**, say what's locking it and route to that step instead. Once the run order is done and at least one team has reported, the next bigger step is usually **projects**; if a project is waiting on the owner (proposed, ready to deploy or failed), say so first.

## Step 3: Say it in one line

"You've got 4 scans waiting for an audit. I'll audit them now, highest priority first. Ready?" Then, on a yes, run that skill. When the owner may want it again, give its command too (e.g. `/lift:marketing-team <site UUID>`).

## Never

- Read the whole catalogue out. Name the one step, and at most two alternatives if asked.
- Skip the run order: the server refuses a strategy before the audits and a plan before the strategy.
