# OpenAI follow-up actions on AI-generated maths results (19 Oct – 19 Nov 2026)

Research date: 19 Nov 2026. Labels: **[confirmed]** = primary source (repo, OpenAI/AGMAI page, arXiv record); **[reported]** = secondary source only; **[disputed]** = parties disagree. Lab-reported figures are OpenAI's own claims and are not independently verified.

Access note: openai.com returned HTTP 403 to automated fetches, so the 26 Oct OpenAI post itself could not be read directly. Its content below comes from press coverage, the repo's `history.md`, and AGMAI's statements. Re-check the post by hand before quoting it on slides.

## Q1. What does "Working with academic communities to build scientific understanding" announce, and how does it map to the IAS/AGMAI recommendations?

### Takeaway
On 26 Oct 2026 OpenAI posted three new claimed results: a refutation of the Exponential Time Hypothesis (ETH), Sogge local smoothing implying the Kakeya conjectures, and existence of interacting 4D QFTs including Yang–Mills and QCD. It also introduced a "shepherd" model, where invited experts lead groups that examine each result, and reportedly gave US$5m to the Simons Foundation. A day earlier, on 25 Oct, AGMAI had advised labs not to designate mathematicians in this way. On 26 Oct AGMAI publicly asked OpenAI to release the Yang–Mills outputs it was holding back.

