# Lead-Gen Content Plan — a Claude Skill

A free [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) that
researches a local niche and produces a **Weekly Instagram Lead-Generation Content Plan**, delivered
as a polished, viewable HTML report.

Give Claude a niche + a city (e.g. *"real estate in Austin"*) and it will:

1. **Research the market** — web-search current local data (prices, trend direction, days-on-market,
   demand signals) and capture 3–5 real, recent numbers with sources.
2. **Find the weekly angle** — the single story the data tells this week.
3. **Read competitor signal** — name what the known players do well and the content gap you can own.
4. **Write 5 posts** — each with format, content pillar, a first-3-seconds hook, why it pulls leads,
   and the exact comment/DM CTA keyword.
5. **Give you a checklist** — 4 concrete "your move this week" actions.
6. **Render a report** — a clean HTML artifact you can view, email, or save as a PDF.

It optimizes for what actually books appointments — **saves, shares, and DMs** — not vanity likes.

## What's inside

| File | Purpose |
|------|---------|
| `SKILL.md` | The skill definition and procedure Claude follows |
| `reference/lead-gen-principles.md` | What converts in local social content (loaded when writing posts) |
| `assets/report-template.html` | The report shell Claude fills in and renders |

## Install

This is a standard Claude Skill. Drop the folder into your skills directory.

**Claude Code**

```bash
git clone https://github.com/leverantlabs/Lead-Gen-Content-Plan.git
# personal (all projects):
cp -r Lead-Gen-Content-Plan ~/.claude/skills/lead-gen-content-plan
# or project-scoped:
cp -r Lead-Gen-Content-Plan .claude/skills/lead-gen-content-plan
```

**Claude apps (claude.ai / desktop)**

Zip the folder and upload it under **Settings → Capabilities → Skills** (where available).

## Use

Just ask, naturally:

> "Make me a weekly content plan for a med spa in Scottsdale."

Claude invokes the skill, runs the research, and hands back the report. If you omit the niche or city,
it asks once, then proceeds.

### Emailing the report

To have the skill **draft the report to your inbox**, run it in **Claude cowork** (the agentic
workspace) with the Gmail connector enabled. Cowork is what lets Claude use connected tools end to end;
a plain chat or Project can build the report but can't complete the email draft.

The email is a **short, email-safe HTML summary** (the angle, the numbers, the post hooks, the
checklist) — not the full styled page. The Gmail connector can't attach files, and the full report is
too large to drop into a message body, so the polished report stays the Artifact (or save it to Drive
and the skill links it).

## License

[MIT](LICENSE) — free to use, modify, and share. Made by [Leverant Labs](https://github.com/leverantlabs).
