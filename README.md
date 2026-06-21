# RunDrill AnyLearn

> **© 2026 Mikhail Podgurskiy / RunDrill — proprietary, all rights reserved.** No use, copying, or distribution without written permission. Licensing & contact: mikhail@viewflow.io

**Learn anything** inside your AI agent — AnyLearn turns the chat into a saved, plan-based course you
can come back to. Tell it what you want to learn; it builds a plan of tiny topics for your goal and
teaches them one at a time, **grounding each topic in trusted sources it looks up first** — so you're
learning from real material, not a guess. It runs inside your AI agent (Claude, Codex,
Gemini/Antigravity) and is backed by the [RunDrill](https://rundrill.com) MCP engine, which remembers
your plan and progress across sessions.

## What it does

You say what you want to learn. AnyLearn asks a few quick questions — your **goal**, your **level**, any
**deadline**, and the one **win** that means it worked — then generates an ordered plan of very small
topics, scaled to your timeframe (a crash path for next week, a sustainable path for next year). Then it
teaches one topic at a time:

1. **Grounds it** — looks up trusted sources on the web and bases the lesson on them (links + notes are
   saved, so a topic is researched once and reused).
2. **Explains** the single idea simply — one tangible win.
3. **Drills** it — 3-5 short exercises with feedback on every one.
4. **Checks** it — a quick retrieval check, then on to the next topic.

You can run **several courses at once**, stop and pick up later, and see a **day-by-day trail** of what
you've done. For goals that need it, a course can switch on extras: **spaced review** (re-surface what
you learned), **mistake tracking** (re-drill what you got wrong), **evidence tiers**
(Bronze → Silver → Gold), or **strict prerequisites**. Works for languages, exam cram, certifications,
coding, chess — anything.

## Install

This repo is its own marketplace — the catalog lives alongside the plugin.

**Claude Code / Desktop**
```
/plugin marketplace add rundrill/rundrill-anylearn
/plugin install rundrill-anylearn@rundrill-anylearn
/reload-plugins        # → /anylearn is live
```

**Codex**
```
codex plugin marketplace add rundrill/rundrill-anylearn
codex plugin install rundrill-anylearn
```

**Google Antigravity** — drop this folder into `~/.gemini/config/plugins/` (or a workspace
`.agents/plugins/`).

On first use AnyLearn asks you to **authorize** the RunDrill MCP server once (a browser sign-in); after
that your plan and progress are remembered across sessions.

## How it works

The skill is the voice; the MCP server is the source of truth. Three tools drive the course: `status`
(your courses and where each one is), `next` (the next thing to do — onboard, plan, teach a topic, or
finish — with the prompt + contract to run it), and `record` (create/remove a course, set your language,
save the onboarding profile, save the generated plan, cache a topic's grounding, mark a topic done,
regenerate the plan). The server is served at `https://mcp.rundrill.com/anylearn/anylearn`.

## License

Proprietary — all rights reserved. See [LICENSE](./LICENSE). No use without written permission.
