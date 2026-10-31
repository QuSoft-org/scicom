---
name: scicom-quantum
description: Quantum-specific knowledge for communicating quantum computing, quantum information and algorithms, quantum networks and communication, quantum sensing and post-quantum cryptography to non-specialists. Use it together with the scicom skill whenever the topic is quantum science or technology, for news items, press releases, social posts, explainers, talks or policy briefs, or when someone asks to explain a quantum paper or result.
---

# Quantum add-on for scicom

This add-on supplies subject knowledge only. Follow the `scicom` skill for the workflow, formats, accuracy rules, quote rule and review checklist; load it if it is available.

If scicom is not installed, still apply its core rules:
- never invent facts, numbers or quotes;
- mark unknowns `[CHECK]`;
- state the type of evidence and the stage.

## Audiences

- **Knowledge is polarised.** Public knowledge of quantum is polarised: most people know either very little or a great deal (MIT Quantum Index Report 2025, a US survey). On mixed channels, write the opening for people who know nothing, and add depth further down.
- **Two common beliefs to correct:** "it's decades away and irrelevant", and "it will break all encryption tomorrow". Both are wrong.
- **Decision-makers** (policy, industry, funders) need:
  - the stakes;
  - timelines as ranges with sources;
  - what is near-term (sensing, networks, post-quantum cryptography) and what is not.

## Analogies that mislead, and better framings

| Concept | Common analogy | Problem | Better framing |
|---|---|---|---|
| Superposition | "0 and 1 at the same time"; a spinning coin | Suggests two definite values at once; a coin shows chance, not superposition | A qubit's state combines possibilities with weights (amplitudes). It is not secretly both, and measuring it gives one outcome |
| Quantum speed-up | "Tries all answers at once" | Suggests brute-force parallelism; ignores interference | Algorithms choreograph possibilities so that wrong answers cancel and right ones reinforce. Speed-ups exist only for specific problems |
| Entanglement | "Spooky action at a distance", "instant communication"; twins, dancers, compass needles | Suggests faster-than-light signalling; physicists rated these analogies low | Entangled systems share correlations no classical model explains, but no information travels between them |
| Quantum error correction | "Like classical error correction, but harder" | Misses the ban on copying and the limits on measuring | It must protect information it may not look at directly; it measures only checks (syndromes) on groups of qubits |
| Measurement | "Opening the box to look" | Suggests passive observation | Measurement is an interaction that forces a definite outcome, more like a question that changes the answer |

**Using any analogy:**
- Say what it illustrates, and where it breaks down. If the breakdown is interesting, use it as the hook.
- Treat analogies you generate as drafts for a physicist to check.
- Draw fresh analogies from waves, resonance, balancing, social coordination, games or puzzles.
- Avoid computer metaphors that assume what you are trying to explain.

## Mystique

- **What the research shows:**
  - About a quarter (23%) of 501 English TEDx talks on quantum (2009–2021) framed it as spooky or weird (Meinsma et al. 2023).
  - In 385 Dutch newspaper articles (2009–2021), benefit (33%) and enigma (24%) were common themes, and risk rare (6%). About half the articles that named a technology explained the physics (Meinsma et al. 2025).
  - In an experiment with 637 Dutch adults (representative, preregistered), calling quantum "enigmatic" (one word, shown once) made no measurable difference to engagement; explaining the physics raised self-reported interest (Meinsma et al. 2026a).
