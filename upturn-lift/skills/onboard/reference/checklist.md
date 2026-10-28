# Setup checklist

`list_sites` (and `add_site`, for a site it has just added) returns each site's `setup` list: `step`, `label`, `status` (`done`, `skipped` or `pending`) and `url`. Give the owner the `url` exactly as returned. Don't build dashboard links yourself.

| Step | Who does it | What it unlocks | Done when |
|---|---|---|---|
| `claude` Connect Claude | Owner, in Claude | Everything below | The connector answers `list_sites` |
| `brief` Marketing brief | Claude researches, owner confirms | Every report, review and the strategy are ranked against it | Written and confirmed by the owner |
| `extension` Browser extension | Owner, in Chrome or Edge | Page scans, which page audits need | A scan exists for the site |
| `analytics` Google Analytics & Search Console | Owner, in the dashboard | Visits, conversions, revenue and search queries per page | Analytics is connected |
| `seo-audit` SEO audit | Owner starts it in the dashboard | The site-wide crawl the strategy reads | A crawl has finished |
| `store` Store access | Owner, in the dashboard | Product and order data for merchandising checks | Store API access saved |
| `ads` Google Ads & Merchant Center | Owner, in the dashboard (plans with Ads & Shopping) | Spend, revenue and ROAS per page; feed issues | Ads is connected |
| `pagespeed` PageSpeed API key | Owner, optional | Lighthouse runs and real-user Core Web Vitals | A key is saved |
| `github` Nightly runs on GitHub | Owner, optional | Audits, strategy and plan run every night on their Claude plan | The repo is set up |

Only steps the dashboard shows for this site are in the list. If a step is missing, it doesn't apply to their plan, so don't mention it.

## Getting started

`list_sites` and `add_site` also return `getting_started`: the six steps a new site works through, in this order, the same as the guide on the dashboard's Home. Each has `step`, `label`, `status` (`done`, `skipped` or `pending`), `url` and, where Claude does the work, a `hint`.

| Step | Done when |
|---|---|
| `integrations` Connect your integrations | Every setup step above is done or skipped |
| `brief` Confirm your marketing brief | The brief is written and confirmed |
| `seo_crawl` Crawl the site | An SEO crawl has finished (only where the crawler is available) |
| `page_audits` Audit your top pages with AI | At least one scanned page has an audit summary |
| `teams` Run each team | Every active team has reported at least once |
| `claude` Chat to Claude about what to fix | The site has at least one project |

The owner can skip a step on the dashboard. Skipped steps aren't nagged about; mention them once at most.

## Tone

- One step at a time, one line on why it matters, then the link.
- Plain words. "Connect Google Analytics so I can see which pages make money", not "authorise the GA4 property".
- If they say "skip", say "No problem, it's under Integrations whenever you want it" and move on.
