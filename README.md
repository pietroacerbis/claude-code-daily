# Claude Code plugins

The plugins we run every day at [gaja](https://trygaja.com), and others worth trying, in seven categories. For each one: what you get, the install lines, and what it costs on every message you send.

Checked on 2026-11-17: every repository answered on GitHub, and the costs marked in tokens were measured on our machine with `claude plugin details`.

## Before you install anything

A plugin is cheap to install and easy to forget. Every skill it brings puts its name and description into **every message you send**, whether you use it that day or not. Ten plugins with thirty skills each make a slower, more expensive Claude that follows each instruction less closely.

| Command | What it tells you |
|---|---|
| `claude plugin details NAME` | what the plugin adds to every message, in tokens |
| `claude plugin list` | what is installed, and what is on |
| `/plugin install NAME --scope project` | installs it for one project only |

Our rule:

- **On everywhere** only what changes how every session runs, like superpowers.
- **On per project** what serves one kind of work, like vercel in the website repo.
- **Off** what you used once.
- **Reviewed before install** when you did not write it. A plugin runs with your permissions: [review-skill](https://github.com/pietroacerbis/how-to-build-a-skill) reads it for hidden instructions, secrets read and data sent out, and never runs it.

Most rows below install from Anthropic's official marketplace. If `/plugin` does not list it, add it first:

```
/plugin marketplace add anthropics/claude-plugins-official
```

---

## 1. GTM and sales

For when Claude works the pipeline: lists, call prep, CRM updates, outbound copy. Most vendor plugins are a connector plus a few skills, and they need a paid account with the vendor. The bundles put dozens of skills on every message, so keep them in the repository where you sell.

| Plugin | What you get | Install | Ours | Cost and note |
|---|---|---|---|---|
| [sales](https://github.com/anthropics/knowledge-work-plugins) | call prep, account research, deal and pipeline review, forecasts, outreach drafts, wired to 23 sales tools | `/plugin marketplace add anthropics/knowledge-work-plugins`<br>`/plugin install sales@knowledge-work-plugins` | to try | 36 skills, about 4,400 tokens. Only in a sales repository |
| [marketing](https://github.com/anthropics/knowledge-work-plugins) | campaign plans, content drafts, email sequences, SEO audits, performance reports | `/plugin install marketing@knowledge-work-plugins` | to try | 8 skills, about 870 tokens |
| [apollo](https://github.com/apolloio/apollo-mcp-plugin) | prospect, enrich leads and load sequences in Apollo.io from the chat | `/plugin install apollo@claude-plugins-official` | to try | 3 skills, about 200 tokens. Apollo account |
| [hubspot-sales](https://github.com/HubSpot/hubspot-mcp-plugins) | a morning brief, call prep, follow-ups and call logging that write back to HubSpot | `/plugin install hubspot-sales@claude-plugins-official` | to try | 9 skills |
| [clay](https://github.com/clay-run/agent-plugins) | query Clay tables, search its people and company data, run audiences and sequences | `/plugin install clay@claude-plugins-official` | to try | 39 skills. No licence declared |
| [marketing-skills](https://github.com/coreyhaines31/marketingskills) | 53 marketing skills: conversion, copywriting, SEO, analytics, growth | `/plugin marketplace add coreyhaines31/marketingskills`<br>`/plugin install marketing-skills@marketingskills` | to try | 53 skills, expect thousands of tokens. Per project |

## 2. Productivity and workflow

These change how every session runs: plan first, prove before saying done, shorter answers. They are the ones worth keeping on everywhere, and the easiest to stack until the total hurts.

| Plugin | What you get | Install | Ours | Cost and note |
|---|---|---|---|---|
| [superpowers](https://github.com/obra/superpowers) | Claude brainstorms, writes a plan, tests and verifies before it says done | `/plugin install superpowers@claude-plugins-official` | we use it | 15 skills, about 850 tokens. On everywhere |
| [mattpocock-skills](https://github.com/mattpocock/skills) | grilling interviews, specs turned into tickets, handoffs, test-first work across sessions | `/plugin install mattpocock-skills@claude-plugins-official` | we use it | 25 skills, about 1,600 tokens |
| [i-have-adhd](https://github.com/ayghri/i-have-adhd) | replies that start with the action: the answer, then the steps, short | `/plugin marketplace add ayghri/i-have-adhd`<br>`/plugin install i-have-adhd@i-have-adhd` | we use it | 1 skill and a hook, about 110 tokens |
| [caveman](https://github.com/JuliusBrussee/caveman) | clipped answers that cut output tokens, by 65% on the author's measure | `/plugin marketplace add JuliusBrussee/caveman`<br>`/plugin install caveman@caveman` | we use it | 25 skills and 5 agents, about 2,800 tokens. Off for anything a customer reads |
| [slack](https://github.com/slackapi/slack-skills-plugin) | search channels, read threads, draft standups and announcements | `/plugin install slack@claude-plugins-official` | we use it | 13 skills, about 1,290 tokens. Off where nobody posts to Slack |
| [task-observer](https://github.com/rebelytics/one-skill-to-rule-them-all) | watches your sessions and proposes skill updates from your corrections, applied only when you approve | `/plugin marketplace add rebelytics/one-skill-to-rule-them-all`<br>`/plugin install task-observer@one-skill-to-rule-them-all` | to try | 1 skill. Needs its session hook and a CLAUDE.md block to fire |

## 3. Design and frontend

For anything a customer sees: landing pages, decks, product screens. Generated interfaces converge when everyone installs the same design skills, so we review this category every quarter.

| Plugin | What you get | Install | Ours | Cost and note |
|---|---|---|---|---|
| [taste-skill](https://github.com/Leonxlnx/taste-skill) | quality bars and named styles (minimalist, brutalist, soft) for interfaces that stop looking generated | `/plugin marketplace add Leonxlnx/taste-skill`<br>`/plugin install taste-skill@taste-skill` | we use it | 13 skills, about 1,700 tokens. Per project |
| [playground](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/playground) | single-file HTML explorers with controls and a live preview | `/plugin install playground@claude-plugins-official` | we use it | 1 skill, about 90 tokens |
| [gsap-skills](https://github.com/greensock/gsap-skills) | GreenSock's own guidance for GSAP animations, timelines and scroll effects | `/plugin marketplace add greensock/gsap-skills`<br>`/plugin install gsap-skills@gsap-skills` | we use it | 8 skills, about 1,140 tokens. On only for animation work |
| [frontend-design](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/frontend-design) | Anthropic's skill for frontend that avoids the generic AI look | `/plugin install frontend-design@claude-plugins-official` | to try | 1 skill |
| [figma](https://github.com/figma/mcp-server-guide) | reads Figma files, components and tokens, and turns designs into code | `/plugin install figma@claude-plugins-official` | to try | 16 skills, about 2,420 tokens |

## 4. Development and code quality

For repositories that hold code or ship a site. A plugin that is only a connector costs nothing until it is called. A plugin with forty skills costs about 4,000 tokens on every message, so it belongs in the repositories that use it.

| Plugin | What you get | Install | Ours | Cost and note |
|---|---|---|---|---|
| [compound-engineering](https://github.com/EveryInc/compound-engineering-plugin) | Every's plan, work and review loop, where each change records what makes the next one cheaper | `/plugin marketplace add EveryInc/compound-engineering-plugin`<br>`/plugin install compound-engineering@compound-engineering-plugin` | we use it | 43 skills, about 4,160 tokens. Off outside code repositories |
| [github](https://github.com/anthropics/claude-plugins-official/tree/main/external_plugins/github) | GitHub's connector: issues, pull requests, reviews, repository search | `/plugin install github@claude-plugins-official` | we use it | no skills, close to 0 tokens |
| [vercel](https://github.com/vercel/vercel-plugin) | deployments, build logs and domains, plus Next.js and AI SDK guidance | `/plugin install vercel@claude-plugins-official` | we use it | 37 skills and 3 hooks, about 4,220 tokens. Only in the website repository |
| [skill-creator](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/skill-creator) | Anthropic's skill for writing, testing and benchmarking your own skills | `/plugin install skill-creator@claude-plugins-official` | we use it | 1 skill, about 110 tokens |
| [claude-code-setup](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/claude-code-setup) | reads a codebase and recommends hooks, skills, connectors and subagents | `/plugin install claude-code-setup@claude-plugins-official` | we use it | 1 skill, about 140 tokens. Run once per repository |
| [ecc](https://github.com/affaan-m/ECC) | Everything Claude Code: a large bundle of agents, skills, hooks and rules | `/plugin marketplace add affaan-m/ECC`<br>`/plugin install ecc@ecc` | to try | 327 skills, the largest cost on this page. Read it, take what you need |

## 5. Research and web data

For when Claude reads the web: account research, competitor pages, pages that only load with JavaScript. Most of these are a connector with few skills, cheap to keep installed. The cost is the API credits each call spends.

| Plugin | What you get | Install | Ours | Cost and note |
|---|---|---|---|---|
| [playwright](https://github.com/anthropics/claude-plugins-official/tree/main/external_plugins/playwright) | Microsoft's browser connector: click, fill, screenshot, read JavaScript pages | `/plugin install playwright@claude-plugins-official` | we use it | no skills, close to 0 tokens |
| [firecrawl](https://github.com/firecrawl/firecrawl-claude-plugin) | scrape, crawl, search and extract structured data from sites | `/plugin install firecrawl@claude-plugins-official` | we use it | 3 skills, about 230 tokens. API key |
| [exa](https://github.com/exa-labs/exa-mcp-server) | web search by meaning, company and people research, content extraction | `/plugin install exa@claude-plugins-official` | to try | 2 skills, about 190 tokens. API key |
| [chrome-devtools-mcp](https://github.com/ChromeDevTools/chrome-devtools-mcp) | drives a live Chrome: performance traces, network requests, console errors | `/plugin marketplace add ChromeDevTools/chrome-devtools-mcp`<br>`/plugin install chrome-devtools-mcp@chrome-devtools-plugins` | to try | 8 skills |
| [brightdata-plugin](https://github.com/brightdata/skills) | scrapes past bot blocks, structured Google results, data from 40+ sites | `/plugin install brightdata-plugin@claude-plugins-official` | to try | 7 skills. Paid account |

## 6. Memory and context

For work that spans more than one session. Two kinds: plugins that recall past chats, and plugins that keep a project's memory current. Recall plugins overlap, so pick one.

| Plugin | What you get | Install | Ours | Cost and note |
|---|---|---|---|---|
| [episodic-memory](https://github.com/obra/episodic-memory) | search by meaning over your past Claude Code conversations | `/plugin marketplace add obra/superpowers-marketplace`<br>`/plugin install episodic-memory@superpowers-marketplace` | we use it | 1 skill and a hook, about 100 tokens. After a Node upgrade: `npm rebuild better-sqlite3` |
| [claude-md-management](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/claude-md-management) | audits your CLAUDE.md files and writes what a session learned into them | `/plugin install claude-md-management@claude-plugins-official` | we use it | 2 skills, about 180 tokens |
| [claude-mem](https://github.com/thedotmack/claude-mem) | records what the agent does, compresses it, and injects it into later sessions | `/plugin marketplace add thedotmack/claude-mem`<br>`/plugin install claude-mem@thedotmack` | to try | 30 skills. Overlaps episodic-memory |
| [understand-anything](https://github.com/Egonex-AI/Understand-Anything) | turns a codebase into a knowledge graph you can explore and question | `/plugin marketplace add Egonex-AI/Understand-Anything`<br>`/plugin install understand-anything@understand-anything` | to try | 9 skills |
| [claude-hud](https://github.com/jarrodwatts/claude-hud) | a status line with context usage, active tools, running agents and todos | `/plugin marketplace add jarrodwatts/claude-hud`<br>`/plugin install claude-hud@claude-hud` | to try | 1 skill |

Prefer plain files you own and can read? [claude-personal-memory](https://github.com/pietroacerbis/claude-personal-memory) is our take: a journal per day, a mistakes log, and two skills that read and write them.

## 7. Content and video

For when you publish: posts, launch films, scheduling. These cover the input, reading a video, and the output, rendering and scheduling. The writing itself still needs your own voice rules.

| Plugin | What you get | Install | Ours | Cost and note |
|---|---|---|---|---|
| [watch](https://github.com/bradautomates/claude-video) | Claude watches a video, from a link or a file: frames plus transcript | `/plugin marketplace add bradautomates/claude-video`<br>`/plugin install watch@claude-video` | we use it | 1 skill and a hook, about 100 tokens, about 8,000 per video. Frame extraction fails on ffmpeg 9 |
| [hyperframes](https://github.com/heygen-com/hyperframes) | HeyGen's HTML-to-video: compositions, captions, voiceover, a website turned into a video | `/plugin install hyperframes@claude-plugins-official` | to try | 9 skills. We used its command line on a launch film |
| [humanizer](https://github.com/blader/humanizer) | removes the tells of AI writing from a draft | `/plugin marketplace add blader/humanizer`<br>`/plugin install humanizer@humanizer` | to try | 1 skill |
| [postiz](https://github.com/gitroomhq/postiz-agent) | schedules posts and reads analytics across 28+ networks, LinkedIn and X included | `/plugin install postiz@claude-plugins-official` | to try | 1 skill. Needs the postiz command line and an API key |
| [brand-voice](https://github.com/anthropics/knowledge-work-plugins) | builds brand guidelines from your material and checks drafts against them | `/plugin install brand-voice@knowledge-work-plugins` | to try | 6 skills, about 2,600 tokens |

---

## Related lists

- [awesome-claude-code-for-gtm](https://github.com/matteotitta/awesome-claude-code-for-gtm), Matteo Titta's list for go-to-market work: skills, agents, connectors and courses. The one that gave us the idea for this page.
- [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code), the general list.
- [claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice), a guide to setting Claude Code up.
- [claude-code-system-prompts](https://github.com/Piebald-AI/claude-code-system-prompts), the prompts Claude Code runs on, for reference.

## The Skill kit

This repository is one of three:

- [How to build a skill](https://github.com/pietroacerbis/how-to-build-a-skill): the guide, the format, a template, and two skills that create and review skills.
- [Claude personal memory](https://github.com/pietroacerbis/claude-personal-memory): Claude that remembers who you are and what you corrected, in plain files you own.
- Claude Code plugins: this one.

<!-- CTA -->
---

## Want the stack set up on your own go-to-market?

Plugins give Claude tools. What makes them work for your team is the knowledge they read: your ICP, your stages, your objections, your voice. At gaja we build that from your calls, your CRM and your team.

- Pietro Acerbis, pietro@trygaja.com, [LinkedIn](https://www.linkedin.com/in/pietroacerbis-prospeiq/)
- [trygaja.com](https://trygaja.com)

MIT licence.
