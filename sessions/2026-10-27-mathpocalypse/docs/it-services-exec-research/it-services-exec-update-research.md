# AI for Research: Why It Must Be a Strategic Priority for IT Services
*Briefing evidence pack for the IT Services Executive Team, University of Sheffield. Evidence current to 15 November 2026.*

AI for research should be a critical strategic priority for IT Services now: in 2026 AI agents moved from summarising papers to producing machine-checked mathematics, peer-reviewed hypotheses confirmed in the wet lab and operational forecasting systems, and the institutions that provide governed compute, tooling and skills will capture that advantage while the rest absorb the risks through unmanaged "shadow AI".

## TL;DR

- **The capability is real, but verification is the bottleneck.** Lean-checked mathematics (Anthropic's 13-million-line Fermat's Last Theorem formalisation, OpenAI's forced Navier–Stokes blow-up) shows that agents can now produce checkable research. The OpenAI 722-manuscript release (3 withdrawn within a day, only about 42% formalised) shows that generating results is now cheaper than trusting them. **Confidence: High.**
- **The pattern is spreading wherever a cheap verifier exists:** weather (ECMWF runs AI forecasts operationally), algorithms (AlphaEvolve), protein structure and, more slowly, wet-lab biology and materials. Fields that depend on slow physical experiments are moving more slowly, and some early claims (Berkeley's A-Lab) have had to be corrected. **Confidence: High.**
- **The recommendation:** treat AI for research as research infrastructure, not a productivity app. Within three months, publish guidance, licence a governed frontier-model service and stand up an agent sandbox on Stanage. Within twelve months, build a verification and provenance service with RSE and the Library. Beyond that, invest in GPU capacity and federated national access (AIRR) at scale. **Confidence in direction: High; in costs: Low to Medium (estimates).**

---

## 1. Executive summary

The five findings that matter most:

1. **AI agents are now producing checkable research results, not just prose.** In September 2026 Anthropic reported that Claude agents produced a complete Lean 4 formalisation of Fermat's Last Theorem in 11 days: about 13 million lines and 29,500 intermediate theorems, checked by two independent proof kernels. OpenAI reported a Lean-certified proof of finite-time blow-up for the *forced* 3D Navier–Stokes equations, produced by about 10,000 agents in 88 hours. (High confidence that these artefacts exist; Medium confidence on what they mean.)
2. **Generating results is now cheap; trusting them is not.** OpenAI's 6 October release of 722 manuscripts covered 372 result families from about 4,000 attempted problems. Three manuscripts were withdrawn within a day for a sign error, 14 were revised, and only about 300 of 719 top-line results (about 42%) were formalised. A peer-group paper argues that the Navier–Stokes Lean proof does not match the written proof. The Clay Mathematics Institute calls the problem "apparently settled" but has awarded nothing. (High.)
3. **The pattern extends beyond mathematics where cheap verifiers exist.** These include operational AI weather forecasts at ECMWF, AlphaEvolve's machine-checkable algorithms and production scheduling, AlphaFold 3, and multi-agent "co-scientist" systems published in *Nature* in May 2026 with wet-lab confirmation. Slower-to-verify fields lag behind, and some early autonomous-lab claims were corrected. (High.)
4. **The research system is straining.** arXiv received a record 40,363 submissions in September 2026 and has capped submitters at two per month since 1 October. Mathematics submissions were about 75% higher than a year earlier, and AI acknowledgements in arXiv mathematics papers rose from 4% to 25% between April and August 2026. (High.)
5. **The policy and peer environment is moving fast.** Three moves are setting the bar: the UK AI for Science Strategy (up to £137m, AIRR expanding twentyfold by 2030), the US Genesis Mission (over $5bn), and campus-wide licences. UT Austin's licences are a useful reference point: a two-year ChatGPT Edu deal at about $1.1m a year plus a $2m Claude Edu commitment for 70,000 users. *The Daily Texan* (29 October 2026) also reports that only about 18,000 people had created accounts since June. Wiley's August 2025 survey of 2,430 researchers found AI use rose from 57% in 2024 to 84% in 2025. Yet 57% cite a lack of guidelines and training as a barrier, and only 41% feel their organisation offers adequate support. (High.)

**Headline recommendation:** IT Services should own a governed "AI for research" platform. This means licensed frontier models with research-grade data terms, open-weight models and agent sandboxes on Stanage, a verification and provenance service (Lean, reproducible containers, AI-use records) run with RSE and the Library, and brokered access to national compute. Sheffield already has the ingredients: Stanage GPUs, RSE Sheffield, the Centre for Machine Intelligence, a working `stanage-llm` template and the October 2026 AI for Research Days. The missing piece is a funded, coordinated service.

---

## 2. What has changed since October 2026 (newest first)

- **9 November 2026:** a Bloomberg Opinion column ("Is AI Going to Kill Math? Don't Count on It") pushes back on "end of mathematics" framing. *Expert opinion; shows the debate is now mainstream.*
- **3 November 2026:** Jisc publishes a strategic AI-adoption framework for college and university leaders. It covers ambition, risk appetite, funding, ownership and academic standards. *Directly relevant to this Executive Team.*
- **29 October 2026:** *The Daily Texan* reports UT Austin's contracts, obtained through open-records requests:
  - ChatGPT Edu: a two-year deal for 75,000 users, signed 6 May 2026, at about $1.1m a year.
  - Claude Edu: a $2m commitment for 70,000 users.
  - Only about 18,000 faculty, staff and students had created accounts since June.
  - *Reported fact from contract documents.*
- **27–28 October 2026:** Harmonic says its Lean-based Aristotle model now verifies C code and Verilog chip designs, reports 96.8% on the VERINA code-verification benchmark, and says the DIII-D fusion facility used it to rebuild control software. *Lab claim reported via Reuters; Medium–Low confidence.*
- **19 October 2026:** Jisc and Google announce a two-year partnership to move universities "beyond experimentation", with an initial institutional cohort and a procurement framework.
- **7–9 October 2026:** OpenAI withdraws three manuscripts after one sign error (in "Algebraicity of Weil classes on split abelian eightfolds") invalidated the paper and two dependants. It revises 14 others and adds six formalisations, giving 300 of 719 formalised. Retraction Watch reports that about 50% of results were released unconfirmed, on the advice of the Advisory Group on Mathematics and AI (AGMAI). *Science* reports that the advisory group asked OpenAI to stop testing open problems on unreleased models and that OpenAI refused.
- **6 October 2026:** Bastounis, Circelli and Hansen post "Navier–Stokes lost in translation" (arXiv:2610.08144). They argue that the Lean proof "does not correspond to the NL proof" and that semantically faithful autoformalisation is undecidable in general.
- **6 October 2026:** OpenAI releases 722 manuscripts in 372 families to `openai/math` under Apache-2.0, from about 4,000 problems at an average of about three hours of ChatGPT Pro-equivalent compute per result.
- **1–2 October 2026:** Sheffield's AI for Research Days run, co-organised by the Centre for Machine Intelligence (CMI), Dell and NVIDIA, with an "Agentic AI for research" workshop and an RSE/NVIDIA hackathon.
- **1 October 2026:** arXiv rate limit takes effect: two submissions per submitter per month and three active at once, after a record 40,363 submissions in September.

*Corrections to the October baseline:* the Fields Medallists' statement has 25 or 26 signatories depending on source; the formalised share of OpenAI's release is about 42% (one secondary source says 162, which conflicts); and Clay's position is "apparently settled" with an unhurried, multi-year process, not acceptance.

---

## 3. Findings

### A. Mathematics: what has happened

**A1. Navier–Stokes: status unresolved, artefact real, meaning contested.**

*Key terms:*
- **Lean 4** is a programming language and proof assistant in which a computer checks every logical step of a proof.
- **Mathlib** is its community library of formalised mathematics.
- **Comparator** is a tool that checks a formal statement matches an agreed reference statement, so an agent cannot "prove" a subtly different claim.
- **Autoformalisation** is AI translation of ordinary mathematical writing into Lean.
- An **agent swarm** is many AI agents working in parallel and exchanging messages.
- A **verifier** is any cheap, reliable check (proof checker, simulator, benchmark) that can grade agent output automatically.

What we know:
- On 8 September 2026 OpenAI announced that an internal system "produced an analytical proof and a Lean formalization that an initially smooth fluid at rest can develop a singularity in a finite time".
- It claims this settles statements C and D of the Clay formulation, which allow a smooth external force.
- OpenAI states that about 10,000 agents ran for 88 hours, exchanging 2.7 million messages and using about 130 billion tokens, and that Lean formalisation took a further 17 hours (as reported by the *Tufts Daily* from OpenAI's description).
- OpenAI says it will not claim the prize. (Reported fact: High.)
- The Clay Mathematics Institute's statement of 11 September said it "shares in the excitement of the global mathematical community as we contemplate the announcement that the Navier-Stokes problem has apparently been settled", while keeping a deliberately unhurried process.
- Clay's rules require publication in a qualifying outlet, two years' wait and general acceptance. No prize has been awarded and, as of mid-November, there is no evidence of journal acceptance. (High.)

The contested points:
- **The forcing loophole:** *Scientific American* notes the result does not address the unforced problem "that mathematicians really care about", though it fits Clay's own wording.
- **The translation gap:** Bastounis, Circelli and Hansen argue the Lean proof follows a different argument from the 166-page written proof. So the Lean check certifies the formal statement, not the human-readable paper.
- An independent Zenodo record documents a successful rebuild of OpenAI's Lean code.
- **The priority dispute:** NYU's Tristan Buckmaster alleged that OpenAI pursued the route after learning of his work with Levent Alpöge. OpenAI denies wrongdoing; reporting says OpenAI acknowledged their priority on the related Euler result. (Medium.)

*My inference:* the Lean artefact is very probably a correct proof of *some* precise statement. Whether that statement is the one mathematicians care about is a human judgement that machines cannot make. This is the central lesson for IT Services: verification tooling is necessary but not sufficient.

**A2. The 722-manuscript release: what has held up.**
- **Released on 6 October:** 722 manuscripts in 372 families across about 17 fields, from about 4,000 problems.
- **Errata so far:** three withdrawn, 14 revised and 13 cross-references updated within 24 hours.
- **Formalised so far:** 300 of 719 top-line results (about 42%) per OpenAI's changelog as reported by *Science* and others.
- Only 10 manuscripts include the model's reasoning trace. (High.)
- I found **no evidence** of journal acceptance of any manuscript, nor a systematic expert audit of the whole set, by 15 November. An earlier human audit of OpenAI's August "Ten Advances" (arXiv:2608.14673) is the best model for how such audits work.
- Expert judgement of significance is mixed. The withdrawn trio included claimed progress on the rational Hodge conjecture for products of K3 surfaces, which shows the most ambitious claims carry the most risk. (Medium.)

**A3. Other labs and groups.**
- **Anthropic: Fermat's Last Theorem formalised (announced 4 September 2026).**
  - About 13 million lines of Lean, about 29,500 intermediate theorems, about 6 billion output tokens, 11 days.
  - Coordinated through Columbia's open Prove2Me platform.
  - Independently re-checked by the Rust-based nanoda kernel and by Comparator.
  - Kevin Buzzard (Imperial) called it "an amazing feat of automatic formalization". (Medium–High: Anthropic primary posts plus several secondary accounts; I could not fetch the Anthropic blog directly.)
  - It is formalisation of a known theorem, not a new result, but it shows what agent swarms can do with a verifier.
- **Google DeepMind's Aletheia (arXiv:2602.10177).**
  - Ran against 700 open Erdős problems (2–9 December 2025), producing 212 candidates, 63 technically correct, 13 "meaningfully correct" and four autonomous resolutions (Erdős-652, 654, 1040, 1051).
  - Of 200 graded candidates, only 6.5% were meaningfully correct; 50 correct answers were "mathematically vacuous" because the agent picked trivial readings.
  - The paper warns of "subconscious plagiarism" from training data. (High: primary source.) This is the clearest published error-rate evidence available.
- **OpenAI before the Navier–Stokes result:** disproof of the Erdős unit-distance conjecture (20 May 2026). Alon, Bloom, Gowers, Litt and Sawin quickly produced a "human-verified" digest that traced key ideas to existing literature. (High.)
- **Math Inc's Gauss:** autoformalised the strong Prime Number Theorem in three weeks (2025), then Viazovska's 24-dimensional sphere-packing proof, over 200,000 lines in two weeks (IEEE Spectrum, 2026). (Medium–High.)
- **Benchmarks:** commercial leaderboards (November 2026) show open-weight models near the frontier on competition mathematics, but rankings are inconsistent; do not quote them on slides. (Low.)

**A4. Workflow, norms and policy.**
- **arXiv:**
  - May 2026: one-year bans for "incontrovertible evidence" of unchecked LLM output, such as hallucinated references.
  - 1 October 2026: two submissions a month across all categories. AI-assisted papers remain permitted if disclosed.
  - Submissions doubled in two years (20,569 in September 2024 to 40,363 in September 2026), with cs.AI up more than six times. (High: arXiv blog.)
- **Academy for the Mathematical Sciences (October 2026 report):** September 2026 mathematics submissions were 7,428 against 4,252 a year earlier, about 75% up. AI acknowledgements rose from 4% (April) to 25% (August). (High: primary report, quoted via search extract; I could not fetch the PDF.)
- An econometric preprint (arXiv:2609.04872) finds mathematics entries to August were 33.5% above 2025, with an 11.9% mathematics-specific excess after controls. Its conclusion: "the cost of producing candidates is falling faster than the cost of establishing trust."
- **The Leiden Declaration (2 June 2026, IMU-endorsed):**
  - Recommends disclosure of AI use, independently verifiable results, and human responsibility for correctness and attribution.
  - Calls on governments to "invest in public alternatives to commercial technologies".
  - Written by a working group of 16 researchers from 15 universities, convened by Jim Portegies (TU Eindhoven).
  - The official site now lists 4,445 signatories (November 2026).
  - Early counts conflict: Gizmodo reported "more than 130 signatories" at publication, while a secondary account cites Mateja Jamnik saying over 1,000 signed on the first day.
- **"A Severe Misalignment of AI in Mathematics" (11 September 2026):** signed by 25 Fields Medallists (EPFL reports 26), including Tao, Scholze, Hairer and Viazovska. It argues that treating famous problems as benchmarks is "harmful to the science of mathematics and the mathematical community", while conceding AI can "enhance and accelerate genuine mathematical study". (High.)
- **Peer review:** Frontiers' whitepaper "Unlocking AI's untapped potential" (December 2025) surveyed 1,645 active researchers in 111 countries in May–June 2025. It found that 53% of reviewers now use AI tools, often against guidance, rising to 87% among early-career researchers. (High.)

**A5. What a university can actually deploy now.**
- **Lean 4, Mathlib, Lake and Comparator:** open-source; run on any Linux host, including Stanage.
- **Open-weight models and provers:** the GLM, Kimi and Qwen families, plus DeepSeek-Prover-V2, Goedel-Prover-V2 and Kimina-Prover, can run on-premises on A100/H100 nodes.
- **Cloud and API:** Harmonic Aristotle and frontier models (Claude, GPT, Gemini) via enterprise or education licences.
- **Agent harnesses:** Claude Code, Codex and Gemini CLI, plus open coordination layers such as Prove2Me.
- Sheffield's IT Services Research & Innovation team already publishes `rcgsheffield/stanage-llm`, a template for running open-weight LLMs on Stanage. (Public fact.)
- The frontier systems behind the headline results (OpenAI's internal model, Aletheia) are **not** available to universities. This is the "two-tier" risk in concrete form.

**So what for IT Services:** mathematics shows the operating model of AI research. It needs large parallel compute, a sandbox where agents can run code safely, a verifier (Lean, Comparator), provenance records and humans to adjudicate. IT Services can provide every element except the last, and can make that last one cheaper.

### B. Beyond mathematics: the same pattern

**Hypothesis:** fields with cheap, reliable verification move first. The evidence broadly supports it, with nuance. Weather and algorithms (cheap, objective verifiers) have reached *operational* deployment. Biology and chemistry, where verification needs wet labs, have strong but slower results and a visible correction record. Physics theory sits close to mathematics but has little peer-reviewed agent output yet.

**Physics and astronomy** (verifier: numerics, simulation, reanalysis of open data)
- A Gemini Deep Think agent derived an analytic solution for a cosmic-string radiation integral and checked it numerically (Brenner, Cohen-Addad and Woodruff, arXiv:2603.04735, March 2026; preprint).
- Agents reproduced a CMS Open Data H→ττ analysis and claim a new Lund-plane measurement on LEP data (arXiv:2603.20179, 2026; preprint, not independently verified).
- Emory's interpretable ML model identified non-reciprocal forces in dusty plasma at over 99% accuracy (*PNAS*, April 2026; seen via ScienceDaily).
- *Assessment:* promising but thin. No AI-proposed physics prediction has yet been confirmed experimentally, as far as I could find. (Medium.)
- *Unverified:* reports of an AI-discovered dwarf planet (November 2026) trace only to social media. Exclude them.

**Chemistry and materials** (verifier: DFT simulation, robotic synthesis, X-ray diffraction)
- GNoME predicted 2.2 million crystal structures, about 381,000 judged stable by DFT (*Nature* 624, 2023). Cheetham and Seshadri (*Chem. Mater.*, 2024) found "scant evidence" of compounds that are novel, credible and useful at once.
- Berkeley's A-Lab originally reported 41 of 58 targets synthesised in 17 days (*Nature* 624, 2023). Leeman, Palgrave and colleagues (*PRX Energy*, 2024) argued "no new materials have been discovered". *Nature*'s **Author Correction (19 January 2026)** retitled the paper from "novel" to "inorganic" materials and revised the count to 36 of 57 targets.
- 2026 self-driving labs are making steady progress in closed-loop optimisation: Flex-Cat homogeneous catalysis (*Nature Communications*, 2026) and red-shifted organic laser dyes (*Nature Communications*, February 2026).
- *Assessment:* simulation verification is cheap but does not by itself establish discovery. Wet-lab confirmation is slow, and that is where overclaims were caught. (High.)

**Biology, drug discovery and medicine** (verifier: structure benchmarks, wet lab, clinical trial)
- AlphaFold 3 predicts complexes of proteins with ligands, nucleic acids and antibodies (*Nature* 630, May 2024), benchmarked against the PDB. Code was initially withheld and later released.
- Google's Co-Scientist (*Nature* 655:487–496, May 2026) and FutureHouse's Robin (*Nature* 655:497–505) generated hypotheses that were then tested in the wet lab. Validation still depended on human experimenters.
- AutoDNA (*Nature*, 2026) orchestrated over 20 instrument types across more than 11,000 steps, with humans only restocking.
- Rentosertib, with an AI-chosen target (TNIK) and molecule, had a Phase IIa trial in idiopathic pulmonary fibrosis: 71 patients, 12 weeks. FVC rose by 98.4 mL at 60 mg, against a 20.3 mL fall on placebo (*Nature Medicine* 31, June 2025). The result is exploratory. A Phase III trial (NCT07687459) started in September 2026, with completion around 2029.
- *Assessment:* real, but the slowest verifier (clinical trials) sets the pace. (High.)

**Computer science and software engineering** (verifier: program execution, formal proof, production telemetry)
- AlphaEvolve (Google DeepMind, May 2025) found a 48-multiplication algorithm for 4×4 complex matrices, beating the 49 of recursive Strassen and improving 14 matrix-multiplication targets.
- Its Borg scheduling heuristic recovers on average 0.7% of Google's worldwide compute (Google's own measurement).
- Humans quickly built on its result (arXiv:2506.13242).
- Harmonic now applies Lean proof to C and Verilog (October 2026).
- *Assessment:* fastest-moving after mathematics, because the verifier is literally running the code. (High.)

**Engineering, climate and earth sciences** (verifier: forecast skill against observations)
- GraphCast beat ECMWF's deterministic model (HRES) on 90.3% of 1,380 targets (*Science* 382, 2023). GenCast beat ECMWF's ensemble on 97.2% of 1,320 targets (*Nature* 637, 2024).
- ECMWF's AIFS Single became operational on 25 February 2025, the ensemble version on 1 July 2025, and v2 on 12 May 2026. They run *alongside*, not instead of, the physics model, at coarser resolution.
- *Assessment:* the clearest proof that cheap, objective verification leads to operational adoption. (High.)

**Humanities and social sciences** (verifier: human coding agreement, replication)
- Anthropic surveyed 1,260 social scientists (February–March 2026): 81% had used chatbots in research, but only 20% had adopted coding agents. Adoption was "highly uneven" by career stage, gender and institutional rank. (Medium–High: vendor-run survey.)
- Sheffield's own AI for Research Day included literature-review and clinical-notes text-analysis talks.
- *Assessment:* adoption is driven by productivity (literature review, coding, transcription), not discovery. The equity gap is a governance issue IT Services can address.

**So what for IT Services:** the same stack recurs in every field: compute, agent sandbox, domain verifier (Lean, simulator, benchmark, instrument), data management and provenance. A central platform serves physics, chemistry, biomedicine and engineering as well as mathematics. Sheffield's strengths in materials (Royce), advanced manufacturing, biomedicine and machine intelligence map onto the fields moving fastest.

### C. Scale, speed and economics

- **Output growth:** arXiv submissions doubled from 20,569 (September 2024) to 40,363 (September 2026), generating almost 9,000 support tickets in one month. (High.)
- **Cost of headline results:**
  - OpenAI reports about three hours of "ChatGPT Pro-equivalent" compute per manuscript result. It does not give pounds or GPU-hours. (Lab claim.)
  - The Navier–Stokes run used about 130 billion tokens across 10,000 agents.
  - The FLT formalisation used about 6 billion output tokens.
  - A widely repeated $1–2 million estimate for the Navier–Stokes formalisation comes from a blog comment and is **unverified**. (Low.)
  - John D. Cook estimated that formalising the 166-page paper by hand would take about 132,800 person-hours (his estimate).
- **Prices are falling:** November 2026 frontier API list prices range from about $2/$10 per million input/output tokens (for example GPT-6.1 Sol and Gemini 4 Carbon introductory pricing) to $5/$25 or more (for example Claude Opus 5). These are from aggregator sites; treat as indicative. (Low–Medium.)
- *My inference, labelled as an estimate:* at $10 per million output tokens, 6 billion output tokens would be about $60,000 at list price. Swarm-scale research is therefore within reach of a well-funded group or a central service, not just a frontier lab. Input tokens and retries would raise this.
- **What a typical group needs:** for literature, coding and data work, a licensed frontier-model seat (about £15–£25 per user per month at list price; institutional deals vary). For agentic and formal work, a sandboxed environment with a GPU or two for open-weight models, plus API budget. For swarm-scale work, national allocations (Isambard-AI calls offer 50,000 to 1.4 million GPU-hours per project) or vendor research partnerships.
- **Adoption:**
  - Wiley ExplanAItions 2025 (2,430 researchers): 84% use AI in their work (up from 57% in 2024) and 62% for research or publication tasks.
  - 80% use general-purpose tools, against 25% using specialist research tools.
  - 57% would let a capable agent act autonomously, and 57% cite a lack of guidelines and training as a barrier.
  - Early-career researchers lead adoption. Wiley found 92% of ECRs use AI in some aspect of their work. Frontiers' 2025 survey found 87% of early-career researchers use AI in peer review, against 53% of all reviewers. (High.)
- **Investment and policy:**
  - **UK AI for Science Strategy (November 2025):** up to £137m within a £2bn 2026–2030 envelope; at least 1,000 AI-fluent researchers trained; a data repository co-located with Isambard-AI.
  - **AIRR:** to grow twentyfold by 2030; over £1bn for expansion and up to £750m for an Edinburgh national supercomputer.
  - **Isambard-AI** (£225m) also powers the £500m Sovereign AI fund. The 2026 AIRR open call offered 8 million GPU-hours (closed 17 July 2026).
  - **US Genesis Mission:** executive order November 2025; over $5bn in federal commitments announced 22 July 2026, plus over $800m from partners.
  - I did not verify current EU, China, UKRI/EPSRC or Wellcome figures in this round (see Gaps).

**So what for IT Services:** the binding constraint is not model access alone. It is *governed* access at research scale, plus the ability to verify. National compute is plentiful but competitive. Universities with ready-made sandboxes, data pipelines and RSE support will win more AIRR allocations.

### D. Peers, guidance and what IT Services should do

**Peer moves (public facts):**
- **Licensing:**
  - Oxford is named by OpenAI as an "AI-powered university" with ChatGPT Edu.
  - LSE and Northumbria have campus-wide Claude for Education agreements.
  - Kent rolled out ChatGPT Edu (GPT-5.2) to all staff from March 2026.
  - UT Austin committed about $4.2m over two years for both ChatGPT Edu and Claude Edu (Claude Code included).
  - Stanford, Chicago and Emory hold Claude for Education contracts.
- **Compute:**
  - Bristol hosts Isambard-AI (part of AIRR).
  - Cambridge's DAWN capacity is being expanded sixfold.
  - Edinburgh will host the new national supercomputer (up to £750m).
- **I could not verify** in this round current Russell Group-specific AI research platforms (for example Imperial, UCL or Manchester central AI teams), nor specific MIT or ETH investments. Check these manually.

**Sector guidance:**
- Jisc's AI leadership framework (3 November 2026).
- Jisc's AI procurement due-diligence guidance and its guidance on resisting restrictive AI clauses in publisher licences.
- The Jisc–EAUC guide to AI's environmental impact (June 2026).
- The Jisc–Google partnership (October 2026).
- The Leiden Declaration's recommendations to institutions and funders.
- UCISA and EDUCAUSE guidance was not retrieved this round.

**Sheffield context:**
- *Public facts:*
  - Stanage is described in Sheffield's citation text as a £3m+ investment with about 12,000 CPU cores and 104 GPUs (72 A100, 32 H100). The January 2026 HPC newsletter reports 16 H100 NVL GPUs in a new partition and a Blackwell node (8× RTX 6000 Pro) on order.
  - Researchers also have access to N8's Bede (Tier 2; V100 and GH200).
  - IT Services' Research & Innovation team runs Stanage and publishes the `stanage-llm` template and a "gemini-gems" repository.
  - The Centre for Machine Intelligence launched its Strategy 2026 and co-ran the AI for Research Days on 1–2 October 2026 with Dell and NVIDIA. Topics included self-driving labs for materials and an agentic AI workshop.
  - RSE Sheffield won a £235k UKRI Metascience grant on AI's impact on research stewardship.
  - The Royce Institute at Sheffield has published commentary on the AI for Science Strategy.
- *Inference:*
  - Stanage's GPU fleet is modest next to national facilities. It suits sandboxed open-weight inference and development, not swarm-scale work.
  - The "gemini-gems" repository suggests Google Gemini is in institutional use. Confirm the University's current enterprise AI licence position.
  - I could not retrieve the University's institutional AI strategy, nor confirm the status of Bessemer (possibly retired) or the Turing partnership.

**IT Services responsibilities:** GPU and HPC provision; secure agent sandboxes (containerised, network-restricted, secrets-free); research data management and provenance; identity and access, including API-key brokering; procurement with research-grade data terms; information security (prompt injection, data leakage, export control); FinOps-style cost control for tokens; and training with RSE and the Library.

**So what for IT Services:** peers are licensing at campus scale and the government is funding national compute. The differentiator is the layer in between: governed, supported, verifiable research use. That is an IT Services competence.

### E. Risks and critics (summary; full table in section 6)

The strongest critiques are credible and come from the field's leaders:
- the Fields Medallists' misalignment statement;
- the Leiden Declaration;
- an essay arguing for "total opposition to the use of artificial intelligence in mathematics" (arXiv:2608.02859);
- Aletheia's own 6.5% "meaningfully correct" rate;
- the A-Lab correction;
- the Navier–Stokes translation-gap paper.

None argues that the capability is fake. They argue that trust, credit, understanding and access are at risk. Each risk has a mitigation IT Services can own or co-own; unmanaged use maximises every risk they name.

---

## 4. Evidence by field

| Field | Example | Date | What the AI did | How it was verified | Source | Confidence |
|---|---|---|---|---|---|---|
| Mathematics | Fermat's Last Theorem formalisation (Anthropic Claude) | Sep 2026 | About 13m lines of Lean and 29,500 theorems in 11 days | Lean kernel, independent nanoda kernel, Comparator | Anthropic research blog and repository; Buzzard review | Medium–High |
| Mathematics | Navier–Stokes forced blow-up (OpenAI) | 8 Sep 2026 | About 10,000 agents, 88 h; 166-page proof plus Lean | Lean (17 h); independent rebuild; disputed correspondence with the written proof | OpenAI; Clay statement; arXiv:2610.08144 | High (artefact); Medium (significance) |
| Mathematics | 722 manuscripts (OpenAI) | 6 Oct 2026 | 372 result families from about 4,000 problems | About 42% Lean-formalised; 3 withdrawn, 14 revised | Retraction Watch; *Science*; openai/math | High |
| Mathematics | Aletheia on Erdős problems (DeepMind) | Dec 2025 – Feb 2026 | 4 autonomous resolutions; 13 meaningful out of 700 | Expert human grading (6.5% meaningful) | arXiv:2602.10177 | High |
| Mathematics | Erdős unit-distance disproof (OpenAI) | 20 May 2026 | Counterexample construction | Human-verified digest by Alon, Bloom, Gowers, Litt, Sawin | arXiv:2608.28997 (summary) | High |
| Mathematics | 24-dimensional sphere packing (Math Inc Gauss) | 2026 | Autoformalised 200,000+ lines in about two weeks | Lean | IEEE Spectrum | Medium–High |
| Computer science | AlphaEvolve (DeepMind) | May 2025 | 4×4 complex matrix multiplication in 48 multiplications; Borg scheduling | Mechanical check; production telemetry (0.7%, self-reported) | DeepMind blog and white paper | High (maths); Medium (0.7%) |
| Computer science | Aristotle code verification (Harmonic) | Oct 2026 | Lean proofs for C and Verilog | VERINA benchmark (96.8%, self-reported) | Reuters via trade press | Medium–Low |
| Climate and weather | GraphCast / GenCast | 2023–2024 | Medium-range and ensemble forecasts | Skill against ECMWF on 1,380 / 1,320 targets | *Science* 382; *Nature* 637 | High |
| Climate and weather | ECMWF AIFS operational | Feb/Jul 2025; v2 May 2026 | AI forecasts in operational service | Ongoing operational verification | ECMWF | High |
| Materials | GNoME | Nov 2023 | 2.2m predicted crystals, about 381k stable | DFT simulation; criticised on novelty | *Nature* 624; *Chem. Mater.* 2024 | High (with caveat) |
| Materials | A-Lab | Nov 2023; corrected Jan 2026 | Autonomous synthesis | Robotic synthesis plus XRD; revised to 36 of 57; "novel" removed | *Nature* 624; *PRX Energy* 2024; *Nature* 650 correction | High |
| Chemistry | Flex-Cat self-driving lab | 2026 | Closed-loop catalyst optimisation | Wet lab | *Nature Communications* 2026 | Medium |
| Biology | Co-Scientist; Robin | May 2026 | Multi-agent hypothesis generation and experiment design | Wet-lab validation by humans | *Nature* 655:487 and 497 | High |
| Biology | AutoDNA | 2026 | Autonomous nucleic-acid lab, over 11,000 steps | Instrumented wet lab | *Nature* 2026 | Medium–High |
| Biology | AlphaFold 3 | May 2024 | Biomolecular complex structure | PDB benchmarks | *Nature* 630 | High |
| Medicine | Rentosertib (Insilico) | Jun 2025; Phase III Sep 2026 | AI-chosen target and molecule | Randomised Phase IIa (n=71); Phase III ongoing | *Nature Medicine* 31; NCT07687459 | High (safety); Low–Medium (efficacy) |
| Physics | Cosmic-string radiation integral | Mar 2026 | Analytic solution by Gemini agent | Numerical check (preprint) | arXiv:2603.04735 | Medium–Low |

---

## 5. Recommendations

Costs below are **my estimates** unless stated, for order-of-magnitude planning only.

| # | Horizon | Recommendation | Problem solved | Evidence | Indicative cost / effort (estimate) | Owner and partners | Risk of inaction | Measure of success |
|---|---|---|---|---|---|---|---|---|
| 1 | Now (0–3 months) | Publish a researcher-facing "AI for research" guidance page: approved tools, data classes, disclosure wording aligned with arXiv and Leiden, export-control triggers | Researchers lack guidance (57% cite this barrier) | Wiley 2025; arXiv bans; Leiden Declaration | Low: about 0.2 FTE for 2 months | IT Services (InfoSec, Research IT) with Research Services, Library, Research Integrity | Shadow AI; integrity incidents; arXiv bans affecting Sheffield authors | Guidance live; page views; fewer data-incident tickets |
| 2 | Now | Inventory current AI use and licences (including Gemini, Copilot and individual subscriptions); a short survey of PIs and PGRs | Unknown demand and spend | Uneven adoption (Anthropic survey); ECR-led adoption | Low | IT Services (Procurement, BI) with Faculties | Under- or over-provisioning | Baseline report to the Executive Team |
| 3 | Now | Productise `stanage-llm` as a supported open-weight inference service with an agent sandbox (containers, no outbound network by default, Lean toolchain preinstalled) | Safe on-premises option for sensitive data; avoids lock-in | Open-weight models near frontier on maths; existing template | Low–Medium: existing GPUs; about 0.5 FTE RSE/HPC for 3 months | Research & Innovation IT with RSE | Researchers run agents on laptops with credentials exposed | Monthly active users; jobs run; zero security incidents |
| 4 | Next (3–12 months) | Procure an institutional frontier-model licence with research-grade terms (no training on data, UK/EU data residency where possible, agentic coding tools, API pool) through Jisc frameworks where available | Equitable access; data protection | UT Austin, Kent, LSE, Oxford precedents; Jisc–Google framework | Medium: indicatively £0.3m–£1m a year depending on scope (estimate from public US pricing) | IT Services (Procurement, InfoSec) with Faculties and Finance | Two-tier access inside Sheffield; uncontrolled data flows | Licence uptake; equity of uptake across faculties and career stages |
| 5 | Next | Stand up a verification and provenance service: Lean/Mathlib/Comparator environment, reproducible containers, AI-use logs attached to research outputs in the repository | Verification bottleneck; integrity | arXiv:2609.04872 ("trust" costs); OpenAI withdrawals; A-Lab correction | Medium: about 1 FTE RSE plus Library time | RSE and Library with IT Services, Research Integrity | Sheffield outputs untrustworthy or rejected | Number of outputs with provenance records; external audits passed |
| 6 | Next | Create an AIRR and national-compute brokerage: help groups bid for Isambard-AI and DAWN and port workloads | Local GPU scarcity | AIRR calls (50k–1.4m GPU-hours); twentyfold expansion | Low–Medium: about 0.5 FTE | Research IT with Research Services | Missed national allocations | GPU-hours won; bids supported |
| 7 | Next | Training pathway: "AI for Research 101", agentic workflows, Lean basics and secure agent practice, building on the October 2026 Research Days | Skills gap, especially for non-adopters | Wiley; Anthropic gender and career gaps; strategy target of 1,000 AI-fluent researchers | Low–Medium | RSE, Library and CMI with IT Services | Uneven adoption; ECR disadvantage | Attendance; post-course adoption |
| 8 | Next | Token FinOps: budgets, chargeback codes and dashboards for API spend | Cost control | Token-scale experiments (billions of tokens) | Low | IT Services Finance and Platforms | Bill shock; ungoverned grant spend | Spend visible per project |
| 9 | Later (12+ months) | GPU capacity uplift on Stanage or its successor, sized from inventory and usage data; consider N8 shared investment | Local capacity for sensitive and iterative work | Stanage modest next to national systems; Blackwell node already ordered | High: indicatively £1m–£5m capital (estimate) | IT Services with the Vice-President for Research & Innovation and N8 | Dependence on external queues and vendors | Utilisation; research income enabled |
| 10 | Later | Strategic partnership(s) with model providers or national programmes (for example research-access programmes, AIRR missions, Genesis-style consortia) aligned to Sheffield strengths (materials, manufacturing, biomedicine) | Access to frontier capability | Two-tier risk; government missions | Medium, mostly staff time | Vice-President for Research & Innovation, CMI, IT Services | Locked out of frontier systems | Partnerships signed; joint outputs |

### What we would tell a sceptical Director

- **"This is hype."** Some of it is, and we should say so: OpenAI withdrew three papers within a day, the A-Lab paper was formally corrected, and Aletheia's own authors report only 6.5% of candidates were meaningfully correct. But the artefacts are checkable. A 13-million-line Lean proof is either accepted by the kernel or it is not, and ECMWF does not run hype operationally. The right response to mixed evidence is governed adoption that makes verification cheap, not waiting.
- **"Our researchers aren't asking for it."** They are already using it, just not through us. Wiley's survey of 2,430 researchers found AI use rose from 57% in 2024 to 84% in 2025. Early-career researchers lead: 87% use AI in peer review, against 53% of reviewers overall (Frontiers, 2025). Our own AI for Research Days in October 2026 ran an agentic AI workshop. Silence in the service desk queue means shadow AI, not no demand.
- **"We cannot afford it."** We cannot afford all of it, and we do not need to. The "Now" actions reuse Stanage and existing staff. Swarm-scale compute is available free through AIRR calls if we help researchers bid. Licences can be bought through Jisc frameworks and phased. The bigger cost is losing grants, staff and PhD students to better-equipped institutions.
- **"It's a security risk."** Yes, and unmanaged it is a bigger one. Agents run code, read files and call the internet, so prompt injection and data leakage are real. A sandbox we control, licences with no-training terms, and guidance on data classes and export control reduce the risk below today's baseline of personal accounts.
- **"Mathematicians themselves oppose this."** Some do, and their concerns are about credit, understanding and corporate control. The Leiden Declaration asks institutions to keep results verifiable, require disclosure and invest in public alternatives. Those are exactly the services we propose.

---

## 6. Risks and counter-arguments

| Argument (strongest version and evidence) | Mitigation IT Services can own |
|---|---|
| **Reliability and the translation gap.** Agents produce plausible but wrong proofs; formal checks can certify the wrong statement. Evidence: OpenAI's sign-error withdrawals; arXiv:2610.08144; Aletheia's 6.5% meaningful rate and "vacuous" answers. | Provide Lean, Mathlib and Comparator environments plus guidance that formal statements need human sign-off; provenance records linking prose to formal artefacts. |
| **Verification is the bottleneck.** "The cost of producing candidates is falling faster than the cost of establishing trust" (arXiv:2609.04872); arXiv's ~9,000 tickets in a month. | Build a verification service (Rec. 5); fund RSE time for checking, not just generation; metrics that reward verified outputs. |
| **Reproducibility, provenance, integrity and peer-review overload.** Only 10 of 719 OpenAI manuscripts include reasoning traces; 53% of reviewers use AI, often against guidance. | Containerised, logged agent runs; repository metadata for AI use; reviewer guidance with the Library and Research Integrity. |
| **Credit, priority and authorship.** The Buckmaster priority dispute; Aletheia's "subconscious plagiarism"; the Fields Medallists' attribution concerns. | Disclosure templates aligned with Leiden; timestamped, access-controlled project spaces protecting researchers' unpublished ideas from leakage to vendors. |
| **Security, data protection and IP.** Agents with tool access are vulnerable to prompt injection and exfiltration; UK GDPR, export control and commercial confidentiality apply. | Sandboxes with no default egress; enterprise terms with no training on our data and UK/EU residency where possible; data-classification rules; DPIA templates; export-control screening for sensitive fields. |
| **Energy and environment.** AI's energy, water and embodied carbon are poorly disclosed by vendors (Jisc–EAUC, June 2026). | Report GPU energy on Stanage; prefer efficient open-weight inference where adequate; join Jisc collective requests for vendor data. |
| **Proprietary dependence and two-tier science.** The headline results came from unreleased internal models; the advisory group asked OpenAI to stop and was refused; Leiden calls for public alternatives. | Dual-track: licensed frontier access plus open-weight on-premises capability; AIRR brokerage; avoid exclusive lock-in in contracts; data and workflow portability. |
| **Skills and workforce.** ECRs and PhD students may lose formative training, or be left behind; adoption gaps by career stage and gender. | Training pathway (Rec. 7); work with doctoral schools on AI-use policy; equitable licence allocation. |
| **Academic scepticism ("fluke, not sea change").** Bloomberg Opinion (November 2026); the "total opposition" essay (arXiv:2608.02859); Aletheia solutions were often easy, and AlphaEvolve gains are incremental. | Frame investment as low-regret infrastructure (sandbox, verification, skills) useful whatever the trajectory; review annually against measured uptake. |

---

## 7. Slide-ready headline statistics

1. **40,363** arXiv submissions in September 2026, a record and double September 2024 (20,569). *Source:* arXiv blog, 1 October 2026. *Confidence:* High. *Caveat:* not all growth is AI-driven.
2. **2 per month:** arXiv's submission cap per submitter since 1 October 2026. *Source:* arXiv blog. *Confidence:* High. *Caveat:* described as a stopgap.
3. **4% → 25%:** share of arXiv mathematics papers acknowledging AI, April to August 2026. *Source:* Academy for the Mathematical Sciences, October 2026. *Confidence:* Medium–High. *Caveat:* acknowledgement is not the same as AI authorship.
4. **13 million lines, 11 days:** Claude's Lean formalisation of Fermat's Last Theorem. *Source:* Anthropic, September 2026. *Confidence:* Medium–High. *Caveat:* formalisation of a known proof, not a new theorem.
5. **10,000 agents, 88 hours:** OpenAI's forced Navier–Stokes blow-up proof. *Source:* OpenAI, 8 September 2026. *Confidence:* High (claim); Medium (significance). *Caveat:* forced case only; Clay has not accepted it; translation gap disputed.
6. **722 → 719; 42% formalised:** OpenAI's manuscript release after a day of errata. *Source:* Retraction Watch and *Science*, October 2026. *Confidence:* High. *Caveat:* figures change as the repository updates.
7. **6.5%:** share of Aletheia's graded Erdős candidates that were "meaningfully correct". *Source:* DeepMind, arXiv:2602.10177. *Confidence:* High. *Caveat:* December 2025 model; rates are likely improving.
8. **84%** of researchers use AI in their work (57% in 2024). *Source:* Wiley ExplanAItions 2025. *Confidence:* High. *Caveat:* self-selected survey; 2025 data.
9. **57%** of researchers say lack of guidelines and training is a barrier. *Source:* Wiley 2025. *Confidence:* High. *Caveat:* as above.
10. **20×:** planned UK AI Research Resource expansion by 2030; Isambard-AI calls offer up to 1.4 million GPU-hours per project. *Source:* DSIT / GOV.UK, 2026. *Confidence:* High. *Caveat:* competitive allocation.
11. **97.2%:** GenCast beat ECMWF's ensemble on 97.2% of targets; ECMWF now runs AI forecasts operationally. *Source:* *Nature* 637; ECMWF. *Confidence:* High. *Caveat:* runs alongside physics models, not instead of them.
12. **36 of 57:** A-Lab's corrected synthesis count after *Nature*'s January 2026 correction (originally 41 of 58, "novel" dropped). *Source:* *Nature* 650. *Confidence:* High. *Caveat:* use it as the honest counterweight slide.

---

## 8. Narrative arc and slide titles (20 minutes)

**Arc:** something real happened → here is why maths went first → it is spreading by the same rule → the system is straining → peers and government are moving → risks are real and manageable → what we ask for.

1. **"In 2026, AI started producing research you can check"**: open with the FLT formalisation and Navier–Stokes, framed neutrally.
2. **"Why mathematics went first: the verifier"**: explain Lean in one sentence; cheap generation plus cheap checking.
3. **"But checking the checker matters"**: the forcing loophole, the translation gap and Clay's unhurried stance.
4. **"Generation is cheap; trust is not"**: the 722 manuscripts, 3 withdrawals and 42% formalised; Aletheia's 6.5%.
5. **"The same rule in other fields"**: weather operational, algorithms in production, biology in *Nature*, materials corrected.
6. **"The research system is straining"**: arXiv doubling and cap; peer-review AI use.
7. **"Researchers are already using AI, mostly ungoverned"**: Wiley 84% and 57%; ECR-led adoption; the uneven-adoption chart.
8. **"Government and peers are moving"**: AI for Science Strategy, AIRR, Genesis Mission, campus licences.
9. **"The two-tier risk"**: internal models universities cannot access; the Leiden call for public alternatives.
10. **"What Sheffield already has"**: Stanage GPUs, `stanage-llm`, RSE, CMI, the October Research Days.
11. **"Risks we will manage"**: the two-column risk/mitigation table.
12. **"Now / Next / Later"**: the roadmap with costs and owners.
13. **"Answers for the sceptic"**: the five Q&A points.
14. **"What we are asking the Executive Team to decide today"**: approve the Now actions and a business case for Next.

**Suggested diagrams:**
- **"Generate → verify → adjudicate" pipeline:** a three-stage funnel using Aletheia's real numbers (700 → 212 → 63 → 13 → 4). It shows why verification capacity, not generation, is the bottleneck.
- **"Verifier cost vs adoption speed" matrix:** fields placed by how cheap verification is (x-axis) and how far deployment has reached (y-axis: preprint → peer-reviewed → operational). Mathematics, algorithms and weather sit top right; materials and medicine lower. This makes the core hypothesis visible.
- **arXiv monthly submissions bar chart (2016, 2024, 2026)** annotated with the October 2026 cap, a simple, robust "scale" visual.

---

## 9. Gaps and uncertainties

- **Not verified directly:** I could not fetch OpenAI's or *Science*'s pages (bot-blocked). Navier–Stokes and 722-release figures rely on Retraction Watch, *Scientific American*, *Tufts Daily* and secondary trackers that quote OpenAI's changelog. Re-check the live `openai/math` changelog before presenting.
- **Conflicting figures:** 300 (OpenAI-reported) against 162 (one secondary site) formalised results; 25 against 26 Fields Medallist signatories. Use the primary counts.
- **Likely to change before the presentation:** OpenAI errata and formalisation counts; any journal submission of the Navier–Stokes paper; Clay statements; the outcome of Harvard CMSA's "Doing Mathematics with AI Agents" workshop (21 November 2026); model prices (some introductory prices end 30 November 2026).
- **Not researched in depth:** EU (for example RAISE), China, UKRI/EPSRC and Wellcome positions; UCISA and EDUCAUSE guidance; Russell Group and N8 peers' central AI-research teams and headcounts; MIT and ETH investments; Jisc and HEPI 2026 researcher surveys; Nature or Elsevier 2026 surveys.
- **Sheffield specifics to confirm internally:**
  - the University AI strategy and research strategy text;
  - Stanage GPU totals: the Stanage Specifications page lists 104 GPUs across A100 (4 per node, NVLink), H100 PCIe (2 per node, 6 public nodes) and H100 NVL (4 per node, 94GB) nodes, and caps each user at 12 GPUs at once;
  - Bessemer status;
  - existing enterprise AI licences (Gemini, Copilot);
  - the status of the Turing partnership;
  - Research Services' view of AIRR bids.
