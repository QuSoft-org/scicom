# scicom: science communication for Claude

A Claude Code plugin with one skill, **scicom**. It helps communication staff and researchers at universities and research institutes plan, write, adapt and review communication about STEM research. Since version 1.3 it also supports science journalists, through a role switch.

## What it helps with

- **Press and media:** news items, press releases, media advisories, pitches to journalists, interview preparation.
- **Social media:** posts and threads for LinkedIn, Bluesky, X, Instagram, TikTok and YouTube.
- **Video and audio:** video and podcast scripts.
- **Talks and events:** talks, pitches, posters, public events, school visits.
- **Longer texts:** op-eds, blogs, newsletters, lay summaries, web pages, bios.
- **Policy:** policy briefs and briefings.
- **Planning:** communication plans, stakeholder analyses, evaluation.
- **Reviewing and risk:** checking drafts for hype, jargon and accuracy; communicating uncertainty and risk; responding to misinformation.
- **Journalism** (role `journalist`): assessing studies and press releases, finding and vetting independent experts, interview questions, news stories and features, fact-check memos, filing notes, corrections, pitches to editors.

**Accuracy comes first.** The skill matches claims to the evidence and marks anything unverified as `[CHECK]`. It never invents quotes, and it lists what the researcher should approve.

## Roles

The skill works for three kinds of user. Set the role in your request or in the house-style file:

- `communicator` (default): press officers and communication staff;
- `researcher`: the same rules, in the researcher's own voice;
- `journalist`: science journalists. Institutional rules (approvals, credits, boilerplate, funder visibility) are switched off; sources never approve the article; every suggested expert comes with a verifiable link. See `references/journalism.md`.

The skill infers `journalist` only from clear cues ("for our science desk", "I'm a freelance journalist"). Writing *to* a journalist doesn't make you one.

## Install

This repository is private. Before installing you need two things:
- access to `QuSoft-org/scicom` on GitHub (ask a QuSoft-org owner);
- to be signed in to GitHub on your computer. The simplest way is to install GitHub's tool (`brew install gh`), then run `gh auth login` and `gh auth setup-git`.

Then, in Claude Code, type:

```
/plugin marketplace add QuSoft-org/scicom
/plugin install scicom@qusoft
```

Or run these in a terminal:

```bash
claude plugin marketplace add QuSoft-org/scicom
claude plugin install scicom@qusoft
```

### Quantum add-on

For quantum science and technology, also install the add-on. It adds subject knowledge, such as which analogies mislead and how to check quantum claims; scicom still does the rest.

```
/plugin install scicom-quantum@qusoft
```

## Update

- In Claude Code: run `/plugin marketplace update qusoft`.
- In a terminal: run `claude plugin update scicom@qusoft` (and `claude plugin update scicom-quantum@qusoft`).
- Automatically: in `/plugin`, go to Marketplaces, select `qusoft`, and select **Enable auto-update**.

## Use

Just ask. For example:

- "Write a press release about this paper", with the paper attached or pasted.
- "Turn this paper into a news item, a LinkedIn post and a short video script."
- "Review this draft for hype."
- "Make a communication plan for our new lab."
- "I'm a science reporter: assess this press release against the paper and draft my news story."

You can also call the skill directly with `/scicom:scicom`.

## Automated use (no person in the loop)

In pipelines, scheduled jobs or headless runs, the skill can run in automated mode. It then never asks questions. It closes gaps by leaving unverified facts out (never by guessing), and adds a review report with a status (`ready`, `needs_review` or `needs_input`), or nothing at all.

Turn it on in the request, for example `scicom: mode=automated, checks=hidden`, or in the house-style file. Details are in `references/automation.md`.

## House style

If your project contains a file called `scicom-house-style.md`, the skill follows it: names, boilerplate, tone, spelling, contacts and approval rules. Ask "set up our house style" and it will interview you and create the file.

Without a house style, it writes British English with European Commission style conventions.

## What's inside

- `plugins/scicom/skills/scicom/SKILL.md`: the workflow, ten principles and a routing table.
- `plugins/scicom/skills/scicom/references/`: guides per format, a review checklist, templates, fictional worked examples, a Netherlands/EU context file, the journalist role (`journalism.md`, `templates-journalism.md`), and the sources.

## Sources

The skill draws on science-communication research and practice. That includes the open-access books *50 Essentials on Science Communication* (2024) and *Science Communication for Scientists* (2026), as well as Besley & Dudo, Pielke, Shipman and Dean, plus guidance from press offices, journals, research councils and EU institutions. The journalist role draws on Kovach & Rosenstiel's *The Elements of Journalism*, Blum & Knudson's *A Field Guide for Science Writers*, the KSJ *Science Editing Handbook*, the Raad voor de Journalistiek *Leidraad*, the NVJ and IFJ codes, and Science Media Centre guidance. It paraphrases its sources and cites them; the full list is in `references/sources.md`.

## Feedback

Open an issue in this repository.

## Licence

No licence has been chosen yet; all rights are reserved by QuSoft.
