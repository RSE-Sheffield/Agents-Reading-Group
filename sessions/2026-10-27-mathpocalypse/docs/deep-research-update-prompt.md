# Deep Research prompt: Mathpocalypse update (19 Oct – 19 Nov 2026)

Prompt for a Deep Research tool to catch up on developments since the session materials were
prepared (sources gathered 18–19 Oct 2026; session held 27 Oct 2026).

---

## Prompt

I ran a university discussion session (27 Oct 2026) on the "Mathpocalypse": the recent flood of
research-level mathematics produced by AI agents. My sources date from **18–19 October 2026**.
Please find and summarise what has happened **between 19 October 2026 and today (19 November
2026)**, so I can update the slides and notes. Only include something from before 19 October if it
was missed and matters a lot, and label it as such.

### What I already know (don't re-report this unless it has changed)

- **8 Sep 2026:** OpenAI announced that a swarm of ~10,000 agents on an unreleased internal model,
  running for 88 hours, produced a 166-page Lean-formalised proof of finite-time blow-up for 3D
  Navier–Stokes with smooth forcing (repo `openai/NavierStokesAndEuler`; Comparator check;
  statement adapted from Google DeepMind's Formal Conjectures). There is a priority dispute with
  Buckmaster (NYU) and Alpöge, and critiques from Tao. The "forcing loophole" and the
  English-to-Lean "translation gap" (Bastounis, Circelli & Hansen, arXiv 2610.08144) are covered.
  The Clay Mathematics Institute issued a statement.
- **6 Oct 2026:** `openai/math` released 722 manuscripts in 372 result families from ~4,000
  problems (~42% Lean-formalised, 10 reasoning summaries). Three were withdrawn within a day after a
  sign error cascaded, 14 were revised, and the README now says 719. Claims include the Unique
  Games Conjecture and L = BPL, plus partial progress on Riemann and Hodge.
- **Responses:** IAS Advisory Group recommendations (29 Sep); the Leiden Declaration (IMU-endorsed,
  June); the Fields Medallists' "A Severe Misalignment of AI in Mathematics"; the Association for
  Human Mathematics statement (Oct); Aaronson's "The Mathocalypse" (7 Oct); Tao's "Math 2.0" and ICM
  essay; Gowers on the jagged frontier; Szegedy's "Quo Vadis, Mathematics?".
- **Other labs and tools:** DeepMind's Aletheia (Feb 2026), AlphaProof and AlphaEvolve; an
  unreleased Claude model's partial Riemann-hypothesis progress (Aug); Harmonic's Aristotle; Math,
  Inc.'s Gauss; AxiomProver; DeepSeekMath-V2 and the open provers; Open Math OS; Tao's
  crowdsourced GitHub projects (Equational Theories, Erdős problems, optimisation constants).

### What to find

1. **OpenAI's follow-up.** Especially
   <https://openai.com/index/building-scientific-understanding-with-academic-communities/>: what
   exactly it announces (programmes, partners, funding, model access, disclosure commitments), when,
   and how it maps onto each of the IAS Advisory Group's seven recommendations. Also: any further
   result releases, changes to the `openai/math` repo (withdrawals, revisions, new formalisations,
   manuscript count), journal or arXiv submissions, release of the model behind the results, and
   new statements on the Buckmaster/Alpöge priority dispute.
2. **Verification status of the headline claims.** Independent checks, refutations or endorsements
   of the Navier–Stokes proof and of the biggest `openai/math` claims (UGC, L = BPL, and others).
   Any statement or process from the Clay Mathematics Institute. Expert reviews, workshops or
   seminars dedicated to checking them. New work on the translation gap or on Comparator.
3. **Other labs.** Announcements from Google DeepMind, Anthropic, Harmonic, Math Inc., Axiom,
   DeepSeek, Mistral, Meta, xAI and academic groups: new results on open problems, new maths
   models or agents, releases to the public, academic access schemes, and any adoption of the
   IAS recommendations.
4. **Community and institutional responses.** New statements or policies from the IMU, AMS, LMS,
   EMS, IAS, Clay, journals and arXiv (e.g. policies on AI-generated submissions or bulk
   releases), funders (UKRI/EPSRC, NSF, ERC, Simons, Renaissance Philanthropy/XTX) and universities.
   Updates from the Association for Human Mathematics, the Fields Medallists' group or the Leiden
   Declaration. Notable blog posts, essays or talks by Tao, Gowers, Aaronson, Litt, Wood,
   Strogatz, Buzzard, Kontorovich, Szegedy and others.
5. **Open and crowdsourced efforts.** Progress in Formal Conjectures, the Erdős problems wiki,
   Mathlib, Equational Theories follow-ups, and public-model results by amateurs or small teams.
6. **Beyond maths.** Comparable "agent swarm plus verifier" claims in theoretical physics, computer
   science, software verification or other sciences, and debates about transferring the model.
7. **Media and numbers.** Major coverage (Quanta, Nature, Science, SciAm, FT, NYT and others) and any
   reported figures on cost, compute or the number of attempted versus failed problems.

### How to report

- **Sources:** use primary sources where they exist (lab posts, GitHub repos and commit history,
  arXiv papers, official statements, authors' own blogs). Use journalism for context and reaction.
  Give the URL and publication date for every claim.
- **Hedging:** this story is contested and fast-moving. Mark each item as **confirmed** (primary
  source), **reported** (secondary source only) or **disputed**. When sources disagree, give both
  sides and say which is primary. Don't present lab marketing figures as independently verified.
- **Balance:** keep the tone neutral to optimistic. The session's stance is that AI progress in
  maths is broadly good for research. Still present critical and sceptical views fairly; I need
  them as discussion material.
- **Structure:**
  1. A dated **timeline** (19 Oct – 19 Nov 2026) of the significant events, one line each.
  2. One **section per topic** above. Say explicitly if you found nothing for a topic.
  3. **What has changed:** a list of claims in my "What I already know" summary that are now
     outdated or wrong, with the correction.
  4. **Suggested slide updates:** 5–10 concrete edits (e.g. "Update the bulk-release slide count
     from 719 to N").
  5. **New discussion questions** raised by the developments (2–4).
  6. **Bibliography** in BibTeX (`@online` with `url`, `date` and `urldate = {2026-11-19}`), for
     every source cited.