### Cited Findings
- **Date and title [reported]:** The post at openai.com/index/building-scientific-understanding-with-academic-communities/ is titled "Working with academic communities to build scientific understanding" and dated 26 Oct 2026. — [Gizmodo, 26 Oct 2026](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956); [hybridai.in summary citing the OpenAI News listing](https://www.hybridai.in/article/57183-working-with-academic-communities-to-build-scientific-understanding); [TNW, 26 Oct 2026](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills). The OpenAI URL itself is [here](https://openai.com/index/building-scientific-understanding-with-academic-communities/) (not fetchable).
- **Three results [confirmed for the two maths/CS results, reported for physics]:**
  1. "The Exponential Time Hypothesis is False": a deterministic algorithm that counts satisfying assignments of fixed-width CNF formulas in subexponential time and polynomial space, so the 3-SAT case refutes ETH. Lean formalisation included (`SubexponentialSAT` Comparator challenge). — [openai/math history.md, 26 Oct 2026](https://github.com/openai/math/blob/main/history.md); [commit 42907c9, 26 Oct 2026](https://github.com/openai/math/commit/42907c9)
  2. "Local smoothing for the Euclidean wave equation": proves Sogge's local smoothing for waves in every dimension ≥2 and, OpenAI claims, also gives the Kakeya maximal and dimension conjectures and Stein's spherical restriction estimates throughout the interior of the conjectured range. Lean formalised (`LocalSmoothing` Comparator challenge). — [history.md](https://github.com/openai/math/blob/main/history.md)
  3. Existence proofs for interacting 4D QFTs with gauge fields and fermions, including QCD and "a unified completion of the Standard Model". — [Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956); [AGMAI, 26 Oct 2026](https://agmai.org/#request-immediate-release). Reportedly this covers existence only, not the Yang–Mills mass gap, so it would not meet the Millennium Prize criteria. — [datastudios.org (aggregator)](https://www.datastudios.org/post/openai-models-exponential-time-hypothesis-disproof-kakeya-yang-mills-proofs) [reported, low-quality source]
- **"Shepherd" release model [reported]:** OpenAI "reached out to external experts and asked them to act as shepherds, organizing groups to understand the new results". The post calls the manuscripts "raw research data" and says OpenAI does not "seek academic credit". It also acknowledges that choosing shepherds creates an information asymmetry. — [Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956); [Dan Roberts (OpenAI) on X](https://x.com/danintheory/status/2114833683949764882) (snippet only, page not fetchable)
- **Named groups [confirmed for ETH via the repo; reported for physics]:**
  - ETH: Russell Impagliazzo and Ramamohan Paturi (UCSD) and Ryan Williams (MIT) lead "an independent working group" that will "examine and explain the proof". The materials were made public immediately at the group's request. — [history.md](https://github.com/openai/math/blob/main/history.md)
  - The ETH reviewers reportedly say their role is not an endorsement. They also say they signed no NDAs and will not be paid, and that OpenAI agreed to release all raw data on the ETH result at their request. — [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills) [reported]
  - Physics: the group is led by David Gross, with Michael Douglas, Arthur Jaffe, Igor Klebanov and Nikita Nekrasov. It chose not to release the AI-produced material for now and will write up the work itself. — [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills); [Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956) [reported]
  - Kakeya/local smoothing: no shepherd group was named in the coverage found. — [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)
- **Funding [reported]:** US$5 million to the Simons Foundation for workshops, conferences and programmes for researchers building on AI-produced results. Sources disagree on whether this is new money or a previously announced commitment. — [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills); [search summaries of aiweekly / datastudios](https://aiweekly.co/alerts/openai-hands-eth-kakeya-yang-mills-proofs-to-reviewers). No other partners or amounts were found.
- **Model access [gap]:** None of the coverage reports any programme giving academics access to the unreleased model. TNW states it is "not stated". — [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)
- **Disclosure changes visible in the repo [confirmed]:** The 26 Oct commit changed the README from "an internal OpenAI model" to "an **unnamed** internal OpenAI model". It added "these manuscripts are best understood as a form of raw research data, rather than polished academic papers. We defer to the math community completely on matters of credit, precedence, and concurrent work." The README now also lists "abridged summaries of the model's reasoning" for 10 families and states "on average, each result used three hours of ChatGPT Pro thinking compute" across "approximately 4,000 problems". (The README diff confirms only the first two of these changes came in this commit; the reasoning-summary and compute text may predate it.) It names exceptions to the fixed procedure: the Riemann zero-free region work, where the Re(s) > 11/12 write-up was "human edited for readability", and the Hodge conjecture for CM abelian varieties. — [commit 42907c9 README diff](https://github.com/openai/math/commit/42907c9); [README](https://github.com/openai/math)
- **AGMAI reaction 1 (25 Oct, the day before the release) [confirmed]:** "Disadvantages of Designating Mathematicians for AI Output Releases" concludes the disadvantages outweigh the advantages: "we recommend that AI companies do not adopt this practice for future releases". It gives five reasons: delayed or unequal access, denied agency, biased selection, borrowed reputation, and "it is unnecessary". It stresses that this is not criticism of the mathematicians involved. — [AGMAI, 25 Oct 2026](https://agmai.org/#disadvantages-designating-mathematicians)
- **AGMAI reaction 2 (26 Oct) [confirmed]:** "Recommendation for Immediate Release of Yang–Mills AI Output" calls on OpenAI "to make public without delay the natural-language and Lean outputs behind its announced existence proofs for Yang–Mills theory, quantum chromodynamics, and a completion of the Standard Model". It argues that by OpenAI's own account the Lean formalisation is complete, so "there is no scientific reason for delaying the release any further". It expresses "great respect" for the scientists OpenAI asked to lead the work. — [AGMAI, 26 Oct 2026](https://agmai.org/#request-immediate-release)
- **No later AGMAI posts:** As of 19 Nov 2026, AGMAI's site lists nothing after 26 Oct. — [agmai.org](https://agmai.org/) [confirmed]
- **Earlier item, before the window and possibly missed [confirmed]:** On 6 Oct AGMAI said it had "discussed [its recommendations] with OpenAI" and found the talks "constructive", but that "it is ultimately up to the mathematical community to assess the extent to which our recommendations were followed". It also said "this release is the beginning, not the completion, of the process of human understanding". — [AGMAI, 6 Oct 2026](https://agmai.org/#openai-release). TechCrunch reported OpenAI followed some but not all steps. — [TechCrunch, 8 Oct 2026](https://techcrunch.com/2026/10/08/openais-math-solutions-arent-meeting-the-fields-standards-yet/) [reported]

#### What the AGMAI 29 Sep recommendations actually say
The "seven recommendations" framing does not match the primary text. The [29 Sep General Guidelines](https://agmai.org/general-sep29/) have three principles, two pathways (2.A for human-understood papers, 2.B for output nobody yet understands), five Step I release norms and three Step II funding items. AGMAI's own 25 Oct summary of pathway 2B lists six points ([source](https://agmai.org/#disadvantages-designating-mathematicians)). The mapping below uses the 2B items, which is what OpenAI's releases fall under. Principle P3 is included because it is the one most at stake.

| AGMAI item (paraphrased from primary text) | OpenAI action, 26 Oct release / repo | Assessment |
|---|---|---|
| P1: release significant results responsibly and ASAP | ETH and local smoothing released immediately; QFT/Yang–Mills outputs held back by the physics group | Partial. AGMAI publicly objected on 26 Oct |
| P2: labs releasing bulk output must ensure understanding follows, including by funding it | Shepherd groups plus a reported US$5m to the Simons Foundation | Broadly aligned on funding |
| P3: understanding should be organic and community-led, not lab-directed | Shepherds hand-picked by OpenAI | Conflicts with AGMAI's 25 Oct clarification |
| I.1: scour the literature, cite related ideas, rewrite proofs in conventional style | Repo says manuscripts are "raw research data, rather than polished academic papers" | Not met as stated; OpenAI frames output as raw |
| I.2: deposit in repositories not controlled by any AI lab, with persistent IDs and revision history; avoid using releases as marketing | Still OpenAI's own GitHub repo; README says "exploring community-hosted repositories". No arXiv or Zenodo deposit by OpenAI found | Not met (revision history is kept in history.md and git) |
| I.3: publish model name, prompts, summarised chain of thought, time and compute cost | Model now explicitly "unnamed"; abridged reasoning summaries for 10 families; average "three hours of ChatGPT Pro thinking compute" per result; no per-result prompts or cost found | Partial. Model name explicitly withheld |
| I.4: formalise where possible, state status if delayed | Both new maths/CS results formalised in Lean; CM Hodge formalisation added; comparator fixes | Largely met for the new results |
| I.5: document AI use; for bulk releases, report failed attempts and how problems were chosen | README gives ~4,000 problems posed and states the procedure; no list of failed attempts found | Partial |
| II.1–3: fund conferences, workshops/working groups, expository books; independent non-profits decide allocation | Reported US$5m to the Simons Foundation (an independent non-profit) for workshops and conferences | Appears aligned, but the terms are unverified |

### Inferences
- The shepherd model directly contradicts AGMAI's 25 Oct guidance. Since AGMAI says labs had been asking it about designated mathematicians, the timing suggests the 25 Oct note anticipated this release, though that is not confirmed.
- Routing funding through the Simons Foundation matches AGMAI's request that independent non-profits allocate the money. Holding back the physics outputs and keeping the model unnamed are the clearest departures.
- The "unnamed" wording in the README looks like a deliberate reply to AGMAI item I.3 (publish the model name), effectively a refusal.

### Gaps
- The full text of the OpenAI post could not be retrieved (HTTP 403). Exact wording on model access, funding terms and disclosure commitments is unconfirmed.
- No source shows whether the US$5m is new money or was previously announced, or what its governance terms are.
- No OpenAI response to AGMAI's 26 Oct call to release the Yang–Mills outputs was found, and no evidence that those outputs have since been released.
- The "seven recommendations" count in the brief could not be matched to AGMAI's text (see above).

## Q2. Changes to openai/math and openai/NavierStokesAndEuler since 19 Oct

### Takeaway
openai/math had two updates in the window: 26 Oct (two new formalised manuscripts, the CM Hodge Lean formalisation, comparator fixes) and 29 Oct (a CM Hodge comparator namespace fix). The README now says **721 manuscripts in 373 families**. There were no new withdrawals. openai/NavierStokesAndEuler has had no commits since 10 Sep 2026.

### Cited Findings
- **Commit history in the window [confirmed]:** It contains only 42907c9 (26 Oct 2026, "Update math/cs papers, formalizations, and verification data", merged as PR #3) and 204e5f8 (29 Oct 2026, "Align CM Hodge comparator declarations with the Lean solution", merged as PR #4 on 30 Oct). The last push was 30 Oct 2026, with no commits from 31 Oct to 19 Nov. — [openai/math commits](https://github.com/openai/math/commits/main) (via GitHub API)
- **26 Oct update [confirmed]:** It touched 300 files (278 added, 22 modified, about 3.95M lines added). Contents:
  - The ETH and local smoothing manuscripts.
  - "*The rational Hodge conjecture for CM abelian varieties*. A Lean formalization was added."
  - "Some Comparator configurations were fixed, and some Lean formalizations were improved."
  - For *The maximum number of mutually unbiased bases in dimension six*, "we restored the C++ source and saved numerical records", with a Python checker.
  — [history.md](https://github.com/openai/math/blob/main/history.md); [commit 42907c9](https://github.com/openai/math/commit/42907c9)
- **29 Oct fix [confirmed]:** "Diverging namespaces in the Comparator challenge and solution were adjusted" for CM Hodge (281 files modified). — [history.md](https://github.com/openai/math/blob/main/history.md); [commit 204e5f8](https://github.com/openai/math/commit/204e5f8)
- **Manuscript count [confirmed]:** The README went from "719 manuscripts organized into 372 families" to "721 manuscripts organized into 373 families" in the 26 Oct commit. The README still says "~42% top-line results formalized". The last explicit ratio in history.md is from 7 Oct: "300 / 719 = ~42%". No updated ratio has been published. — [commit 42907c9 README diff](https://github.com/openai/math/commit/42907c9)
- **No new withdrawals or revisions in the window [confirmed]:** The 7 Oct entry (3 withdrawn, 14 revised, 13 citation updates) is still the only withdrawal/revision entry in history.md. — [history.md](https://github.com/openai/math/blob/main/history.md)
- **Earlier item, possibly missed [confirmed]:** On 12 Oct 2026 OpenAI added automation to "Lock pull request conversations when opened" (PR #2). The repo shows no public issues. — [commit 2710f99](https://github.com/openai/math/commit/2710f99)
- **openai/NavierStokesAndEuler [confirmed]:** It has two commits in total (8 Sep and 10 Sep 2026, both with the message "."). The last push was 10 Sep 2026, with no issues or commits since 19 Oct. The `updated_at` metadata changed on 17 Nov, but that reflects stars or metadata, not code. — [repo](https://github.com/openai/NavierStokesAndEuler) (via GitHub API)

### Inferences
- The family count rose by one while the manuscript count rose by two. This suggests only one of the two new manuscripts opened a new family, possibly ETH, with local smoothing going into an existing harmonic-analysis family. This has not been verified against CONTENTS.md.
- The Navier–Stokes repo has not been corrected or updated despite published critiques of the Lean–natural-language correspondence (see Q4).

### Gaps
- No updated formalisation percentage after the 26 Oct additions was found.
- Per-manuscript changes inside the 22 modified files of 42907c9 were not itemised.

## Q3. Journal/arXiv submissions; release or naming of the model

### Takeaway
No journal or arXiv submission by OpenAI of any of these results was found. Third parties are posting expository arXiv versions of the Navier–Stokes proof. OpenAI's README now explicitly calls the model "unnamed", and no product release of it was found.

### Cited Findings
- **No OpenAI deposit [confirmed absence in repo; searches found none]:** The README still says OpenAI is "exploring community-hosted repositories for these materials". — [openai/math README](https://github.com/openai/math)
- **Third-party Navier–Stokes exposition [confirmed]:** Zhen Lei and Xiao Ren, arXiv:2609.35406, "Finite-Time Blowup for Navier-Stokes with Smooth Forcing, Part I: Construction of Self-Similar Solutions with Admissible Stress and Flat Remainder". It was posted as v1 on 28 Sep, v2 on 29 Sep, and **v3 on 18 Nov 2026** (in the window). The comment reads "We have reduced the length of the paper from 245 to 182 pages. We claim no original mathematical contribution." A companion Part II is arXiv:2611.06869 (November 2026; not fetched). — [arXiv:2609.35406](https://arxiv.org/abs/2609.35406)
- **Critique of the Lean formalisation [confirmed, just before the window]:** Bastounis, Circelli and Hansen, arXiv:2610.08144 (v1 6 Oct 2026), "Navier-Stokes lost in translation". It argues "the formalised Lean proof does not correspond to the NL proof of blow-up" because of AI mistranslation into Lean. — [arXiv:2610.08144](https://arxiv.org/abs/2610.08144). Gizmodo (26 Oct) likewise reports that readers found Lean verified a weaker assertion than the one OpenAI published. — [Gizmodo](https://gizmodo.com/openai-trumpets-3-more-math-and-science-results-along-with-a-new-plan-for-publishing-them-2000830956) [reported]
- **Model naming [confirmed]:** The README now reads "an unnamed internal OpenAI model" (changed 26 Oct). The 26 Oct coverage calls it "an internal OpenAI model". — [commit 42907c9](https://github.com/openai/math/commit/42907c9); [TNW](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills)
- **"GPT-6 Astra" [reported, unverified]:** One aggregator names "GPT-6 Astra" as the system that formalised the Navier–Stokes result in Lean in 17 hours, as distinct from the unnamed main model. A blog refers to a model "more capable than GPT-6 Astra". Neither is primary, and OpenAI confirmation was not found. — [Implicator (dated 8 Sep 2026)](https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/); [e-discoveryteam blog, 13 Nov 2026](https://e-discoveryteam.com/2026/11/13/evidence-ai-has-attained-superintelligence-in-one-field-mathematics-and-what-this-means-to-law-and-society-part-one-of-three/)
- **Anthropic parallel ETH claim [reported]:** Several outlets say Anthropic posted its own proof refuting ETH on the same day, listing Claude as author. Dates in the coverage vary (16, 17 or 26 Oct). — [letsdatascience](https://letsdatascience.com/news/openai-and-anthropic-claim-ai-models-disproved-exponential-t-f4369e39); [Level Up / gitconnected](https://levelup.gitconnected.com/two-ai-labs-disproved-the-exponential-time-hypothesis-on-the-same-day-b0d2694f21b6). This was not checked against Anthropic primary sources and is outside this brief's OpenAI scope; flag it for whoever covers other labs.

### Inferences
- Pathway 2A-style human write-ups are coming from third parties (Lei & Ren) and from shepherd groups (Gross et al. for physics), not from OpenAI as author. This matches OpenAI's stated "no academic credit" stance.

### Gaps
- No evidence was found of a journal submission, an arXiv post by OpenAI, or a public release, API or product name for the model.
- Authorship of arXiv:2611.06869 (Part II) was not verified.

## Q4. New statements on the Buckmaster/Alpöge priority dispute

### Takeaway
No new statements from Buckmaster, Alpöge, Bubeck or OpenAI dated 19 Oct – 19 Nov were found. The latest material is commentary, and the dispute remains unresolved.

### Cited Findings
- **Background, all before the window [disputed]:** Buckmaster says Sébastien Bubeck offered him lead authorship if Alpöge were removed, and that OpenAI's work followed his and Alpöge's progress. Bubeck denies asking for Alpöge's removal and apologised for a career remark as an "extremely poor choice of words". OpenAI says neither its researchers nor its agents saw the pair's work. Mark Chen: "that's also our understanding". OpenAI says it cannot rule out that de-identified product-use data improved its models. — [Implicator](https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/); [Scientific American](https://www.scientificamerican.com/article/the-inside-story-behind-openais-million-dollar-math-proof/) [reported]
- **Repo stance (26 Oct) [confirmed]:** The openai/math README added "We defer to the math community completely on matters of credit, precedence, and concurrent work". This is generic language, not specific to Navier–Stokes, and the NavierStokesAndEuler repo was not updated. — [commit 42907c9](https://github.com/openai/math/commit/42907c9)
- **Commentary in the window [reported, low authority]:** An e-discoveryteam blog post (13 Nov 2026) and a Varsity student-paper piece (18 Nov 2026) discuss the episode but contain no new statements from the parties found here. — [e-discoveryteam, 13 Nov](https://e-discoveryteam.com/2026/11/13/evidence-ai-has-attained-superintelligence-in-one-field-mathematics-and-what-this-means-to-law-and-society-part-one-of-three/); [The Varsity, 18 Nov](https://thevarsity.ca/2026/11/18/is-ai-replacing-mathematicians)
- **Clay Institute [reported, before the window]:** President Martin Bridson called the announcement "exciting" and said evaluation would be "deliberately unhurried". Navier–Stokes is still listed as unsolved. — [Implicator](https://www.implicator.ai/clay-institute-navier-stokes-openai-proof-claim/)

### Inferences
- OpenAI's generic "defer to the math community" line on credit reads as its de facto position on the dispute. No retraction or concession was found.

### Gaps
- None of the searches found a statement from Alpöge.
- None of the searches found a statement dated in the window from Buckmaster, Bubeck or OpenAI. X posts could not be fetched (HTTP 402), so posts made only on X may have been missed.
