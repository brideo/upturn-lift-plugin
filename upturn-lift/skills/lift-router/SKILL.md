---
name: lift-router
description: "The front door to Upturn Lift. Works out where a site is in its run order and sends the owner to the one skill that fits right now. Use when the owner asks \"what can Upturn Lift do\", \"what should I do next\", \"what's next for my site\", \"help me grow my site\", \"catch up on Upturn Lift\", \"run whatever is pending\", or makes any open-ended website, marketing or conversion request that doesn't clearly match one skill."
allowed-tools: Read
---

# Upturn Lift router

You route; the other skills do the work. Pick the **single best** next step, not a menu.

## Step 1: Where is the site?

Call `list_sites` and pick the site. If there's more than one and the owner hasn't said which, ask. If the connector isn't signed in, or no site has a confirmed brief and no scans, hand over to **lift-onboard**.

Then call `get_run_order` with the `site_id` and `purpose: check`.

## Step 2: Route

| The owner says something like… | Route to |
|---|---|
| "set me up", "get started", "connect my site" | **lift-onboard** |
| "set up a new site", "add a site", "add https://… to Upturn Lift", a site that isn't in `list_sites` | **lift-onboard** (it adds the site, then sets it up) |
| "what is this site for", "research the brief", "set up the goals" | **site-brief** |
| "audit this page", "full audit for scan 42", "audit my pending pages", "review the latest scan" | **page-audit** |
| "catch up", "run whatever is pending", "do my weekly run" | **page-audit** in catch-up mode (`get_run_order` with `purpose: run`) |
| "marketing strategy", "channel plan", "priorities", "quick wins", "90-day plan" | **site-strategy** |
| "what should I do first", "most important tasks", "to-do list", "plan of work" | **task-plan** |
| "fix the tasks", "do the developer tasks" (in Claude Code) | **task-plan**, do mode |
| "test the fixes", "did that work", "verify the shipped tasks" | **task-plan**, test mode |
| "proposal", "quote", "pitch", "scope of work for a client" | **client-proposal** |
| Broken links, redirects, titles, canonicals, anything site-wide | `get_seo_audit` directly; offer **site-strategy** after |

For an open request ("help me grow sales"), follow the run order: route to the first step that's **ready**. If a step is **locked**, say what's locking it and route to that step instead.

## Step 3: Say it in one line

"You've got 4 scans waiting for an audit. I'll audit them now, highest priority first. Ready?" Then, on a yes, run that skill.

## Never

- Read the whole catalogue out. Name the one step, and at most two alternatives if asked.
- Skip the run order: the server refuses a strategy before the audits and a plan before the strategy.
