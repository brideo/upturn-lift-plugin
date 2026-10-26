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
/plugin install upturn-lift@upturn
```

Then type `/mcp`, choose **upturn-lift**, sign in, and say **"set up Upturn Lift"**.

Setup checks the connector, picks your site, shows where it's up to, and links each dashboard step only you can do: the browser extension, Google Analytics and Search Console, and the SEO audit. Then it writes your marketing brief. It takes 10 to 15 minutes.

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
| "run a security audit" | A passive, report-only review of your platform's known vulnerabilities, key pages and sign-in forms, ranked by severity for your developers |
| "catch up on Upturn Lift" | Runs whatever is pending, in order. Good as a weekly habit |

## Works better with

- Anthropic's **Marketing** plugin (Customize › Plugins › Browse plugins) for more thorough SEO, brand and competitor reviews.
- **Claude in Chrome**, so Claude can check the live page's mobile layout, console errors and memory.

## Help and privacy

- Questions or problems: [upturnstudio.com.au/contact](https://upturnstudio.com.au/contact).
- The connector only sees your own sites, and only while your subscription is active. Claude never submits forms, signs in or changes settings on your website. To disconnect, remove Upturn Lift under **Customize › Connectors**. [Privacy policy](https://upturnstudio.com.au/privacy).
