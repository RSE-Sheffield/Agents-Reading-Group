# AI-for-mathematics announcements from labs other than OpenAI, 19 Oct to 19 Nov 2026

Scope note: about 25 searches and fetches, run on 19 Nov 2026. Status labels:
- **Confirmed** means a primary source exists (lab page, repository or journal). It does not mean the mathematics was independently checked.
- **Reported** means only secondary or press sources were found.
- **Disputed** means the sources conflict.

Lab figures are self-reported unless stated otherwise. Items outside the window are marked **[EARLIER]**.

## New results, models, agents and public releases by lab

### Takeaway
In this window the other labs announced large **formalisations of known mathematics** and **software or hardware verification**, not new solutions to open problems:
- Axiom announced Faltings, Weil, Stacks and the Minimal Model Program.
- Anthropic's Fable 5.2 formalised Fermat's Last Theorem.
- DeepMind's AlphaProof Code verified Signal.
- Harmonic moved Aristotle into C, Verilog and Rust.

The biggest open-problem claim from a non-OpenAI lab was DeepMind's peer-reviewed AlphaProof Nexus paper in *Science*. It came on 12 Oct, just before the window.

### Cited Findings

**Google DeepMind**
- **[EARLIER, 12 Oct 2026, confirmed: peer-reviewed in *Science*, doi:10.1126/science.aej2213]** AlphaProof Nexus.
  - It is built on Gemini 3.1 Pro, which drafts and revises Lean proofs using compiler feedback, and it can call AlphaProof for hard sub-goals.
  - Claimed results:
    - 9 of 353 open Erdős problems attempted were solved, two of them open for 56 years.
    - 44 OEIS conjectures were proved.
    - An open question in algebraic geometry was solved.
    - A known min-max optimisation bound was improved.
  - DeepMind says the 9 Erdős solutions did not need AlphaProof. The solutions were shared online before the paper appeared.
  - The press framed it as a peer-reviewed contrast to OpenAI's GitHub bulk release.
  - No independent mathematicians were quoted, and the article does not mention public access to the system.
  - Source: [The Decoder, 12 Oct 2026](https://the-decoder.com/google-deepminds-alphaproof-nexus-solved-dozens-of-open-math-problems-and-actually-got-peer-reviewed/)
- **10 Nov 2026, confirmed by the DeepMind blog: "Introducing AlphaProof Code."** Authors are Pushmeet Kohli and Swarat Chaudhuri. Source: [DeepMind blog](https://deepmind.google/blog/introducing-alphaproof-code/)
  - **What it did:** agents powered by "Gemini Carbon" wrote more than 6 million lines of Lean to formally verify the implementation of the Signal protocol, covering compiled code and post-compromise security properties.
  - **Human role:** about 1% of the codebase was flagged for human review.
  - **Time:** 4 weeks, which DeepMind contrasts with years for expert teams.
  - **Test:** two previously fixed bugs were re-inserted, and the system produced machine-checked proofs that both versions were insecure.
  - **Claim:** DeepMind calls it "first formal verification of such a protocol's implementation by any method."
  - **Release:** the artefacts are open-sourced at google-deepmind.github.io/code-verification. The page states no licence.
  - **Partner:** Signal gave feedback on the method.
  - **Context:** this is software verification, not mathematics research. The page does not mention IAS, disclosure norms or OpenAI.
  - Also reported in [Mind and Machine Weekly, 15 Nov 2026](https://mindandmachineweekly.substack.com/p/mind-and-machine-weekly-15-november).
- No other DeepMind mathematics announcement dated in the window was found. Searched: [DeepMind research](https://deepmind.google/research/).

**Anthropic**
- **9 Nov 2026, confirmed by the Anthropic page (amended 11 Nov to clarify the formalisation subsection and add footnote 4): Claude Fable 5.2 and Mythos 5.2.** Source: [Anthropic](https://www.anthropic.com/claude-fable-and-mythos-5-2)
  - **Fermat's Last Theorem:** 1,000 Fable 5.2 agents completed a Lean formalisation of FLT in 30 hours with "minimal human intervention."
    - They started from 60 statements, a one-sentence sketch, definitions and 47 lemmas reused from an earlier formalisation.
    - The earlier effort, by an unreleased research model, took 11 days with a purpose-built harness and human guidance.
    - Fable 5.2 used about one-third as many action tokens and produced a proof about 7x shorter.
    - Opus 5.5, in the same setup, completed 26% of the work.
    - Because the footnote 4 starting material was substantial, "minimal human intervention" should be read with that in mind.
  - **Open problems:** the page makes no claim to have solved an open mathematics problem.
  - **Physics:** it does claim two open theoretical-physics problems about black holes and holography were solved. Preprints are 2611.00175 and 2611.00174 on hexagonmath.org.
  - **Benchmark:** Humanity's Last Exam (with tools) scores were 74.2% for Fable 5.2, 67.7% for Opus 5.5 and 57.2% for GPT-6 Astra. These are self-reported.
  - **Access:** Fable 5.2 is generally available. Mythos 5.2 is restricted to vetted organisations through the Life Sciences and Cyber Verification Programs. There is **no mathematics access programme**.
  - **External review:** the page names UK AISI, METR and Frontier Design as pre-release evaluators. It also says "None of the external organizations reviewed the contents of this blog post." IAS is not mentioned.
- **[EARLIER, about Sep 2026, reported]** The original 11-day FLT formalisation by an unreleased model was reported as about 13M lines of Lean, a formalisation of a known theorem rather than new mathematics. — [Yahoo Tech](https://tech.yahoo.com/ai/claude/articles/ai-just-solved-350-old-130103863.html)

**Harmonic (Aristotle)** — all items below are confirmed by headlines only on [harmonic.fun/news](https://www.harmonic.fun/news); the article texts were not read.
- 27 Oct 2026: Aristotle expands into formal verification of software and hardware, starting with C and Verilog.
- 3 Nov 2026: Aristotle formally verifies the MUL and DIV instructions of the Ibex RISC-V CPU.
- 12 Nov 2026: Aristotle adds multiclock (hardware) verification support.
- 16 Nov 2026: Aristotle expands into Rust.
- No new open-problem claims by Harmonic were found in the window. Harmonic is pivoting visibly toward verification.
- Earlier academic-support items, for context: [EARLIER, 22 Jan 2026] mathematician sponsorships, and [EARLIER, 11 Feb 2026] a $300k donation to the Lean FRO. Source: [harmonic.fun/news](https://www.harmonic.fun/news)

**Axiom (AxiomProver)** — the most active lab in the window. Every item is self-reported, and none mentions independent review.
- **[EARLIER, Oct 2026, exact day unknown, confirmed by a title on the Axiom blog index]** "Formalizing the Enormous Theorem": a Lean formalisation of the Classification of Finite Simple Groups (CFSG), hosted at cfsg.axiommath.ai. — [Axiom research index](https://axiommath.ai/territory/)
- **6 Nov 2026, confirmed by the Axiom post: the Weil conjectures formalised in Lean.** — [Axiom](https://axiommath.ai/research/the-weil-conjectures-formalized-in-lean/)
  - It covers rationality, the functional equation, topological comparison and RH over finite fields. The proof is reported as sorry-free with no extra axioms.
  - Repository: [github.com/AxiomMath/Weil](https://github.com/AxiomMath/Weil)
  - The post credits **humans only**: lead Tony Yue Yu, plus Letong Hong, Kenny Lau, Jannis Limperg, Brian Nugent, Ken Ono, Ashvin Swaminathan, Jesse Thorner and Edison Xie. It does not describe the AI's role.
  - **Disputed scale and timeline.** An Axiom employee's LinkedIn post claims an AxiomProver "swarm" wrote 50M lines of Lean over 24 days. A post by CEO Carina Hong reportedly says "less than a day." — [LinkedIn, Vasily Ilin](https://www.linkedin.com/in/vasilyilin/); [X, Carina Hong](https://x.com/CarinaLHong). These were seen only as search snippets and were not verified against the repository.
- **12 Nov 2026, confirmed by the Axiom post: Faltings' theorem (Mordell conjecture) formalised.** — [Axiom](https://axiommath.ai/research/faltings-theorem-formalized/)
  - Axiom calls it "the first complete, machine-verified proof," following the Bombieri–Vojta route.
  - Size: about 110k lines of proof-specific Lean on top of about 6.4M lines of Stacks-library Lean.
  - Repository: [github.com/AxiomMath/Mordell](https://github.com/AxiomMath/Mordell)
  - No individual authors, time taken or licence are given.
- **Nov 2026, confirmed by titles on the Axiom index, no exact days** — [Axiom index](https://axiommath.ai/), [research index](https://axiommath.ai/territory/):
  - "The Stacks Project, Formalized in Lean," at stacks.axiommath.ai.
  - "The Minimal Model Program, Formalized in Lean." The teaser mentions "recent AI-generated proofs" and 2.1M lines.
  - "Cluster Algebras, Formalized in Lean."
  - "Beyond the Classification: What the CFSG Corpus Unlocks." The teaser says AxiomProver formalised 30 published theorems on top of CFSG.
  - Two publications: "Quantum unique ergodicity and the critical crossover for 1-d Gaussian band matrices" and "Log-Concavity in Narayana Transforms and Stack-Sorting Fibers." Their content and AI role were not checked.

**Math, Inc. (Gauss)**
- No dated announcements were found in the window. The [math.inc homepage](https://www.math.inc/) shows an undated position piece, "Abstraction considered helpful," on specification engineering and autoverification. Its tagline, "Scaling autoverification to all future software," suggests a shift toward software verification.
- **[EARLIER, date not established, reported]** Math, Inc. published an executable Lean model of the Linux WireGuard handshake as a future Gauss target. — [hermes-ai.net](https://hermes-ai.net/news/math-inc-runs-wireguard-s-linux-handshake-inside-a-formal-proof-engine/)

**DeepSeek:** nothing found in the window. The latest maths releases found were DeepSeekMath-V2 (late 2025) and Prover-V2 (Apr 2025). — [Neowin](https://www.neowin.net/news/deepseek-launches-new-math-oriented-model-to-solve-secrets-of-the-universe/), [SCMP](https://www.scmp.com/tech/tech-trends/article/3308566/deepseek-quietly-updates-open-source-model-handles-maths-proofs)

**Mistral:** nothing found in the window.
- **[EARLIER, about early Jul 2026, reported]** Leanstral 1.5. It is reported as Apache-2.0 with open weights, a 119B mixture-of-experts model with 6.5B active parameters. Its claimed PutnamBench score is 587/672 and its claimed miniF2F score is 100%. — [DevOps.com](https://devops.com/mistral-releases-leanstral-1-5-an-open-model-that-solved-587-of-672-putnam-math-problems), [Developers Digest](https://www.developersdigest.tech/blog/leanstral-1-5-theorem-proving-model)

**Meta:** nothing found.

**xAI:** nothing found.

### Inferences
- Outside OpenAI, the frontier moved toward **very large formalisations of known mathematics** and **verification of real-world code and hardware**: Axiom, Anthropic, DeepMind's AlphaProof Code and Harmonic all did this. These outputs are machine-checkable, so they are far less contested than natural-language claims about open problems. That may be a deliberate positioning against the OpenAI controversy, though no lab says so.
- Axiom's run of announcements (Stacks, Weil, Faltings, MMP and CFSG within about 6 weeks) is striking. However, the AI-versus-human split is unclear and the published accounts conflict, so it should be presented as company-reported.
- DeepMind's choice of peer review for Nexus is the clearest example of a lab following traditional norms. It was published before the window.

### Gaps
- Full texts of Harmonic's posts from 27 Oct to 16 Nov were not read. Only headlines were seen.
- No independent expert review was found of Axiom's Weil or Faltings repositories or of Anthropic's FLT formalisation.
- Exact November dates for Axiom's Stacks, MMP, cluster-algebra and CFSG-corpus posts were not established.
- The "Gemini Carbon" model behind AlphaProof Code: no separate release information was found.
- Nothing was found for DeepSeek, Meta or xAI. The searches were general, so a quiet Hugging Face or GitHub release could have been missed.

## Academic access schemes or partnerships for mathematicians

### Takeaway
No new academic access scheme for mathematicians from a non-OpenAI lab was found in the window. Anthropic's restricted Mythos 5.2 access programmes cover life sciences and cybersecurity only. The labs' main way of giving access is open-sourcing Lean repositories.

### Cited Findings
- Anthropic's Mythos 5.2 verification programmes cover life sciences and cybersecurity only. None covers mathematics. — [Anthropic, 9 Nov 2026](https://www.anthropic.com/claude-fable-and-mythos-5-2)
- Axiom released its Weil and Mordell (Faltings) Lean code publicly on GitHub, with no licence stated on the pages. — [Weil post](https://axiommath.ai/research/the-weil-conjectures-formalized-in-lean/), [Faltings post](https://axiommath.ai/research/faltings-theorem-formalized/)
- DeepMind open-sourced the AlphaProof Code verification artefacts. — [DeepMind, 10 Nov 2026](https://deepmind.google/blog/introducing-alphaproof-code/)
- The Weil formalisation credits academic mathematicians, including Ken Ono and Jesse Thorner, as contributors. This is a de facto academic collaboration with Axiom. — [Axiom](https://axiommath.ai/research/the-weil-conjectures-formalized-in-lean/)
- **[EARLIER]** Harmonic's mathematician sponsorships (22 Jan 2026) and its Lean FRO donation (11 Feb 2026). — [harmonic.fun/news](https://www.harmonic.fun/news)

### Inferences
- Labs offer access mainly through open Lean artefacts and by employing or crediting academics. None has a formal access programme for mathematicians.

### Gaps
- DeepMind, Axiom, Harmonic and Math Inc may run access programmes that are not publicised. None was found.

## Lab responses to the IAS/AGMAI recommendations and to OpenAI's bulk release

### Takeaway
No non-OpenAI lab was found publicly adopting or citing the IAS-hosted Advisory Group on Mathematics and AI (AGMAI) recommendations in the window. AGMAI says it is in contact with unnamed other labs. The only implicit contrast is DeepMind's peer-reviewed *Science* route, which the press framed against OpenAI's approach.

### Cited Findings
- AGMAI statements in or near the window:
  - 6 Oct, "On OpenAI's Release": not an endorsement; AGMAI has "already been in contact with several" other labs, unnamed.
  - **25 Oct**, "Disadvantages of Designating Mathematicians for AI Output Releases": labs should stop pre-designating mathematicians to receive outputs early and should use pathway 2A (scholarly papers) or 2B (posted on independent repositories with citable IDs, disclosing how problems were chosen and how many were attempted). It refers to "people from multiple labs," unnamed.
  - **26 Oct**, "Recommendation for Immediate Release of Yang–Mills AI Output": calls on OpenAI to release its natural-language and Lean outputs for Yang–Mills, QCD and a Standard Model completion.
  - No statements are dated November.
  - Sources: [agmai.org](https://agmai.org/); [proofsandprompts.com, 26 Oct 2026](https://proofsandprompts.com/2026/10/26/disadvantages-of-designating-mathematicians-for-ai-output-releases/)
- AGMAI's site names no other lab (DeepMind, Anthropic, Harmonic, Axiom, Math Inc or DeepSeek) as adopting, consulting on or responding to its recommendations. — [agmai.org](https://agmai.org/)
- None of the in-window primary posts mentions IAS, AGMAI or disclosure norms: Anthropic (9 Nov), DeepMind AlphaProof Code (10 Nov), and Axiom Weil (6 Nov) and Faltings (12 Nov). — [Anthropic](https://www.anthropic.com/claude-fable-and-mythos-5-2), [DeepMind](https://deepmind.google/blog/introducing-alphaproof-code/), [Axiom Weil](https://axiommath.ai/research/the-weil-conjectures-formalized-in-lean/), [Axiom Faltings](https://axiommath.ai/research/faltings-theorem-formalized/)
- **[EARLIER, 12 Oct]** The press framed DeepMind's AlphaProof Nexus as peer-reviewed before publication, in contrast to OpenAI posting proofs on GitHub. — [The Decoder](https://the-decoder.com/google-deepminds-alphaproof-nexus-solved-dozens-of-open-math-problems-and-actually-got-peer-reviewed/)
- **[EARLIER, 7 Oct, academic reaction; the details are disputed]** An "Association for Human Mathematics" statement was reposted as a guest post on Terence Tao's blog. It criticised OpenAI's catalogue of 722 manuscripts (other reports say 719) and urged mathematicians to stop collaborating.
  - **Name:** reported variously as "Association of Human Mathematicians" and "Human Mathematics Association."
  - **Membership:** reported as about 600, about 800, or 1,008 members, of whom 654 are in an "AI-free caucus."
  - **Tao's role:** The Decoder says the group is "led by Terence Tao," while another report says Tao is not on the member list.
  - Sources: [OfficeChai](https://officechai.com/ai/association-of-human-mathematicians-now-has-over-600-members-that-have-pledged-to-not-use-ai-or-work-with-frontier-labs/), [OfficeChai](https://officechai.com/ai/mathematicians-did-not-ask-this-openai-has-total-disregard-for-norms-of-scientific-research-association-of-human-mathematics/), [Mezha](https://mezha.ua/en/news/mathematicians-urge-end-to-openai-collaboration-315962/), [Kingy.ai opinion, 8 Oct, arguing against a boycott](https://kingy.ai/blog/terence-tao-ai-math-backlash-gatekeeping/)

### Inferences
- The other labs appear to be responding by choice of output type, not by statement. They put out machine-checked formalisations and open repositories, or peer review in DeepMind's case, all of which sidestep the AGMAI concern about unverifiable claims from internal models. Anthropic's FLT result came from an *internal* unreleased model at first, but it concerned a known theorem.

### Gaps
- No public statement from DeepMind, Anthropic, Harmonic, Axiom, Math Inc or DeepSeek on AGMAI or on OpenAI's bulk release was found.
- The AHM's actual name, membership and Tao's relationship to it could not be confirmed from the AHM's own site.

## Notable academic-group results (agents plus Lean)

### Takeaway
Little was found that is clearly dated in the window and comes from independent academic groups. Most notable Lean and agent results in the window were lab-led, with academic co-authors in Axiom's case.

### Cited Findings
- **[EARLIER, Oct 2026, arXiv 2610.05367]** "AIProver: Agentic Auto-Formalization of Mathematical Research via Certificate-Driven Evolving Harness." Its affiliation and exact date were not checked. — [arXiv](https://arxiv.org/pdf/2610.05367)
- **[EARLIER, Oct 2026, arXiv 2610.13461]** "SqueezeBench: Saturation-Resilient Evaluation of Mathematical Capability," a benchmark paper. — [arXiv](https://arxiv.org/pdf/2610.13461)
- **[EARLIER, about Sep 2026, arXiv 2609.37471]** "A negative answer to Erdős Problem #786." It reportedly used GPT and Claude. — [arXiv](https://arxiv.org/pdf/2609.37471)
- **8 Nov 2026, reported:** press coverage says an eight-author team checked an AI-assisted proof of Erdős #1196 (from Apr 2026, GPT-5.4 Pro, with a Lean version) and applied its central idea to other open problems. — [Ecoticias](https://www.ecoticias.com/en/a-forum-user-asked-an-ai-model-about-an-erdos-problem-that-had-been-open-for-60-years-and-the-trick-hidden-in-its-proof-is-now-settling-other-puzzles-mathematicians-had-left-unsolved/53752/)
- **[EARLIER, Jun 2026]** LeanMarathon (arXiv 2606.05400) reports that Aristotle failed to autoformalise two Erdős-problem papers after tens of hours. This is a useful counterpoint to lab claims. — [arXiv](https://arxiv.org/pdf/2606.05400)

### Inferences
- The academic literature continues to produce benchmarks and harness papers, and some independent negative results on lab tools, such as LeanMarathon. These are useful for balancing lab marketing in discussion.

### Gaps
- No systematic arXiv sweep of math.LO, cs.LO or cs.AI from 19 Oct to 19 Nov was done. In-window academic results may have been missed.
- The authorship, affiliation and exact dates of the October arXiv papers above were not checked.
