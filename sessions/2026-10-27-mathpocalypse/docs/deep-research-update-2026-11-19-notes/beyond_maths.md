# Beyond maths: "agent swarm plus verifier" claims in physics, CS theory, software verification and other sciences (19 Oct – 19 Nov 2026)

Method note: about 18 searches and fetches, run on 19 Nov 2026. I read primary pages for Anthropic, PSI, DeepMind and the arXiv/NeurIPS items. Some figures come from secondary pages only, and those are labelled. Status labels: **confirmed** = stated on the claimant's own primary page or paper (that confirms the *claim was made*, not that it is correct); **reported** = secondary coverage only; **disputed** = sources conflict or were critical.

## Q1. Comparable claims in theoretical physics, CS theory, software verification and the lab sciences

### Takeaway
The window has three close analogues of the maths model. All three use a cheap checker, and in every case that checker is Lean: Anthropic's black-hole/bootstrap physics results (17 Nov), PSI's Lean-checked proof of the Aaronson–Ambainis conjecture in quantum complexity (6 Nov), and DeepMind's AlphaProof Code, which produced more than 6M lines of Lean verifying Signal's compiled crypto code (10 Nov). In biology the "swarm" part transfers (OpenAI ran about 2,000 GPT-Rosalind agents, 21 Oct), but the verifier does not: the outputs are hypotheses that still need wet-lab validation.

### Cited Findings

