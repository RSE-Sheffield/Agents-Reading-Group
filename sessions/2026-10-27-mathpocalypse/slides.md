---
marp: true
theme: uos
paginate: true
---

<!-- _class: lead -->
<!-- _footer: "Albrecht Dürer, _The Four Horsemen_ (1498). National Gallery of Art, CC0, with AI company logos added (trademarks of their owners)" -->

![bg right:36%](images/durer-four-horsemen-ai.jpg)

![width:220px](images/UOSLogo_Primary_White_RGB.png)

# Mathpocalypse

_AI agents and the dawn of machine-generated mathematics_

Joe Heffer
November 20th 2026


<!-- Horizon-scan briefing, ~20 minutes. No decisions requested today: the aim is a shared picture and a good discussion. The title is a joke; the stance is optimistic. Evidence is current to 19 November 2026 (see docs/it-services-exec-research/it-services-exec-update-research.md and, for 19 Oct – 19 Nov, docs/deep-research-update-2026-11-19.md). -->

---

## Overview

_AI agents can now do frontier research._

- **What** happened in mathematics?
- **How** is it done?
- Can we trust it?
- After math: Impact on the research ecosystem

<!-- The headline is simple: in autumn 2026 AI systems started producing results on open research problems, not just exam questions. Everything else in the deck follows from that. The middle section is the "how": thousands of agents working in parallel, with a proof checker (Lean) deciding what counts. Trust, other fields and what it means in practice are the questions that fact raises. -->

---

<!-- _class: lead -->
<!-- _footer: "Katsushika Hokusai, _The Great Wave off Kanagawa_ (c. 1830–32), cropped. Metropolitan Museum of Art, public domain" -->

![bg right:45%](images/hokusai-great-wave.jpg)

# Introduction

_Five weeks that changed mathematics_

<!-- The wave: hundreds of machine-made manuscripts landing at once. Hokusai's boatmen are still rowing. -->

---

<!-- _class: small -->
<!-- _footer: "Blow-up vortex visualisation from OpenAI, \"On the Navier–Stokes Millennium Prize Problem\" (8 Sep 2026). © OpenAI" -->

![bg right:25% fit](images/openai-navier-stokes-vortex.jpg)

## Three headline events

_In autumn 2026, AI labs stopped answering exam questions and started producing research at industrial scale_

- **4 Sep — Fermat's Last Theorem formalised** (Anthropic): a famous 1990s proof turned into machine-checkable code. ~**13M lines** of Lean in **11 days**
- **8 Sep — Navier–Stokes** (OpenAI): ~**10,000 agents**, **88 hours**, an unreleased model. A machine-checked proof that a fluid can suddenly "break", claiming one route to a $1M Millennium Prize problem
- **6 Oct — the bulk release** (`openai/math`): ~4,000 open problems → **722 manuscripts** in one drop. **3 withdrawn** next day; only ~42% machine-checked

