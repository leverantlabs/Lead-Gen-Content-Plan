---
name: lead-gen-content-plan
description: Researches a local niche and produces a weekly Instagram lead-generation content plan, rendered as a polished viewable HTML report. Use when the user asks for content ideas, a content plan, weekly posts, or social media topics for a local business/market.
---

# Lead-Gen Content Plan

Produce a **Weekly Lead-Gen Content Plan** for a local service business and deliver it as a clean,
viewable HTML report (an Artifact). Offer to email it or save a PDF.

## Inputs
The user provides a **niche** + **market/city** (and optionally competitor handles). If either is
missing, ask once, then proceed.

## Procedure (run in order)
1. **Research the market.** Web-search current local data: prices, trend direction, days-on-market,
   demand signals — plus what content formats convert in this niche right now. Capture **3–5 real,
   recent numbers** and their sources. Never invent a number; if you can't find one, say so.
2. **Find the angle.** State the single story the data tells this week (one sentence). Every post
   ladders up to it.
3. **Competitor signal.** NOTE: you cannot read Instagram directly (login wall + no public API).
   Use what you CAN access: (a) web search for who the known players are and their general style from
   articles/press, (b) any **screenshots or captions the user pastes in**, (c) data from a connected
   scraper if one is provided. Do NOT claim to have analyzed live IG posts you didn't actually see.
   Name what the competitors do well and the **content gap** the user can own.
4. **Write 5 posts.** Each must include: format + length · content pillar · a first-3-seconds hook
   (text-overlay, sound-off) · *why it pulls leads* · the exact comment/DM CTA keyword.
5. **Checklist.** 4 concrete "your move this week" actions.
6. **Render.** Fill `assets/report-template.html` — replace every `{{TOKEN}}`, duplicate the
   `<!-- POST CARD -->` block to exactly 5 cards, keep all styling. Output as a viewable HTML
   report, then ask: *"Want me to draft this to your email or save it as a PDF?"*

## Operating rules (from reference/lead-gen-principles.md)
- Optimize for **saves, shares, DMs** — not likes.
- Every post = **local data + a clear CTA**. Always include the **city name** (local SEO).
- Lead Reels with a text hook in the first 3s; assume no sound.
- Honor the user's voice and "will not post" rules from their Project (Level 1).

## Files
- `reference/lead-gen-principles.md` — what converts in local social content (load when writing posts)
- `assets/report-template.html` — the report shell; fill the `{{TOKENS}}` and render
