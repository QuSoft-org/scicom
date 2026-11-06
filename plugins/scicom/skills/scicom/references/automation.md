# Automated (unattended) mode

Use this mode when no person can answer questions: pipelines, scheduled jobs, headless runs (`claude -p`, the Agent SDK), or bots that turn new papers into posts.

## Rules

1. **Never ask, never wait.** Make reasonable, conservative choices and record them in the report, if there is one.
2. **Resolve before you omit.** Look in this order:
   - the source material itself: papers usually give authors, affiliations, funders, journal, date and numbers;
   - the house-style file: names, boilerplate, contacts, handles;
   - reliable lookups, if your tools allow, such as the DOI record, the journal page or institutional pages.

   Prefer the source over lookups.
3. **Never fill a gap by inventing.** For anything that is still unresolved:
   - **name or affiliation:** write around it ("researchers at [organisation from the house style]", "an international team");
   - **number:** use a qualitative description only if the source supports it ("fewer", "faster"); otherwise leave it out;
   - **quote:** write without quotes. Never draft a quote in automated mode;
   - **background you cannot verify:** leave it out;
   - **"first" or "better than" claim you cannot verify:** drop the comparison.
4. **When in doubt, use the weaker wording,** following the calibration rules in `press-and-media.md`.
5. **Don't pretend something is final when it needs a human.** That includes unknown embargo times, quotes, approvals, health claims and policy positions. If the task depends on these, deliver the draft with status `needs_review`.
6. **Stop when the core is missing.** If you cannot identify the main finding, or there is no source, return status `needs_input` with what is missing, instead of a draft.
7. **No conversation:** no questions, no notes to the user, no headline alternatives unless the settings ask for them. The deliverable comes first.
8. **Label unreviewed output.** Unless the request or the house style says `review: human`, assume the text may be published without a person reviewing it, and include the AI disclosure (below). The EU AI Act (Art. 50(4), applying since 2 August 2026) requires AI-generated text published to inform the public on matters of public interest to be labelled, unless a person has reviewed it and someone holds editorial responsibility. Treat research news as public interest. The disclosure is part of the text, not a check marker, so it stays with every `checks` setting, `hidden` included.
9. **No one's voice without their approval.** Never write in a real person's first-person voice (a researcher's LinkedIn post, a blog under their name) for publication without review, and never draft words for anyone (rule 3). Write in the institution's voice instead. If the request asks for a named person's voice, deliver the draft with status `needs_review` and list that person's approval under approvals, unless the operator has confirmed that this person approves each text before it is published.

## Settings

Set these in the house-style file, under the "Automation" section, or in the request, for example `scicom: mode=automated, checks=hidden, report=json`. The request overrides the house style.

| Setting | Values | Meaning | Default in automated mode |
|---|---|---|---|
| `mode` | `interactive`, `automated` | Whether a person can answer questions | (`interactive` everywhere else) |
| `checks` | `inline`, `list`, `hidden` | `inline`: `[CHECK]` markers in the text. `list`: clean text plus a review report. `hidden`: clean text only | `list` |
| `report` | `text`, `json` | Format of the review report when `checks` is `list` | `text` |
| `variants` | a number | How many alternative headlines or hooks to add | `0` |
| `review` | `none`, `human` | `none`: the output may be published without a person reviewing it, so the AI disclosure is required. `human`: a person reviews it and takes editorial responsibility before publication | `none` (journalists: always `human`) |

Hiding the markers never permits guessing. Rule 3 always applies.

## AI disclosure

Required when `review` is `none`. The law asks for a clear, distinguishable label at the reader's first sight of the text, so put it where readers see it first, in plain text (not only inside an image):
- **News items, blogs, newsletters and other longer texts:** directly under the headline or standfirst: *This text was written by an AI system (Claude) from [the source, for example the paper in [journal], [date]] and published without review by an editor.*
- **Social posts:** in the part shown before "more": *AI-generated, not reviewed by an editor.* Where the platform has its own AI label, the operator should switch it on as well; say so in the report.
- **Video and audio:** on screen at the start, and spoken.

The house style may set its own wording, in Dutch too (field "AI disclosure line"), as long as it says both that AI generated the text and that no person reviewed it. The law requires the first; the second keeps readers from assuming an editor checked it. Never weaken it to "with help from AI", and never leave it out because the text is short. AI images and audio follow `visuals.md`: label them, and never use them to depict real people, experiments or events.

## Output format

The deliverable comes first. Then, when `checks` is `list`:

```
---
Review report
Status: ready | needs_review | needs_input
Left out because unverified: …
Assumptions: …
Needs human approval before publishing: …
AI disclosure: included | not needed (review: human)
Sources used: …
```

With `report=json`, end instead with one fenced JSON block:

```json
{"status": "ready", "omitted_unverified": [], "assumptions": [], "approvals_needed": [], "ai_disclosure": "included", "sources_used": []}
```

**Status meanings:**
- **`ready`:** everything in the text comes from the source, the house style or verified lookups; nothing needs approval, or the operator has said approvals are handled elsewhere; and, when `review` is `none`, the AI disclosure is in place. Text in a real person's voice is `ready` only when the operator has confirmed that this person approves each text before it is published.
- **`needs_review`:** a usable draft, but something needs a person first; the report says what.
- **`needs_input`:** no draft, because the core is missing; the report says what is needed.

## Advice for whoever sets up the automation

- **Where humanless publishing is safe:** low-risk formats built only from published, public sources, such as a post announcing a published paper or a newsletter digest, in the institution's voice and with the AI disclosure. Dutch media apply the same labelling rule (Media Campus NL 2026). For journalists, automated output is always a draft for an editor.
- **Post from an institutional account,** never from a researcher's personal account, and mark the account as automated where the platform allows it.
- **Where to keep a person in the loop:** press releases, quotes, health claims, policy briefs, and anything under embargo.
- **Fix the settings in the house-style file,** so every run behaves the same.
- **Keep the review report even when it isn't shown** (`report=json` is easy to log). It is the audit trail of what was left out and why.
