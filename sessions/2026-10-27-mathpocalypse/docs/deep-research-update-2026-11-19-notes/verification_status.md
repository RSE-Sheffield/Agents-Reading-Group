# Independent verification status of OpenAI's headline AI-generated maths claims (19 Oct – 19 Nov 2026)

Labels: **[confirmed]** = verified from a primary source or the page itself; **[reported]** = secondary report I could not check against a primary source; **[disputed]** = sources disagree or the claim is contested. Items dated before 19 Oct are marked **(pre-window)**.

Method note: about 19 searches and fetches. Science.org and openai.com returned HTTP 403, so I could not read those pages directly. I did not search Lean Zulip, MathOverflow, Tao's blog (directly), Quanta or Nature for in-window items. Treat "nothing found" below as "nothing found by this search", not proof that nothing exists.

## Q1. Independent checks, refutations or endorsements of the Navier–Stokes proof since 19 Oct; does the forcing loophole matter for the Millennium Prize statement?

### Takeaway
I found no independent refutation or full endorsement of the Navier–Stokes proof in the window. The main in-window event is that King's College London publicised (27 Oct) the Bastounis–Circelli–Hansen translation-gap preprint. It shows a mismatch between the Lean statement and the English proof (Lemma 8.6), not an error in the maths. The forcing issue is a loophole *within* Clay's official framing, which permits a forcing term. So it does not by itself disqualify the result, but it makes the result much less physically meaningful than "Navier–Stokes solved" suggests.

