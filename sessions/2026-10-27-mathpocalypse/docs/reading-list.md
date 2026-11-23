# Prioritised reading list: the Mathpocalypse

* **Added:** 18 October 2026
* **Purpose:** a single ordered list for anyone who wants to read around the
  [Mathpocalypse session](../README.md), whether or not they attend.

> **Caveat.** Most entries come from the other notes in this folder, which checked them against
> primary sources on 18 October 2026. Two additions (marked *new*) were found by a web search on
> the same day and only checked at search-result level. The story is moving daily and many figures
> are lab-reported, so recheck anything you plan to quote. Where counts differ, use the
> [`openai/math` README](https://github.com/openai/math) figures.

## How the list is ordered

Priority combines four things: how much it explains about what happened, whether it is a primary
source, how well it covers a view the group has not yet heard, and how long it takes. Times are
rough.

* **Tier 1** is the minimum for joining the discussion (about 90 minutes).
* **Tier 2** fills in the technology and the main positions (about 3 hours).
* **Tier 3** is for people who want depth on one thread.
* **Tier 4** is video and audio, which can replace reading in any tier.
* **Trackers** are for staying current after the session.

The session’s stance is broadly optimistic, so Tier 1 and Tier 2 each include at least one critical
source and one hopeful one.

---

## Tier 1: read before the session (about 90 minutes)

| # | Read | Time | Why it is here |
|---|---|---|---|
| 1 | Jordana Cepelewicz, [“Is AI the End of Math As We Know It?”](https://www.quantamagazine.org/is-ai-the-end-of-math-as-we-know-it-20261005/), *Quanta*, 5 Oct | 20 min | The best general-audience account of the human side: incentives, behaviour changes, and the futures mathematicians fear and hope for. |
| 2 | Scott Aaronson, [“The Mathocalypse”](https://scottaaronson.blog/?p=10169), 7 Oct, with updates | 25 min | The enthusiastic case, the list of headline results, and the two release models (OpenAI’s open dump against Anthropic’s chosen human authors). Comments #24, #35, #48, #86, #115 and #119 add the best objections. Notes: [aaronson-mathocalypse.md](aaronson-mathocalypse.md). |
| 3 | Quanta, [“AI Has Solved One of Math’s $1 Million Millennium Prize Problems”](https://www.quantamagazine.org/ai-has-solved-one-of-maths-1-million-millennium-prize-problems-20260908/), 8 Sep | 10 min | The plain-language explainer for the Navier–Stokes claim and the agent swarm. Read it with the forcing caveat in mind (see #5). |
| 4 | AGMAI, [“Responsible Release of AI-Generated Mathematics”](https://agmai.org/general-sep29/), 29 Sep | 10 min | Short and concrete. The disclosure checklist is the basis of the Track B activity, and the access and equity points apply directly to universities. |
| 5 | Bastounis, Circelli & Hansen, [“Navier–Stokes lost in translation”](https://arxiv.org/abs/2610.08144), 6 Oct | 15 min (skim the proofs) | Explains why “Lean-verified” does not mean “the English proof is right”. The most useful single corrective to the headline. |
| 6 | NPR, Geoff Brumfiel, [“AI solved one of math’s hardest problems. Humanity learned nothing (so far)”](https://www.npr.org/2026/09/22/nx-s1-5968588/openai-navier-stokes-problem-mathematicians-learn-little), 22 Sep | 8 min | Short, quotable reactions from Maynard and Gómez-Serrano: probably correct, hard to extract understanding from. Sets up the proof-versus-understanding prompt. |

If you have 30 minutes, read #1, #4 and #5.

## Tier 2: the technology and the main positions (about 3 hours)

### What was claimed and how it was produced

| # | Read | Why it is here |
|---|---|---|
| 7 | OpenAI, [“On the Navier–Stokes Millennium Prize Problem”](https://openai.com/index/navier-stokes-solution/), 8 Sep | Primary source for the swarm: roughly 10,000 agents, 88 hours, 2.7 million messages. It reports tokens and messages, not cost. |
| 8 | OpenAI, [“Sharing AI progress in mathematics”](https://openai.com/index/sharing-ai-progress-in-mathematics/), 6 Oct, and the [`openai/math` README](https://github.com/openai/math) | Primary source for the bulk release. The README holds the current counts (719 manuscripts, 372 families) and the labelling scheme. |
| 8a | OpenAI, [“Working with academic communities to build scientific understanding”](https://openai.com/index/building-scientific-understanding-with-academic-communities/), 26 Oct | The revised release model (external “shepherd” groups, no academic credit claimed) and three large unverified claims: local smoothing, ETH refuted, Yang–Mills/QCD existence. Notes: [openai-academic-communities.md](openai-academic-communities.md). |
| 9 | Terence Tao, [finite-time blowup with smooth forcing](https://terrytao.wordpress.com/2026/09/07/finite-time-blowup-with-smooth-forcing-term-for-the-incompressible-porous-medium-boussinesq-and-incompressible-euler-equations), 7 Sep | How the construction works, and the human, AI-assisted work it builds on. Useful for the priority dispute. |
| 10 | Feng et al., [“Towards Autonomous Mathematics Research”](https://arxiv.org/abs/2602.10177) (DeepMind’s Aletheia) | The measured precedent, with autonomy and novelty ratings and “human–AI interaction cards”. A model for how disclosure could work. |
| 11 | Anthropic, [“Formalizing Fermat’s Last Theorem”](https://www.anthropic.com/research/formalizing-fermats-last-theorem), 4 Sep | The contrasting release model, and the clearest example of autoformalisation at scale (13 million lines in 11 days). |

### Why the frontier is jagged, and why the proofs are opaque

| # | Read | Why it is here |
|---|---|---|
| 12 | Tim Gowers, [“What sort of maths are LLMs good at?”](https://gowers.wordpress.com/2026/08/12/what-sort-of-maths-are-llms-good-at/), 12 Aug | The best single reading on which problems are getting cheap and which are not. Notes: [jagged-frontier-gowers.md](jagged-frontier-gowers.md). |
| 13 | William Thurston, [“On proof and progress in mathematics”](https://arxiv.org/abs/math/9404236) (1994) | The classic argument that the product of mathematics is human understanding. Nearly every current essay draws on it. Notes: [opacity-alien-proofs.md](opacity-alien-proofs.md). |
| 14 | Thomas Hales, [“What mathematicians should know about the Lean Theorem Prover”](https://terrytao.wordpress.com/2026/10/09/what-mathematicians-should-know-about-the-lean-theorem-proverquestions-of-reliability-and-ai/), 9 Oct | Soundness bugs in the checker itself. Pair with #5: the statement can be wrong, and so can the kernel. |

### Community positions

| # | Read | Why it is here |
|---|---|---|
| 15 | Terence Tao, [“Math 2.0”](https://terrytao.wordpress.com/2026/10/10/math-2-0/) (post and [slides](https://teorth.github.io/tao-web/slides/math-2-0-caltech-2026.pdf)), 9–10 Oct | The constructive proposal: use AI to strengthen the human community. The most hopeful serious source. Notes: [tao-math-2-0.md](tao-math-2-0.md). |
| 16 | [“A Severe Misalignment of AI in Mathematics”](https://mathandai.org/), 11 Sep | The Fields Medallists’ statement. Short, and the clearest critical position. Notes: [mathandai-statement-summary.md](mathandai-statement-summary.md). |
| 17 | [Leiden Declaration on AI and Mathematics](https://leidendeclaration.ai/), 2 Jun | The IMU-endorsed statement of values: proof, attribution, transparency, evaluation, autonomy. Notes: [leiden-declaration-summary.md](leiden-declaration-summary.md). |
| 18 | Lior Pachter, [“Align AI and mathematics to something else”](https://liorpachter.wordpress.com/2026/09/12/align-ai-and-mathematics-to-something-else/), 12 Sep | Agrees with the Fields Medallists about the labs and criticises their own haste. A useful check on #16. |

## Tier 3: depth on one thread

### Priority, credit and the labs

* Fortune, [on the priority dispute and Tao’s critique](https://fortune.com/2026/09/08/openai-says-it-cracked-navier-stokes-math-grand-challenge-buckmaster-accusation-cheating-intimidation-tao-lament/), 8 Sep.
* Buckmaster and Alpöge’s statement and the [Clay Institute announcement](https://www.claymath.org/news/navier-stokes-announcement). The Clay problem concerns the unforced equations, which is the forcing loophole.
* [Industry perspectives summary](industry-perspectives-summary.md) for what lab leaders and investors say.

### Essays from mathematicians (collected by Tao, [12 Oct](https://terrytao.wordpress.com/2026/10/12/additional-recent-pieces-on-math-and-ai/))

These were not read in full for the research brief. Titles are in rough order of usefulness to this group.

* Kevin Buzzard, [“To grieve, or not to grieve?”](https://xenaproject.wordpress.com/2026/10/01/to-grieve-or-not-to-grieve/): from the leading Lean advocate.
* Dakshita Khurana, [“Classical at heart”](https://dakshitakhurana.substack.com/p/classical-at-heart): a researcher working through the AI proof of a problem she spent years on.
* Harald Helfgott, [“Mathematics and the AI crisis”](https://valuevar.wordpress.com/2026/10/01/mathematics-and-the-ai-crisis/).
* Gil Kalai, [“Be a Grothendieck!”](https://gilkalai.wordpress.com/2026/09/22/be-a-grothendieck-on-ai-and-mathematics/).
* Matilde Marcolli, [“Duet for the end of math”](https://www.its.caltech.edu/~matilde/AImathNew.pdf).
* Fenner Stanley Tanswell, [“Enshittification of Mathematics”](https://link.springer.com/article/10.1007/s00283-026-10566-7).
* Rikab Gambhir, [“Why are we even doing all this?”](https://terrytao.wordpress.com/2026/10/15/why-are-we-even-doing-all-this/): satire, but the comments hold the strongest counter-arguments from biomedicine.

### Philosophy of proof and opacity

* Tao, [“Mathematics in the age of AI”](https://arxiv.org/abs/2608.16753), ICM 2026 essay. Frames the present as a crisis of values comparable to 1900–1930.
* Tymoczko, “The Four-Color Problem and Its Philosophical Significance” (1979), and Duede, “A Priori Knowledge in an Era of Computational Opacity” (2025). Both are in `references.bib`; [opacity-alien-proofs.md](opacity-alien-proofs.md) summarises how they apply.
* Yu, “Truth Without Comprehension” (2025), and Moradifam, “What Remains Human in Mathematics in the Age of AI” (2026), also in `references.bib`.

### Other subjects

* *Nature* editorial, “Mathematicians are developing rules for AI use — other fields should follow”, 18 Jun. Input for the “beyond maths” prompt.
* TheoPhysEval, [arXiv 2610.16733](https://arxiv.org/abs/2610.16733): 49 of 50 unpublished physics problems solved. Check the caveats about memorisation and lab-reported grading.
* OpenProblemBench, [arXiv 2610.11118](https://arxiv.org/abs/2610.11118): best solve rate 14% on 82 open problems, graded by AI evaluators.
* Alman and Williams, [3SUM and APSP preprint](https://arxiv.org/abs/2610.06783): a human-written paper built on an idea from an Anthropic model.

### Tools and infrastructure

* [AI mathematics research tools](ai-mathematics-research-tools.md): a survey of provers, harnesses and Open Math OS.
* [Practical next steps](practical-next-steps.md): the Natural Number Game, the Lean web editor and other take-home exercises. Do these before reading anything on formalisation, because they make the translation gap concrete.
* *New.* Survey, [“Autoformalization in the Era of Large Language Models”](https://arxiv.org/pdf/2505.23486) (2025). The standard background survey on turning informal maths into Lean. It predates the 2026 events, so treat it as method background only.
* *New.* Lecture notes, [“Auto-formalization of mathematics with Lean”](https://bnaskrecki.faculty.wmi.amu.edu.pl/vietnam2026/book/lectures/l6_autoformalization.html) (2026). A short, clear statement of the distinction between formalising a statement and formalising a proof. A proof assistant cannot confirm that the statement matches the mathematician’s intent.

### Crowdsourcing and the optimistic long view

* [Crowdsourced GitHub mathematics](crowdsourced-github-mathematics.md): the Equational Theories Project, Polymath and the community databases. The strongest evidence that cheap checking can scale human collaboration.
* [*Solve Everything* summary](solve-everything-summary.md) and [accelerationist viewpoints](accelerationist-viewpoints.md): the utopian counterpoint. Read critically.

---

## Tier 4: video and audio

| Order | Item | Time | Notes |
|---|---|---|---|
| 1 | Tao, [“Math 2.0”](https://aimath.org/videos/terry-tao-pl/), Caltech public lecture, 9 Oct | about 1 hour | The best single talk for this session. Can replace #15. |
| 2 | [“No More Heroes: Terence Tao Talks to Numberphile About AI”](https://www.youtube.com/watch?v=bAnwMdfcMVw), 15 Oct | short | Accessible. A clip could open a meeting. |
| 3 | 3Blue1Brown, from 20:46: why there has never been a better time to go into maths | 10 min | The optimistic counterweight. Notes: [3blue1brown-better-time-for-math.md](3blue1brown-better-time-for-math.md). |
| 4 | Aaronson on the *Modern CTO* podcast | about 30 min | Spoken version of the Mathocalypse argument. Notes: [aaronson-modern-cto-interview.md](aaronson-modern-cto-interview.md). |
| 5 | Tao, [“The integrated explicit analytic number theory network”](https://www.youtube.com/watch?v=Boo72U-9u3c), IPAM, 17 Sep | about 1 hour | A working example of human–AI collaboration at scale. |
| 6 | Borcherds and Weinstein, [“Fields Medalist & Eric Weinstein on the Future of Mathematics”](https://www.youtube.com/watch?v=XqgnJyQZGG4), *Theories of Everything*, 9 Nov | first 15 min | The bleakest framing from a Fields Medallist (“no reason for employing me”), quickly qualified: AI fills in the “convex hull”, theory building stays human for now. Notes: [borcherds-weinstein-toe.md](borcherds-weinstein-toe.md). |

Paywalled, so lower priority: the NYT *Daily* episode with Steven Strogatz (13 Oct) and the NYT Tao
interview (16 Oct).

## Trackers (for after the session)

* Tao’s [summary of his views](https://teorth.github.io/tao-web/ai-views.html) and [list of talks and posts](https://teorth.github.io/tao-web/mastodon-posts.html).
* [Proofs and Prompts](https://proofsandprompts.com/), including “100+ reactions to 100+ solutions”.
* [AGMAI](https://agmai.org/) for further recommendations, and the [`openai/math` repository](https://github.com/openai/math) for withdrawals and corrections.
* [First Proof](https://1stproof.org/) for the controlled, non-lab evidence.

## Suggested paths

* **Thirty minutes:** #1, #4, #5.
* **One evening:** Tier 1, then #12 and #15.
* **For research software engineers:** #4, #5, #14, then [practical-next-steps.md](practical-next-steps.md).
* **For sceptics:** #5, #14, #16, #18, then Tanswell and Helfgott.
* **For optimists:** #2, #15, #17, then the crowdsourcing note and the 3Blue1Brown clip.
