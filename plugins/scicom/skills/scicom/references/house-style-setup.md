# Creating a house style (`scicom-house-style.md`)

A house style file makes every later draft use the organisation's own names, tone, spelling, boilerplate, contacts and approval rules. Create it once and update it when things change.

## How to run the setup

1. **Start from existing material.**
   - In your first reply, ask for whatever already exists: a recent press release, the "about us" text, the brand or style guide, the website newsroom, social media handles.
   - Fill in what you can from it, then ask only what is still missing.
   - If they have nothing to hand, start Round 1 straight away.
   - Also offer a quick version: the five questions that matter most (names, boilerplate, English variant, tone, approvals), with the rest left as `[TODO]`.
2. **Ask in short rounds.** Use the four rounds below, five or six questions at a time, never all at once. Suggest a default in brackets so the user can simply say "yes". Accept "skip" and "don't know"; leave those fields as `[TODO]`.
3. **Show the draft.** Write the file using the template at the end, show it, and ask for corrections.
4. **Save it.** Save it as `scicom-house-style.md` in the project folder the user works from. Tell the user they can edit it by hand at any time. If you cannot save files, give the full file content for the user to save.

## Guiding questions

**Journalists:** ask Round 0 instead of Rounds 1 and 3, and skip questions 13, 14 and 16. Freelancers keep one house-style file per outlet folder.

### Round 0: role (journalists only)

A. Which code does the outlet follow (the Raad voor de Journalistiek *Leidraad* for Dutch outlets, or its own)?
B. Its policy on previews and quote checks with sources.
C. Its rules on anonymous sources and right-of-reply deadlines.
D. Its corrections policy.
E. Its AI policy: what AI may be used for (research, summaries, transcription, translation, headline options, drafting copy, images), and the disclosure format.

### Round 1: identity

1. What is the organisation's official name in English, its short name, and how should it be named on second mention?
2. Is it part of, or shared by, other institutions? How should they be named? (For example, "a joint institute of A and B".)
3. Is there a standard "about us" paragraph of 50–80 words for the end of press releases? (Default: draft one from the website for approval.)
4. In one sentence, what is the mission? Which two or three themes should the organisation be known for?
5. Who are the spokespeople and media contacts: name, role, email, phone? (Default: placeholders.)

### Round 2: voice and language

6. Which English: British or American? Which reference guide? (Default: British English and the EC English Style Guide.)
7. What should the tone be, in three words? (Default: clear, curious, modest.) May texts use "we" for the organisation?
8. Are there words or phrases to avoid (such as "breakthrough"), or preferred terms for the field?
9. How should academic titles and names be written? (Default: full name and role on first mention, surname after, and no "Dr" or "Prof." in running text except in quote attributions.)
10. Any conventions for numbers, dates and units? (Default: those of the EC English Style Guide. For thousands, choose 15 000 or 15,000.)

### Round 3: audiences, channels and process

11. Which audiences matter most, in order, and what do you want from each?
12. Which channels do you use: website or newsroom URL, social media handles, hashtags, newsletter, YouTube?
13. Who approves what (researcher, head of communications, director), and how long does approval usually take?
14. What is your embargo practice, and how do you distribute releases (own list, EurekAlert!, AlphaGalileo, a national news agency)?

### Round 4: visual, legal and sensitive topics

15. What are the rules for logos, photo credits, consent forms and AI-generated images?
16. Which standard funding acknowledgements and disclaimers must appear? (For example, the EU emblem with "Funded by the European Union" for EU grants.)
17. What accessibility rules apply? (Default: alt text for every image, captions on every video, sufficient colour contrast.)
18. Which topics are sensitive and need escalation, and to whom? (Examples: security-sensitive research, patents, controversies, crises.)
19. Is there a policy on disclosing AI use in communication texts?

### Round 5: automation (only if relevant)

20. Will the skill run without a person, for example in a pipeline or scheduled job? Which mode, and how should unresolved facts be shown? (Default: `mode: interactive`, `checks: inline`. For pipelines: `mode: automated`, `checks: list` or `hidden`, `report: text` or `json`. See `automation.md`.)
21. Which formats may be published without human approval, if any? (Default: none. Safest: posts about already published papers.) Unreviewed output always carries an AI disclosure; see `automation.md`.
22. Do you want your own wording for that disclosure, for example in Dutch? (Default: the wording in `automation.md`.)

## Template

```markdown
# House style: <organisation>
Last updated: <date>, by <name>

## Identity
- Official name:
- Short name / second mention:
- Parent or partner institutions, and how to name them:
- Boilerplate ("about us", 50–80 words):
- Mission (one sentence):
- Key themes:

## Voice
- English variant and reference guide:
- Tone (three words):
- "We" for the organisation: yes / no
- Use:
- Avoid:
- Titles and names:
- Numbers, dates, units:

## Audiences (in priority order)
1.

## Channels
- Website / newsroom:
- Social media handles and hashtags:
- Newsletter:

## Process
- Approvals and turnaround:
- Embargo practice and distribution:
- Media contacts:

## Visual and legal
- Logo and image rules:
- Photo credit format:
- Consent forms:
- AI-generated images:
- Funding acknowledgements and disclaimers:
- Accessibility:
- Sensitive topics and escalation:
- AI-use disclosure:

## Role
- role: communicator   # communicator, researcher or journalist
- (journalists) code; preview and quote-check policy; anonymity and right of reply; corrections; AI policy and disclosure:

## Automation
- mode: interactive   # or automated
- checks: inline      # inline, list or hidden
- report: text        # text or json (used when checks is list)
- variants: 0         # alternative headlines or hooks in automated runs
- review: none        # none (may be published unreviewed: AI disclosure required) or human
- Formats that may be published without human approval: none
- AI disclosure line (unreviewed output): default
```
