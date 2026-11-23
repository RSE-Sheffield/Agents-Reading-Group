# Verification overtakes discovery as the story

**Generated:** 19 Nov 2026, by running the prompt in [`docs/deep-research-update-prompt.md`](deep-research-update-prompt.md) (window: 19 Oct – 19 Nov 2026).
**Sources:** seven research notes in [`docs/deep-research-update-2026-11-19-notes/`](deep-research-update-2026-11-19-notes/) (OpenAI follow-up, verification status, other labs, institutional responses, open efforts, beyond maths, media and numbers).

> **Caveat: what was and wasn't checked**
>
> - **Blocked sites.** openai.com, science.org, nature.com and the major newspapers (NYT, FT, Guardian, Economist, WSJ, Wired, Atlantic, New Scientist) blocked the researchers' tools. **The wording of OpenAI's 26 Oct post was not read directly.** Its content is reconstructed from the `openai/math` repo (primary), Gizmodo and The Next Web. Re-read the post by hand before quoting it on a slide. Items from Science, Nature, the Economist, the Guardian and New Scientist are known from titles or search snippets only.
> - **Aggregator reliance.** Several institutional items (Imperial's Langlands Lab, IMS and MSP policies, the Yang–Mills validation repos, the HEP open letter, the "MisAnthropic Statement") come via the community aggregator [Proofs and Prompts](https://proofsandprompts.com/newsfeed/). They are marked **reported**.
> - **Checked directly:** GitHub repos and commit histories (`openai/math`, `openai/NavierStokesAndEuler`, Formal Conjectures, Erdős database, ETP, Lean/Mathlib), arXiv abstract pages, agmai.org, Tao's and Buzzard's blogs, Aaronson's and Fortnow's blogs, and the Anthropic, DeepMind, Axiom, PSI, KCL, EDP Sciences, Simons and Clay pages.
> - **Not searched:** Lean Zulip, MathOverflow, Mastodon, X (paywalled to the tools), Hacker News, department seminar listings beyond UT Austin, and a systematic arXiv sweep. "Nothing found" means nothing found by these searches, not that nothing happened.
> - **Labels used throughout:** **confirmed** = primary source read (this confirms the *claim was made*, not that the mathematics is right); **reported** = secondary source only; **disputed** = sources conflict or the claim is contested. Lab figures are the labs' own unless stated otherwise. Items before 19 Oct are marked **[pre-window]**.

OpenAI followed its 6 Oct bulk release with a **second wave on 26 Oct 2026**: a claimed refutation of the Exponential Time Hypothesis (ETH), a proof of Sogge's local smoothing conjecture that it says implies the Kakeya conjectures, and existence proofs for interacting 4D quantum field theories including Yang–Mills. It handed each result to hand-picked expert "shepherds" and reportedly gave US$5m to the Simons Foundation ([Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956); [openai/math history.md](https://github.com/openai/math/blob/main/history.md)). Anthropic reportedly posted its own ETH refutation the same day, so coverage reframed the story from "one lab flooding the field" to a **lab race** ([Scientific American](https://www.scientificamerican.com/article/dueling-proofs-from-openai-and-anthropic-astound-scientists/)). The `openai/math` README now says **721 manuscripts in 373 families**, not 719 ([commit 42907c9](https://github.com/openai/math/commit/42907c9)). No headline claim was refuted in the window. The Unique Games proof drew the most careful positive expert reading (Moshkovitz with Khot, Håstad and Minzer), but **nothing has been formally verified by humans and nothing has been peer reviewed**. The IAS-hosted advisory group (AGMAI) pushed back publicly on OpenAI's shepherd model and on its withholding of the Yang–Mills material ([AGMAI](https://agmai.org/#disadvantages-designating-mathematicians)). Elsewhere, the action was in **formalising known mathematics** (Fermat, Weil, Faltings) and **"agent swarm plus Lean" results outside pure maths** (Signal's code, a quantum-complexity conjecture, black-hole physics). The community's mood moved from anger towards absorption: humanisation repos, a forum for AI papers (MathHelm), Buzzard's audit of what "Lean-checked" means, and calls to change hiring and teaching. For the deck, the biggest changes are the counts, the IAS slide's framing, the "results held in reserve" rumour (now partly borne out), and a new "second wave" event.

---

## 1. Timeline, 19 Oct – 19 Nov 2026

| Date | Event | Status |
|---|---|---|
| 19 Oct | ESAIM: Probability and Statistics pauses new submissions until 8 Nov, citing an AI-driven surge; five other probability journals reportedly join ([EDP Sciences](https://www.edpsciences.org/en/news-highlights/3058-esaim-probability-and-statistics-takes-action-to-address-increasing-manuscript-submissions); [MACCUS](https://maccus.fr/en/ai-paper-flood/)) | confirmed (ESAIM); reported (others) |
| 19 Oct | Tao posts a human sketch of the AI-generated proof that Siegel zeros do not exist ([Tao](https://terrytao.wordpress.com/2026/10/19/a-sketch-of-the-proof-of-non-existence-of-siegel-zeroes/)) | confirmed |
| 19 Oct | Sarnak tells Quanta he won't call the quasi-Riemann result a "theorem" until humans understand it ([Quanta](https://www.quantamagazine.org/ai-proved-the-quasi-riemann-hypothesis-what-happens-now-20261019/)) | reported |
| 19 Oct | Shing-Tung Yau launches the Yau Laboratory Alliance for AI in maths research in China ([SCMP](https://www.scmp.com/news/china/science/article/3370492/leading-chinese-mathematicians-unite-behind-use-ai-research)) | reported |
| 20 Oct | AHM passes 1,008 members; 654 also pledge not to use AI in research ([Magica](https://magica.com/news/human-mathematics-association-passes-1000-members-ai-commitments)) | reported |
| 21 Oct | OpenAI runs ~2,000 GPT-Rosalind agents on a mouse-brain CRISPR atlas ([OpenAI](https://openai.com/index/scaling-ai-research-for-complex-biological-data/); [AI Weekly](https://aiweekly.co/alerts/openai-perturbai-and-scripps-run-2000-gpt-rosalind-agents-on-8m-cell-brain)) | reported |
| 24 Oct | Lekili & Sheridan preprint sets out the errors in OpenAI's withdrawn Hodge-type manuscripts ([arXiv:2610.30976](https://arxiv.org/abs/2610.30976)) | reported |
| 25 Oct | AGMAI: "Disadvantages of Designating Mathematicians for AI Output Releases" ([AGMAI](https://agmai.org/#disadvantages-designating-mathematicians)) | confirmed |
| 26 Oct | OpenAI's second wave: ETH refuted, local smoothing ⇒ Kakeya, 4D Yang–Mills/QCD existence; shepherd groups; US$5m to Simons ([Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956); [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)) | confirmed (ETH, local smoothing in repo); reported (rest) |
| 26 Oct | `openai/math` README goes to 721 manuscripts / 373 families; model now "unnamed" ([commit 42907c9](https://github.com/openai/math/commit/42907c9)) | confirmed |
| 26 Oct | Anthropic posts its own ETH refutation, "hours after OpenAI" ([SciAm](https://www.scientificamerican.com/article/dueling-proofs-from-openai-and-anthropic-astound-scientists/)) | reported; date disputed |
| 26 Oct | AGMAI asks OpenAI to release the Yang–Mills outputs "without delay" ([AGMAI](https://agmai.org/#request-immediate-release)) | confirmed |
| 26 Oct | Equational Theories Project merges an end-to-end Lean certificate for all 4,694 equations ([PR #1506](https://github.com/teorth/equational_theories/pull/1506)) | confirmed |
| 27 Oct | KCL press release: "OpenAI's Navier-Stokes proof called into question" ([KCL](https://www.kcl.ac.uk/news/openais-navier-stokes-proof-called-into-question)) | confirmed |
| 27 Oct | Harmonic's Aristotle expands into C and Verilog verification ([Harmonic](https://www.harmonic.fun/news)) | confirmed (headline only) |
| 28 Oct | Fortnow: ETH is "toast"; Impagliazzo, Paturi and Williams to examine the proof ([Computational Complexity](https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html)) | confirmed |
| 29 Oct | Formal Conjectures makes Palomar registry links mandatory for formal proofs ([PR #7631](https://github.com/google-deepmind/formal-conjectures/pull/7631)) | confirmed |
| 29 Oct | Community corrections site for OpenAI's problems launches ([mathcommunity](https://mathcommunity.github.io/oai-math-revised/)); Royal Society "Mathematics in the Age of AI" event ([Royal Society](https://portal.royalsociety.org/events/details/?id=baa5caea-28ff-491f-b747-7b9fea66d759)) | reported |
| 30 Oct | Aaronson: Moshkovitz has studied the UGC proof with Khot, Håstad and Minzer ([Shtetl-Optimized](https://scottaaronson.blog/?p=10232)); Tau Ceti announces an Anthropic grant ([Tau Ceti](https://taucetiproject.org/)) | confirmed |
| 31 Oct | Altman: sympathises with mathematicians, but "the onslaught will not stop" ([The Verge](https://www.theverge.com/ai-artificial-intelligence/1023054/altman-cheeky-pint-ai-math-interview)) | reported |
| 1 Nov | Calegari guest post on Tao's blog: "Mathematics has changed. Let's act like it" ([Tao](https://terrytao.wordpress.com/2026/11/01/mathematics-has-changed-lets-act-like-it/)); MSP draft AI policy ([MSP](https://msp.org/publications/ai/)) | confirmed; reported |
| 3 Nov | AHM Doctoral Advising Guidelines ([Tao](https://terrytao.wordpress.com/2026/11/03/doctoral-advising-guidelines-by-the-ahm/)) | confirmed |
| 4 Nov | Moshkovitz's two-hour UGC talk at UT Austin, "Proved (!!?)" ([UT Austin](https://ai.utexas.edu/events/2026-11-04/unique-games-conjecture-proved)) | confirmed |
| 4 Nov | Imperial announces a £5M XTX-funded "Langlands Lab" for AI-assisted maths ([Imperial](https://www.imperial.ac.uk/news/articles/admin-services/giving/2026/5-million-grant-to-establish-new-laboratory-for-ai-assisted-mathematics-at-imperial/)); NPR *Short Wave* episode ([NPR](https://www.npr.org/2026/11/04/nx-s1-6010471/ai-math-navier-stokes-mathematicians-openai)) | reported |
| 6 Nov | PSI claims a Lean-checked proof of the Aaronson–Ambainis conjecture using a non-public Anthropic model ([PSI](https://psi.inc/research/aaronson-ambainis/)) | confirmed (claim) |
| 6 Nov | Axiom: Weil conjectures formalised in Lean ([Axiom](https://axiommath.ai/research/the-weil-conjectures-formalized-in-lean/)) | confirmed (claim) |
| 8 Nov | IMS updates its AI policy ([IMS](https://imstat.org/journals-and-publications/policy-on-use-of-ai/)) | reported |
| 9 Nov | Anthropic launches Claude Fable 5.2: Fermat's Last Theorem formalised by 1,000 agents in 30 hours; two black-hole physics problems claimed ([Anthropic](https://www.anthropic.com/claude-fable-and-mythos-5-2)) | confirmed (claim) |
| 9–11 Nov | Gross-led shepherd committee affirms OpenAI's Yang–Mills existence result in Lean: "We do not claim to fully understand the proof yet" ([CASRAI](https://casrai.org/news/ai-rivals-physics-mathematical-challenge-2026); [assessment](https://github.com/yang-mills-group/YM/blob/main/docs/assessment-1.pdf)) | reported |
| 10 Nov | DeepMind's AlphaProof Code: over six million lines of Lean verifying Signal's compiled code ([DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/)) | confirmed (claim) |
| 11 Nov | Woit, "The Yang-Mills Publicity Stunt" ([Not Even Wrong](https://www.math.columbia.edu/~woit/wordpress/?p=15986)); Hairer and Armstrong start public humanisation repos ([Hairer](https://github.com/hairer/humanise-yang-mills); [Armstrong](https://github.com/scottnarmstrong/yang-mills-informalization)) | confirmed; reported |
| 12 Nov | Buzzard: "…and the proof is checked in Lean" (~38 OpenAI Lean packages don't state the paper's main theorem) ([Xena](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/)) | confirmed |
| 12 Nov | Axiom: Faltings' theorem formalised ([Axiom](https://axiommath.ai/research/faltings-theorem-formalized/)) | confirmed (claim) |
| 13 Nov | MathHelm launches, a forum for discussing AI-generated papers ([Tao](https://terrytao.wordpress.com/2026/11/13/introducing-mathhelm-a-place-to-discuss-ai-generated-papers/)) | confirmed |
| 16 Nov | HEP physicists' open letter calling for open release of AI-produced results ([hep-open-release.org](https://hep-open-release.org)); Lean v4.36.0 released ([Lean](https://github.com/leanprover/lean4/releases)) | reported; confirmed |
| 17 Nov | Anthropic research post on the two black-hole results ([Anthropic](https://www.anthropic.com/research/claude-black-hole-physics)) | confirmed (claim) |
| 18 Nov | Tao in The Economist: "Performance is outpacing understanding and safety in AI" ([Economist](https://www.economist.com/the-world-ahead/2026/11/18/performance-is-outpacing-understanding-and-safety-in-ai-says-terence-tao)); Lei & Ren post v3 of their Navier–Stokes exposition ([arXiv:2609.35406](https://arxiv.org/abs/2609.35406)) | reported; confirmed |
| 19 Nov | "MisAnthropic Statement" by mathematicians, timed to Anthropic's IPO ([misanthropicstatement.com](https://misanthropicstatement.com)) | reported |

---

## 2. Findings by topic

### 2.1 OpenAI's follow-up: a second wave, shepherds and a renamed model

**What the 26 Oct post announces (reported; post not read directly).** The post at [openai.com/index/building-scientific-understanding-with-academic-communities](https://openai.com/index/building-scientific-understanding-with-academic-communities/) is reportedly titled "Working with academic communities to build scientific understanding" and dated 26 Oct ([Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956); [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)). It announces:

- **Three results.** (1) "The Exponential Time Hypothesis is False": a deterministic, polynomial-space, subexponential-time algorithm for counting satisfying assignments of fixed-width CNF formulas, Lean-formalised as the `SubexponentialSAT` Comparator challenge. (2) Local smoothing for the wave equation in all dimensions ≥2, which OpenAI says gives the Kakeya maximal and dimension conjectures and Stein's restriction estimates in the interior of the range, formalised as `LocalSmoothing`. Both are **confirmed as present in the repo** ([history.md](https://github.com/openai/math/blob/main/history.md)). (3) Existence of interacting 4D QFTs with gauge fields and fermions, including QCD and "a unified completion of the Standard Model" (**reported**). This covers existence only, **not the mass gap**, so it would not meet the Millennium Prize criteria ([CASRAI](https://casrai.org/news/ai-rivals-physics-mathematical-challenge-2026)).
- **A "shepherd" release model (reported).** OpenAI asked outside experts to "act as shepherds, organizing groups to understand the new results". It calls the manuscripts "raw research data" and says it does not seek academic credit ([Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956)).
  - *ETH:* Impagliazzo, Paturi (UCSD) and Williams (MIT) lead "an independent working group". The materials were released immediately at their request (**confirmed**, [history.md](https://github.com/openai/math/blob/main/history.md)). They say their role "should not be taken as certification", and that they signed no NDAs and are unpaid (**reported**, [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)).
  - *Physics:* David Gross leads, with Douglas, Jaffe, Klebanov and Nekrasov. The group chose **not to release** the AI material at first (**reported**, [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)).
  - *Local smoothing:* no shepherd group named; one account says it was released "without external collaboration" (**reported**, [Proofs and Prompts](https://proofsandprompts.com/newsfeed/)).
- **Funding (reported).** US$5m to the Simons Foundation for workshops and programmes on AI-produced results ([TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)). Sources disagree on whether this is new money. *Inference:* OpenAI had already committed US$5M to the 15 Oct Simons/Anthropic/OpenAI US$15M fund (deck notes, "The bigger picture"), so this may be the same money re-announced. Treat it as **unconfirmed**.
- **Model access: nothing found.** TNW says it is "not stated" ([TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)).
- **Disclosure changes in the repo (confirmed).** The README now says "an **unnamed** internal OpenAI model" and adds "We defer to the math community completely on matters of credit, precedence, and concurrent work" ([commit 42907c9](https://github.com/openai/math/commit/42907c9)).

**Repo changes (confirmed).** `openai/math` had two updates in the window ([commits](https://github.com/openai/math/commits/main)):

- **26 Oct** ([42907c9](https://github.com/openai/math/commit/42907c9)): 300 files. Adds the ETH and local smoothing manuscripts, a Lean formalisation of "The rational Hodge conjecture for CM abelian varieties", Comparator fixes, and restored C++ source for the mutually-unbiased-bases result. README count goes from **719/372 to 721/373**.
- **29 Oct** ([204e5f8](https://github.com/openai/math/commit/204e5f8)): CM Hodge Comparator namespace fix.
- **No new withdrawals or revisions.** The 7 Oct entry (3 withdrawn, 14 revised) is still the only one. No updated formalisation percentage has been published (the README still says "~42%").
- `openai/NavierStokesAndEuler` has had **no commits since 10 Sep** and has 0 open issues ([repo](https://github.com/openai/NavierStokesAndEuler)), despite the translation-gap critique.

**Journal/arXiv submissions and the model.** No journal or arXiv submission by OpenAI was found. The README still says OpenAI is "exploring community-hosted repositories" ([README](https://github.com/openai/math)). Third parties are writing the human versions instead: Lei & Ren's Navier–Stokes exposition reached **v3 on 18 Nov**, cut from 245 to 182 pages, "We claim no original mathematical contribution" ([arXiv:2609.35406](https://arxiv.org/abs/2609.35406)). The model is now explicitly "unnamed". A secondary source says "GPT-6 Astra" did the 17-hour Lean translation of Navier–Stokes (**reported, unverified**, [Implicator](https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/)). The Gross committee reportedly used OpenAI's "Astra" to parse the Yang–Mills Lean code ([CASRAI](https://casrai.org/news/ai-rivals-physics-mathematical-challenge-2026)).

**Buckmaster/Alpöge priority dispute: no new statements found.** Nothing in the window from Buckmaster, Alpöge, Bubeck or OpenAI specific to Navier–Stokes (X posts could not be read). OpenAI's generic "defer to the math community" line is its de facto position ([commit 42907c9](https://github.com/openai/math/commit/42907c9)). Buckmaster did comment on Yang–Mills: "There is no way it took one month to Lean-verify Yang-Mills" (**reported**, [CASRAI](https://casrai.org/news/ai-rivals-physics-mathematical-challenge-2026)).

**Mapping to the IAS Advisory Group (AGMAI) recommendations.** The deck's "seven recommendations" are a paraphrase. AGMAI's primary text ([29 Sep guidelines](https://agmai.org/general-sep29/)) has 3 principles, 2 pathways (2A human-understood papers; 2B output nobody yet understands), 5 "Step I" release norms and 3 "Step II" funding items. The table maps the deck's seven onto those items, plus the two new statements.

| Deck's rec | AGMAI item | OpenAI, 26 Oct release and repo | Assessment |
|---|---|---|---|
| 1. Stop testing open problems on proprietary models | Late-Sept statement, as quoted by [Futurism](https://futurism.com/artificial-intelligence/mathematicians-openai-furious) | Three more results from an unnamed internal model | **Not met** |
| 2. Repositories no lab controls, persistent IDs | I.2 | Still OpenAI's own GitHub; "exploring community-hosted repositories"; revision history kept | **Not met** |
| 3. Not model marketing | I.2 | "Raw research data", "no academic credit" ([Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956)); critics call Yang–Mills a "publicity stunt" ([Woit](https://www.math.columbia.edu/~woit/wordpress/?p=15986)) | **Disputed** |
| 4. Disclose model, prompts, reasoning, time, compute | I.3 | Model now "unnamed"; 10 reasoning summaries; average "three hours of ChatGPT Pro thinking"; for 26 Oct results, no prompts, compute or chains of thought ([SciAm](https://www.scientificamerican.com/article/dueling-proofs-from-openai-and-anthropic-astound-scientists/)) | **Partial**; model name withheld |
| 5. Formalise | I.4 | ETH and local smoothing in Lean; CM Hodge formalised; Yang–Mills reportedly in Lean | **Largely met** for new results |
| 6. Report attempts, failures, selection | I.5 | ~4,000 problems stated; no failure list | **Partial** |
| 7. Fund understanding; equitable model access | P2, II.1–3 | US$5m to Simons (reported); no access scheme | Funding **aligned** (terms unverified); access **not met** |
| *New, 25 Oct:* don't pre-designate mathematicians | P3, 2B | Hand-picked shepherds | **Conflicts** |
| *New, 26 Oct:* release Yang–Mills outputs now | P1 | Physics group withheld; Lean code reportedly public by ~11 Nov; ~1,147-page write-up reportedly still withheld ([Woit](https://www.math.columbia.edu/~woit/wordpress/?p=15986)) | **Partial / disputed** |

AGMAI's 25 Oct statement gives five reasons against designated mathematicians: delayed or unequal access, denied agency, biased selection, "borrowed reputation", and "it is unnecessary". It stresses this is not criticism of the mathematicians involved ([AGMAI](https://agmai.org/#disadvantages-designating-mathematicians)). The timing (one day before OpenAI's release) suggests it anticipated the shepherd model, but that is inference. AGMAI has posted nothing since 26 Oct ([agmai.org](https://agmai.org/)).

### 2.2 Verification status: no refutations, some cautious endorsements, no verdicts

| Claim | Status at 19 Nov | Evidence |
|---|---|---|
| **Navier–Stokes (forced)** | No independent full check or refutation found. Lean code compiles and is accepted by several kernels; the Lean–English correspondence is questioned | KCL publicised the translation-gap preprint on 27 Oct. Its authors say they "have not shown the original proof is wrong", only that the Lean version "does not fully match" the written one (**confirmed**, [KCL](https://www.kcl.ac.uk/news/openais-navier-stokes-proof-called-into-question)). Divergence reportedly at Lemma 8.6 (**reported**, [AI Weekly](https://aiweekly.co/alerts/paper-flags-gap-in-openais-lean-verified-navier-stokes-proof)). Buzzard: the ~640K-line formalisation compiles and passes several kernels (**confirmed**, [Xena](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/)) |
| **Unique Games Conjecture** | Most closely checked; cautiously positive; no formal verdict | Moshkovitz studied it "with Subhash Khot himself, Johan Håstad, Dor Minzer"; the key idea is "a totally alien new error-correcting code", the rest "standard" (**confirmed**, [Aaronson](https://scottaaronson.blog/?p=10232)). Two-hour talk on 4 Nov, titled "Proved (!!?)" (**confirmed**, [UT Austin](https://ai.utexas.edu/events/2026-11-04/unique-games-conjecture-proved)) |
| **L = RL = BPL** | No expert confirmation or refutation | Repo has a Lean doc covering binary languages in a log-workspace TM model ([103.md](https://github.com/openai/math/blob/main/lean/docs/103.md)). A Lean library dropped the "OpenAI preprint route", saying this "is not a claim that its endpoint was proved or disproved" (**confirmed**, [complexitylib #1444](https://github.com/cslib-community/complexitylib/issues/1444)) |
| **ETH refutation (new)** | Treated as likely correct by Fortnow; formal review under way | "I have not verified the proof myself, but it is safe to assume now that the exponential-time hypothesis is toast." The Lean proof gives a slightly weaker bound than the paper. O'Donnell and Kintali posted simpler proofs (**confirmed**, [Fortnow](https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html)). Follow-up generalisation by Strassle & Subercaseaux ([arXiv:2611.11832](https://arxiv.org/abs/2611.11832v1)) |
| **Yang–Mills existence (new)** | Shepherd committee affirms Lean proof; scope disputed | "We do not claim to fully understand the proof yet"; mass gap untouched (**reported**, [CASRAI](https://casrai.org/news/ai-rivals-physics-mathematical-challenge-2026)). Woit argues it is *weak* existence, which the Clay description excludes; Kalai calls it a major breakthrough (**disputed**, [Woit](https://www.math.columbia.edu/~woit/wordpress/?p=15986)) |
| **Hodge-type claims** | Errors documented | Lekili & Sheridan set out the errors behind the 7 Oct withdrawals (**reported**, [arXiv:2610.30976](https://arxiv.org/abs/2610.30976)); a Lean formalisation of the renamed CM case was added 26 Oct (**confirmed**, [history.md](https://github.com/openai/math/blob/main/history.md)) |
| **Riemann-related** | Human digestion under way | Tao's Siegel-zeros sketch (**confirmed**, [Tao](https://terrytao.wordpress.com/2026/10/19/a-sketch-of-the-proof-of-non-existence-of-siegel-zeroes/)); Sarnak repurposed a class to study the quasi-RH result (**reported**, [Quanta](https://www.quantamagazine.org/ai-proved-the-quasi-riemann-hypothesis-what-happens-now-20261019/)) |

**Clay Mathematics Institute: nothing new.** The only Sep–Nov item on its news page is the 11 Sep "Navier-Stokes Announcement" ([Clay news](https://www.claymath.org/news/)). No review committee or process was found. Under Clay's rules (qualifying publication plus two years), no prize decision could come before about late 2028, and OpenAI says it won't claim the prize ([Implicator](https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/)).

**Translation gap and Comparator.** Bastounis–Circelli–Hansen ([arXiv:2610.08144](https://arxiv.org/abs/2610.08144)) remains the key paper. No paper evaluating Comparator itself was found. The strongest new evidence is Buzzard's audit (**confirmed**, [Xena](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/)):

- About **290 of the 722 papers (~45%) came with Lean code**.
- About **38 Lean packages do not state or prove the paper's main theorem**. For example, the Lech's conjecture package proves Corollary 5.4 instead.
- Lean compiling "does not mean that any corresponding pdf also contains a correct proof!" He recommends `lake comparator` and checking with several kernels.

Science reportedly discusses the risk that Lean software bugs let invalid proofs through (**reported**, [Science](https://www.science.org/content/article/ai-shaking-math-can-its-proofs-be-trusted); not readable). Tao's views page records an Aug 2026 Lean flaw, found by a model, that could certify any statement (**confirmed**, [Tao](https://teorth.github.io/tao-web/ai-views.html)).

### 2.3 Other labs: formalising known maths and verifying code

Outside OpenAI, the window brought **very large formalisations of known theorems** and **software and hardware verification**, not new open-problem claims in pure maths. All the figures below are self-reported.

| Lab | Date | Announcement | Status |
|---|---|---|---|
| Google DeepMind | **[pre-window] 12 Oct** | AlphaProof Nexus, **peer-reviewed in *Science***: 9 of 353 Erdős problems attempted, 44 OEIS conjectures. Press framed it as the peer-reviewed alternative to GitHub dumps ([The Decoder](https://the-decoder.com/google-deepminds-alphaproof-nexus-solved-dozens-of-open-math-problems-and-actually-got-peer-reviewed/)) | reported; missed and important |
| Google DeepMind | 10 Nov | **AlphaProof Code**: "Gemini Carbon" agents wrote over six million lines of Lean in 4 weeks verifying Signal's compiled code; ~1% flagged for human review; two re-inserted bugs caught ([DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/)) | confirmed (claim); line count disputed (see §3.2) |
| Anthropic | 9 Nov (amended 11 Nov) | **Claude Fable 5.2**: 1,000 agents formalised **Fermat's Last Theorem** in 30 hours with "minimal human intervention". They started from 60 statements, a sketch and 47 reused lemmas, so read "minimal" with care. **No open-maths claim.** Fable 5.2 is generally available; Mythos 5.2 is restricted to life sciences and cyber programmes, with **no maths access programme** ([Anthropic](https://www.anthropic.com/claude-fable-and-mythos-5-2)) | confirmed (claim) |
| Anthropic | 26 Oct | Rival ETH refutation ([SciAm](https://www.scientificamerican.com/article/dueling-proofs-from-openai-and-anthropic-astound-scientists/); [Fortnow](https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html)) | reported; date disputed |
| Axiom | 6 & 12 Nov, plus undated Nov posts | **Weil conjectures** (sorry-free; the post credits humans only, led by Tony Yue Yu with Ken Ono and others) and **Faltings' theorem** (~110k proof-specific lines on ~6.4M lines of Stacks Lean) ([Weil](https://axiommath.ai/research/the-weil-conjectures-formalized-in-lean/); [Faltings](https://axiommath.ai/research/faltings-theorem-formalized/)). Also Stacks Project, Minimal Model Program, cluster algebras and a CFSG corpus ([index](https://axiommath.ai/territory/)) | confirmed (claims); AI role unclear; Weil scale **disputed** (an employee says 50M lines over 24 days, the CEO reportedly "less than a day") |
| Harmonic | 27 Oct – 16 Nov | Aristotle moves into C, Verilog, RISC-V (Ibex MUL/DIV), multiclock hardware and Rust ([Harmonic](https://www.harmonic.fun/news)) | confirmed (headlines only) |
| Math, Inc. | undated | Homepage tagline: "Scaling autoverification to all future software" ([math.inc](https://www.math.inc/)) | confirmed; no dated announcement |
| DeepSeek, Mistral, Meta, xAI | — | **Nothing found** in the window | — |

**Academic access and IAS adoption: none found.** No non-OpenAI lab announced a maths access scheme. None of the in-window primary posts from Anthropic, DeepMind or Axiom mentions AGMAI, IAS or disclosure norms. AGMAI says it is in contact with unnamed labs ([AGMAI](https://agmai.org/)). In practice, labs give access by open-sourcing Lean repos. *Inference:* choosing machine-checkable outputs (formalisations of known theorems, verified code) sidesteps the contested "unverifiable claim from a secret model" problem, though no lab says so.

### 2.4 Community and institutional responses: from statements to practical measures

**Learned societies (IMU, AMS, LMS, EMS) and IAS itself: nothing new found.** The Leiden Declaration news page has nothing after 17 Sep ([Leiden](https://leidendeclaration.ai/news)). The Fields Institute's "Engaging with the Leiden Declaration" panel series ran until 17 Nov ([Fields](https://www.fields.utoronto.ca/activities/26-27/Leiden)). The UK Academy for the Mathematical Sciences released an Oct 2026 report preprint whose contents could not be checked (**reported**, [AcadMathSci](https://www.acadmathsci.org.uk/wp-content/uploads/2026/10/Mathematical_Sciences_AI_AcadMathsSci_Oct2026_preprint_final.docx.pdf)). The advisory role has passed to AGMAI (see §2.1).

**Journals, publishers and arXiv: coping with volume.**

- ESAIM: P&S paused new submissions from 19 Oct to 8 Nov, citing "a substantial increase in manuscript submissions… driven largely by the rapid development of artificial intelligence" (**confirmed**, [EDP Sciences](https://www.edpsciences.org/en/news-highlights/3058-esaim-probability-and-statistics-takes-action-to-address-increasing-manuscript-submissions)).
- Five more probability journals reportedly paused alongside it: EJP, ECP, SPA, Bernoulli and AIHP (**reported**, [MACCUS](https://maccus.fr/en/ai-paper-flood/)).
- IMS updated its AI policy on 8 Nov, and MSP released a "deliberately minimal" draft on 1 Nov (**reported**, [IMS](https://imstat.org/journals-and-publications/policy-on-use-of-ai/); [MSP](https://msp.org/publications/ai/)).
- Nothing from Annals, Acta, JAMS or Inventiones.
- **arXiv: nothing new.** The **[pre-window] 1 Oct** rate limit (two submissions per author per month) is still the relevant policy ([arXiv blog](https://blog.arxiv.org/2026/10/01/updated-rate-limit-policy/)).

**Funders: private money builds capacity, public funders are quiet.**

- **[pre-window] 15 Oct:** the Simons US$15M fund with Anthropic and OpenAI. Its Math+AI Institutes call closes 1 Dec ([Simons](https://www.simonsfoundation.org/news/simons-foundation-launches-15m-effort-to-help-mathematicians-navigate-ai-era/); [RFA](https://www.simonsfoundation.org/funding/targeted-grants-to-mathai-institutes-2027/)).
- **4 Nov:** Imperial's £5M XTX-funded Langlands Lab, linked to Buzzard (**reported**, [Imperial](https://www.imperial.ac.uk/news/articles/admin-services/giving/2026/5-million-grant-to-establish-new-laboratory-for-ai-assisted-mathematics-at-imperial/)).
- An ERC project is using Claude to decipher Gödel's notebooks (**reported**, [Guardian](https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths)).
- **Nothing found from UKRI/EPSRC, NSF or ERC as policy.**

**Universities.**

- New centres: Imperial, the Yau Alliance (above).
- Oxford Mathematics launched a maths-and-AI video series with Green and Maynard (**reported**, [Oxford](https://www.maths.ox.ac.uk/node/86322)).
- At Northwestern, Bryna Kra said OpenAI's rollout broke community conventions (**reported**, [Daily Northwestern](https://dailynorthwestern.com/2026/11/10/campus/a-canary-in-the-coal-mine-nu-math-professors-share-optimism-resilience-as-they-adapt-to-growing-ai-research/)).
- A CNRS-hosted AI-free group theory initiative, GGTH, was set up (**reported**, [GGTH](https://ggth.pages.math.cnrs.fr)).
- **Dartmouth paused maths PhD admissions, but the article does not mention AI. Do not present this as an AI response** ([The Dartmouth](https://www.thedartmouth.com/article/2026/11/gandhi-fagell-guarini-will-not-admit-math-ph-d-cohort-this-year)).

**AHM, Fields Medallists, Leiden.**

- The AHM reports 1,008 members, 654 of them in an AI-free caucus; these are self-reported figures from a self-selected group (**reported**, [Magica](https://magica.com/news/human-mathematics-association-passes-1000-members-ai-commitments); [New Scientist](https://www.newscientist.com/article/2593621-a-thousand-human-mathematicians-pledge-to-shun-ai-in-their-research/)).
- It published Doctoral Advising Guidelines on 3 Nov (**confirmed**, [Tao](https://terrytao.wordpress.com/2026/11/03/doctoral-advising-guidelines-by-the-ahm/)).
- Its statements page lists nothing new after 7 Oct ([AHM](https://www.ahmath.org/statements)).
- **Nothing new found** from the Fields Medallists' group or the Leiden organisers.
- A "MisAnthropic Statement" turns the same critique on Anthropic (**reported**, [misanthropicstatement.com](https://misanthropicstatement.com)).

**Essays and talks.** Tao opened his blog to guest posts, and it became the community's main forum. The tone is mostly adaptive, not doom-laden:

- **Calegari** (1 Nov) makes six proposals, including "Evaluate all work as if it is AI-assisted", hiring on in-person interaction, higher standards of exposition from journals, and treating AI results as shared heritage ([Tao](https://terrytao.wordpress.com/2026/11/01/mathematics-has-changed-lets-act-like-it/)).
- **"Egoless Mathematics in the AI Era"** (Karthik C. S., Sahai, Xue; 2 Nov) ([Tao](https://terrytao.wordpress.com/2026/11/02/egoless-mathematics-in-the-ai-era/)).
- Essays by **Etingof, Gilbert, Guth and Kasirzadeh** (6 Nov) ([Tao](https://terrytao.wordpress.com/2026/11/06/more-posts/)).
- An undergraduate-teaching post, an early-career survey (job security and funding are the main worries) and Futures of Maths (5–9 Nov) ([Tao's blog](https://terrytao.wordpress.com/)).
- **MathHelm** (13 Nov): "takes no predetermined position for or against AI"; "Mathematicians have no obligation to check AI-generated papers"; bans training on forum content ([Tao](https://terrytao.wordpress.com/2026/11/13/introducing-mathhelm-a-place-to-discuss-ai-generated-papers/)).
- **Buzzard** on what Lean does and does not certify (§2.2).
- **Aaronson** on UGC (§2.2) and on PSI's proof of his own conjecture (**reported**, [Shtetl-Optimized](https://scottaaronson.blog/?p=10295)).
- **Tao** in The Economist (18 Nov; text not read) and on *Conversations with Tyler* (19 Nov) (**reported**, [Economist](https://www.economist.com/the-world-ahead/2026/11/18/performance-is-outpacing-understanding-and-safety-in-ai-says-terence-tao); [CWT](https://conversationswithtyler.com/episodes/terence-tao/)).
- Danny Calegari's talk "Collaborating with Claude" (24 Oct) (**reported**, [YouTube](https://www.youtube.com/watch?v=jj7cEfnN09c)).
- **Nothing found** in the window from Litt, Wood (as an individual), Strogatz, Kontorovich or Szegedy.

### 2.5 Open and crowdsourced efforts: consolidation and curation

- **Formal Conjectures (confirmed).** About **360 PRs merged** in the window and 842 open ([merged PRs](https://github.com/google-deepmind/formal-conjectures/pulls?q=is%3Apr+is%3Amerged+merged%3A2026-10-19..2026-11-19)).
  - From 29 Oct, formal proofs of "research solved" entries must link a **Palomar registry** entry. 1,096 existing proof annotations on 1,070 declarations were grandfathered in ([PR #7631](https://github.com/google-deepmind/formal-conjectures/pull/7631)).
  - An "AI audit tracker" flagged misformalised statements that were false for every choice of answer, and these were fixed ([PR #8015](https://github.com/google-deepmind/formal-conjectures/pull/8015)).
  - Newly settled in the repo: a Lean disproof of Kelly's conjecture, an Erdős #338 variant. It may duplicate Hennecart (2005), and AI use is not stated ([PR #7788](https://github.com/google-deepmind/formal-conjectures/pull/7788)). Also WOWII Conjecture 19 ([PR #7571](https://github.com/google-deepmind/formal-conjectures/pull/7571)).
  - R(5,5) ≥ 43 is now kernel-checked; this is a known result ([PR #7998](https://github.com/google-deepmind/formal-conjectures/pull/7998)).
- **Erdős problems.**
  - **[pre-window, missed and important] 6 Oct:** Thomas Bloom froze proof claims and comments on erdosproblems.com, **removed problem statuses and the solved count**, and dropped credit language. His reason: the site had become a place to "advertise their AI-generated proofs… to record a (increasingly meaningless) priority claim" ([erdosproblems.com](https://www.erdosproblems.com/forum/thread/blog:9)).
  - On 8 Oct he catalogued the 25 Erdős problems OpenAI claimed (21 formalised). He judged the papers "very poorly written" but likely "correct", and noted plagiarism accusations ([erdosproblems.com](https://www.erdosproblems.com/forum/thread/blog:10)).
  - The community database **did not change its solved count in the window** (579 solved, 642 open). Lean-formalised problems rose from 874 to 1,018 (**confirmed**, [statistics_history.csv](https://github.com/teorth/erdosproblems/blob/main/data/statistics_history.csv)).
  - **No Erdős problem newly solved with AI help in the window was found.**
- **Revision repo.** `teorth/oai-math-revised` ("we will cite the people") invites PRs that add literature reviews and fix OpenAI's write-ups. Who leads it is unclear (**reported**, [GitHub](https://github.com/teorth/oai-math-revised)).
- **Mathlib and Lean (confirmed).**
  - Lean v4.36.0 was released on 16 Nov, and Mathlib took ~809 commits in the window ([Lean](https://github.com/leanprover/lean4/releases)).
  - mathlib3 was archived on 6 Nov ([mathlib3](https://github.com/leanprover-community/mathlib3)).
  - **[pre-window] 15 Oct:** de Moura announced "con-leche", a Lean kernel written in Lean and proven consistent (**reported**, self-published, [blog](https://leodemoura.github.io/blog/2026-10-15-lean-now-ships-with-verified-kernels/)).
  - Tau Ceti, an AI-authored library built on Mathlib, announced an Anthropic grant on 30 Oct ([Tau Ceti](https://taucetiproject.org/)).
- **Equational Theories and Tao's other projects (confirmed).**
  - ETP added an end-to-end Lean certificate for all 4,694 equations (26 Oct) and is responding to referees ([PR #1506](https://github.com/teorth/equational_theories/pull/1506); [commits](https://github.com/teorth/equational_theories/commits/main)).
  - The optimisation-constants repo saw ~100 curation commits ([commits](https://github.com/teorth/optimizationproblems/commits/main)).
- **Amateurs and small teams: nothing clearly dated in the window that credits a public model.** The best case is from before the window: Liam Price with GPT-5.4 Pro on Erdős #1196/#1202. Its Codex formalisation was linked in Formal Conjectures on 27 Oct ([PR #7638](https://github.com/google-deepmind/formal-conjectures/pull/7638); [ecoticias](https://www.ecoticias.com/en/a-forum-user-asked-an-ai-model-about-an-erdos-problem-that-had-been-open-for-60-years-and-the-trick-hidden-in-its-proof-is-now-settling-other-puzzles-mathematicians-had-left-unsolved/53752/)).

### 2.6 Beyond maths: the model transfers wherever Lean can follow

| Date | Who | Field | Verifier | Reception |
|---|---|---|---|---|
| 21 Oct | OpenAI + PerturbAI + Scripps | Neurogenomics (~2,000 GPT-Rosalind agents) | None formal: blinded experts preferred the reports 75% of the time; wet-lab validation pending | Preprint only (**reported**, [OpenAI](https://openai.com/index/scaling-ai-research-for-complex-biological-data/); [AI Weekly](https://aiweekly.co/alerts/openai-perturbai-and-scripps-run-2000-gpt-rosalind-agents-on-8m-cell-brain)) |
| 6 Nov | PSI (non-public Anthropic model) | Quantum query complexity: Aaronson–Ambainis conjecture | Lean plus human audit | Stanford group who proved a special case call it "a huge result"; no peer review (**confirmed**, [PSI](https://psi.inc/research/aaronson-ambainis/); [GitHub](https://github.com/physical-superintelligence/aaronson-ambainis); [Quantum Insider](https://thequantuminsider.com/2026/11/06/ai-assisted-proof-settles-longstanding-question-about-quantum-speedups/)) |
| 10 Nov | Google DeepMind + Signal | Software / cryptography | Lean; human-reviewed specifications | Signal's CTO quoted; no independent review (**confirmed**, [DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/)) |
| 9 & 17 Nov | Anthropic | Theoretical physics: Hawking–Page transition in N=4 SYM; 3D-gravity modular bootstrap bound | Lean for the bootstrap bound; duplicate agents plus a physicist for Hawking–Page | Anthropic: neither describes our universe. Gizmodo: not independently peer reviewed (**confirmed**, [Anthropic](https://www.anthropic.com/research/claude-black-hole-physics); [Gizmodo](https://gizmodo.com/anthropics-says-its-new-ai-model-can-solve-black-hole-mysteries-what-could-go-wrong-2000837274)) |

**The debate.** The model transfers only as far as a field can be formalised or has a trusted, cheap checker.

- Krippendorf, Sarra and Tooby-Smith: "a verified proof does not guarantee its definitions match the intended physics" (**[pre-window] 6 Oct**, [arXiv:2610.14059](https://arxiv.org/abs/2610.14059)).
- A NeurIPS 2026 workshop: "The bottleneck for AI for Science is no longer hypothesis generation, it is verification" ([workshop](https://ai4sciencecommunity.github.io/neurips26)).
- **Counter-evidence:** the FrontierPhysics benchmark (~4 Nov) reports that every agent passed fewer than 30% of end-to-end research tasks. The best was Claude Opus 5.5 at 27.4%, with failures put down to rigour and intuition (**reported**, [arXiv:2611.06910](https://arxiv.org/abs/2611.06910); [Kashani](https://qelvin.substack.com/p/an-ai-proved-a-quantum-conjecture)).
- *Inference:* verifiers form a spectrum. Lean is cheap and near-perfect, but the specs must be right. Below it come redundant agents plus expert spot-checks, then simulators, then slow physical experiments. The deck's slogan "an agent generates, a cheap checker decides" holds at the top tier only.

### 2.7 Media and numbers: no costs, contested counts

**Coverage.**

- Scientific American (Joseph Howlett) was the de facto beat reporter:
  - "Dueling proofs from OpenAI and Anthropic astound scientists" (27 Oct) ([SciAm](https://www.scientificamerican.com/article/dueling-proofs-from-openai-and-anthropic-astound-scientists/)).
  - "OpenAI's 'shepherds' affirm blockbuster physics result" (11 Nov; page not readable, details via [CASRAI](https://casrai.org/news/ai-rivals-physics-mathematical-challenge-2026)) ([SciAm](https://www.scientificamerican.com/article/openais-shepherds-affirm-blockbuster-physics-result/)).
- Other outlets:
  - The Next Web and Gizmodo covered 26 Oct.
  - NPR *Short Wave*, "Is it hurting the field?" (4 Nov; content not retrieved) ([NPR](https://www.npr.org/2026/11/04/nx-s1-6010471/ai-math-navier-stokes-mathematicians-openai)).
  - Axios, "'AI is a finisher'" (4 Nov; optimistic framing) ([Axios](https://www.axios.com/2026/11/04/ai-math-hope-human-intellect)).
- **Undated, possibly in the window:**
  - A Nature column, "why I think the field will survive OpenAI's disruption" ([Nature](https://www.nature.com/articles/d41586-026-03622-x)).
  - Emily Riehl in Science: an AI proof "does not have an author who can explain the main ideas" ([Science](https://www.science.org/doi/10.1126/science.ael8339)).
- **Quanta:** nothing dated in the window apart from the 19 Oct Sarnak piece.
- **NYT, FT, Guardian (beyond Gödel), Economist (beyond Tao), WSJ, Wired, Atlantic, New Scientist:** could not be checked.
- **Labour-market and education angles were largely absent** from the coverage that could be reached.

**Numbers.** No lab disclosed a dollar cost, GPU-hours or energy figure for any result in the window. For the 26 Oct results, prompts, compute time and chains of thought were not published ([SciAm](https://www.scientificamerican.com/article/dueling-proofs-from-openai-and-anthropic-astound-scientists/)).

| Figure | Value | Status |
|---|---|---|
| Problems posed (bulk release) | ~4,000 | Lab-reported ([README](https://github.com/openai/math)) |
| Compute per result | ~3 h "ChatGPT Pro thinking", **successful results only** | Lab-reported ([OfficeChai](https://officechai.com/ai/openai-used-just-3-hours-of-chatgpt-pro-thinking-per-result-for-its-300-math-proofs-company-reveals/)) |
| Attempted vs failed | Not published | Gap |
| Implied "success rate" | 9–18% (372 families or 722 manuscripts ÷ 4,000) | **Do not present as a success rate**: OpenAI chose what to publish |
| ETH timeline | Found 16 Oct, Lean-checked 17 Oct | Lab-reported ([TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)) |
| Yang–Mills write-up | ~1,147 pages (estimates range 1,146–~1,200) | Reported ([Woit](https://www.math.columbia.edu/~woit/wordpress/?p=15986)) |
| Navier–Stokes run | ~10,000 agents, 88 h, ~130bn tokens; costs "reportedly in the millions" | Lab-reported; cost unsourced ([SciAm](https://www.scientificamerican.com/article/openais-blockbuster-navier-stokes-proof-isnt-what-we-thought-it-was/); [OfficeChai](https://officechai.com/ai/openai-used-just-3-hours-of-chatgpt-pro-thinking-per-result-for-its-300-math-proofs-company-reveals/)) |
| Swarm's contribution | Noam Brown: under 10% of the success came from the multi-agent setup | **[pre-window] 17 Oct**, reported ([The Decoder](https://the-decoder.com/mathematicians-say-openai-doesnt-understand-its-own-navier-stokes-proof/)) |
| AI proof style | Similarity ~0.68 among AI runs vs ~0.37 AI–human; ~40% of AI citations go to foundational definitions | Confirmed (claim) ([arXiv:2611.16527](https://arxiv.org/abs/2611.16527)) |

---

## 3. What has changed

### 3.1 Outdated or wrong items in "What I already know"

| Earlier claim | Correction |
|---|---|
| "The README now says 719." | **721 manuscripts in 373 families** since 26 Oct, after the ETH and local smoothing manuscripts were added (**confirmed**, [commit 42907c9](https://github.com/openai/math/commit/42907c9)). There were 722 at release and 719 after the 7 Oct withdrawals. |
| "~42% Lean-formalised" | The README still says "~42% top-line results" (last stated ratio: 300/719 on 7 Oct). Buzzard counts ~290 of 722 papers (~45%) **with Lean code**, of which ~38 don't state the main theorem ([Xena](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/)). Yahoo reports 162 of 722 with a machine-checked *main result* ([Yahoo](https://tech.yahoo.com/ai/chatgpt/articles/openai-drops-722-ai-math-171537220.html)). **Disputed**: the figure depends on the unit and the definition. |
| "IAS Advisory Group recommendations (29 Sep)", described as seven | The primary text has 3 principles, 2 pathways, 5 release norms and 3 funding items, not seven numbered recommendations ([AGMAI](https://agmai.org/general-sep29/)). AGMAI added two statements: 25 Oct (don't pre-designate mathematicians) and 26 Oct (release the Yang–Mills outputs). |
| Unreleased "internal model" | The README now explicitly says "**unnamed** internal OpenAI model" ([commit 42907c9](https://github.com/openai/math/commit/42907c9)). |
| Translation gap: Lean proof "does not correspond" to the English | Add: the authors say they **have not shown the proof is wrong** ([KCL](https://www.kcl.ac.uk/news/openais-navier-stokes-proof-called-into-question)). Buzzard finds the Navier–Stokes formalisation compiles under several kernels ([Xena](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/)). |
| Claims include UGC and L = BPL, plus partial Riemann and Hodge | Add the 26 Oct claims (ETH, Kakeya via local smoothing, 4D Yang–Mills/QCD existence). UGC now has a serious expert exposition (Moshkovitz). The Hodge errors are documented by Lekili & Sheridan, and the CM case is now Lean-formalised. |
| Association for Human Mathematics statement (Oct) | It now reports 1,008 members and has published doctoral advising guidelines. Its name and Tao's role are **disputed** in coverage (see §3.2). |
| Other labs: "an unreleased Claude model's partial Riemann progress" | Anthropic's newest public model, Fable 5.2, formalised FLT, and its claims now extend to physics and to a rival ETH proof. An unreleased Anthropic model powers PSI's Aaronson–Ambainis proof. DeepMind's AlphaProof Nexus was peer-reviewed in *Science* (12 Oct). Axiom formalised Weil and Faltings. |
| Tao's Erdős problems project as a live AI scoreboard | Since 6 Oct, erdosproblems.com **shows no statuses or solved counts** and has frozen proof claims ([Bloom](https://www.erdosproblems.com/forum/thread/blog:9)). The wiki stopped updating on 30 Jun (deck notes). |
| Clay issued a statement | Still true, and there is **nothing newer** than 11 Sep ([Clay](https://www.claymath.org/news/)). |
| Priority dispute | No new statements from the parties in the window. |

### 3.2 Conflicts between sources, reconciled

| Conflict | Sources | Resolution |
|---|---|---|
| Manuscript count: 722 / 719 / 721; 372 / 373 families; "~400" | Repo diff (primary); Yahoo; tech-insider (says 27 Oct); MathHelm post (722); SciAm (~400) | **Use the repo:** 721 manuscripts / 373 families since 26 Oct (the commit is dated 26 Oct; tech-insider's "27 Oct" is likely the merge or report date). 722 is the release-day figure, which MathHelm still uses. Bloom's "372 proof claims" are the families. SciAm's "~400" is loose. |
| Lean coverage: 42% / ~45% / 162 of 722 / 235 of 372 families | README; Buzzard; Yahoo | **Disputed.** "Has Lean code" (~45%), "top-line result formalised" (~42%) and "main result machine-checked" (162/722 ≈ 22%) measure different things. Quote the README with Buzzard's caveat. |
| "Seven" IAS recommendations | Deck vs AGMAI text | **Not literally seven.** The deck's list is a reasonable paraphrase of I.1–I.5, P2 and II, but should say so. |
| Date of Anthropic's ETH paper: 16, 17 or 26 Oct | [letsdatascience](https://letsdatascience.com/news/openai-and-anthropic-claim-ai-models-disproved-exponential-t-f4369e39), [Level Up](https://levelup.gitconnected.com/two-ai-labs-disproved-the-exponential-time-hypothesis-on-the-same-day-b0d2694f21b6) vs SciAm ("hours after OpenAI"), Fortnow (28 Oct) | **Disputed; 26 Oct most likely.** The 16/17 Oct dates match OpenAI's own discovery and Lean-check dates for ETH ([TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)), which suggests confusion in secondary sources. The Anthropic primary was not read. |
| AlphaProof Code: three or six million lines | Search summary vs fetched page | The **fetched page says "over six million"**. Use that, hedged. |
| Anthropic black-hole results: Gizmodo 9 Nov vs Anthropic 17 Nov | Gizmodo; Anthropic launch page; research post | **Not a real conflict.** The physics claims first appeared on the 9 Nov Fable 5.2 launch page, which Gizmodo covered. The detailed research post followed on 17 Nov. A [Medium piece](https://medium.com/write-a-catalyst/the-most-important-line-in-claudes-black-hole-paper-is-not-the-result-it-is-some-parts-59aacd4dff98) says the Hawking–Page preprint was posted 7 Nov and labelled "Primarily AI-generated" (unverified). |
| Yang–Mills affirmation: 9–10 Nov vs 11 Nov | SciAm via CASRAI vs Proofs and Prompts | Committee statement 9–10 Nov; SciAm report and assessment repo 11 Nov. Use "9–11 Nov". |
| Yang–Mills release status | AGMAI (26 Oct: release both NL and Lean) vs Woit (11 Nov: Lean public, ~1,147-page write-up withheld) | **Disputed / partial**: Lean code reportedly public by ~11 Nov; the natural-language write-up reportedly not. |
| Yang–Mills scope | OpenAI ("existence") vs Woit ("weak existence", excluded by Jaffe–Witten) vs Kalai ("major breakthrough") | **Disputed.** All sides agree the mass gap is untouched. |
| US$5m to Simons | TNW vs aggregators | **Unconfirmed** whether this is new money. It may be OpenAI's US$5M share of the 15 Oct US$15M fund. |
| AHM name, size and Tao's role | "Association for Human Mathematics" / "Association of Human Mathematicians" / "Human Mathematics Association"; ~600 / ~800 / 1,008 members; The Decoder says Tao chairs it, others say he is not on the member list | **Disputed.** Primary site is ahmath.org. Guest posts on Tao's blog do not establish membership. Don't say Tao leads it. |
| Weil formalisation scale | Axiom employee (50M lines, 24 days) vs CEO ("less than a day") | **Disputed**; neither checked against the repo. |
| Clay wording "apparently been settled" | One secondary source vs others stressing non-acceptance | Primary text not read; the deck already quotes it. Keep the quote alongside "status stays active". |

---

## 4. Suggested slide updates

1. **"Is any of it a big deal?"**: change the bold line "**Today the README says 719 manuscripts.** Where did three go?" to "**The README said 719 after the withdrawals, and now says 721 in 373 families** (two new results added 26 Oct)". In "Meanwhile: the bulk release", add a speaker note giving the 722 → 719 → 721 history ([commit 42907c9](https://github.com/openai/math/commit/42907c9)).
2. **"Timeline (2/2): open problems"**: add a row: "26 Oct 2026 | **OpenAI's second wave**: ETH refuted, local smoothing ⇒ Kakeya, 4D Yang–Mills existence; Anthropic posts a rival ETH proof | Lab race; 'shepherd' review". Optionally add "9 Nov | Anthropic formalises Fermat's Last Theorem (1,000 agents, 30 h)".
3. **"IAS Advisory Group: responsible release"**: change the subtitle to say the list is *paraphrased* from 3 principles and 8 norms (or drop the numbering). Add a line: "**Since then:** 25 Oct, labs should not hand results to chosen mathematicians first; 26 Oct, OpenAI should release the Yang–Mills outputs now." Replace the speaker note "Reportedly the 6 Oct release fell short of several of these" with the scorecard from §2.1: not met on #1 and #2, partial on #4 and #6, largely met on #5, funding but no access on #7 ([AGMAI](https://agmai.org/#disadvantages-designating-mathematicians)).
4. **"Rumour: results held in reserve?"**: change "**No public evidence** of a reserve or of that motive" to "**Partly borne out:** on 26 Oct OpenAI released three more results. ETH was found on 16 Oct (OpenAI's account), and the physics outputs were held back by its chosen reviewers." Keep "motive unsourced". Change the **Ask** to: "Is a hand-picked 'shepherd' group responsible stewardship, or gatekeeping?"
5. **"The translation gap"**: soften "They report that OpenAI's Lean proof **does not correspond** to its natural-language proof" to "…**does not fully match** it in at least one place (reportedly Lemma 8.6). They **do not claim the proof is wrong**." Add a bullet: "Buzzard (12 Nov): of OpenAI's ~290 Lean packages, ~38 don't state the paper's main theorem" ([Xena](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/); [KCL](https://www.kcl.ac.uk/news/openais-navier-stokes-proof-called-into-question)).
6. **"Is any of it a big deal?"**: update the "**Not yet confirmed**" bullet to: "Not yet confirmed, but checking has begun: Moshkovitz worked through UGC with Khot, Håstad and Minzer (talk 4 Nov, "Proved (!!?)"); an independent group (Impagliazzo, Paturi, Williams) is examining ETH; no peer review yet" ([Aaronson](https://scottaaronson.blog/?p=10232); [Fortnow](https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html)).
7. **"Meanwhile on GitHub: open, crowdsourced maths with AI"**: in the Erdős row, replace "Wiki logs **~700 AI contributions**, including failed ones" with "Site **stopped showing solved counts** and froze proof claims (6 Oct) after a flood of unexplained AI claims". In the Formal Conjectures row, add "proof links must go through the Palomar registry (since 29 Oct)". Add a row: "[oai-math-revised](https://github.com/teorth/oai-math-revised) / MathHelm | 2026 | Community rewrites and discussion of OpenAI's papers".
8. **"Secret models only? Who can use what"**: add two rows: "Fermat's Last Theorem formalised (Nov) | Claude Fable 5.2 | **Yes**" and "Aaronson–Ambainis conjecture, by startup PSI (Nov) | Non-public Anthropic model | **No**". Note that the 26 Oct OpenAI results also used the unnamed internal model ([Anthropic](https://www.anthropic.com/claude-fable-and-mythos-5-2); [PSI](https://psi.inc/research/aaronson-ambainis/)).
9. **"Why the swarm works: a cheap, trustworthy verifier"** (or "The bigger picture"): add "**It's spreading:** Lean-checked agent results in Nov for crypto code (DeepMind/Signal, ~6M lines), quantum complexity (PSI) and a black-hole physics bound (Anthropic). Without Lean, as with OpenAI's ~2,000 biology agents, the checker is a slow experiment." This turns the speaker-note discussion question into evidence ([DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/); [Anthropic](https://www.anthropic.com/research/claude-black-hole-physics)).
10. **"How mathematicians responded"**: add "**Calegari (1 Nov):** 'Evaluate all work as if it is AI-assisted'; rethink hiring, journals and teaching" and "**AHM:** 1,008 members (self-reported); doctoral advising guidelines (3 Nov)". In "The bigger picture" Institutions bullet, add "journals pausing submissions (six probability journals, 19 Oct) and a £5M AI-maths lab at Imperial (reported)".

---

## 5. New discussion questions

1. **Shepherds or open release?** OpenAI handed ETH to an unpaid, no-NDA group that asked for immediate public release, but handed Yang–Mills to a group that held the material back. AGMAI says no lab should pre-designate mathematicians at all. Which model would you trust, and does it matter who picks the reviewers?
2. **A certified theorem nobody understands.** The Yang–Mills committee says the Lean proof checks but "we do not claim to fully understand the proof yet", and Sarnak won't call the quasi-Riemann result a theorem until humans understand it. Is a Lean-checked result "known" mathematics? Compare Tao's cancer-cocktail thought experiment on the Math 2.0 slide.
3. **When the scoreboard switches off.** erdosproblems.com stopped showing solved counts because AI priority claims had become "increasingly meaningless", and Calegari proposes evaluating all work "as if it is AI-assisted". If credit for solving problems is no longer a signal, what should hiring, PhDs and promotion reward instead?
4. **Where does your field sit on the verifier spectrum?** In November the agent-swarm model succeeded where results could be put into Lean (code, quantum complexity, a physics bound), and stalled at "expert preference" in biology. What is the cheapest trustworthy checker in your research software, and who writes its specification?

---

## 6. Bibliography

```bibtex
@online{openai2026academic,
  author = {{OpenAI}},
  title = {Working with academic communities to build scientific understanding},
  url = {https://openai.com/index/building-scientific-understanding-with-academic-communities/},
  date = {2026-10-26},
  urldate = {2026-11-19},
  note = {Not read directly (HTTP 403); title and date as reported by Gizmodo and TNW}
}
@online{openai2026rosalind,
  author = {{OpenAI}},
  title = {Scaling AI research for complex biological data},
  url = {https://openai.com/index/scaling-ai-research-for-complex-biological-data/},
  date = {2026-10-21},
  urldate = {2026-11-19},
  note = {Not read directly (HTTP 403)}
}
@online{openaimath2026readme,
  author = {{OpenAI}},
  title = {openai/math (repository README)},
  url = {https://github.com/openai/math},
  date = {2026-10-30},
  urldate = {2026-11-19}
}
@online{openaimath2026history,
  author = {{OpenAI}},
  title = {openai/math history.md},
  url = {https://github.com/openai/math/blob/main/history.md},
  date = {2026-10-29},
  urldate = {2026-11-19}
}
@online{openaimath2026commit42907c9,
  author = {{OpenAI}},
  title = {Update math/cs papers, formalizations, and verification data (commit 42907c9)},
  url = {https://github.com/openai/math/commit/42907c9},
  date = {2026-10-26},
  urldate = {2026-11-19}
}
@online{openaimath2026commit204e5f8,
  author = {{OpenAI}},
  title = {Align CM Hodge comparator declarations with the Lean solution (commit 204e5f8)},
  url = {https://github.com/openai/math/commit/204e5f8},
  date = {2026-10-29},
  urldate = {2026-11-19}
}
@online{openaimath2026commits,
  author = {{OpenAI}},
  title = {openai/math commit history},
  url = {https://github.com/openai/math/commits/main},
  date = {2026-10-30},
  urldate = {2026-11-19}
}
@online{openaimath2026lean103,
  author = {{OpenAI}},
  title = {openai/math lean/docs/103.md (L = RL = BPL)},
  url = {https://github.com/openai/math/blob/main/lean/docs/103.md},
  date = {2026-10-06},
  urldate = {2026-11-19}
}
@online{openai2026nsrepo,
  author = {{OpenAI}},
  title = {openai/NavierStokesAndEuler},
  url = {https://github.com/openai/NavierStokesAndEuler},
  date = {2026-09-10},
  urldate = {2026-11-19}
}
@online{gizmodo2026openai3,
  author = {{Gizmodo}},
  title = {OpenAI trumpets 3 more math and science results, along with a new plan for publishing them},
  url = {https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956},
  date = {2026-10-26},
  urldate = {2026-11-19}
}
@online{tnw2026eth,
  author = {Constantin, Ana Maria},
  title = {OpenAI says its AI model has disproved the Exponential Time Hypothesis},
  organization = {The Next Web},
  url = {https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills},
  date = {2026-10-26},
  urldate = {2026-11-19}
}
@online{agmai2026general,
  author = {{Advisory Group on Mathematics and AI}},
  title = {General Guidelines},
  url = {https://agmai.org/general-sep29/},
  date = {2026-09-29},
  urldate = {2026-11-19}
}
@online{agmai2026openairelease,
  author = {{Advisory Group on Mathematics and AI}},
  title = {On OpenAI's Release},
  url = {https://agmai.org/#openai-release},
  date = {2026-10-06},
  urldate = {2026-11-19}
}
@online{agmai2026designating,
  author = {{Advisory Group on Mathematics and AI}},
  title = {Disadvantages of Designating Mathematicians for AI Output Releases},
  url = {https://agmai.org/#disadvantages-designating-mathematicians},
  date = {2026-10-25},
  urldate = {2026-11-19}
}
@online{agmai2026yangmills,
  author = {{Advisory Group on Mathematics and AI}},
  title = {Recommendation for Immediate Release of Yang--Mills AI Output},
  url = {https://agmai.org/#request-immediate-release},
  date = {2026-10-26},
  urldate = {2026-11-19}
}
@online{agmai2026home,
  author = {{Advisory Group on Mathematics and AI}},
  title = {AGMAI home page},
  url = {https://agmai.org/},
  date = {2026-10-26},
  urldate = {2026-11-19}
}
@online{futurism2026fury,
  author = {Landymore, Frank},
  title = {Mathematicians React With Fury as OpenAI Releases Hundreds of New AI-Generated Proofs},
  organization = {Futurism},
  url = {https://futurism.com/artificial-intelligence/mathematicians-openai-furious},
  date = {2026-10-09},
  urldate = {2026-11-19}
}
@online{leiren2026ns,
  author = {Lei, Zhen and Ren, Xiao},
  title = {Finite-Time Blowup for Navier-Stokes with Smooth Forcing, Part I},
  url = {https://arxiv.org/abs/2609.35406},
  date = {2026-11-18},
  urldate = {2026-11-19},
  note = {arXiv:2609.35406, v3}
}
@online{bastounis2026lost,
  author = {Bastounis, Alexander and Circelli, Fabian and Hansen, Anders},
  title = {Navier--Stokes lost in translation: Why Lean verification of AI autoformalisation does not guarantee correct natural language proofs},
  url = {https://arxiv.org/abs/2610.08144},
  date = {2026-10-06},
  urldate = {2026-11-19},
  note = {arXiv:2610.08144}
}
@online{kcl2026ns,
  author = {{King's College London}},
  title = {OpenAI's Navier-Stokes proof called into question},
  url = {https://www.kcl.ac.uk/news/openais-navier-stokes-proof-called-into-question},
  date = {2026-10-27},
  urldate = {2026-11-19}
}
@online{aiweekly2026lemma,
  author = {{AI Weekly}},
  title = {Paper flags gap in OpenAI's Lean-verified Navier-Stokes proof},
  url = {https://aiweekly.co/alerts/paper-flags-gap-in-openais-lean-verified-navier-stokes-proof},
  date = {2026-10},
  urldate = {2026-11-19},
  note = {Exact date not confirmed}
}
@online{implicator2026clay,
  author = {{Implicator}},
  title = {Clay Institute responds to OpenAI Navier-Stokes proof claim},
  url = {https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/},
  date = {2026-09-08},
  urldate = {2026-11-19}
}
@online{clay2026news,
  author = {{Clay Mathematics Institute}},
  title = {News},
  url = {https://www.claymath.org/news/},
  date = {2026-09-11},
  urldate = {2026-11-19}
}
@online{sciam2026nsnot,
  author = {Howlett, Joseph},
  title = {OpenAI's blockbuster Navier-Stokes proof isn't what we thought it was},
  organization = {Scientific American},
  url = {https://www.scientificamerican.com/article/openais-blockbuster-navier-stokes-proof-isnt-what-we-thought-it-was/},
  date = {2026-10-13},
  urldate = {2026-11-19}
}
@online{sciam2026dueling,
  author = {Howlett, Joseph and Hall, Peter},
  title = {Dueling proofs from OpenAI and Anthropic astound scientists},
  organization = {Scientific American},
  url = {https://www.scientificamerican.com/article/dueling-proofs-from-openai-and-anthropic-astound-scientists/},
  date = {2026-10-27},
  urldate = {2026-11-19}
}
@online{sciam2026shepherds,
  author = {{Scientific American}},
  title = {OpenAI's 'shepherds' affirm blockbuster physics result},
  url = {https://www.scientificamerican.com/article/openais-shepherds-affirm-blockbuster-physics-result/},
  date = {2026-11-11},
  urldate = {2026-11-19},
  note = {Not read directly; details via CASRAI}
}
@online{casrai2026ym,
  author = {{CASRAI}},
  title = {AI rivals physics on a mathematical challenge},
  url = {https://casrai.org/news/ai-rivals-physics-mathematical-challenge-2026},
  date = {2026-11-14},
  urldate = {2026-11-19}
}
@online{woit2026ym,
  author = {Woit, Peter},
  title = {The Yang-Mills Publicity Stunt},
  organization = {Not Even Wrong},
  url = {https://www.math.columbia.edu/~woit/wordpress/?p=15986},
  date = {2026-11-11},
  urldate = {2026-11-19}
}
@online{ymgroup2026assessment,
  author = {{Yang--Mills group}},
  title = {Assessment 1},
  url = {https://github.com/yang-mills-group/YM/blob/main/docs/assessment-1.pdf},
  date = {2026-11-11},
  urldate = {2026-11-19},
  note = {Via Proofs and Prompts newsfeed; not read directly}
}
@online{hairer2026humanise,
  author = {Hairer, Martin},
  title = {humanise-yang-mills},
  url = {https://github.com/hairer/humanise-yang-mills},
  date = {2026-11-11},
  urldate = {2026-11-19}
}
@online{armstrong2026informal,
  author = {Armstrong, Scott},
  title = {yang-mills-informalization},
  url = {https://github.com/scottnarmstrong/yang-mills-informalization},
  date = {2026-11-11},
  urldate = {2026-11-19}
}
@online{hep2026openletter,
  author = {{HEP open release signatories}},
  title = {Open letter on open release of AI-produced results},
  url = {https://hep-open-release.org},
  date = {2026-11-16},
  urldate = {2026-11-19},
  note = {Via Proofs and Prompts newsfeed}
}
@online{proofsandprompts2026newsfeed,
  author = {{Proofs and Prompts}},
  title = {Newsfeed},
  url = {https://proofsandprompts.com/newsfeed/},
  date = {2026-11-19},
  urldate = {2026-11-19}
}
@online{utaustin2026ugc,
  author = {{UT Austin AI}},
  title = {The Unique Games Conjecture -- Proved (!!?) (Dana Moshkovitz)},
  url = {https://ai.utexas.edu/events/2026-11-04/unique-games-conjecture-proved},
  date = {2026-11-04},
  urldate = {2026-11-19}
}
@online{aaronson2026ugc,
  author = {Aaronson, Scott},
  title = {Shtetl-Optimized post on the Unique Games proof},
  url = {https://scottaaronson.blog/?p=10232},
  date = {2026-10-30},
  urldate = {2026-11-19}
}
@online{aaronson2026psi,
  author = {Aaronson, Scott},
  title = {Shtetl-Optimized post on the Aaronson--Ambainis proof},
  url = {https://scottaaronson.blog/?p=10295},
  date = {2026-11-09},
  urldate = {2026-11-19},
  note = {Date approximate; content not read}
}
@online{fortnow2026eth,
  author = {Fortnow, Lance},
  title = {The Exponential-Time Refutation},
  organization = {Computational Complexity},
  url = {https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html},
  date = {2026-10-28},
  urldate = {2026-11-19}
}
@online{complexitylib2026issue1444,
  author = {{cslib-community}},
  title = {complexitylib issue \#1444},
  url = {https://github.com/cslib-community/complexitylib/issues/1444},
  date = {2026-10-28},
  urldate = {2026-11-19}
}
@online{strassle2026nondet,
  author = {Strassle, Jackson and Subercaseaux, Bernardo},
  title = {Follow-up generalising the ETH refutation to nondeterministic time},
  url = {https://arxiv.org/abs/2611.11832v1},
  date = {2026-11},
  urldate = {2026-11-19},
  note = {arXiv:2611.11832}
}
@online{lekili2026hodge,
  author = {Lekili, Yank{\i} and Sheridan, Nick},
  title = {Errors in OpenAI's claimed Hodge-conjecture cases},
  url = {https://arxiv.org/abs/2610.30976},
  date = {2026-10-24},
  urldate = {2026-11-19},
  note = {arXiv:2610.30976; title paraphrased, not read directly}
}
@online{mathcommunity2026revised,
  author = {{mathcommunity}},
  title = {OAI math revised: corrections, comments and reading groups},
  url = {https://mathcommunity.github.io/oai-math-revised/},
  date = {2026-10-29},
  urldate = {2026-11-19}
}
@online{teorth2026oairevised,
  author = {{teorth}},
  title = {oai-math-revised},
  url = {https://github.com/teorth/oai-math-revised},
  date = {2026-10-27},
  urldate = {2026-11-19}
}
@online{quanta2026sarnak,
  author = {{Quanta Magazine}},
  title = {AI Proved the Quasi-Riemann Hypothesis. What Happens Now?},
  url = {https://www.quantamagazine.org/ai-proved-the-quasi-riemann-hypothesis-what-happens-now-20261019/},
  date = {2026-10-19},
  urldate = {2026-11-19}
}
@online{tao2026siegel,
  author = {Tao, Terence},
  title = {A sketch of the proof of non-existence of Siegel zeroes},
  url = {https://terrytao.wordpress.com/2026/10/19/a-sketch-of-the-proof-of-non-existence-of-siegel-zeroes/},
  date = {2026-10-19},
  urldate = {2026-11-19}
}
@online{buzzard2026lean,
  author = {Buzzard, Kevin},
  title = {...and the proof is checked in Lean},
  organization = {Xena},
  url = {https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/},
  date = {2026-11-12},
  urldate = {2026-11-19}
}
@online{yahoo2026722,
  author = {{Yahoo Tech}},
  title = {OpenAI drops 722 AI math manuscripts},
  url = {https://tech.yahoo.com/ai/chatgpt/articles/openai-drops-722-ai-math-171537220.html},
  date = {2026-10},
  urldate = {2026-11-19},
  note = {Exact date not confirmed}
}
@online{techinsider2026721,
  author = {{Tech Insider}},
  title = {OpenAI 722 math manuscripts from an unreleased model},
  url = {https://tech-insider.org/openai-722-math-manuscripts-unreleased-model-2026/},
  date = {2026-10-27},
  urldate = {2026-11-19}
}
@online{officechai20263h,
  author = {{OfficeChai}},
  title = {OpenAI Used Just 3 Hours Of ChatGPT Pro Thinking Per Result For Its 300+ Math Proofs, Company Reveals},
  url = {https://officechai.com/ai/openai-used-just-3-hours-of-chatgpt-pro-thinking-per-result-for-its-300-math-proofs-company-reveals/},
  date = {2026-10-07},
  urldate = {2026-11-19}
}
@online{decoder2026brown,
  author = {{The Decoder}},
  title = {Mathematicians say OpenAI doesn't understand its own Navier-Stokes proof},
  url = {https://the-decoder.com/mathematicians-say-openai-doesnt-understand-its-own-navier-stokes-proof/},
  date = {2026-10-17},
  urldate = {2026-11-19}
}
@online{decoder2026nexus,
  author = {{The Decoder}},
  title = {Google DeepMind's AlphaProof Nexus solved dozens of open math problems and actually got peer reviewed},
  url = {https://the-decoder.com/google-deepminds-alphaproof-nexus-solved-dozens-of-open-math-problems-and-actually-got-peer-reviewed/},
  date = {2026-10-12},
  urldate = {2026-11-19}
}
@online{anthropic2026fable,
  author = {{Anthropic}},
  title = {Claude Fable 5.2 and Mythos 5.2},
  url = {https://www.anthropic.com/claude-fable-and-mythos-5-2},
  date = {2026-11-09},
  urldate = {2026-11-19},
  note = {Amended 11 Nov 2026}
}
@online{anthropic2026blackhole,
  author = {{Anthropic}},
  title = {Claude Fable 5.2 solves two open problems in the physics of black holes},
  url = {https://www.anthropic.com/research/claude-black-hole-physics},
  date = {2026-11-17},
  urldate = {2026-11-19}
}
@online{gizmodo2026anthropic,
  author = {{Gizmodo}},
  title = {Anthropic says its new AI model can solve black hole mysteries. What could go wrong?},
  url = {https://gizmodo.com/anthropics-says-its-new-ai-model-can-solve-black-hole-mysteries-what-could-go-wrong-2000837274},
  date = {2026-11-09},
  urldate = {2026-11-19}
}
@online{deepmind2026apcode,
  author = {Kohli, Pushmeet and Chaudhuri, Swarat},
  title = {Introducing AlphaProof Code},
  organization = {Google DeepMind},
  url = {https://deepmind.google/blog/introducing-alphaproof-code/},
  date = {2026-11-10},
  urldate = {2026-11-19}
}
@online{harmonic2026news,
  author = {{Harmonic}},
  title = {News},
  url = {https://www.harmonic.fun/news},
  date = {2026-11-16},
  urldate = {2026-11-19}
}
@online{axiom2026weil,
  author = {{Axiom}},
  title = {The Weil conjectures, formalized in Lean},
  url = {https://axiommath.ai/research/the-weil-conjectures-formalized-in-lean/},
  date = {2026-11-06},
  urldate = {2026-11-19}
}
@online{axiom2026faltings,
  author = {{Axiom}},
  title = {Faltings' theorem, formalized},
  url = {https://axiommath.ai/research/faltings-theorem-formalized/},
  date = {2026-11-12},
  urldate = {2026-11-19}
}
@online{axiom2026index,
  author = {{Axiom}},
  title = {Research index},
  url = {https://axiommath.ai/territory/},
  date = {2026-11},
  urldate = {2026-11-19}
}
@online{mathinc2026home,
  author = {{Math, Inc.}},
  title = {Math, Inc. home page},
  url = {https://www.math.inc/},
  date = {2026-11},
  urldate = {2026-11-19},
  note = {Undated content}
}
@online{psi2026aa,
  author = {{Physical Superintelligence}},
  title = {A proof of the Aaronson--Ambainis conjecture},
  url = {https://psi.inc/research/aaronson-ambainis/},
  date = {2026-11-06},
  urldate = {2026-11-19}
}
@online{psi2026github,
  author = {{Physical Superintelligence}},
  title = {aaronson-ambainis (code and Lean)},
  url = {https://github.com/physical-superintelligence/aaronson-ambainis},
  date = {2026-11-06},
  urldate = {2026-11-19}
}
@online{quantuminsider2026aa,
  author = {{The Quantum Insider}},
  title = {AI-assisted proof settles longstanding question about quantum speedups},
  url = {https://thequantuminsider.com/2026/11/06/ai-assisted-proof-settles-longstanding-question-about-quantum-speedups/},
  date = {2026-11-06},
  urldate = {2026-11-19}
}
@online{kashani2026aa,
  author = {Kashani},
  title = {An AI proved a quantum conjecture},
  url = {https://qelvin.substack.com/p/an-ai-proved-a-quantum-conjecture},
  date = {2026-11-07},
  urldate = {2026-11-19}
}
@online{aiweekly2026rosalind,
  author = {{AI Weekly}},
  title = {OpenAI, PerturbAI and Scripps run 2,000 GPT-Rosalind agents on 8M-cell brain atlas},
  url = {https://aiweekly.co/alerts/openai-perturbai-and-scripps-run-2000-gpt-rosalind-agents-on-8m-cell-brain},
  date = {2026-10-21},
  urldate = {2026-11-19}
}
@online{frontierphysics2026,
  author = {{FrontierPhysics authors}},
  title = {FrontierPhysics},
  url = {https://arxiv.org/abs/2611.06910},
  date = {2026-11-04},
  urldate = {2026-11-19},
  note = {arXiv:2611.06910; not read directly}
}
@online{krippendorf2026physics,
  author = {Krippendorf, Sven and Sarra, Lorenzo and Tooby-Smith, Joseph},
  title = {The Future of AI-assisted Physics: Discovering, Verifying and Organizing Results via Formalization},
  url = {https://arxiv.org/abs/2610.14059},
  date = {2026-10-06},
  urldate = {2026-11-19},
  note = {arXiv:2610.14059}
}
@online{neurips2026verification,
  author = {{NeurIPS 2026 workshop organisers}},
  title = {Verification in the Age of AI Scientists},
  url = {https://ai4sciencecommunity.github.io/neurips26},
  date = {2026-11},
  urldate = {2026-11-19}
}
@online{tao2026views,
  author = {Tao, Terence},
  title = {AI views},
  url = {https://teorth.github.io/tao-web/ai-views.html},
  date = {2026-11},
  urldate = {2026-11-19},
  note = {Undated page}
}
@online{economist2026tao,
  author = {Tao, Terence},
  title = {Performance is outpacing understanding and safety in AI},
  organization = {The Economist},
  url = {https://www.economist.com/the-world-ahead/2026/11/18/performance-is-outpacing-understanding-and-safety-in-ai-says-terence-tao},
  date = {2026-11-18},
  urldate = {2026-11-19},
  note = {Not read directly}
}
@online{science2026trust,
  author = {{Science}},
  title = {AI is shaking up math. But can its proofs be trusted?},
  url = {https://www.science.org/content/article/ai-shaking-math-can-its-proofs-be-trusted},
  date = {2026},
  urldate = {2026-11-19},
  note = {Not read (HTTP 403); date unknown}
}
@online{riehl2026science,
  author = {Riehl, Emily},
  title = {AI has solved many math problems, but it has not solved math},
  organization = {Science},
  url = {https://www.science.org/doi/10.1126/science.ael8339},
  date = {2026},
  urldate = {2026-11-19},
  note = {Not read (HTTP 403); date unknown}
}
@online{nature2026survive,
  author = {{Nature}},
  title = {'Mathematics is more than a mechanical process' -- why I think the field will survive OpenAI's disruption},
  url = {https://www.nature.com/articles/d41586-026-03622-x},
  date = {2026},
  urldate = {2026-11-19},
  note = {Not read (login redirect); date unknown}
}
@online{npr2026shortwave,
  author = {{NPR}},
  title = {OpenAI published tranches of math proofs. Is it hurting the field?},
  url = {https://www.npr.org/2026/11/04/nx-s1-6010471/ai-math-navier-stokes-mathematicians-openai},
  date = {2026-11-04},
  urldate = {2026-11-19}
}
@online{axios2026finisher,
  author = {{Axios}},
  title = {'AI is a finisher.' One mathematician's reasons for hope after AI's new dawn},
  url = {https://www.axios.com/2026/11/04/ai-math-hope-human-intellect},
  date = {2026-11-04},
  urldate = {2026-11-19}
}
@online{arxiv2026style,
  author = {{arXiv:2611.16527 authors}},
  title = {AI has its own style in mathematical proving},
  url = {https://arxiv.org/abs/2611.16527},
  date = {2026-11-12},
  urldate = {2026-11-19}
}
@online{edp2026esaim,
  author = {{EDP Sciences}},
  title = {ESAIM: Probability and Statistics takes action to address increasing manuscript submissions},
  url = {https://www.edpsciences.org/en/news-highlights/3058-esaim-probability-and-statistics-takes-action-to-address-increasing-manuscript-submissions},
  date = {2026-10-19},
  urldate = {2026-11-19}
}
@online{maccus2026flood,
  author = {{MACCUS}},
  title = {The AI paper flood},
  url = {https://maccus.fr/en/ai-paper-flood/},
  date = {2026-10-26},
  urldate = {2026-11-19}
}
@online{ims2026policy,
  author = {{Institute of Mathematical Statistics}},
  title = {Policy on use of AI},
  url = {https://imstat.org/journals-and-publications/policy-on-use-of-ai/},
  date = {2026-11-08},
  urldate = {2026-11-19}
}
@online{msp2026policy,
  author = {{Mathematical Sciences Publishers}},
  title = {AI policy (draft)},
  url = {https://msp.org/publications/ai/},
  date = {2026-11-01},
  urldate = {2026-11-19}
}
@online{arxiv2026ratelimit,
  author = {{arXiv}},
  title = {Fair Moderation, Equitable Access, and AI: updated rate limit policy},
  url = {https://blog.arxiv.org/2026/10/01/updated-rate-limit-policy/},
  date = {2026-10-01},
  urldate = {2026-11-19}
}
@online{acadmathsci2026report,
  author = {{Academy for the Mathematical Sciences}},
  title = {The mathematical sciences in an AI-enabled world (preprint)},
  url = {https://www.acadmathsci.org.uk/wp-content/uploads/2026/10/Mathematical_Sciences_AI_AcadMathsSci_Oct2026_preprint_final.docx.pdf},
  date = {2026-10},
  urldate = {2026-11-19},
  note = {Not read (HTTP 403)}
}
@online{fields2026leiden,
  author = {{Fields Institute}},
  title = {Engaging with the Leiden Declaration},
  url = {https://www.fields.utoronto.ca/activities/26-27/Leiden},
  date = {2026-11-17},
  urldate = {2026-11-19}
}
@online{royalsociety2026maths,
  author = {{Royal Society}},
  title = {Mathematics in the Age of AI},
  url = {https://portal.royalsociety.org/events/details/?id=baa5caea-28ff-491f-b747-7b9fea66d759},
  date = {2026-10-29},
  urldate = {2026-11-19}
}
@online{leiden2026news,
  author = {{Leiden Declaration}},
  title = {News},
  url = {https://leidendeclaration.ai/news},
  date = {2026-09-17},
  urldate = {2026-11-19}
}
@online{simons2026fund,
  author = {{Simons Foundation}},
  title = {Simons Foundation launches \$15M effort to help mathematicians navigate AI era},
  url = {https://www.simonsfoundation.org/news/simons-foundation-launches-15m-effort-to-help-mathematicians-navigate-ai-era/},
  date = {2026-10-15},
  urldate = {2026-11-19}
}
@online{simons2026rfa,
  author = {{Simons Foundation}},
  title = {Targeted Grants to Math+AI Institutes 2027},
  url = {https://www.simonsfoundation.org/funding/targeted-grants-to-mathai-institutes-2027/},
  date = {2026-10-15},
  urldate = {2026-11-19}
}
@online{imperial2026langlands,
  author = {{Imperial College London}},
  title = {£5 million grant to establish new laboratory for AI-assisted mathematics at Imperial},
  url = {https://www.imperial.ac.uk/news/articles/admin-services/giving/2026/5-million-grant-to-establish-new-laboratory-for-ai-assisted-mathematics-at-imperial/},
  date = {2026-11-04},
  urldate = {2026-11-19},
  note = {Not read (HTTP 403); via Proofs and Prompts}
}
@online{guardian2026godel,
  author = {{The Guardian}},
  title = {Kurt Gödel notebooks: AI helps unlock hidden discoveries},
  url = {https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths},
  date = {2026-11-13},
  urldate = {2026-11-19}
}
@online{scmp2026yau,
  author = {{South China Morning Post}},
  title = {Leading Chinese mathematicians unite behind use of AI in research},
  url = {https://www.scmp.com/news/china/science/article/3370492/leading-chinese-mathematicians-unite-behind-use-ai-research},
  date = {2026-10-19},
  urldate = {2026-11-19}
}
@online{oxford2026series,
  author = {{Oxford Mathematics}},
  title = {Maths and AI video series},
  url = {https://www.maths.ox.ac.uk/node/86322},
  date = {2026-11-10},
  urldate = {2026-11-19}
}
@online{dailynu2026,
  author = {{The Daily Northwestern}},
  title = {'A canary in the coal mine': NU math professors share optimism, resilience as they adapt to growing AI research},
  url = {https://dailynorthwestern.com/2026/11/10/campus/a-canary-in-the-coal-mine-nu-math-professors-share-optimism-resilience-as-they-adapt-to-growing-ai-research/},
  date = {2026-11-10},
  urldate = {2026-11-19}
}
@online{dartmouth2026phd,
  author = {{The Dartmouth}},
  title = {Guarini will not admit math Ph.D. cohort this year},
  url = {https://www.thedartmouth.com/article/2026/11/gandhi-fagell-guarini-will-not-admit-math-ph-d-cohort-this-year},
  date = {2026-11-12},
  urldate = {2026-11-19}
}
@online{ggth2026,
  author = {{GGTH}},
  title = {Géométrie des groupes humaine},
  url = {https://ggth.pages.math.cnrs.fr},
  date = {2026-10-31},
  urldate = {2026-11-19}
}
@online{magica2026ahm,
  author = {{Magica}},
  title = {Human Mathematics Association passes 1,000 members},
  url = {https://magica.com/news/human-mathematics-association-passes-1000-members-ai-commitments},
  date = {2026-10-20},
  urldate = {2026-11-19}
}
@online{newscientist2026ahm,
  author = {{New Scientist}},
  title = {A thousand human mathematicians pledge to shun AI in their research},
  url = {https://www.newscientist.com/article/2593621-a-thousand-human-mathematicians-pledge-to-shun-ai-in-their-research/},
  date = {2026-10},
  urldate = {2026-11-19},
  note = {Not read directly; exact date not confirmed}
}
@online{ahm2026guidelines,
  author = {{Association for Human Mathematics}},
  title = {Doctoral Advising Guidelines by the AHM},
  url = {https://terrytao.wordpress.com/2026/11/03/doctoral-advising-guidelines-by-the-ahm/},
  date = {2026-11-03},
  urldate = {2026-11-19}
}
@online{ahm2026statements,
  author = {{Association for Human Mathematics}},
  title = {Statements},
  url = {https://www.ahmath.org/statements},
  date = {2026-10-07},
  urldate = {2026-11-19}
}
@online{misanthropic2026,
  author = {{MisAnthropic Statement signatories}},
  title = {MisAnthropic Statement},
  url = {https://misanthropicstatement.com},
  date = {2026-11-19},
  urldate = {2026-11-19},
  note = {Via Proofs and Prompts; signatories not verified}
}
@online{calegari2026changed,
  author = {Calegari, Frank},
  title = {Mathematics has changed. Let's act like it},
  url = {https://terrytao.wordpress.com/2026/11/01/mathematics-has-changed-lets-act-like-it/},
  date = {2026-11-01},
  urldate = {2026-11-19}
}
@online{karthik2026egoless,
  author = {Karthik C. S. and Sahai, Amit and Xue, Jie},
  title = {Egoless Mathematics in the AI Era},
  url = {https://terrytao.wordpress.com/2026/11/02/egoless-mathematics-in-the-ai-era/},
  date = {2026-11-02},
  urldate = {2026-11-19}
}
@online{tao2026moreposts,
  author = {Tao, Terence},
  title = {More posts},
  url = {https://terrytao.wordpress.com/2026/11/06/more-posts/},
  date = {2026-11-06},
  urldate = {2026-11-19}
}
@online{tao2026blog,
  author = {Tao, Terence},
  title = {What's new (blog front page)},
  url = {https://terrytao.wordpress.com/},
  date = {2026-11-13},
  urldate = {2026-11-19}
}
@online{mathhelm2026,
  author = {Yuan, Xinyi and others},
  title = {Introducing MathHelm: a place to discuss AI-generated papers},
  url = {https://terrytao.wordpress.com/2026/11/13/introducing-mathhelm-a-place-to-discuss-ai-generated-papers/},
  date = {2026-11-13},
  urldate = {2026-11-19}
}
@online{cwt2026tao,
  author = {Cowen, Tyler},
  title = {Terence Tao (Conversations with Tyler)},
  url = {https://conversationswithtyler.com/episodes/terence-tao/},
  date = {2026-11-19},
  urldate = {2026-11-19}
}
@online{dcalegari2026claude,
  author = {Calegari, Danny},
  title = {Collaborating with Claude},
  url = {https://www.youtube.com/watch?v=jj7cEfnN09c},
  date = {2026-10-24},
  urldate = {2026-11-19}
}
@online{verge2026altman,
  author = {{The Verge}},
  title = {Altman on Cheeky Pint: AI and mathematics},
  url = {https://www.theverge.com/ai-artificial-intelligence/1023054/altman-cheeky-pint-ai-math-interview},
  date = {2026-10-31},
  urldate = {2026-11-19}
}
@online{erdos2026changes,
  author = {Bloom, Thomas},
  title = {Changes},
  organization = {erdosproblems.com},
  url = {https://www.erdosproblems.com/forum/thread/blog:9},
  date = {2026-10-06},
  urldate = {2026-11-19}
}
@online{erdos2026openai,
  author = {Bloom, Thomas},
  title = {Erdős problems in the OpenAI proofs},
  organization = {erdosproblems.com},
  url = {https://www.erdosproblems.com/forum/thread/blog:10},
  date = {2026-10-08},
  urldate = {2026-11-19}
}
@online{erdosdb2026stats,
  author = {{teorth/erdosproblems contributors}},
  title = {statistics\_history.csv},
  url = {https://github.com/teorth/erdosproblems/blob/main/data/statistics_history.csv},
  date = {2026-11-12},
  urldate = {2026-11-19}
}
@online{fc2026merged,
  author = {{Google DeepMind and contributors}},
  title = {Formal Conjectures: PRs merged 19 Oct -- 19 Nov 2026},
  url = {https://github.com/google-deepmind/formal-conjectures/pulls?q=is%3Apr+is%3Amerged+merged%3A2026-10-19..2026-11-19},
  date = {2026-11-19},
  urldate = {2026-11-19}
}
@online{fc2026pr7631,
  author = {{Paul-Lez}},
  title = {Formal Conjectures PR \#7631: Palomar proof linter},
  url = {https://github.com/google-deepmind/formal-conjectures/pull/7631},
  date = {2026-10-29},
  urldate = {2026-11-19}
}
@online{fc2026pr7788,
  author = {{veljjanoski}},
  title = {Formal Conjectures PR \#7788: Kelly's conjecture disproof},
  url = {https://github.com/google-deepmind/formal-conjectures/pull/7788},
  date = {2026-11-08},
  urldate = {2026-11-19}
}
@online{fc2026pr7571,
  author = {{hamsade-google}},
  title = {Formal Conjectures PR \#7571: WOWII Conjecture 19 solved},
  url = {https://github.com/google-deepmind/formal-conjectures/pull/7571},
  date = {2026-11-16},
  urldate = {2026-11-19}
}
@online{fc2026pr7998,
  author = {{Arth-Singh}},
  title = {Formal Conjectures PR \#7998: R(5,5) $\geq$ 43},
  url = {https://github.com/google-deepmind/formal-conjectures/pull/7998},
  date = {2026-11-14},
  urldate = {2026-11-19}
}
@online{fc2026pr8015,
  author = {{aryanamol10}},
  title = {Formal Conjectures PR \#8015: AI-audit misformalisation fixes},
  url = {https://github.com/google-deepmind/formal-conjectures/pull/8015},
  date = {2026-11-16},
  urldate = {2026-11-19}
}
@online{fc2026pr7638,
  author = {{AItoBit}},
  title = {Formal Conjectures PR \#7638: Erdős \#1202 proof link},
  url = {https://github.com/google-deepmind/formal-conjectures/pull/7638},
  date = {2026-10-27},
  urldate = {2026-11-19}
}
@online{ecoticias2026erdos,
  author = {{Ecoticias}},
  title = {A forum user asked an AI model about an Erdős problem that had been open for 60 years},
  url = {https://www.ecoticias.com/en/a-forum-user-asked-an-ai-model-about-an-erdos-problem-that-had-been-open-for-60-years-and-the-trick-hidden-in-its-proof-is-now-settling-other-puzzles-mathematicians-had-left-unsolved/53752/},
  date = {2026-11-08},
  urldate = {2026-11-19}
}
@online{etp2026pr1506,
  author = {{vlad902}},
  title = {Equational Theories PR \#1506: end-to-end proof certificate},
  url = {https://github.com/teorth/equational_theories/pull/1506},
  date = {2026-10-26},
  urldate = {2026-11-19}
}
@online{etp2026commits,
  author = {{Equational Theories Project}},
  title = {equational\_theories commit history},
  url = {https://github.com/teorth/equational_theories/commits/main},
  date = {2026-11-18},
  urldate = {2026-11-19}
}
@online{optprob2026commits,
  author = {{teorth/optimizationproblems contributors}},
  title = {optimizationproblems commit history},
  url = {https://github.com/teorth/optimizationproblems/commits/main},
  date = {2026-10-28},
  urldate = {2026-11-19}
}
@online{lean2026releases,
  author = {{Lean FRO}},
  title = {Lean 4 releases (v4.36.0)},
  url = {https://github.com/leanprover/lean4/releases},
  date = {2026-11-16},
  urldate = {2026-11-19}
}
@online{mathlib32026archived,
  author = {{leanprover-community}},
  title = {mathlib3 (archived)},
  url = {https://github.com/leanprover-community/mathlib3},
  date = {2026-11-06},
  urldate = {2026-11-19}
}
@online{demoura2026kernel,
  author = {de Moura, Leonardo},
  title = {Lean now ships with verified kernels},
  url = {https://leodemoura.github.io/blog/2026-10-15-lean-now-ships-with-verified-kernels/},
  date = {2026-10-15},
  urldate = {2026-11-19}
}
@online{letsdatascience2026eth,
  author = {{Let's Data Science}},
  title = {OpenAI and Anthropic claim AI models disproved the Exponential Time Hypothesis},
  url = {https://letsdatascience.com/news/openai-and-anthropic-claim-ai-models-disproved-exponential-t-f4369e39},
  date = {2026-10},
  urldate = {2026-11-19},
  note = {Exact date not confirmed}
}
@online{levelup2026eth,
  author = {{Level Up Coding}},
  title = {Two AI labs disproved the Exponential Time Hypothesis on the same day},
  url = {https://levelup.gitconnected.com/two-ai-labs-disproved-the-exponential-time-hypothesis-on-the-same-day-b0d2694f21b6},
  date = {2026-10},
  urldate = {2026-11-19},
  note = {Exact date not confirmed}
}
@online{medium2026blackhole,
  author = {{Write A Catalyst (Medium)}},
  title = {The most important line in Claude's black hole paper is not the result},
  url = {https://medium.com/write-a-catalyst/the-most-important-line-in-claudes-black-hole-paper-is-not-the-result-it-is-some-parts-59aacd4dff98},
  date = {2026-11},
  urldate = {2026-11-19},
  note = {Exact date not confirmed}
}
@online{tauceti2026,
  author = {{Tau Ceti project}},
  title = {Tau Ceti: an Anthropic grant for Tau Ceti},
  url = {https://taucetiproject.org/},
  date = {2026-10-30},
  urldate = {2026-11-19}
}
```