- **What follows:** mystique explains nothing, so never use it instead of an explanation. "Spooky" often comes from researchers' own quotes: suggest a plain alternative, but don't rewrite the quote. Avoid wording pseudoscience borrows ("everything is connected").
- **Balanced frames:** in the same experiment, presenting both a benefit and a risk lowered how much people *felt* they knew. That is no reason to drop risks (our view, and the authors' ethical one). A concrete benefit also raised people's sense that they could engage.
- **Metaphors:** in an experiment with 1,167 Dutch adults reading a news article about a quantum computer, explanations of superposition or entanglement raised actual understanding, but lowered how well readers *felt* they understood the article. Metaphorical explanations offered no benefit over plain ones. Effects were small, and real understanding stayed low (Meinsma, Reijnierse & Cramer 2026b). The authors conclude that you should explain if you want real understanding, and that metaphors add nothing. Using analogies to head off misconceptions is our advice. In a short item, aim for one idea correctly grasped, and link for depth.

## Look beyond quantum computing

Coverage concentrates on quantum computers: in TEDx talks (Meinsma et al. 2023) and in Dutch newspapers, where computing featured in 40% of articles and sensing in two (Meinsma et al. 2025). The authors expect sensing to reach daily life sooner; networks and post-quantum cryptography may too. Ask whether computing is really the most relevant angle.

## Subfield framings

- **Error correction:** quantum information is extremely fragile, and the ingenuity lies in protecting it. Always distinguish physical from logical qubits.
- **Algorithms:** say what an algorithm achieves and why that is hard classically, before (or instead of) the circuit. Grover, Shor, VQE and QAOA each have a different story.
- **Complexity theory:** questions about what nature allows us to compute efficiently.
- **Networks and communication:** being tested in city-scale networks; secure communication, distributed computing, a future quantum internet. Separate what has been demonstrated from what is theoretical.
- **Sensing:** perhaps the nearest-term application (navigation, imaging, materials research). Check the claim for the specific sensor.
- **NISQ-era results** (today's noisy, intermediate-scale machines): frame them within the limits of the hardware. Avoid both "advantage is here" and "NISQ is useless".
- **Quantum software and information theory:** the layer between hardware and applications. It finds clever ways to use strange physics.
- **Post-quantum cryptography:** classical encryption that resists quantum attacks, already standardised and being rolled out. "Harvest now, decrypt later" makes it urgent for long-lived secrets. Never raise that threat without the response: migration to post-quantum cryptography exists, and organisations can start with an inventory of what they encrypt.

## Quantum claim checks (in addition to scicom's checklist)

- **Qubits:** physical or logical? Qubit counts mean little without error rates and coherence times.
- **"Quantum advantage" or "supremacy":** on which task, against which classical method, and has it been challenged since?
- **Evidence and platform:** theory, simulation or hardware? Which platform: superconducting circuits, trapped ions, photons, spins, neutral atoms?
- **Speed-up:** for which problem? Theoretical (asymptotic) or measured, and including overheads?
- **Timelines** ("useful quantum computers by…", "Q-day"): only if the researchers give and justify them. Otherwise give ranges, with sources.
- **"First":** compared with recent competing work?
- **Limits paragraph:** every quantum news item has at least one paragraph on limitations, risks or uncertainty, and a central limitation is not only at the bottom. No mystique in the headline or lede.

## The quantum hype ecosystem

- **Researchers:** in focus groups with 24 quantum physicists at one research centre, most said they used hype strategically, mainly for funding (Soto-Sanfiel et al. 2025). Calibrate your own researchers' claims too.
- **Companies:** corporate interest has grown fast (MIT Quantum Index Report 2025), and commercial framing leaks into research news.
- **Media:**
  - Of 192 online US national news stories from 2022–2023, about 16% were exaggerated. More than three-quarters never mentioned risks, and close to 70% never mentioned uncertainty. Exaggeration sat mostly in headlines and ledes. Writers with a science background gave more substantive detail but did not exaggerate less (Wang & Xu 2025).
  - In Dutch newspapers, risks and economic or social-progress themes were less common than benefit and enigma (Meinsma et al. 2025).
  - Dutch quantum coverage is concentrated in a few national newspapers and a small group of science reporters (2009–2021). Check who covers it now.
- **Your advantage is credibility:** a calm, precise voice when others are breathless. Don't overcorrect: if a result is genuinely significant, say so.

## Writing in Dutch (only if asked)

Use established Dutch terms in running text: verstrengeling (entanglement), superpositie, quantumcomputer, qubit. Add the English term in brackets on first use where it helps.

## Sources

All findings above were checked against the published full texts in October 2026.

- MIT Initiative on the Digital Economy (2025). *Quantum Index Report 2025*. arXiv:2506.04259
- Meinsma, A. L. (2026). *In a State of Superposition: Exploring (In)Effective Public Communication About Quantum Technology*. PhD thesis, Leiden University: https://hdl.handle.net/1887/4288270
- Meinsma, A. L., Reijnierse, W. G. & Cramer, J. (2026b). Like a coin spinning in the air: the effect of (non-)metaphorical explanations on comprehension and attitudes towards quantum technology. *Metaphor and the Social World* 16(2): https://doi.org/10.1075/msw.25018.mei
- Meinsma, A. L. et al. (2023). Is everything quantum 'spooky and weird'? An exploration of popular communication about quantum science and technology in TEDx talks. *Quantum Science and Technology* 8: 035004: https://doi.org/10.1088/2058-9565/acc968
- Meinsma, A. L., Rothe, T., Reijnierse, W. G., Smeets, I. & Cramer, J. (2025). Quantum in the media: a content analysis of Dutch newspapers. *Science Communication* 48(1), 2026: https://doi.org/10.1177/10755470251318300
- Meinsma, A. L., Albers, C. J., Vermaas, P. E., Smeets, I. & Cramer, J. (2026a). The effect of frames on engagement with quantum technology. *EPJ Quantum Technology*: https://doi.org/10.1140/epjqt/s40507-026-00549-0
- Soto-Sanfiel, M. T., Chong, C.-W. & Latorre, J. I. (2025). *Humanities and Social Sciences Communications*: https://doi.org/10.1057/s41599-025-05200-4
- Wang, M. & Xu, D. (2025). *Online Media and Global Communication*: https://doi.org/10.1515/omgc-2025-0009
- QuSoft's earlier quantum-scicomm skill: the analogy table and subfield framings.