### Cited Findings
- **[confirmed]** On 27 Oct 2026, KCL put out a news release, "OpenAI's Navier-Stokes proof called into question", on the arXiv preprint by Bastounis (KCL), Circelli and Hansen (Cambridge). Its points:
  - The Lean version "does not fully match" the written proof; in one example the written proof claims something stronger than the Lean statement.
  - The authors say they **have not shown the original proof is wrong**, and that the written proof still needs independent checking.
  - Using the Solvability Complexity Index hierarchy, they argue there are fundamental limits to automatic autoformalisation.
  - Bastounis is quoted: "verifying the correctness of the output of an AI remains exceptionally difficult."
  - The release says the preprint is not peer-reviewed and gives no OpenAI response. — [KCL news, 27 Oct 2026](https://www.kcl.ac.uk/news/openais-navier-stokes-proof-called-into-question); preprint [arXiv 2610.08144](https://arxiv.org/abs/2610.08144) (pre-window, posted ~6 Oct)
- **[reported]** A secondary summary says the preprint singles out Lemma 8.6 as the place where the translation diverges, and that the Lean code "watered down" some of the English claims. — [AI Weekly alert](https://aiweekly.co/alerts/paper-flags-gap-in-openais-lean-verified-navier-stokes-proof) (undated in search result)
- **[confirmed] (pre-window, 13 Oct)** Scientific American (Joseph Howlett) reports:
  - The proof exploits "the same loophole in the Clay Mathematics Institute's framing", namely constructing an unphysical force that "stirs" the fluid. Its resemblance to the Córdoba / Martínez-Zoroa programme is "superficial": "When you go to the details, it is a different approach" (Gonzalo Cao-Labora, EPFL).
  - On the priority dispute with Buckmaster and Alpöge, Camillo De Lellis (IAS) said: "I honestly don't see a factual resolution of this… not anymore a matter of clearly verifiable mathematical facts."
  - Several groups are using the Lean code and other LLMs to build simplified explanations, and "no one fully" understands the proof yet.
  - Buckmaster alleges OpenAI tried to bribe and threaten him (his allegation; OpenAI denies the model could have seen his data). — [Scientific American, 13 Oct 2026](https://www.scientificamerican.com/article/openais-blockbuster-navier-stokes-proof-isnt-what-we-thought-it-was/)
- **[reported] (pre-window)** OpenAI's claim covers only the *forced* problem. It does not claim unforced blow-up, and OpenAI says it will not claim the $1M prize. — [Clay statement coverage, implicator.ai](https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/); [arXiv 2610.08144 abstract/search summary](https://arxiv.org/abs/2610.08144)
- **[reported] (pre-window, 8 Sep)** Tao criticised AI companies on social media for using long-standing problems as "marketing proof points". He reportedly welcomed Stan Palasek's observation that viscous dissipation may counter the instabilities in the unforced case. — [Fortune, 8 Sep 2026](https://fortune.com/2026/09/08/openai-says-it-cracked-navier-stokes-math-grand-challenge-buckmaster-accusation-cheating-intimidation-tao-lament/). I did not find an in-window Tao blog post on the forcing loophole.
- **[confirmed] (pre-window)** Follow-up human papers on the forcing question exist, e.g. "Density of Forces Producing Navier–Stokes Blowup" ([arXiv 2609.10262](https://arxiv.org/pdf/2609.10262)) and "The Positive Defect Problem… Programmatic Search for Unforced Navier–Stokes Blowup" ([arXiv 2609.23868](https://arxiv.org/pdf/2609.23868)). Titles only; I did not read their conclusions.
- **[confirmed]** The `openai/NavierStokesAndEuler` GitHub repo showed **0 open issues** when fetched on 19 Nov 2026. The closed count was not visible. — [GitHub issues](https://github.com/openai/NavierStokesAndEuler/issues)

### Inferences
- Clay's official problem statement allows a forcing term, so the forcing loophole is a legitimate route *under the letter* of the statement (Scientific American calls it a loophole "in the Clay Mathematics Institute's framing"). The open dispute is about significance and physical meaning, not admissibility. This is my reading; no Clay ruling on this point was found.
- The translation-gap critique and the forcing critique are independent. The first is about whether the Lean check certifies the English theorem. The second is about whether the English theorem is the "interesting" one.

### Gaps
- No in-window independent human verification (full read-through or seminar verdict) of the 166-page Navier–Stokes paper was found.
- No OpenAI response to the Bastounis et al. preprint was found.
- Science's article "AI is shaking up math. But can its proofs be trusted?" ([science.org](https://www.science.org/content/article/ai-shaking-math-can-its-proofs-be-trusted)) returned 403, so I could not get its date or content. A search summary says it discusses Lean software bugs that could let invalid proofs through.

## Q2. Status of the UGC, L = BPL and other big openai/math claims

### Takeaway
UGC is the claim experts have checked most closely, and the signs are cautiously positive. Dana Moshkovitz studied it for weeks with Khot, Håstad and Minzer and gave a two-hour exposition at UT Austin on 4 Nov 2026. Still, nobody has issued a formal "verified" verdict, and the talk title itself is "Proved (!!?)". I found no expert confirmation or refutation of L = RL = BPL. The biggest new in-window claim is OpenAI's **ETH refutation** (paper dated 25 Oct). Lance Fortnow treats it as likely correct, and OpenAI has set up a formal verification partnership with Impagliazzo, Paturi and Williams. The only confirmed errors are the Hodge-type retractions of 7 Oct (pre-window).

### Cited Findings
**Unique Games Conjecture (Problem 102)**
- **[confirmed]** UT Austin event on 4 Nov 2026, "The Unique Games Conjecture – Proved (!!?)", by Dana Moshkovitz. She offers "my mental map" of OpenAI's writeup and Lean formalisation. The key innovation is a new code construction she calls "Hadamard with a noise test". The writeup is described as "not written in a way that's especially readable to human mathematicians." — [UT Austin AI event page](https://ai.utexas.edu/events/2026-11-04/unique-games-conjecture-proved)
- **[confirmed]** Scott Aaronson's *Shtetl-Optimized*, 30 Oct 2026:
  - He reports that Moshkovitz studied the proof "with Subhash Khot himself, Johan Håstad, Dor Minzer" and others, and that she "probably now understands this crown jewel of OpenAI's release as well as anyone does."
  - In comments he calls it "a totally alien new error-correcting code", with the rest "standard, well-understood techniques". He adds that the experts "all failed to come up with this code, although they're perfectly able to understand it once they see it."
  - He also writes: "Welcome to the Mathocalypse."
  - The post does not formally declare the proof verified. — [Shtetl-Optimized, 30 Oct 2026](https://scottaaronson.blog/?p=10232)
- **[reported] (pre-window)** Moshkovitz called the preprint "so horribly written that it's impossible to read it without AI help." Before the release, Minzer and students rushed out a related 2-to-1 games result. — [Quanta, 7 Oct 2026](https://www.quantamagazine.org/as-ai-closed-in-on-unique-games-proof-researchers-raced-to-beat-the-machines-20261007/); [Technology.org, 14 Oct 2026](https://www.technology.org/2026/10/14/openai-372-math-results-what-is-verified/)
- **[disputed] (pre-window)** Scientific American calls the UGC solution "a bit controversial" ([SciAm, 8 Oct 2026](https://www.scientificamerican.com/article/the-most-exciting-claims-from-openais-heap-of-new-proofs/)). An anonymous commenter on the Computational Complexity blog says they "100% agree UGC holds up" ([Fortnow, 7 Oct 2026](https://blog.computationalcomplexity.org/2026/10/open-no-more.html)).

**L = RL = BPL (Problem 103)**
- **[confirmed]** The OpenAI preprint "Exact Derandomization of Logarithmic Space: L = RL = BPL" (dated 23 Sep 2026) is in openai/math. The repo's Lean doc says the formalisation covers the equality for binary languages in an explicit log-workspace Turing-machine model. — [openai/math lean/docs/103.md](https://github.com/openai/math/blob/main/lean/docs/103.md)
- **[disputed] (pre-window)** Fortnow's 7 Oct post lists L = RL = BPL without noting formal verification. An anonymous commenter claims it "is not lean verified" and that their "instinct is it is incorrect". This conflicts with the repo's Lean doc above, so the commenter may be mistaken or referring to a different scope. Ran Raz (Princeton) told SciAm the field expected L = RL but "saw no promising approaches" to a proof, and gave no verdict. — [Fortnow, 7 Oct](https://blog.computationalcomplexity.org/2026/10/open-no-more.html); [SciAm, 8 Oct](https://www.scientificamerican.com/article/the-most-exciting-claims-from-openais-heap-of-new-proofs/)
- **[confirmed]** On 28 Oct 2026, cslib-community/complexitylib issue #1444 originally planned to formalise "BPL ⊆ L via the OpenAI preprint route". It was then reframed to drop that route. The issue says dropping it "is not a claim that its endpoint was proved or disproved", and that RL = L "remains open" for the library's purposes. No errors in OpenAI's proof are reported. — [GitHub issue #1444](https://github.com/cslib-community/complexitylib/issues/1444)

**Exponential Time Hypothesis refutation (new, in window)**
- **[confirmed]** On 28 Oct 2026, Lance Fortnow reported OpenAI's announced proof that ETH (and hence SETH) is false. The paper is "The-Exponential-Time-Hypothesis-is-False" in openai/math, dated 25 Oct 2026; the Lean doc is lean/docs/378.md.
  - Claimed bound: k-SAT in (n+m)^O(1)·2^(O(n log log n/√log n)). The Lean proof gives a slightly weaker bound.
  - Fortnow: "I have not verified the proof myself, but it is safe to assume now that the exponential-time hypothesis is toast."
  - OpenAI is partnering with **Russell Impagliazzo, Mohan Paturi and Ryan Williams to verify and study the proof**. Update (29 Oct): they set up a discussion site and blog.
  - Ryan O'Donnell and Shiva Kintali have posted simpler follow-up proofs, and Anthropic released its own paper.
  - Commenters dispute some of Fortnow's framing (the "galactic" algorithm; whether 2^(n^ε) for 3-SAT implies subexponential time for NP) and question the choice of partners. — [Computational Complexity, 28 Oct 2026](https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html)
- **[confirmed]** Strassle and Subercaseaux posted a follow-up generalising the transfer to nondeterministic time. — [arXiv 2611.11832](https://arxiv.org/abs/2611.11832v1)
- **[reported]** The OpenAI announcement page, "Building scientific understanding with academic communities", returned 403 to me, so its date and details are unverified. — [openai.com](https://openai.com/index/building-scientific-understanding-with-academic-communities/)

**Riemann, Hodge and others**
- **[reported] (pre-window, 7 Oct)** OpenAI withdrew three Hodge-type manuscripts (abelian eightfolds / K3 surfaces) after a sign error (+1 vs −1) broke a cancellation argument. OpenAI said the retraction applies to the proofs, not the propositions, and did not say who found the error. Fourteen more manuscripts were revised within a day. The family was renamed "The Rational Hodge Conjecture for CM Abelian Varieties". — [KuCoin news flash](https://www.kucoin.com/news/flash/openai-retracts-3-ai-math-papers-due-to-sign-error-in-key-proof); [Technology.org, 14 Oct](https://www.technology.org/2026/10/14/openai-372-math-results-what-is-verified/); [Wikipedia](https://en.wikipedia.org/wiki/OpenAI_bulk_release_of_mathematical_papers). These are secondary sources; the openai/math changelog should be checked.
- **[confirmed] (pre-window)** On the Riemann-related claims, Héctor Pasten said of the quasi-RH result: "Some people claim it is progress toward Riemann; other people say it's not." On Siegel zeros: "This is not just progress on Siegel zeros—it settles the question." Roland Bauerschmidt on Baby Yang–Mills: the first paper "seems very reasonable" but is not fully digested, and the second is "horrible". SciAm reports retractions after outside scientists found mistakes. — [SciAm, 8 Oct 2026](https://www.scientificamerican.com/article/the-most-exciting-claims-from-openais-heap-of-new-proofs/)
- **[confirmed]** Gil Kalai blogged on one paper from the release (claiming f(9) > 10), noting that "the proof needs to be carefully checked". — [Combinatorics and more](https://gilkalai.wordpress.com/) (exact post date not confirmed)

### Inferences
- The verification model is changing: for complexity theory, OpenAI now runs named, invited verification partnerships (ETH), while for UGC, independent experts are doing their own exposition-based checking.
- "Lean-formalised" status varies by claim (UGC and matrix multiplication yes per Fortnow; L = BPL disputed in comments, though the repo has a Lean doc). The translation-gap concern (Q5) applies to all of them.

### Gaps
- No in-window expert confirmation or refutation of L = BPL was found.
- No public verdict from the Impagliazzo/Paturi/Williams ETH review was found; the discussion-site URL was not retrieved.
- I did not find any in-window new retractions or errata for openai/math, and I did not check the repo's history file directly.
- Recording or slides of the 4 Nov Moshkovitz talk were not found.

## Q3. New Clay Mathematics Institute statement or review process

### Takeaway
I found no new CMI statement in the window. Clay's news page shows only the 11 Sep 2026 "Navier-Stokes Announcement" and nothing from October or November.

### Cited Findings
- **[confirmed]** On fetching claymath.org/news (19 Nov 2026), the only Sep–Nov 2026 item was "Navier-Stokes Announcement", 11 Sep 2026. Nothing from Oct or Nov appeared. — [Clay news](https://www.claymath.org/news/)
- **[reported] (pre-window)** In the 11 Sep statement, CMI president Martin Bridson called evaluation "deliberately unhurried" and "absolutely rigorous". Standard rules apply: publication in a qualifying outlet, a two-year wait, and general acceptance. The problem is still listed as unsolved. — [implicator.ai](https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/); [Seoul Inside Substack, 12 Sep](https://seoulinside.substack.com/p/did-openai-just-solve-navierstokes)
- **[disputed]** One secondary source says CMI described the problem as having "apparently been settled". Others emphasise that CMI has not accepted it. — same sources as above; I could not read the primary statement text.

### Inferences
- Under Clay's two-year rule, no prize decision can come before about late 2028 even if the result were published now. OpenAI's stated intention not to claim the prize makes the process moot in practice.

### Gaps
- I could not retrieve the full text of the 11 Sep CMI statement, and I found no evidence of a CMI review committee or process.

## Q4. Expert reviews, workshops, seminars or reading groups dedicated to checking the results

### Takeaway
I found two clear in-window verification activities: Moshkovitz's UGC talk (UT Austin, 4 Nov) and the ETH verification partnership (Impagliazzo, Paturi, Williams) with its discussion site (from 29 Oct). There are also informal community efforts, such as the complexitylib formalisation attempt and groups building simplified explanations of the Navier–Stokes proof.

### Cited Findings
- **[confirmed]** UT Austin talk, 4 Nov 2026, Dana Moshkovitz, GDC 6.302, two hours. — [UT Austin](https://ai.utexas.edu/events/2026-11-04/unique-games-conjecture-proved); [Shtetl-Optimized, 30 Oct](https://scottaaronson.blog/?p=10232)
- **[confirmed]** ETH verification partnership and discussion site/blog set up by Impagliazzo, Paturi and Williams (update dated 29 Oct). — [Computational Complexity, 28 Oct](https://blog.computationalcomplexity.org/2026/10/the-exponential-time-refutation.html)
- **[confirmed]** complexitylib issue #1444 (28 Oct): community Lean-library planning that started with the OpenAI L = BPL route and then dropped it. — [GitHub](https://github.com/cslib-community/complexitylib/issues/1444)
- **[confirmed] (pre-window)** "Several groups" are using the Navier–Stokes Lean code and paper with LLMs to build simplified explanations. — [SciAm, 13 Oct](https://www.scientificamerican.com/article/openais-blockbuster-navier-stokes-proof-isnt-what-we-thought-it-was/)

### Gaps
- I found no dedicated Navier–Stokes verification workshop or reading group in the window.
- I did not search department seminar listings beyond UT Austin, or Lean Zulip and MathOverflow threads.

## Q5. New papers on the translation gap, autoformalisation fidelity or the Comparator tool

### Takeaway
The Bastounis–Circelli–Hansen preprint (arXiv 2610.08144, ~6 Oct) remains the key translation-gap paper, and it drew media coverage in the window via KCL on 27 Oct. Searches found no in-window paper specifically about OpenAI's Comparator tool. Fidelity work continues, e.g. updates to the "Evaluating the Robustness of Proof Autoformalization in Lean 4" code.

### Cited Findings
- **[confirmed]** arXiv 2610.08144, "Navier–Stokes lost in translation: Why Lean verification of AI autoformalisation does not guarantee correct natural language proofs". Publicised by KCL on 27 Oct. — [arXiv](https://arxiv.org/abs/2610.08144); [KCL](https://www.kcl.ac.uk/news/openais-navier-stokes-proof-called-into-question)
- **[reported]** "Evaluating the Robustness of Proof Autoformalization in Lean 4" (arXiv 2606.14867, pre-window). It tests faithfulness under perturbation, e.g. whether a model "reverts" by proving a deleted step instead of leaving it as a gap. Its code repo was reportedly updated in Oct 2026 for a revised paper. — [arXiv 2606.14867](https://arxiv.org/html/2606.14867); [GitHub](https://github.com/ucr-rai/robust-proof-autoformalization)
- **[reported]** Other possibly relevant preprints appeared in search results; I did not read them or verify their dates: "Sage: Formalization with Semantic Correction" ([arXiv 2609.35790](https://arxiv.org/pdf/2609.35790)), "Lean Pool: An AI-Maintained Archive of Formalized Mathematics" ([arXiv 2609.25199](https://arxiv.org/pdf/2609.25199)), "AI Agent Swarms as Researchers" ([arXiv 2609.35719](https://arxiv.org/pdf/2609.35719)).
- **[reported]** The Science article reportedly raises the risk that Lean kernel or software bugs let invalid proofs through. — [Science](https://www.science.org/content/article/ai-shaking-math-can-its-proofs-be-trusted) (403; date unknown)

### Inferences
- The 7 Oct L = BPL commenter dispute and the Lemma 8.6 mismatch both suggest that "Lean-verified" claims need a per-claim audit of the formal *statement*, not just the kernel check. That is exactly what the translation-gap paper argues.

### Gaps
- I found no papers or blog posts specifically evaluating the Comparator tool.
- I did not check arXiv listings systematically for 19 Oct – 19 Nov autoformalisation papers.
