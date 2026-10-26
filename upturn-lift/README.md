<img src=".claude-plugin/icon.png" alt="Upturn Lift" width="72" height="72" align="right">

# Upturn Lift

Upturn Lift scans your website the way a shopper sees it and measures what's holding sales back. This plugin connects your Upturn Lift account to Claude and walks you through setup. Claude then writes your marketing brief, audits your pages, plans your marketing strategy and ranks the tasks that matter most. Everything is saved back to your Upturn Lift dashboard.

You need an Upturn Lift subscription. See the plans at [upturnstudio.com.au/lift](https://upturnstudio.com.au/lift).

## Set up

**Claude Desktop, Cowork or claude.ai**

1. Open **Customize › Plugins**, click **Add**, then **Add marketplace**, and paste `brideo/upturn-lift-plugin`.
2. Install **Upturn Lift**.
3. Open the plugin's **Connectors** tab, click **Connect** and sign in with your [Upturn account](https://upturnstudio.com.au/login).
4. In a new chat, say **"set up Upturn Lift"**.

**Claude Code**

```
/plugin marketplace add brideo/upturn-lift-plugin
/plugin install lift@upturn
```

Then type `/mcp`, choose **upturn-lift**, sign in, and say **"set up Upturn Lift"** or type `/lift:onboard`.

> **Upgrading from 1.x?** In 2.0 the plugin is called `lift`, so its commands are `/lift:onboard`, `/lift:marketing-team` and so on (they were `/upturn-lift:…`). Uninstall the old `upturn-lift` plugin and install `lift` (in Claude Code: `/plugin uninstall upturn-lift@upturn`, then `/plugin install lift@upturn`). Your account and sites stay as they are, though you may need to sign the connector in again (`/mcp` in Claude Code, the plugin's **Connectors** tab elsewhere).


Setup checks the connector, picks your site, shows where it's up to, and links each dashboard step only you can do: the browser extension, Google Analytics and Search Console, and the SEO audit. Then it writes your marketing brief and asks for each team's goal. It takes 15 to 20 minutes.

## What you can say

| Say | What happens |
|---|---|
| "set up Upturn Lift" | Guided setup: connector, site, dashboard steps, then your marketing brief |
| "set up a new site: https://…" | Adds the site to your account and walks you through its setup |
| "what should I do next?" | Checks where your site is up to and picks the next step |
| "research my marketing brief" | Writes the brief every audit is ranked against |
| "audit my pending pages" | Full audits of every scan waiting, highest priority first |
| "run the full audit for scan 42" | Report, security, marketing and performance reviews and a summary for one page |
| "write my marketing strategy" | Priorities, channel plan, quick wins and a 90-day plan |
| "what should I do first?" | A ranked task plan across developer, content and marketing work |
| "fix the tasks" (Claude Code) | Works through the plan's developer tasks in your repo |
| "test the fixes" | Checks shipped tasks on the live site and marks each verified or failed |
| "write a proposal for this client" | A priced proposal PDF backed by the measurements |
| "set goals for my teams" | Asks each of your teams' questions and saves the goal each one works towards |
| "have marketing grow organic revenue" (`/lift:marketing-team`) | The team's head confirms the goal with you, splits it between specialists, runs them side by side and reports one ranked plan to Team › Reports |
| "make the site safer" (`/lift:technical-team`) | The same for the Technical team; `/lift:ecommerce-team`, `/lift:product-team` and `/lift:client-services-team` for the others your site has |
| "be my Head of Product" (`/lift:product-strategy`) | Who to win first, what mainstream customers still need, three bets and a roadmap for a product business |
| "run a security audit" | A passive, report-only review of your platform's known vulnerabilities, key pages and sign-in forms, ranked by severity for your developers |
| "what should we work on next?" (`/lift:projects`) | The CEO proposes a few projects from every team's findings, each with the number it should move, and saves the ones you approve to Projects |
| "build P-3" (Claude Code) | Builds a scoped project on its own branch, reviews it and opens a pull request |
| "catch up on Upturn Lift" | Runs whatever is pending, in order. Good as a weekly habit |

## Commands

| Command | What it does |
|---|---|
| `/lift:onboard` | Guided setup: connector, site, dashboard steps, the marketing brief and each team's goal |
| `/lift:marketing-team` | The Marketing team sets its goal with you, then the strategist, SEO, content, competitor and PPC specialists work on it |
| `/lift:ecommerce-team` | The Ecommerce team (stores and marketplaces): product pages, the feed and merchandising |
| `/lift:technical-team` | The Technical team: security, speed and page security, written for your developers |
| `/lift:product-team` | The Product team (software and marketplaces): the Head of Product's advisers, then a product strategy |
| `/lift:client-services-team` | The Client services team: the brief, the plan of work and proposals |
| `/lift:projects` | The CEO reads every team's report and proposes three to five projects with the metric each should move; you approve, change or drop each |
| `/lift:project-scope <project uuid>` | The project manager writes the scope: tasks, acceptance checks, risks and rollout |
| `/lift:project-build <project uuid>` | Claude Code, in your site's repo: builds the project on its own branch, reviews the code and opens a pull request |
| `/lift:project-test <project uuid>` | Once you've deployed it, checks each task on the live site and marks the project complete or failed |
| `/lift:site-brief`, `/lift:page-audit`, `/lift:site-strategy`, `/lift:task-plan`, `/lift:security-audit`, `/lift:product-strategy`, `/lift:client-proposal` | One job each |
| `/lift:router` | Works out the next step for your site |

Each team command takes an optional site: `/lift:marketing-team <site UUID or address>`. Without one, Claude lists your sites and asks which. You don't have to type commands: saying what you want works too.

## Projects

Projects turn the teams' findings into a few bigger bets, each with an owner, a pull request and a number it should move.

1. **Plan:** `/lift:projects`. The CEO reads every team's report, the goals and your numbers, and proposes three to five projects ranked by value, each with a baseline and a target. You approve, change or drop each one.
2. **Scope:** `/lift:project-scope <project uuid>`. The project manager writes what's in and out, the tasks and the checks that prove each is done.
3. **Build:** `/lift:project-build <project uuid>`, in Claude Code inside your site's code repository. Claude works each task on a `lift/p-…` branch, reviews the code, opens a pull request and marks the project ready to deploy. It never merges or deploys: you do, then press **It's live** on the project.
4. **Test:** `/lift:project-test <project uuid>`. Claude checks each task on the live site without changing anything. When everything passes the project is complete, and Lift measures its impact at 30, 60 and 90 days.

Every project and its timeline is on the **Projects** tab of your dashboard.

## Works better with

- Anthropic's **Marketing** plugin (Customize › Plugins › Browse plugins) for more thorough SEO, brand and competitor reviews.
- **Claude in Chrome**, so Claude can check the live page's mobile layout, console errors and memory.

## Help and privacy

- Questions or problems: [upturnstudio.com.au/contact](https://upturnstudio.com.au/contact).
- The connector only sees your own sites, and only while your subscription is active. Claude never submits forms, signs in or changes settings on your website. To disconnect, remove Upturn Lift under **Customize › Connectors**. [Privacy policy](https://upturnstudio.com.au/privacy).