<!-- FLT: Anthropic research posts plus several secondary accounts (confidence Medium–High; the briefing couldn't fetch the Anthropic blog directly). It's a formalisation of a known theorem, not a new result, but it shows what an agent swarm can do with a verifier. Kevin Buzzard (Imperial): "an amazing feat of automatic formalization". Re-checked by an independent kernel (nanoda) and by Comparator.

Navier–Stokes: OpenAI says it won't claim the prize; Clay calls the problem "apparently settled" but has awarded nothing and runs a deliberately unhurried process (publication + 2 years). Clay's news page has nothing newer than 11 Sep (checked 19 Nov). Bulk release figures from the openai/math changelog as reported by Science and Retraction Watch: 300 of 719 top-line results formalised (~42%). Count history: 722 at release → 719 after the 7 Oct withdrawals → 721 in 373 families since 26 Oct, when the ETH and local smoothing manuscripts were added (commit 42907c9). Re-check the live repo before presenting. -->

---

<!-- _class: small -->

## Since then: a second wave, and a lab race

_26 Oct – 19 Nov: more big claims, a new way of releasing them, and the first expert checks_

- **26 Oct — OpenAI's second wave** (same unnamed internal model), all claims for now:
  - **ETH refuted**: a widely assumed limit on how fast hard problems can be solved
  - **Local smoothing**, which OpenAI says settles the Kakeya conjectures
  - **Yang–Mills / QCD existence** in 4D physics (not the mass gap, so no Millennium Prize)
- **Same day:** Anthropic reportedly posts its own ETH refutation. The story becomes a **lab race**
- **"Shepherds":** OpenAI hands each result to hand-picked expert groups (unpaid, no NDAs) and says it seeks "no academic credit"
- **First checks:** ETH is "toast" (Fortnow); the Unique Games proof worked through with its originator; Yang–Mills reviewers: "We do not claim to fully understand the proof yet." **Still no peer review**

<!-- Sources: docs/openai-academic-communities.md (post text, copied in by hand) and docs/deep-research-update-2026-11-19.md §2.1–2.2. All results are lab claims. ETH = Exponential Time Hypothesis (Impagliazzo & Paturi): it underpins conditional hardness results in hundreds of papers. Found 16 Oct, Lean-checked 17 Oct (OpenAI's account). Shepherds: Impagliazzo, Paturi and Williams (ETH; they asked for immediate public release and say their role "should not be taken as certification"); David Gross with Douglas, Jaffe, Klebanov and Nekrasov (physics; they held the AI material back). Fortnow (28 Oct): "I have not verified the proof myself, but it is safe to assume now that the exponential-time hypothesis is toast." UGC: Dana Moshkovitz studied it with Subhash Khot, Johan Håstad and Dor Minzer, talk at UT Austin 4 Nov titled "Proved (!!?)". Yang–Mills scope is disputed: Woit calls the release a "publicity stunt" and the result "weak existence"; Kalai calls it a major breakthrough. Anthropic's ETH date is disputed in secondary sources; 26 Oct is most likely, primary not read.

The advisory group at IAS (AGMAI) objected the day before (25 Oct) to labs pre-designating mathematicians: unequal access, biased selection, "borrowed reputation". It asked on 26 Oct for the Yang–Mills outputs to be released "without delay"; Lean code reportedly public by ~11 Nov, the ~1,147-page write-up reportedly not. -->

---

<!-- _class: small -->

## How big is this?

_Any one of these results, if confirmed, would make a human mathematician famous overnight_

> "One of the biggest days in mathematical history." — **Scott Aaronson** (UT Austin), on the 6 Oct release

> "If the claim is correct, it will change an important part of theoretical computer science." — **Impagliazzo, Paturi & Williams**, on the ETH refutation

> "They went from being mediocre undergraduates to being the best mathematicians on the planet." — **Richard Borcherds** (Fields Medal 1998)

- **A career's problem, solved:** Aaronson's son teased his mother, Dana Moshkovitz, that a robot had solved the Unique Games Conjecture she'd worked on her whole career. "He also wasn't wrong"
- **"Result of the year"** in its area, for any one of several results (Aaronson). At least a dozen "could have merited a Fields Medal in the pre-AI era" (*Scientific American*)
- **Even the labs were surprised:** "I did not expect a result of this magnitude to happen so soon" (Sam Altman, on Navier–Stokes)

<!-- The point of this slide: these aren't incremental papers. Under normal circumstances, each of the headline results would be a career-defining achievement for a human mathematician. Hedge: almost none of it is peer-reviewed yet.

Aaronson, "The Mathocalypse", Shtetl-Optimized, 7 Oct (aaronson2026mathocalypse; docs/aaronson-mathocalypse.md §1). His "Aladdin's cave" shortlist from his own fields: Unique Games, L = BPL, integer multiplication below n log n, the unitary synthesis problem (which he posed with Kuperberg in 2007; the answer is the opposite of what most people expected) and a new route to fast matrix multiplication. "Result of the year" applies within each area, and for UGC and L = BPL across all of CS theory. Moshkovitz is a complexity theorist at UT Austin, married to Aaronson. Her later verdict on the UGC paper is that it is "so horribly written that it's impossible to read it without AI help" (The Decoder, 8 Oct; decoder2026boycott). That leads into the trust section.

Impagliazzo, Paturi and Williams are the ETH "shepherds"; Impagliazzo and Paturi formulated the hypothesis. Quote via The Next Web, 26 Oct (tnw2026eth). In the same statement: "Our involvement should not be taken as certification of the claim."

Borcherds: Theories of Everything, 9 Nov (jaimungal2026borcherdsweinstein), around 01:49. Speaker attribution is inferred from a partial transcript, so rewatch before presenting. He also says it "was a real shock to pretty much all mathematicians".

The "Fields Medal" line is the journalist's framing (Howlett, Scientific American, 13 Oct; sciam2026notwhat), not a named mathematician's. Altman: X post, 8 Sep (altman2026navierstokes). He is the CEO of the lab making the claim, so treat it as a sign of surprise, not as evidence.

For balance: on Yang–Mills, Woit says "weak existence" and Kalai says "major breakthrough". The size of each claim is still being argued over, not only whether it is correct. -->

---

<!-- _class: lead -->
<!-- _footer: "Paul Erdős and Terence Tao, University of Adelaide, 1985 (cropped). Photo: Billy or Grace Tao, CC BY-SA 2.0" -->

![bg right:50%](images/erdos-tao-1985.jpg)

# How we got here

_From competition problems to open problems_

<!-- Erdős working through problems with a 10-year-old Terence Tao. Tao is the field's most-quoted voice on AI; Erdős problems became the standard test for AI novelty claims. -->

---

<!-- _class: small -->

<style scoped>
table { font-size: 0.85em; }
</style>

## From exams to open problems in two years

_**2024–25:** AI matched the best students on problems with known answers.
**2026:** problems _nobody_ had solved_

| When | What | Why it matters |
|------|------|----------------|
| 2024 | **AlphaProof**: Maths Olympiad silver | Machine-checked proofs |
| 2025 | **Olympiad golds**, perfect Putnam | Top *student* level |
| 2025 | **AlphaEvolve**: new algorithms | In Google production |
| 2025 | **"Erdősgate"**: "solved" problems already in the literature | Novelty is hard to check |
| May 2026 | **Unit-distance conjecture** disproved (OpenAI) | An Erdős conjecture, checked by outside experts |
| 2026 | **Aletheia** (Dec 2025 model), FLT, Navier–Stokes, 722 papers | Open problems, at scale |
| Late 2026 | **ETH, Yang–Mills**; Lean-checked code | A lab race |

<!--
Also in 2026: Gowers's number-theory results with ChatGPT Pro (May), partial progress on the Riemann hypothesis (Aug) and an amateur's Busy Beaver result with Claude Code (Oct)

"What's surprising is how fast they have gotten good." — Steven Strogatz (Cornell), Oct 2026. Unit distance (20 May 2026): an internal OpenAI model disproved Erdős's 1946 conjecture that the square grid is essentially optimal for planar unit distances. Alon, Bloom, Gowers, Litt, Sawin and others wrote a human-checked, simplified version (arXiv:2605.20695, bib key alon2026unitdistance). The gain is tiny: secondary reports (aggregators, unchecked against primary sources) put the exponent improvement at ~10^-38 initially, with Sawin pushing it to roughly n^1.014. It shows Erdős's limit was too low, not what the true growth rate is. It is the earliest result in this story that outside mathematicians checked, so a useful contrast with Navier–Stokes. The "Also in 2026" line comes from earlier notes: Gowers (May, ChatGPT Pro, "I didn't even do anything clever with the prompts"), Riemann partial progress (Aug, unreleased Claude; see anthropic2026riemannzeta), Busy Beaver (Oct, Claude Code; no primary source checked, so hedge). Aletheia (DeepMind, Feb 2026): 700 open Erdős problems, 4 solved autonomously, and it published its error rate (see "Generation is cheap"). The step change is in *level*, not only volume: from contest problems with known answers to open research problems. Thickstun (Cornell CS) argues progress was continuous over years, not a sudden jump, so the surprise is partly in our expectations. Putnam = hardest undergraduate maths contest in North America; 12/12 claims are self-reported (AxiomProver, Numina-Lean). "Erdősgate" (2025): GPT-5 "solved" Erdős problems that turned out to be in the literature already. -->

---

<!-- _class: small -->

## Why maths went first: verifiable, navigable, accessible

_Agents thrive where their environment is easy to check, easy to move around in, and keeps its context close by. Maths passes all three_

- **Verifiable:** in **Lean**, a proof *is* code: if it compiles, it's correct. Research becomes a familiar loop:
  - **generate:** cheap, noisy, massively parallel
  - **verify:** cheap and (nearly) exact, like a CI pipeline
  - **filter:** keep only what passes the checker
- **Navigable:** **all text**, no lab, no instruments. Proofs build with `lake` like any codebase
- **Accessible:** **Mathlib** and arXiv put the field's knowledge in one searchable place
- And the models are **trained** on exactly this loop (reinforcement learning on checkable answers)

**Rule of thumb:** AI moves fastest where answers are **cheap to check** and the work is **easy to reach**.
Hard-for-humans can be easy-for-machines (Moravec's paradox.)

<!-- Framework credit: Edwin Brown (Senior RSE, Sheffield), "Agentic Research: From Basics to Full Agentic Armour", 12 Nov 2026 (brown2026agenticarmour). His slide 12 explains why agents excel at coding (verification, navigation, accessible context, RL training); his slides 16–20 turn each into questions a researcher can ask of their own work ("Can a physical process be robotised?", "If a new PhD student joined tomorrow, how well could they understand what you've already tried?").

Tao's three reasons maths fell first line up almost exactly: proofs are objectively verifiable, fully digital, and backed by a large high-quality literature. Every bullet has a direct software analogy for this room: Lean ≈ a strictly typed language; `sorry` ≈ a TODO; formalising ≈ porting pseudocode to a typed language. Thinking time also grew from seconds to hours (the Navier–Stokes run took 88 hours).

Discussion: in the domains we support, what's the verifier (test suites, simulators, instruments, trials), what's the API, and where does the data live? The more of the three a field has, the sooner agents arrive. -->

---

<!-- _class: small -->

## Anatomy of the swarm (as reported)

_Architecturally, it's a distributed system with a CI gate on the shared state_

![width:760px](diagrams/swarm.svg)

- **Only verified results** enter the shared library. ~**130bn tokens** in 88 h
- **Cost is falling:** ~6bn output tokens (the FLT run) is roughly **$60k** at list price (*our estimate*)
- **And faster:** FLT took **11 days** in Sep (unreleased model), **30 h** in Nov (public model)

<!-- Swarm description follows OpenAI's account as reported (Tufts Daily and others); figures vary by source. The $60k figure is an estimate from the research briefing: $10 per million output tokens × 6bn; input tokens and retries would raise it. A widely repeated $1–2m figure for the Navier–Stokes formalisation comes from a blog comment and is unverified, so don't quote it. OpenAI reports ~3 hours of "ChatGPT Pro-equivalent" compute per bulk-release result, with no GPU-hours or pounds given. No lab disclosed a cost, GPU-hours or energy figure for any result between 19 Oct and 19 Nov.

FLT redo: Anthropic's Claude Fable 5.2 launch (9 Nov, amended 11 Nov), lab claim, "minimal human intervention". It started from 60 statements, a sketch and 47 reused lemmas, so read "minimal" with care. A caution on swarms: Noam Brown (OpenAI) reportedly said under 10% of the Navier–Stokes success came from the multi-agent setup itself (The Decoder, 17 Oct), so the model matters more than the orchestration. Edwin Brown's anatomy of an agent (brown2026agenticarmour) puts it neatly: the model is the brain, the tools are the hands and the harness is the nervous system. The brain is the hard part; the hands and nervous system are things institutions can build. -->

---

<!-- _class: lead -->
<!-- _footer: "Leonardo da Vinci, _Studies of water passing obstacles and falling_ (c. 1508), detail. Public domain" -->

![bg right:45%](images/leonardo-studies-of-water.jpg)

# Can we trust it?

_Reading the small print_

<!-- Leonardo was drawing turbulence 300 years before Navier and Stokes wrote down the equations. -->

---

<!-- _class: small -->

## Checking the checker: "it compiles" ≠ "it's right"

_Lean proves the code is correct. It can't tell you whether the code says what you meant_

- **Spec vs implementation:** Lean certifies a *formal statement*. Someone must still check it matches the question we care about
- **Spec gaming:** OpenAI's statement lets the prover **choose the force** pushing the fluid. Valid under the official rules, but the case mathematicians really want (no force) is still open
- **Wrong theorem, still compiles:** of ~290 OpenAI Lean packages, ~**38 don't state the paper's main theorem** (Buzzard, 12 Nov)
  *-* **Mitigation:** *Comparator* checks the AI answered a question written in advance by someone else, not an easier one of its own

**IT parallel:** passing tests you wrote yourself proves little. Independent specs and acceptance tests matter

<!-- The forcing loophole: Clay's official problem has four alternatives; OpenAI claims the ones that allow a smooth external force, and its Lean statement reads "there exist a starting flow and a force". Scientific American: it doesn't address the unforced problem "that mathematicians really care about". Translation gap: Bastounis, Circelli & Hansen, "Navier–Stokes lost in translation", arXiv:2610.08144. KCL's 27 Oct press release has the authors saying they "have not shown the original proof is wrong", only that the Lean version "does not fully match" (reportedly at Lemma 8.6). Buzzard, "…and the proof is checked in Lean" (Xena, 12 Nov): the ~640K-line Navier–Stokes formalisation compiles under several kernels; across the bulk release ~290 of 722 papers came with Lean code, and ~38 packages prove something else (e.g. the Lech's conjecture package proves Corollary 5.4). Compiling "does not mean that any corresponding pdf also contains a correct proof!" He recommends `lake comparator` plus several kernels. Comparator: leanprover/comparator, now `lake comparator` in core Lean; OpenAI's challenge statement came from Google DeepMind's Formal Conjectures repo. Detail in the backup slides. -->

---

## Where the trust gaps are

_The machine closes one link, from formal statement to formal proof. The rest relies on trust amongst the human research community._

![width:940px](diagrams/trust-gaps.svg)

<!-- Recap in one picture. Green is cheap and near-certain; amber is expert time; red is where the arguments are. For an IT audience: the green link is CI; the amber and red links are requirements sign-off and code review, which don't scale with compute. -->

---

<!-- _class: small -->

## Generation is cheap, trust is not

_One sign error took down three manuscripts within a day: unchecked results behave like untested dependencies_

![bg right:30% fit](diagrams/cascade.svg)

**OpenAI's bulk release, within 24 hours:**
- A **sign error** broke one manuscript; **two others** depended on it → all **3 withdrawn**
- **14 revised**; reasoning traces published for only 10
- Only **~42%** machine-checked; no peer review six weeks on

**DeepMind's Aletheia, on 700 open problems (Dec 2025 model, an early-2026 snapshot):**
- 212 candidates → 63 technically correct → **13 meaningfully correct** → 4 solved
- Only **6.5%** of graded candidates meaningful; some "correct" answers solved a trivial reading of the question
- Measured on an older model: a *floor*, not today's rate

<!-- The cascade diagram is illustrative. The withdrawn paper was "Algebraicity of Weil classes on split abelian eightfolds"; the trio included claimed progress on the rational Hodge conjecture for K3 surfaces, so the most ambitious claims carried the most risk. Aletheia: Feng et al., arXiv:2602.10177, December 2025 model; rates are likely improving, so read 6.5% as a floor, not a current rate. It's the clearest published error-rate evidence, which is why it is used for the verification argument, not as a capability claim. Newer DeepMind results exist but with no comparable error rate: a FirstProof challenge entry (arXiv:2602.21201; reported 6 of 10 problems judged correct by majority of expert assessors, in a study run by the Aletheia team itself; found via secondary search, not checked against the paper) and a semi-autonomous Erdős study (arXiv:2601.22401). No newer published Aletheia error rate found as of 19 Nov 2026. It also warns of "subconscious plagiarism" from training data.

"~42%" is the README's own figure (300 of 719 top-line results). It depends on the unit: Buzzard counts ~290 of 722 papers (~45%) with Lean code, and Yahoo reports 162 of 722 with a machine-checked *main* result. Quote the README with that caveat. Lekili & Sheridan (arXiv:2610.30976, 24 Oct) set out the errors behind the withdrawals. Still no new withdrawals, and no journal or arXiv submission by OpenAI, as of 19 Nov.

A fair counterweight: Scott Aaronson called 6 October "surely one of the biggest days in mathematical history", and expects most results to stand: "this isn't the last one that will have some bug … just like with human papers!"

Discussion: who pays for verification? 719 unreviewed manuscripts at once: a gift, or a denial-of-service on peer review? -->

---

<!-- _class: small -->

## The research system is straining

_Output has doubled in two years. The checking side (preprint servers, peer review) is buckling_

- **arXiv:** **40,363** submissions in Sep 2026, double Sep 2024, with ~9,000 support tickets in one month
  - **Rate-limited:** since 1 Oct, **2 submissions per person per month**; one-year bans for unchecked LLM output (e.g. hallucinated references)
  - **Maths submissions up ~75%** year on year; papers acknowledging AI went from **4% → 25%** (Apr–Aug 2026)
- **Journals pausing:** a probability journal stopped taking submissions for three weeks (19 Oct) over an AI-driven surge; five others reportedly followed
- **Peer review:** **53%** of reviewers use AI tools, often against guidance (87% of early-career)

> "The cost of producing candidates is falling faster than the cost of establishing trust." — Nee et. al., "The Generative AI Gold Rush in Theoretical and Computational Research"

<!--
Nee https://doi.org/10.48550/arXiv.2609.04872

Sources: arXiv blog (1 Oct 2026) for submissions, the cap and bans; Academy for the Mathematical Sciences report (Oct 2026) for 7,428 vs 4,252 maths submissions and the 4% → 25% acknowledgement rise (acknowledgement ≠ AI authorship); Frontiers whitepaper "Unlocking AI's untapped potential" (Dec 2025; 1,645 researchers) for peer review. The quote is from an econometric preprint finding an 11.9% maths-specific excess after controls. Not all of the arXiv growth is AI-driven. Journals: ESAIM: Probability and Statistics paused new submissions 19 Oct – 8 Nov, citing "a substantial increase in manuscript submissions… driven largely by the rapid development of artificial intelligence" (EDP Sciences, confirmed); EJP, ECP, SPA, Bernoulli and AIHP reportedly joined (MACCUS, secondary). The community is building its own triage: MathHelm (13 Nov), a forum for AI-generated papers, says "Mathematicians have no obligation to check AI-generated papers".

For Product/Delivery: this is a capacity-planning story. The bottleneck has moved from producing to checking. -->

---

<!-- _class: small -->

<style scoped>
table { font-size: 0.7em; }
</style>

## The same pattern beyond maths

_Wherever a cheap, objective check exists, AI has moved from paper to production. Slow verifiers mean slow adoption_

| Field | Verifier | V · N · A | Where it's got to |
|-------|----------|:---------:|-------------------|
| **Weather** | Forecast skill | ●●● | **Operational:** ECMWF runs AI forecasts (since 2025) |
| **Algorithms** | Run the code | ●●● | **Beat a 56-year record:** AlphaEvolve's 4×4 matrix multiplication (2025) |
| **Quantum computing** | Lean proofs | ●●● | **Claimed (Nov):** Lean-verified quantum programs (DeepMind); Aaronson–Ambainis (PSI) |
| **Biology** | Wet lab | ◐◐◐ | **Peer-reviewed:** agent "co-scientists" in *Nature* (2026) |
| **Lab automation** | Robotic wet lab | ●●◐ | **Peer-reviewed:** AutoDNA ran 11,000+ steps, humans only restocking (*Nature*, 2026) |
| **Materials** | Simulation, lab | ◐●◐ | **Corrected:** A-Lab dropped "novel" in a correction (2026) |

**V · N · A** = verifiable, navigable, accessible (● yes, ◐ partly; our rough judgement). Sheffield's strengths (materials, manufacturing, biosciences, computer science) are in fields now moving. Medicine, ecology and social sciences still fail one or more of the three tests.

<!-- GraphCast beat ECMWF's deterministic model on 90.3% of targets (Science 382, 2023); GenCast beat the ensemble on 97.2% (Nature 637, 2024). ECMWF AIFS Single operational 25 Feb 2025; ensemble 1 Jul 2025; v2 12 May 2026; runs alongside, not instead of, the physics model. AlphaEvolve (May 2025 white paper, self-reported): 4×4 complex matrix multiplication in 48 scalar multiplications, beating Strassen's 49 (1969); on 50+ open maths problems it matched the best known result in ~75% and improved ~20% (e.g. kissing number in 11 dimensions, 593). Production counterpart: AlphaDev's sorting routines merged into LLVM libc++ (Nature 618, 2023); AlphaEvolve also recovers ~0.7% of Google's compute (Google's own measurement). Co-Scientist (Google) and Robin (FutureHouse), Nature 655. AutoDNA (Nature, 2026): an autonomous nucleic-acid lab orchestrating 20+ instrument types over 11,000+ steps; it shows the slow wet-lab verifier getting faster (full citation not yet checked). A-Lab: originally 41 of 58 targets; Nature's Author Correction revised to 36 of 57 and dropped "novel". Use it as the honest counterweight: simulation is cheap but doesn't by itself establish discovery. Drug: rentosertib (Insilico), Phase IIa in Nature Medicine 2025 (n=71, exploratory). Software: AlphaProof Code (DeepMind, 10 Nov), lab claim: "Gemini Carbon" agents wrote over six million lines of Lean in four weeks verifying Signal's compiled code, flagged ~1% for human review, and caught two deliberately re-inserted bugs; some reports say three million, the blog says six. Harmonic's Aristotle has moved into C, Verilog and Rust (Oct–Nov).

V · N · A ratings apply Edwin Brown's three tests (brown2026agenticarmour) and are our own rough judgement, for discussion rather than measurement. Lab automation is the clearest case of a field making itself navigable: robots turn a wet lab into something an agent can drive (Edwin: "Can a physical process be roboticized?"). Biology and materials have plenty of data but it is scattered and the checks are slow or only partial. Quantum programs: Shirobokov et al., "Discovering formally verified quantum programs with AI" (arXiv:2611.09822, Google DeepMind and Google Quantum AI, 6 Nov 2026, v3 16 Nov; shirobokov2026quantum). Agents write quantum programs in a Lean library against formal specifications and verify both correctness and cost; the abstract reports a 290× improvement for quantum arithmetic and 2.5–12× for simulations relevant to fusion, photochemistry and drug metabolism. Lab paper, not peer-reviewed; figures changed between v1 and v3, so quote the current version. It was Edwin's example of "make your science more easily verifiable".

Physics theory sits near maths and is now getting Lean-checked agent results, all lab claims without peer review: PSI proved the Aaronson–Ambainis conjecture in quantum complexity (6 Nov, non-public Anthropic model, Lean plus human audit); Anthropic claims two black-hole physics results (9 and 17 Nov, one Lean-checked; it says neither describes our universe). Counterweights: the FrontierPhysics benchmark (~4 Nov) has every agent below 30% on end-to-end research tasks; OpenAI's ~2,000 biology agents (21 Oct) had no formal checker, just blinded experts preferring the reports 75% of the time. The pattern holds: the verifier sets the pace. -->


---

<!-- _class: lead -->
<!-- _footer: "Albrecht Dürer, _Melencolia I_ (1514). Metropolitan Museum of Art, CC0" -->

![bg right:40%](images/durer-melencolia-i.jpg)

# In practice

_Shadow AI, security, and the stack_

<!-- Dürer's brooding scholar: surrounded by tools, getting no work done. Existential dread about research is at least 500 years old. -->

---

<!-- _class: small -->

## Researchers are already using it, mostly not through us

_Demand isn't coming through the service desk because researchers have already found their own way in_

- **84%** of researchers use AI in their work, up from 57% a year earlier (Wiley, 2,430 researchers)
- **57%** cite a **lack of guidelines and training** as a barrier; only 41% feel their organisation supports them
- **Early-career researchers lead** (92% use AI), so PhD students set the pace
- **Uneven:** social scientists 81% chatbots, only 20% coding agents; gaps by career stage and gender

**The InfoSec angle:** agents don't just chat. They **run code, read files and call the internet**
- Prompt injection, credential and data leakage, export control, UK GDPR
- Personal accounts mean no data terms and no audit trail

<!-- Wiley ExplanAItions 2025 (2025 data; self-selected survey). Social-science figures: Anthropic survey of 1,260 social scientists (Feb–Mar 2026), vendor-run so hedge. Peers: Oxford (ChatGPT Edu), LSE and Northumbria (Claude for Education), Kent (ChatGPT Edu for all staff). UT Austin bought both ChatGPT Edu and Claude Edu (~$4.2m over two years) and only ~18,000 people created accounts since June (Daily Texan, 29 Oct 2026): licences alone don't drive adoption.

Discussion for InfoSec: what does today's baseline look like? Researchers running agents on laptops with API keys in dotfiles is probably already happening. -->

---

<!-- _class: small -->

## Closer to home: Faculty of Science flash surveys

_217 staff and PGRs across MPS, Biosciences and Psychology (4–16 Nov 2026)_

- **90%** use generative AI, mainly for **code (67%)**, literature (47%) and drafting (37%)
- **Gemini isn't enough:** ~72% have tried it, only **~13%** say it meets day-to-day research needs
- **42% pay out of their own pocket**; only 5% charge AI to grants. The least satisfied pay most
  - In Biosciences, over half of PGRs, postdocs and fellows pay personally, some from stipends
- **Chat, not agents:** coding is the top use, yet only 4–9% use coding agents
- **76%** put **frontier model subscriptions** in their top two priorities; **110+** volunteered for working groups

<!-- Source: Faculty of Science flash surveys synthesis (DAS-46 User Research – Support for AI Strategy), drawing on MPS (Luke Wilson, 12 Nov), BIS (Matt Johnson, 13 Nov) and Psychology (16 Nov) analyses. Self-selected samples, so likely over-represent strong views; no response rates. MPS figures partly worked back from rounded percentages ("c."). The coding-agent figure is BIS 9% and Psychology 4% (not reported for MPS). Pure Maths is among the least satisfied with Gemini (79% partially useful or inadequate) because of weak mathematical reasoning. Critical views to air: a minority (8–15% in BIS/Psychology) oppose central funding, with concerns about ethics, sustainability, and research integrity (one supervisor saw systematic-review quality fall). Same story as Wiley, but local: demand is real and researchers are self-funding the gap. -->

---

<!-- _class: small -->

## The two-tier risk: secret models vs what we can buy

_The headline results used models no university can access, but subscription models are only months behind_

| Result | Model | Can we get it? |
|--------|-------|----------------|
| Navier–Stokes, ETH, 722 manuscripts (Sep–Oct) | OpenAI internal | **No** |
| Quantum conjecture, by startup PSI (Nov) | Non-public Claude | **No** |
| Fermat's Last Theorem formalised in 30 h (Nov) | Claude Fable 5.2 | **Yes** |
| Maths provers (DeepSeek, Goedel, Kimina) | Open weights | **Yes, on Stanage** |

- An independent advisory group asked labs to **stop testing on proprietary models**; OpenAI declined, and now hand-picks expert reviewers too
- The Leiden Declaration (IMU-endorsed) asks governments to **invest in public alternatives**

<!-- Aaronson expects the frontier/public gap to close "within the next couple of months". FLT is the clearest evidence so far: an unreleased model took 11 days in Sep; the generally available Fable 5.2 took 30 hours with 1,000 agents in Nov (lab claim). Anthropic's restricted Mythos 5.2 is for life-sciences and cyber programmes, with no maths access scheme, and no lab announced an academic maths access programme in Oct–Nov. Also public: Gowers's number-theory results (May, ChatGPT Pro). PSI's result is the Aaronson–Ambainis conjecture in quantum query complexity. Moved to notes: the Riemann partial progress (Aug, unreleased Claude) and the amateur Busy Beaver result (Oct, Claude Code). Gowers: "I didn't even do anything clever with the prompts". The advisory group is the Advisory Group on Mathematics and AI hosted at IAS Princeton (recommendations in the backup slides); Science reported OpenAI refused. The Leiden Declaration has ~4,445 signatories (Nov 2026).

For the CTO: open vs frontier isn't either/or. Open-weight models near the frontier on maths can run on-premises for sensitive data; frontier models need licences with research-grade terms (no training on our data). -->

---

<!-- _class: small -->

<style scoped>
table { font-size: 0.7em; }
</style>

## The emerging research agent stack

_Wherever agents have produced checkable research, similar layers show up._

| Layer | What it means | Evidence it's needed | Sheffield today |
|-------|---------------|----------------------|-----------------|
| Human adjudication | Research community digests | Lack of general formal verification  | _Global issue_ |
| Provenance & data | Models, prompts, runs, outputs; linked to repository | **Moderate:** 10 of 719 OpenAI papers had traces | Lack of support |
| Domain verifier | Lean, simulator, test suite, instrument, benchmark | **Strongest:** where checks are cheap, AI arrived first | Lack of support |
| Agent sandbox platform | Containers, no default egress, no secrets, logging | **Weak:** security reasoning, no incidents yet | None |
| Models | Licensed frontier APIs + open weights, behind an LLM gateway | **Strong:** the two-tier gap | Gemini vs frontier models |
| Compute | Inference-optimised data centre (GPU/TPU) | **Strong:** agent swarms | No institutional LLM |

<!-- The stack is our own synthesis (docs/it-services-exec-research/), not an external framework. It rests on maths plus a few Lean-checkable physics and CS results (PSI, Anthropic's black-hole results, AlphaProof Code). Biology has the agent swarm but no cheap verifier (GPT-Rosalind's ~2,000 agents), and no peer-reviewed study yet tests whether the pattern transfers, so don't claim "every field". Evidence column: Aletheia ran 700 Erdős problems, giving 212 candidates, 63 technically correct, 13 meaningfully correct and 4 autonomous resolutions. Only 10 of 719 OpenAI manuscripts include reasoning traces. NeurIPS 2026 workshop: "the bottleneck for AI for Science is no longer hypothesis generation, it is verification". Swarm sizes: FLT ~1,000 agents, Navier–Stokes ~10,000 agents and ~130bn tokens (lab claims). The sandbox layer rests on reasoning about prompt injection and exfiltration, not observed incidents. Lean runs fine on Stanage today; "no supported service" means nobody provides or supports it.

Each layer maps to an existing IT responsibility, though only compute and part of the models layer run as services today: HPC/GPU provision; identity and API-key brokering; procurement with data terms; information security (sandboxes, prompt injection); research data management; FinOps-style token cost control; training with RSE and the Library. Stanage figures from Sheffield's citation text (confirm current total: the Jan 2026 newsletter adds 16 H100 NVL); a Blackwell node is on order. National: UK AI for Science Strategy (up to £137m), AIRR expanding 20× by 2030, Isambard-AI calls offering up to 1.4m GPU-hours per project; groups with ready-made sandboxes and RSE support are better placed to win allocations. Sector guidance: Jisc AI leadership framework (3 Nov 2026), Jisc–Google partnership (Oct 2026).

This is a horizon scan, not a business case. The briefing's costed options are in docs/it-services-exec-research/ if the Executive wants to go further. -->

---

<!-- _class: small -->

## Summary: the "six fingers" stage

_Today's flaws are like the six-fingered hands of early AI images: obvious, embarrassing and probably temporary_

A few years ago, AI images were easy to spot: **six fingers**, melted text, impossible hands. Today those flaws feel like ancient history

AI research is at the same point now:

- Spec gaming, translation gaps, withdrawn manuscripts, unread 166-page proofs
- Real problems, but **early-stage** problems. If capability keeps improving as it has since 2022, they'll look as quaint as six-fingered hands
- What *won't* fix itself: **verification, provenance, governed access**. That's infrastructure

> Maths is the first research field we automate. It won't be the last

**The question isn't *whether* the fingers get fixed. It's whether we're ready when they are**

<!-- The closing joke and the session's optimistic stance in one image. That doesn't make today's critiques wrong; it makes them the critiques of 2026. OpenAI's stated roadmap runs from an "automated research intern" (which it says it reached in Sep 2026) to an automated AI researcher by March 2028: its own claim, not a result. -->

---

<!-- _class: small -->

## Links & resources

- OpenAI: [On the Navier–Stokes Millennium Prize Problem](https://openai.com/index/navier-stokes-solution/) · [Sharing AI progress in mathematics](https://openai.com/index/sharing-ai-progress-in-mathematics/) · [openai/math](https://github.com/openai/math)
- [Quanta explainer](https://www.quantamagazine.org/ai-has-solved-one-of-maths-1-million-millennium-prize-problems-20260908/) · [Clay statement](https://www.claymath.org/news/navier-stokes-announcement) · [Navier–Stokes lost in translation (arXiv:2610.08144)](https://arxiv.org/abs/2610.08144)
- [Aletheia (arXiv:2602.10177)](https://arxiv.org/abs/2602.10177) · [leanprover/comparator](https://github.com/leanprover/comparator) · [Leiden Declaration](https://leidendeclaration.ai/)
- Tao, "Math 2.0": [slides](https://teorth.github.io/tao-web/slides/math-2-0-caltech-2026.pdf) · [blog](https://terrytao.wordpress.com/2026/10/10/math-2-0/)
- **Since 26 Oct:** OpenAI, [Working with academic communities](https://openai.com/index/building-scientific-understanding-with-academic-communities/) · [Fortnow on ETH](https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html) · [AGMAI on designated mathematicians](https://agmai.org/#disadvantages-designating-mathematicians) · [Buzzard: "…and the proof is checked in Lean"](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/)
- **Beyond maths (lab claims):** [Claude Fable 5.2](https://www.anthropic.com/claude-fable-and-mythos-5-2) · [AlphaProof Code](https://deepmind.google/blog/introducing-alphaproof-code/) · [PSI: Aaronson–Ambainis](https://psi.inc/research/aaronson-ambainis/) · [Formally verified quantum programs (arXiv:2611.09822)](https://arxiv.org/abs/2611.09822)
- Edwin Brown (RSE, Sheffield), "Agentic Research: From Basics to Full Agentic Armour" (12 Nov 2026): the verifiable / navigable / accessible framework
- Evidence pack for this briefing: `docs/it-services-exec-research/it-services-exec-update-research.md`; 19 Oct – 19 Nov update: `docs/deep-research-update-2026-11-19.md`
- Full citations in `references.bib`

---

<!-- _class: small -->

## Image credits

- Albrecht Dürer, *The Four Horsemen* (1498), woodcut. National Gallery of Art, Washington. [CC0](https://creativecommons.org/publicdomain/zero/1.0/), via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Albrecht_D%C3%BCrer,_The_Four_Horsemen,_1498,_NGA_142352.jpg)
- Katsushika Hokusai, *The Great Wave off Kanagawa* (c. 1830–32), cropped. Metropolitan Museum of Art. Public domain, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Tsunami_by_hokusai_19th_century.jpg)
- *Paul Erdős with Terence Tao*, University of Adelaide (1985), cropped. Photo by Billy or Grace Tao. [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/), via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Paul_Erdos_with_Terence_Tao.jpg)
- Leonardo da Vinci, *Studies of water passing obstacles and falling* (c. 1508), detail. Public domain, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Studies_of_water,_by_Leonardo_da_Vinci_(detail).jpg)
- Albrecht Dürer, *Melencolia I* (1514), engraving. Metropolitan Museum of Art. [CC0](https://creativecommons.org/publicdomain/zero/1.0/), via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Melencolia_I_MET_DP815743.jpg)
- Cover of Ted Chiang, *Stories of Your Life and Others* (Vintage, 2016), via [Open Library](https://openlibrary.org/books/OL26743056M). © the publisher; reproduced as a small, low-resolution illustration of the book
- Diagrams in `diagrams/` were drawn for this session. The swarm diagram follows OpenAI's reported description; the cascade is illustrative

---

<!-- _class: lead -->

# Backup slides

_Detail for questions_

---

<!-- _class: small -->
<!-- _footer: "Cover: Ted Chiang, _Stories of Your Life and Others_ (Vintage, 2016 edition), via Open Library. © the publisher; shown for illustration" -->

![bg right:30% fit](images/chiang-stories-of-your-life-cover.jpg)

## Science fiction saw it coming

_Ted Chiang, "The Evolution of Human Science" (2000): humans become the interpreters of results they didn't produce_

- **The story:** "metahuman" scientists have raced ahead, and human researchers are left reverse-engineering and interpreting their work. It first ran in *Nature* as "Catching Crumbs from the Table" and later appeared in *Stories of Your Life and Others*
- **Further reading:** Lem, *Golem XIV*; Egan, *Luminous*; Banks, the Culture novels (people flourish alongside far smarter Minds)

> Chiang's humans don't stop doing science. They become its **hermeneutists**. Sound familiar? See "the mood in maths"

<!-- Fun closer. Confirmed by web search (Wikipedia, Nature 405, 517, 1 June 2000): published in Nature as "Catching Crumbs from the Table", retitled "The Evolution of Human Science" for the 2002 collection, which also contains "Division by Zero" (first published in Full Spectrum 3, 1991). The 2016 Vintage reprint is titled *Arrival* in some markets, to tie in with the film; the cover shown is the Open Library image for that edition. The story is report-style with no characters. Tone: wistful rather than doom-laden, which matches the session's stance. The Lem, Egan and Banks suggestions are from memory and not web-checked. -->

---

<!-- _class: small -->

## Jargon buster

_Most of these terms have a direct software analogy_

- **Open problem:** a question nobody knows the answer to (unlike an exam problem)
- **Lean:** a programming language where a proof is code: if it compiles, the proof is correct. *Mathlib* is its standard library
- **Formalise:** translate a paper proof into Lean, like porting pseudocode to a strictly typed language
- **`sorry`:** Lean's `TODO`, a gap left unproven
- **Comparator:** checks a proof answers an agreed, independently written statement (an acceptance test)
- **Navier–Stokes:** the equations for how water and air flow. Can a smooth flow suddenly "break" (*blow up*)?
- **Millennium Prize:** seven $1M problems set by the Clay Institute in 2000. **Erdős problems:** ~1,000 open puzzles from Paul Erdős, now a popular AI test

---

## Clay's four ways to win

_You win by proving any one of four things. The "it can break down" options let you choose an outside force_

![width:1100px](diagrams/clay-alternatives.svg)

<!-- From Fefferman's official problem statement. (A) and (B) ask for global smooth solutions with zero force; (C) and (D) ask for a counterexample and let the prover pick a smooth, decaying force. OpenAI claims (C) in all of space and (D) in a repeating box. The cleaner question, blow-up with no force, remains open. OpenAI separately proves unforced blow-up for the Euler equations (no friction). -->

---

<!-- _class: small -->

## What does "Lean-verified" certify?

_The build manifest shows no gaps and only standard assumptions. It can't show the spec is right_

From `formalization.yaml` in `openai/NavierStokesAndEuler`:

```yaml
status:
  scope: "Full formalization of main results."
  sorry_count: 0          # no unproven gaps (no TODOs)
  main_results:
    - declaration: "NavierStokes.Comparator.navier_stokes_breakdown_R3"
      axioms: ["propext", "Classical.choice"]   # standard foundations only
```

```lean
theorem navier_stokes_breakdown_R3 (nu : ℝ) (hnu : nu > 0) :
    ∃ (u₀ : ℝ³ → ℝ³) (f : ℝ³ → ℝ → ℝ³),
    InitialVelocityConditionDecay u₀ ∧ ForceConditionDecay f ∧
    ¬ (∃ v p, NavierStokesExistenceAndSmoothnessRn nu u₀ f v p) := by
  sorry
```

`∃` = "there exists" (so the prover picks the force `f`), `¬` = "not"

<!-- The challenge statement was written in advance by Google DeepMind (Formal Conjectures); Comparator checked the solution matches it exactly. -->


---

<!-- _class: small -->

## IAS Advisory Group: responsible release

_An independent group's release rules: open access, show your working, report failures too_

Independent, unpaid, hosted at IAS Princeton; published 29 Sep 2026. Our paraphrase of its principles and norms:

1. **Stop** testing advanced open problems on proprietary, inaccessible models
2. Deposit results in repositories **no AI lab controls**, with persistent IDs
3. Don't use results as **model marketing**
4. Per result, disclose: **model, prompts, reasoning summary, time, compute**
5. **Formalise** as far as possible
6. For bulk releases: say how many problems were **attempted and failed**
7. Fund **human understanding** and give equitable **model access**

**Since then:** labs shouldn't hand results to chosen mathematicians first (25 Oct); release the Yang–Mills outputs now (26 Oct)

<!-- The primary text (agmai.org/general-sep29) has 3 principles, 2 pathways, 5 release norms and 3 funding items; the seven above are our paraphrase. Scorecard for OpenAI's releases to 19 Nov (docs/deep-research-update-2026-11-19.md §2.1): #1 not met; #2 not met (still its own GitHub, "exploring community-hosted repositories"); #3 disputed; #4 partial, and the model is now "unnamed"; #5 largely met for the new results; #6 partial (~4,000 problems stated, no failure list); #7 funding aligned (US$5m to Simons, possibly the same money as the 15 Oct fund) but no access scheme. The 25 Oct statement conflicts directly with OpenAI's shepherd model. Items 2, 4 and 5 are provenance and repository questions an institution can act on for its own outputs. -->

---

<!-- _class: small -->

## AI maths tools: what can a university actually use?

_Plenty is open or free today, and small open models are catching up with giant ones_

| Availability | Systems |
|--------------|---------|
| **Open weights** (run on Stanage) | DeepSeekMath-V2, DeepSeek-Prover-V2, Goedel-Prover-V2, Kimina-Prover |
| **Open-source agents** | Numina-Lean-Agent (Claude Code + Lean tools), QED, Bolzano |
| **Commercial / free service** | Aristotle (Harmonic), Gauss (Math, Inc.), AXLE (hosted Lean) |
| **General agent harnesses** | Claude Code, Codex, Gemini CLI |
| **Closed / by application** | AlphaProof, AlphaEvolve, AxiomProver |

- **Small is catching up:** Goedel-Prover-V2 **8B** matches DeepSeek-Prover-V2 **671B** on a standard benchmark
- **Beyond maths:** Harmonic says Aristotle now verifies C code and Verilog chip designs (lab claim)
- Lean, Mathlib and Comparator are open source and run on any Linux host

<!-- Scores are developer-reported with different settings. Harmonic's C/Verilog claim and 96.8% VERINA score came via Reuters/trade press (Oct 2026): confidence Medium–Low. Formalising known maths at scale: Axiom says it formalised the Weil conjectures and Faltings' theorem (Nov, lab claims). Axiom's AI role is unclear (the Weil post credits humans only) and the Weil scale is disputed (an employee says 50M lines over 24 days, the CEO reportedly "less than a day"); Faltings is ~110k proof-specific lines on ~6.4M lines of Stacks Lean. Lean v4.36.0 came out on 16 Nov. Full details: docs/ai-mathematics-research-tools.md and docs/deep-research-update-2026-11-19.md §2.3. -->

---

<!-- _class: small -->

## Answers for the sceptic

_The usual objections, and what the evidence says_

- **"It's hype."** Some is: 3 withdrawals, the A-Lab correction, Aletheia's early-2026 6.5% (older model). But a 13M-line Lean proof either compiles or it doesn't, ECMWF doesn't run hype operationally, and a leading complexity theorist calls ETH "toast"
- **"Researchers aren't asking for it."** They're using it anyway (84%), just not through us. A quiet service desk means shadow AI, not no demand
- **"We can't afford it."** Not all of it. Stanage and existing templates go a long way; national compute (AIRR) is free if groups win bids
- **"It's a security risk."** Yes, and unmanaged it's a bigger one. A controlled sandbox with no-training terms beats personal accounts
- **"Mathematicians oppose it."** Some do, over credit, understanding and corporate control (~1,000 have joined a "human mathematics" association). But the mood is shifting to adaptation: "Evaluate all work as if it is AI-assisted" (Calegari, 1 Nov)

<!-- From §5 of the research briefing, reframed as discussion material. The strongest critiques come from the field's leaders (25–26 Fields Medallists' "A Severe Misalignment of AI in Mathematics"; the Leiden Declaration, which asks institutions to keep results verifiable, require disclosure and invest in public alternatives). None argues the capability is fake; they argue that trust, credit, understanding and access are at risk. AHM: 1,008 members, 654 of them pledging not to use AI in research (self-reported, self-selected; 20 Oct); doctoral advising guidelines 3 Nov. Its name and Tao's role are muddled in coverage: don't say Tao leads it. Calegari's guest post on Tao's blog, "Mathematics has changed. Let's act like it", makes six proposals including hiring on in-person interaction and higher standards of exposition. Fortnow's "toast" is hedged: "I have not verified the proof myself". -->

---

<!-- _class: small -->

## The mood in maths, November 2026

_From anger towards absorption: the field is building ways to digest AI results_

> "Math is being entirely wiped out by AI." — Richard Borcherds (Fields Medal 1998), 9 Nov

> "But the AI is as yet nowhere in what I would call theory building." — Eric Weinstein, same conversation

- **A verification gold rush:** teams worldwide are checking the AI proofs, both to see if they're right *and* to claim the credit. The labs say they want none, and only a human can be an author
- **Humanising the proofs:** some rewrite them in public repos (reportedly including Hairer on Yang–Mills); a Navier–Stokes exposition has reached v3
- **New infrastructure:** MathHelm, a forum for AI papers; a community corrections repo; registry links required for formal proofs
- **New money:** Imperial's £5M AI-maths "Langlands Lab" (reported); the Simons US$15M fund's call closes 1 Dec
- **Tao** (The Economist, 18 Nov): "Performance is outpacing understanding and safety in AI"

<!-- The joke: a Fields Medallist says maths is "wiped out", then spends two hours doing maths. Both quotes were checked against a partial transcript (docs/borcherds-weinstein-toe.md); speaker attribution is inferred from context, so rewatch the opening of the Theories of Everything episode (youtube.com/watch?v=XqgnJyQZGG4) before presenting. Borcherds also says the models went "from being mediocre undergraduates to being the best mathematicians on the planet" around summer 2026. Weinstein's (unchecked) "convex hull" picture: AI is exploring "the convex hull of things that we know how to do, but that have been too expensive for us to carry out", clearing the "low-hanging fruit".

Sources (docs/deep-research-update-2026-11-19.md §2.4–2.5): Hairer and Armstrong humanisation repos for Yang–Mills (11 Nov, reported); Lei & Ren's Navier–Stokes exposition v3, 245 → 182 pages, "We claim no original mathematical contribution" (arXiv:2609.35406); MathHelm (Tao blog, 13 Nov); teorth/oai-math-revised ("we will cite the people"); Formal Conjectures' Palomar registry rule (29 Oct). erdosproblems.com stopped showing solved counts on 6 Oct because AI priority claims had become "increasingly meaningless". Imperial's Langlands Lab (4 Nov, XTX-funded, linked to Buzzard) is the nearest UK peer move. The Economist headline is known; its text was not read.

The gold rush: OpenAI says it seeks "no academic credit" and defers "to the math community completely on matters of credit, precedence, and concurrent work" (commit 42907c9), and journal policies (e.g. COPE, Nature, Science) don't let an AI be an author. So the first human team to check, explain and publish a result is well placed to own the paper. Not everyone is grabbing: Lei & Ren's exposition claims "no original mathematical contribution", and the corrections repo promises "we will cite the people". Discussion: is credit for checking and explaining a proof a fair reward, or a new kind of land grab? -->
