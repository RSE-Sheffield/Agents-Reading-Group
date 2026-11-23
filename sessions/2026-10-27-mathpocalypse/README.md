# Mathpocalypse

## AI Agents and the Rise of Machine-Generated Mathematics

Session materials for the RSE agents reading group on the "Mathpocalypse": the sudden explosion of
research-level mathematics produced by AI agents, and what it means for how research is done,
checked, and credited.

> **Current deck:** `slides.md` has been reworked as a ~20-minute horizon-scan briefing for the
> **IT Services Executive** (CTO, Product & Delivery, Head of Product, Head of InfoSec, Head of IT
> Services). It keeps the maths as the case study but frames it for a technical, non-mathematician
> audience: verifiers as CI, trust as the bottleneck, shadow AI, security and the recurring
> research-AI stack. The evidence pack is
> [`docs/it-services-exec-research/`](docs/it-services-exec-research/it-services-exec-update-research.md).
> The original reading-group deck (27 Oct 2026) is in this repo's git history (commit `fbe9f9e`).

## Overview

In five weeks the landscape changed. On **8 September 2026** OpenAI announced that a swarm of
~10,000 agents, running an unreleased internal model for 88 hours, had produced a 166-page,
Lean-formalised proof of finite-time blow-up for the 3D Navier–Stokes equations with smooth forcing
— one of the Clay Millennium Prize alternatives. On **6 October** it released **722 manuscripts in
372 result families** from ~4,000 open problems posed to the same model. Three were withdrawn within
a day.

The session has two halves: **how it was achieved technically** (agent swarms, autoformalisation in
Lean 4, independent checking with Comparator) and **what it means for research** (proof vs
understanding, who pays for verification, credit and priority, and a two-tier science built on
proprietary models). Recurring theme, carried over from the
[01/09 session](../2026-09-01-agents-reviewing-old-papers/README.md): *generating results is now
cheap; adjudicating them is not.*

## Contents

| Path | What it is |
| --- | --- |
| `README.md` | This session plan |
| `slides.md` | The deck (IT Services Executive briefing) — Marp Markdown |
| `slides.css` | `uos` Marp theme (University of Sheffield branding) |
| `references.bib` | BibTeX for everything cited in the deck |
| `images/` | Logo and slide assets |
| [`docs/`](docs/README.md) | Research notes gathered while preparing the session (indexed in `docs/README.md`) |

## Building the slides

