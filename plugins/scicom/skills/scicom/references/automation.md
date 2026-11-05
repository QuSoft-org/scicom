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

## Settings

Set these in the house-style file, under the "Automation" section, or in the request, for example `scicom: mode=automated, checks=hidden, report=json`. The request overrides the house style.

| Setting | Values | Meaning | Default in automated mode |
|---|---|---|---|
| `mode` | `interactive`, `automated` | Whether a person can answer questions | (`interactive` everywhere else) |
| `checks` | `inline`, `list`, `hidden` | `inline`: `[CHECK]` markers in the text. `list`: clean text plus a review report. `hidden`: clean text only | `list` |
| `report` | `text`, `json` | Format of the review report when `checks` is `list` | `text` |
| `variants` | a number | How many alternative headlines or hooks to add | `0` |

Hiding the markers never permits guessing. Rule 3 always applies.

## Output format

The deliverable comes first. Then, when `checks` is `list`:

```
---
Review report
Status: ready | needs_review | needs_input
Left out because unverified: …
Assumptions: …
Needs human approval before publishing: …
Sources used: …
```

With `report=json`, end instead with one fenced JSON block:

```json
{"status": "ready", "omitted_unverified": [], "assumptions": [], "approvals_needed": [], "sources_used": []}
```

**Status meanings:**
- **`ready`:** everything in the text comes from the source, the house style or verified lookups, and nothing needs approval. Or the operator has said approvals are handled elsewhere.
- **`needs_review`:** a usable draft, but something needs a person first; the report says what.
- **`needs_input`:** no draft, because the core is missing; the report says what is needed.

## Advice for whoever sets up the automation

- **Where humanless publishing is safe:** low-risk formats built only from published, public sources, such as a post announcing a published paper or a newsletter digest. AI text on a public-interest topic published with no human editorial review must carry an AI disclosure (EU AI Act Art. 50, as Dutch media read it, Media Campus NL 2026). For journalists, automated output is always a draft for an editor.
- **Where to keep a person in the loop:** press releases, quotes, health claims, policy briefs, and anything under embargo.
- **Fix the settings in the house-style file,** so every run behaves the same.
- **Keep the review report even when it isn't shown** (`report=json` is easy to log). It is the audit trail of what was left out and why.
