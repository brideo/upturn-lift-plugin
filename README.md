<p align="center">
  <img src="upturn-lift/.claude-plugin/icon.png" alt="Upturn Lift" width="96" height="96">
</p>

<h1 align="center">Upturn Lift for Claude</h1>

<p align="center">
  The Claude plugin for <a href="https://upturnstudio.com.au/lift">Upturn Lift</a>: connect your account, get walked through setup, and let Claude audit your website and plan what to fix first.
</p>

---

[Upturn Lift](https://upturnstudio.com.au/lift) scans your website the way a shopper sees it and measures what's holding sales back. This plugin connects your Upturn Lift account to Claude. Claude then writes your marketing brief, audits your pages, plans your marketing strategy and ranks the tasks that matter most. Everything is saved back to your Upturn Lift dashboard.

You need an Upturn Lift subscription. [See the plans](https://upturnstudio.com.au/lift).

## Set up

### Claude Desktop, Cowork or claude.ai

1. Open **Customize › Plugins**, click **Add**, then **Add marketplace**, and paste:
   ```
   brideo/upturn-lift-plugin
   ```
2. Install **Upturn Lift**.
3. Open the plugin's **Connectors** tab, click **Connect** and sign in with your [Upturn account](https://upturnstudio.com.au/login).
4. In a new chat, say **"set up Upturn Lift"**.

### Claude Code

```
/plugin marketplace add brideo/upturn-lift-plugin
/plugin install lift@upturn
```

Then type `/mcp`, choose **upturn-lift**, sign in with your Upturn account, and say **"set up Upturn Lift"** or type `/lift:onboard`.

> **Upgrading from 1.x?** In 2.0 the plugin is called `lift`, so its commands are `/lift:onboard`, `/lift:marketing-team` and so on (they were `/upturn-lift:…`). Uninstall the old `upturn-lift` plugin and install `lift` (in Claude Code: `/plugin uninstall upturn-lift@upturn`, then `/plugin install lift@upturn`). Your account and sites stay as they are, though you may need to sign the connector in again (`/mcp` in Claude Code, the plugin's **Connectors** tab elsewhere).


## What setup does

Say "set up Upturn Lift" and Claude:

1. Checks the connector is signed in.
2. Picks your website, or adds it to your account if it's new. Say "set up a new site: https://…" any time to onboard another.
3. Shows where it's up to: brief, page audits, marketing strategy, task plan.
4. Links each dashboard step only you can do, one at a time: the browser extension, Google Analytics and Search Console, and the SEO audit. Skip any you like.
5. Researches and saves your marketing brief, the goal every audit is ranked against.
6. Walks you through each of your teams (Marketing, then Ecommerce or Product where they apply, Technical and Client services) and saves the goal each one works towards.
7. Offers to start the Marketing team, and tells you the next thing to say.

Progress lives in your Upturn Lift account, so come back any time and say "what should I do next?".

## What's inside

The plugin is in [`upturn-lift/`](upturn-lift). See [its README](upturn-lift/README.md) for everything you can ask.

| Part | What it is |
|---|---|
| Connector | `https://upturnstudio.com.au/mcp/lift`, signed in with your Upturn account |
| `onboard` | The guided setup (`/lift:onboard`) |
| `router` | Works out the next step for your site |
| `site-brief`, `page-audit`, `site-strategy`, `task-plan`, `security-audit`, `client-proposal` | One skill per job |
| `marketing-team`, `ecommerce-team`, `technical-team`, `product-team`, `client-services-team` | One skill per team: its head asks for the goal, splits it between specialists and reports one ranked plan (`/lift:marketing-team` and so on) |
| `product-strategy` | The Head of Product: beachhead, whole product, activation, positioning, bets and roadmap |
| `agents/lift-*` | The specialists a team hands work to (sub-agents in Claude Code) |

## Commands

| Command | What it does |
|---|---|
| `/lift:onboard` | Guided setup: connector, site, dashboard steps, the marketing brief and each team's goal |
| `/lift:marketing-team` | The Marketing team sets its goal with you, then the strategist, SEO, content, competitor and PPC specialists work on it |
| `/lift:ecommerce-team` | The Ecommerce team (stores and marketplaces): product pages, the feed and merchandising |
| `/lift:technical-team` | The Technical team: security, speed and page security, written for your developers |
| `/lift:product-team` | The Product team (software and marketplaces): the Head of Product's advisers, then a product strategy |
| `/lift:client-services-team` | The Client services team: the brief, the plan of work and proposals |
| `/lift:site-brief`, `/lift:page-audit`, `/lift:site-strategy`, `/lift:task-plan`, `/lift:security-audit`, `/lift:product-strategy`, `/lift:client-proposal` | One job each |
| `/lift:router` | Works out the next step for your site |

Each team command takes an optional site: `/lift:marketing-team <site UUID or address>`. Without one, Claude lists your sites and asks which. You don't have to type commands: saying what you want works too.


## Updates

Claude Desktop checks for updates when the marketplace syncs. Use **Check for updates** on the plugin, or turn on **Sync automatically**. In Claude Code, run `/plugin marketplace update upturn`.

## Help and privacy

- Questions or problems: [get in touch](https://upturnstudio.com.au/contact).
- The connector only sees your own sites, and only while your subscription is active. Claude never submits forms, signs in or changes settings on your website. [Privacy policy](https://upturnstudio.com.au/privacy).

This repo is published automatically from the Upturn Studio app. Please raise issues through the contact page rather than pull requests.
