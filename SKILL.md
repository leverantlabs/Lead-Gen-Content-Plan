---
name: lead-gen-content-plan
description: Researches a local niche and produces a weekly Instagram lead-generation content plan, rendered as a polished viewable HTML report. Use when the user asks for content ideas, a content plan, weekly posts, or social media topics for a local business/market.
---

# Lead-Gen Content Plan

Produce a **Weekly Lead-Gen Content Plan** for a local service business and deliver it as a clean,
viewable HTML report (an Artifact). Offer to email it or save a PDF.

> **Email delivery requires Claude cowork.** The research + report steps run anywhere, but the Gmail
> draft step (Step 7) only completes in **Claude cowork** (the agentic workspace), where Claude can use
> connected tools end to end. In a plain chat or Project the draft will fail or time out. If email isn't
> available, still produce the report Artifact and offer a PDF.

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
6. **Render the report (the Artifact).** Fill `assets/report-template.html` — replace every
   `{{TOKEN}}`, duplicate the `<!-- POST CARD -->` block to exactly 5 cards, keep all styling.
   Output as a viewable HTML report. This full styled report is the Artifact the user reads. Do
   NOT put this entire document into an email body or attach it — see Step 7 for why.

7. **Deliver by email (short HTML summary, body only).** When the user wants it emailed, draft a
   **lightweight, email-safe HTML summary**, not the full report. The Gmail connector does **not**
   support attachments, and pasting the whole styled report document into the body is too large and
   times out. So build a small HTML body that renders cleanly in an inbox:
   - **Subject:** `Your weekly {niche} content plan — {city} ({date})`
   - **Body — email-safe HTML, keep it small (aim under ~8 KB):**
     - Use **semantic tags with INLINE styles only** (`<h2 style="...">`, `<p>`, `<strong>`,
       `<ul>`/`<ol>`, `<a>`). Do **NOT** include `<!DOCTYPE>`, `<html>`/`<head>`/`<body>` wrappers,
       a `<style>` block, external CSS, web fonts, scripts, or images — email clients strip those
       and they bloat the payload. Inline styles are what survives.
     - Brand accent for headings/links: indigo `#4f46e5`. One accent color, used lightly.
     - Structure:
       1. An `<h2>` title, then one `<p>` with the **angle** for the week (the `<strong>` bit).
       2. **Market snapshot** — a short `<ul>` of the 3–5 numbers, each with its source.
       3. **This week's 5 posts** — an `<ol>`; each item is the **hook line** in `<strong>` plus
          its CTA keyword. Just the hook + CTA, not the full breakdown.
       4. **Your move this week** — a `<ul>` of the 4 checklist actions.
       5. A closing `<p>`: *"Full styled report is linked below"* (if you added a Drive link), or
          *"Full styled report is the Artifact in Claude."*
   - Draft it with the Gmail **create_draft** tool, passing this HTML as the body (HTML/rich body,
     not plain text). Send only this small summary. Never pass the rendered `report-template.html`
     contents or a PDF into the draft.
   - **Want the full report in their inbox too?** Don't attach it. Save the rendered HTML to Google
     Drive (Drive **create_file**), get a shareable link, and paste that **link** into the email
     body. A link always works on a schedule; an attachment never will.
   - After drafting, tell the user: *"Drafted the summary to your inbox. The full report is the
     Artifact above"* (and the Drive link, if used).

8. **Or save a PDF.** If the user wants a PDF instead of email, render the HTML to PDF locally
   (headless Chrome `--print-to-pdf` with `print-color-adjust:exact`) and give them the file. PDF is
   for download, not for emailing through the connector.

## Operating rules (from reference/lead-gen-principles.md)
- Optimize for **saves, shares, DMs** — not likes.
- Every post = **local data + a clear CTA**. Always include the **city name** (local SEO).
- Lead Reels with a text hook in the first 3s; assume no sound.
- Honor the user's voice and "will not post" rules from their Project (Level 1).

## Files
- `reference/lead-gen-principles.md` — what converts in local social content (load when writing posts)
- `assets/report-template.html` — the report shell; fill the `{{TOKENS}}` and render