Slides are [Marp](https://marp.app/) Markdown using the `uos` theme in `slides.css`. From this
directory (no install needed):

```bash
npx @marp-team/marp-cli@latest -s . --theme-set slides.css                       # live preview: http://localhost:8080/slides.md
npx @marp-team/marp-cli@latest slides.md --theme-set slides.css -o slides.html   # HTML
npx @marp-team/marp-cli@latest slides.md --theme-set slides.css --pdf            # PDF
```

Without `--theme-set`, Marp falls back to its default theme. See
[CONTRIBUTING.md](../../CONTRIBUTING.md#previewing-marp-slides-locally) for more options, including VS Code.

## Background reading

In order, if time is short:

1. **OpenAI — On the Navier–Stokes Millennium Prize Problem** (8 Sep 2026)
   <https://openai.com/index/navier-stokes-solution/>
2. **OpenAI — Sharing AI progress in mathematics** (6 Oct 2026)
   <https://openai.com/index/sharing-ai-progress-in-mathematics/>
3. **Quanta — "AI Has Solved One of Math's $1 Million Millennium Prize Problems"** — the best
   plain-language explainer of the maths and the swarm
   <https://www.quantamagazine.org/ai-has-solved-one-of-maths-1-million-millennium-prize-problems-20260908/>
4. **Terence Tao — blog post on finite-time blowup with smooth forcing** — how the construction works,
   and the human (AI-assisted) work it builds on
   <https://terrytao.wordpress.com/2026/09/07/finite-time-blowup-with-smooth-forcing-term-for-the-incompressible-porous-medium-boussinesq-and-incompressible-euler-equations>
5. **Bastounis, Circelli & Hansen — "Navier–Stokes lost in translation"** — why "Lean-verified" does
   not automatically mean "the English proof is right"
   <https://arxiv.org/abs/2610.08144>
6. **The `openai/math` repository README** — how the 722 manuscripts were produced and labelled
   <https://github.com/openai/math>
7. **Feng et al. — "Towards Autonomous Mathematics Research"** (Google DeepMind's Aletheia) — the
   earlier, more measured precedent, with autonomy/novelty ratings and "human–AI interaction cards"
   <https://arxiv.org/abs/2602.10177>

Optional:

- Fortune's account of the priority dispute and Tao's critique —
  <https://fortune.com/2026/09/08/openai-says-it-cracked-navier-stokes-math-grand-challenge-buckmaster-accusation-cheating-intimidation-tao-lament/>
- Cornell Daily Sun, "We asked Cornell professors what this means for the future of research" —
  <https://www.cornellsun.com/article/2026/10/openai-claims-it-solved-the-navier-stokes-problem-we-asked-cornell-professors-what-this-means-for-the-future-of-research>
- Clay Mathematics Institute statement — <https://www.claymath.org/news/navier-stokes-announcement>

## Timed agenda

| Time | Activity | Who |
|------|----------|-----|
| 3:00–3:10 | Intro & framing — what is the "Mathpocalypse"? | Joe |
| 3:10–3:35 | How it was done — lineage (2024–26), the two pipelines, the swarm, Lean 4 & Comparator | Joe |
| 3:35–3:45 | What was actually proven — the forcing loophole, the translation gap, the cascading withdrawal | Joe |
| 3:45–4:10 | Practical activity: *Read the certificate* (see below) | All, in pairs |
| 4:10–4:30 | Discussion — what it means for research (see prompts below) | All |

Total: 90 minutes.

## Practical activity — "Read the certificate" (~25 min)

**Goal:** get a feel for what a machine-checked certificate actually guarantees, and how far that is
from the headline. No Lean experience needed for tracks A and B.

Pairs pick **one** track (15 min), then report back (10 min).

### Track A — Statement vs headline (no install)

1. Open the Comparator challenge file
   [`ComparatorChallenges/NavierStokes.lean`](https://github.com/openai/NavierStokesAndEuler/blob/main/ComparatorChallenges/NavierStokes.lean)
   and find `navier_stokes_breakdown_R3` near the bottom.
2. Write the theorem out in plain English. Follow the definitions it uses
   (`InitialVelocityConditionDecay`, `ForceConditionDecay`, `NavierStokesExistenceAndSmoothnessRn`).
3. Compare with the press headline "AI solves Navier–Stokes". Where is the **forcing** `f`? Who chooses
   it? What does "uniformly bounded kinetic energy" rule in or out?
4. The statement was adapted from Google DeepMind's independently written
   [Formal Conjectures](https://github.com/google-deepmind/formal-conjectures/blob/main/FormalConjectures/Millennium/NavierStokes.lean)
   version. Why does it matter that the *statement* came from a different party than the *proof*?

### Track B — Audit a manuscript family (no install)

1. Open the [`openai/math`](https://github.com/openai/math) overview and pick one result family
   (or one of the 10 with reasoning summaries).
2. Score it against the IAS Advisory Group's disclosure checklist: model named? prompts? summarised
   chain of thought? time & compute? Lean formalisation? number of failed attempts? How were
   problems chosen?
3. How long would it take *you* (or a colleague in that field) to be confident it is correct and
   novel? Multiply by 719.

### Track C — Build and inspect (optional; needs [elan](https://github.com/leanprover/elan))

```sh
git clone https://github.com/openai/NavierStokesAndEuler && cd NavierStokesAndEuler
lake exe cache get && lake build
```

Then add `#print axioms NavierStokes.Comparator.navier_stokes_breakdown_R3` to a scratch file. What
axioms appear, and what would you be worried to see there? Look at `formalization.yaml`: what does
`sorry_count: 0` certify, and what does it not? (Allow plenty of time for the Mathlib cache.)

### Report back

Each pair answers: *in one sentence, what has actually been verified, and by whom?*

## Discussion prompts

Aim to cover at least four.

1. **Proof vs understanding** — Tao argues that solving problems is "only a proxy goal for the
   primary goal of developing mathematical understanding". If a 166-page proof is correct but nobody
   understands it, has mathematics advanced?
2. **Who pays for verification?** — 719 unreviewed manuscripts land on the community at once. Is this
   a gift or a denial-of-service on peer review? What would a sustainable model look like? (cf. the
   01/09 session: finding is cheap, adjudicating is expensive.) Note that the labs have released
   results via GitHub repos and blog posts, but (as of 18 Oct 2026) none has announced submitting any
   to an academic journal. Should they, or is formal verification plus open review a better route?
3. **Credit and priority** — Buckmaster and Alpöge were weeks from a related result using AI tools,
   including OpenAI's. How should credit work when a lab's model may have seen users' sessions, or
   when the "closest humans" are outpaced by a swarm?
4. **A two-tier science?** — The results came from an unreleased, proprietary model; the Navier–Stokes run alone cost
   millions of dollars. The IAS group asks labs to stop testing open problems on proprietary models.
   Is that realistic? What does it mean for universities?
5. **Beyond maths** — Maths is unusually well suited to this because Lean gives a cheap, trustworthy
   check. What's the equivalent "verifier" in physics, engineering or software — and where is there
   none? (cf. [formal verification in physics & engineering](../../ideas/formal-verification-physics-engineering.md))
6. **A new kind of research?** — Is this a genuinely new mode of research, or the industrialisation
   of an old one (search + check)? What remains distinctively human — choosing the questions, the
   "art side", explanation?
7. **The "six fingers" stage?** — A few years ago AI images gave themselves away with six-fingered
   hands; now those flaws feel like ancient history. Are the forcing loopholes, translation gaps and
   withdrawn manuscripts the "six fingers" of AI maths, early flaws that will be fixed if
   capabilities keep improving at their current (roughly exponential) pace? What's the tell-tale
   flaw in *your* field today, and is anything *not* going to be fixed by scale?
8. **What would we want?** — If you were on the IAS advisory group, what single rule would you add
   for releasing AI-generated research results in *your* field?

## Related

- [Harmonic Aristotle idea](../../ideas/mathematics-harmonic-aristotle.md) — Lean-native automated
  theorem proving; a natural deep-dive follow-up
- [Agents Reviewing Old Papers (01/09/2026)](../2026-09-01-agents-reviewing-old-papers/README.md) —
  the triage/false-positive problem from the other direction
- [Research certificates (10/11/2026)](../2026-11-10-research-certificates.md) — generalising
  machine-checkable certificates beyond maths
- Edwin Brown, "Agentic Research: From Basics to Full Agentic Armour" (RSE talk, 12/11/2026) — why agents need a
  *verifiable*, *navigable* and *accessible* environment; the framework behind "Why maths went first". See also
  [formally verified quantum programs (arXiv:2611.09822)](https://arxiv.org/abs/2611.09822), his example of verifiable science