**Theoretical physics: Anthropic, "Claude Fable 5.2 solves two open problems in the physics of black holes" (17 Nov 2026), confirmed as a claim**
- In August, Anthropic researcher Hongbin Chen asked Claude to list open problems in black-hole physics and the bootstrap method. Claude proposed 22. Separate agents worked on each one in the background for about six weeks. Two were reported solved. — [Anthropic](https://www.anthropic.com/research/claude-black-hole-physics)
- Result 1 is the Hawking–Page transition in N=4 super Yang–Mills at weak coupling. It completes a three-loop calculation proposed in 2003 and finds the gas→black-hole transition is abrupt. Checks: nearly every piece was computed twice by independent agents and cross-checked against the literature. An independent physicist who had used Claude separately reached the same result by a different method. The post does **not** say Lean was used for this result. Preprint: hexagonmath.org/2611.00175v1. — [Anthropic](https://www.anthropic.com/research/claude-black-hole-physics)
- Result 2 is the modular bootstrap for 3D gravity. It gives an exact ceiling M₁ ≤ c/Λ with Λ≈9.1266, proved optimal for the simplest version of the method (the previous proven bound was c/8.5). Half the proof follows the strategy of an OpenAI sphere-packing proof. An earlier agent failed in 61 parallel attempts, and then two agents independently reached the answer. The result was **formally verified in Lean in September**, Claude wrote the paper with minimal guidance, and a physicist checked every main result. Preprint: hexagonmath.org/2611.00174v1. — [Anthropic](https://www.anthropic.com/research/claude-black-hole-physics)
- Anthropic's own caveats: neither result describes our universe. The Hawking–Page result covers N=4 SYM, not real gravity. The bootstrap bound does not reach c/12. — [Anthropic](https://www.anthropic.com/research/claude-black-hole-physics)
- An official Claude post on X summarises the first result as "a laborious calculation that had gone unsolved for 23 years." — [Claude on X](https://x.com/claudeai/status/2119899484373369278)
- Reception, **disputed/critical**: Gizmodo says the black-hole (and Fermat's Last Theorem formalization) results "have yet to undergo independent peer review" and quotes no independent physicists. The article is dated 9 Nov, before the 17 Nov research post, so it probably covers the model launch. I could not resolve the date discrepancy. — [Gizmodo](https://gizmodo.com/anthropics-says-its-new-ai-model-can-solve-black-hole-mysteries-what-could-go-wrong-2000837274)
- A Medium opinion piece says the Hawking–Page paper (posted 7 Nov 2026) has no human author and is labelled "Primarily AI-generated." **Reported**, not checked against the preprint. — [Medium](https://medium.com/write-a-catalyst/the-most-important-line-in-claudes-black-hole-paper-is-not-the-result-it-is-some-parts-59aacd4dff98)
- I found no independent expert technical assessment of either physics result in the window.

**Quantum complexity / theoretical CS: PSI proof of the Aaronson–Ambainis conjecture (6 Nov 2026), confirmed as a claim; Lean-checked; not yet peer-reviewed**
- Physical Superintelligence (PSI), a startup that calls itself an "AI-native physics lab", says its internal research system, running "instances of a non-public Anthropic model", proved the Aaronson–Ambainis conjecture (posed around 2008). The result means quantum computers are at most polynomially faster than classical ones on random inputs. The main lemma: a non-constant bounded polynomial has a variable with influence at least c·v^(5/2)/d^6, with c≈0.0025. — [PSI](https://psi.inc/research/aaronson-ambainis/)
- The system had a complete proof on day three, with exponent 22, and Lean accepted it. Further runs improved the exponent, and Lean accepted the final version too. Agent count and compute are **not disclosed**. — [PSI](https://psi.inc/research/aaronson-ambainis/); exponent figures via [Kashani, Substack, 7 Nov](https://qelvin.substack.com/p/an-ai-proved-a-quantum-conjecture)
- Humans involved: David Turturean ran the system and takes responsibility for correctness, Jim Halverson audited the proof, and Phiala Shanahan commented on the Lean formalization. The Stanford group of Blanc, Docter, Strassle and Tan, who proved a special case in Aug 2026, read the proof, called it "a huge result", and are writing an expository version. — [PSI](https://psi.inc/research/aaronson-ambainis/); code and Lean at [GitHub](https://github.com/physical-superintelligence/aaronson-ambainis)
- As of 7 Nov there was no comment from Aaronson or Ambainis and no peer review (**reported**). — [Quantum Insider, 6 Nov](https://thequantuminsider.com/2026/11/06/ai-assisted-proof-settles-longstanding-question-about-quantum-speedups/); [Kashani Substack](https://qelvin.substack.com/p/an-ai-proved-a-quantum-conjecture)

**Software / formal verification: DeepMind "AlphaProof Code" (10 Nov 2026), confirmed as a claim**
- A multi-LLM framework verified the *compiled code* behind Signal's cryptographic protocol, proving security properties including protection before and after a temporary device compromise. Agents powered by "Gemini Carbon" wrote the proofs and Lean checked them. Output was "over six million lines of Lean" in four weeks. — [Google DeepMind blog (Kohli, Chaudhuri)](https://deepmind.google/blog/introducing-alphaproof-code/)
- Split of work: human experts chose what to prove and reviewed every specification. Agents audited the proofs and flagged about 1% of the codebase for human review. As validation, the team reintroduced two previously fixed bugs, and the system produced machine-checked proofs that those versions were insecure. Signal's CTO Ehren Kret is quoted. The artifacts are being open-sourced. — [DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/)
- **Disputed figure**: a search summary of the same page gave "over three million" lines in one place and six million in another. When I fetched the page I saw only "six million". Hedge the number. — [DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/)
- I found no independent review in the window. Correctness depends on the human-reviewed specs (DeepMind's own caveat: scaling "requires continued research"). — [DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/)
- Context from before the window (labelled): the vericoding benchmark gave off-the-shelf LLM success of 27% for Lean, 44% for Verus and 82% for Dafny ([arXiv 2509.22908](https://arxiv.org/pdf/2509.22908), 2025; [POPL/Dafny 2026](https://popl26.sigplan.org/details/dafny-2026-papers/13/A-benchmark-for-vericoding-formally-verified-program-synthesis)). The Vero repository-scale Lean benchmark (43 instances) shows agents still struggle at repository scale ([arXiv 2608.13522](https://arxiv.org/abs/2608.13522v1), Aug 2026). lf-lean reports 97% (1,237/1,276) automatic Rocq→Lean translation of *Logical Foundations* theorem statements ([theorem.dev](https://theorem.dev/blog/lf-lean/), date not confirmed).

**Biology: OpenAI / PerturbAI / Scripps distributed GPT-Rosalind agents (21 Oct 2026), confirmed as a claim; swarm without a formal verifier**
- "Thousands" of GPT-Rosalind agents (about 2,000 per secondary reports, one per gene perturbation) analyzed an existing mouse-brain CRISPR atlas of millions of cells (about 8M per secondary reports) in 32 minutes. The distributed run cited more than 700 references, against 11 for a single agent, and blinded experts preferred the distributed reports 75% of the time. — [OpenAI](https://openai.com/index/scaling-ai-research-for-complex-biological-data/); counts **reported** by [AI Weekly](https://aiweekly.co/alerts/openai-perturbai-and-scripps-run-2000-gpt-rosalind-agents-on-8m-cell-brain) and [YourStory](https://yourstory.com/ai-story/ai-biology-openai-agents-complex-data)
- The outputs are hypotheses, such as a Tsc1/Tsc2 difference and DCTN1 linked to cholesterol-synthesis genes, and still await experimental validation. The bioRxiv preprint (16 Oct) is not peer-reviewed, and the authors include OpenAI staff and PerturbAI co-founders. — **reported** via [Crypto Briefing](https://cryptobriefing.com/openai-ai-agents-brain-crispr-atlas/), [AI Weekly](https://aiweekly.co/alerts/openai-perturbai-and-scripps-run-2000-gpt-rosalind-agents-on-8m-cell-brain)

**Automated labs (chemistry, biology, materials): closed-loop "physical verifier" items**
- Google Research (around 16 Oct, just before the window) describes AI agents in a closed robotic wet-lab loop reaching single-digit-nanomolar binders (DNA aptamers) for cancer targets. — [Google Research](https://research.google/blog/grounding-ai-agents-in-biological-reality-building-blocks-for-autonomous-wet-labs/)
- Danaher announced an AI-powered autonomous lab for antibodies and molecular tools (7 Oct, before the window). — [Danaher](https://investors.danaher.com/2026-10-07-Danaher-Accelerates-Life-Sciences-Research-with-New-AI-powered-Autonomous-Lab)
- An AI-guided robotic lab searched for heat-resistant thermal barrier coatings (Oct 2026, exact date unconfirmed). — [phys.org](https://phys.org/news/2026-10-ai-powered-robotic-laboratory-paves.html)
- The Chalmers robot scientist "Eve" was upgraded with LLMs for closed-loop yeast hypothesis testing (J. R. Soc. Interface; about 2 Oct, **reported**). — [Innovation News Network](https://www.innovationnewsnetwork.com/ai-scientist-autonomously-generates-and-validates-new-biological-discoveries/74434/)
- Google DeepMind's Co-Scientist: I found no new November 2026 claim. The latest coverage I found was from May 2026. — [SingularityHub](https://singularityhub.com/2026/05/21/ai-lab-partners-are-rewiring-the-hunt-for-new-drugs/)

**Counter-evidence: benchmarks of autonomous physics research in the window**
- FrontierPhysics (arXiv:2611.06910, about 4 Nov): 42 physicists from 26 institutions built 56 end-to-end research tasks, 21 of them unpublished. Every agent passed fewer than 30% of attempts. The best was Claude Opus 5.5, with 46/168 = 27.4%. The authors attribute failures to insufficient rigor and expert intuition, not coding. Grading combined deterministic numeric verifiers with author-written rubrics. **Reported** via [Kashani Substack](https://qelvin.substack.com/p/an-ai-proved-a-quantum-conjecture); the arXiv page ([2611.06910](https://arxiv.org/abs/2611.06910)) was not fetched.
- TheoPhysEval (arXiv 2610.16733, revised 12 Nov) reports about 98% accuracy for GPT-6-Astra+Codex on *verifiable* calculation problems in its realistic track. That covers calculations, not open research. **Reported** from a search summary only. — [arXiv 2610.16733](https://arxiv.org/abs/2610.16733)
- Evidence-supported physics-research agent evaluation (arXiv 2610.21767, late Oct): title only, content not read. — [arXiv](https://arxiv.org/pdf/2610.21767)

### Inferences
- Every "breakthrough" outside pure maths in this window that comes with a strong correctness claim is one that could be *turned into maths* and checked in Lean: the bootstrap bound, the Boolean-function inequality behind Aaronson–Ambainis, and crypto-code security properties. The physics result *without* Lean (Hawking–Page) relies on redundant agents plus human cross-checks. That is a weaker, "statistical" verifier.
- Software verification is the field where "an agent generates, a cheap checker decides" transfers most cleanly. The bottleneck moves to the specifications, which humans still review.
- Biology and the labs show the swarm without the cheap checker. The "checker" there is either expert preference (OpenAI's 75%) or slow, expensive physical experiment.
- Two Anthropic-model results came in two weeks (PSI's uses a non-public Anthropic model), so the trend is not OpenAI-specific.

### Gaps
- The hexagonmath.org preprints (2611.00174/5) were not read directly. I could not confirm the scope of the Lean formalization or what exactly was formalized (for example, whether numerical inputs were trusted).
- I found no independent physicist assessments of the Anthropic results, and no Aaronson/Ambainis statement on PSI.
- The AlphaProof Code technical paper and independent security-community reaction were not found.
- Agent counts for PSI and DeepMind are not disclosed.
- No comparable large-scale claim in chemistry or materials *theory* (e.g. DFT-verified discovery swarms) was found in the window. Nothing was found for amplitudes/QFT specifically beyond the N=4 SYM result.

## Q2. Who made the claims, which verifier, and how they were received (summary table)

### Takeaway
Labs or lab-backed startups made all the major claims. Each was announced on its own blog with preprints on non-journal hosts or arXiv/bioRxiv, and none had independent peer review within the window. Positive outside endorsement exists only for PSI, from the Stanford special-case authors.

### Cited Findings
| Date | Claimant | Field | Verifier | Reception / status |
|---|---|---|---|---|
| 21 Oct | OpenAI + PerturbAI + Scripps | Neurogenomics (hypotheses) | None formal; blinded expert preference, wet-lab pending | Preprint, not peer-reviewed ([OpenAI](https://openai.com/index/scaling-ai-research-for-complex-biological-data/)) |
| 6 Nov | PSI (Anthropic model) | Quantum query complexity | Lean + human audit | Stanford experts positive; no peer review ([PSI](https://psi.inc/research/aaronson-ambainis/)) |
| 10 Nov | Google DeepMind + Signal | Software / crypto verification | Lean; human-reviewed specs | Signal CTO quoted; no independent review ([DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/)) |
| 17 Nov | Anthropic | Theoretical physics (black holes) | Lean for bootstrap result; duplicate agents + physicist for Hawking–Page | Critical press, no independent experts quoted ([Anthropic](https://www.anthropic.com/research/claude-black-hole-physics); [Gizmodo](https://gizmodo.com/anthropics-says-its-new-ai-model-can-solve-black-hole-mysteries-what-could-go-wrong-2000837274)) |

### Inferences
- The pattern of announcing on a corporate blog, hosting the preprint yourself and having little independent review matches OpenAI's maths bulk release. The same credit and accountability debates are likely to follow.

### Gaps
- Peer-review timelines and journal submissions are unknown for all four.

## Q3. Debate: does "generator + cheap checker" transfer to fields without a formal verifier?

### Takeaway
The live debate says it transfers only as far as a field can be formalized or has a trusted cheap simulator or checker. Where that is missing, verification, not generation, becomes the bottleneck. Even Lean has a residual risk: a formally valid proof can still rest on definitions that do not match the intended physics, and the checker itself can be gamed.

### Cited Findings
- Krippendorf, Sarra and Tooby-Smith, "The Future of AI-assisted Physics: Discovering, Verifying and Organizing Results via Formalization" (arXiv 2610.14059, submitted 6 Oct 2026, **just before the window, labelled**). They argue formalization is the core trust layer for AI physics, and that community libraries such as Physlib should anchor it. AI is better at writing proofs than at choosing definitions. The key physics-specific gap: "a verified proof does not guarantee its definitions match the intended physics." — [arXiv](https://arxiv.org/abs/2610.14059)
- The NeurIPS 2026 workshop "Verification in the Age of AI Scientists" (Sydney, around 11–12 Dec; organizers Zitnik, Donti, Du, Fang, Bhagavathula, Rivera, Dupont) frames the issue directly: "The bottleneck for AI for Science is no longer hypothesis generation, it is verification." It adds: "In most sciences the verifier itself is imperfect or prohibitively expensive", and "force fields fail outside their training distribution." It contrasts Lean in maths with climate science. — [Workshop site](https://ai4sciencecommunity.github.io/neurips26)
- Terence Tao's views page says that "in mathematics, almost uniquely, you can automatically check the output." It notes AlphaEvolve-style verifiers are "primarily human-coded and not subject to hallucinations". It also records an August 2026 Lean flaw, found by a model, that could certify any statement. Tao's Economist op-ed "Performance is outpacing understanding and safety in AI" (18 Nov 2026) warns that trusted verification tools might be gamed by capable AI. I did not read the op-ed text itself. — [Tao AI views](https://teorth.github.io/tao-web/ai-views.html); [The Economist](https://www.economist.com/the-world-ahead/2026/11/18/performance-is-outpacing-understanding-and-safety-in-ai-says-terence-tao)
- FrontierPhysics authors say agents fail end-to-end physics research mainly through lack of rigor and expert intuition, which is the part no cheap checker supplies (**reported**). — [Kashani Substack](https://qelvin.substack.com/p/an-ai-proved-a-quantum-conjecture)
- Blog and commentary pieces (dates not individually confirmed, probably late Oct to Nov) argue that experimental claims need wet-lab replication rather than logical review ([MindStudio, "AI Just Published 722 Math Proofs. Who Checks Them?"](https://www.mindstudio.ai/blog/ai-verification-crisis-in-science)), and that the generate-and-verify pattern extends to domains with external physical or simulator verifiers such as materials and protein structure ([Computist Journal](https://blog.apiad.net/p/ai-is-doing-something-weird-to-science)). See also [Kyle Saunders, "OpenAI Posted 722 Math Papers in a Day. Who Answers for Them? (Part 2)"](https://kylesaunders.substack.com/p/openai-posted-722-math-papers-in) on accountability. These are commentary, not research.
- Pre-window context (labelled): ulam.ai (Feb 2026) proposes "domain adapters that translate scientific artifacts into Lean layers" as the route from maths to science. — [ulam.ai PDF](https://www.ulam.ai/research/lean-science.pdf)

### Inferences
- There is a spectrum of verifiers. Lean (cheap, near-perfect, but the definitions and specs must be right) comes first. Next is redundant independent agents plus expert spot-checks (the Hawking–Page result). Then come simulators and surrogate verifiers, which are imperfect off-distribution. Last are physical experiments, which are slow and costly. The session's slogan holds at the first tier. At lower tiers, "cheap checker" gives way to "expensive checker, rationed."
- The shared failure mode is specification and definition risk. Humans still decide *what* the Lean statement means, as with DeepMind's human-reviewed specs and Krippendorf et al.'s definitions. This makes a good optimistic discussion point: human expertise shifts toward stating the right problem.

### Gaps
- I found no peer-reviewed paper in the window that *empirically* tests transfer of the swarm+verifier model to a non-formal science.
- The full text of Tao's Economist op-ed was not read.
- I found no response essays from prominent physicists, chemists or biologists specifically on the Anthropic or PSI results.
