# Practical next steps: exercises and tools to try after the session

- **Audience:** research software engineers, data scientists and researchers. Most of them will
  not prove theorems, but all of them write or depend on code and claims that need checking.
- **Added:** 18 October 2026

The idea to take home is that **an agent generates, and a cheap, trustworthy checker decides what
to keep**. In mathematics the checker is Lean. In our day-to-day work it can be a test suite, a
computer algebra system, an SMT solver or a scoring function. The exercises below go roughly from
least to most effort. They build on the in-session "Read the certificate" activity in the
[session plan](../README.md#practical-activity--read-the-certificate-25-min).

Tool availability changes quickly. All links were checked on 18 October 2026.

## 1. Get a feel for Lean (30–60 minutes, browser only)

- **[Natural Number Game](https://adam.math.hhu.de/)** (Lean 4 Game Server). This is the standard
  introduction. You prove facts about addition and multiplication one tactic at a time and see
  what "the kernel accepted it" means.
- **[Lean 4 web editor](https://live.lean-lang.org/).** Paste in a small theorem, then break it on
  purpose: add `sorry`, add an `axiom`, and run `#print axioms`. After that, `sorry_count: 0` and
  the axiom check from Track C mean something concrete.
- **[Mathematics in Lean](https://leanprover-community.github.io/mathematics_in_lean/)**, for
  anyone who wants to continue on their own.

**Exercise: formalise a claim from your own field.** Pick something simple, for example "this
normalisation always returns values in [0, 1]", and write it as a Lean theorem *statement*. Most
people find that stating the claim is harder than proving it. This is the "translation gap" from
Bastounis, Circelli & Hansen, at a small scale.

## 2. Pair a coding agent with Lean (an afternoon)

- Install Lean with [elan](https://github.com/leanprover/elan) and give a coding agent (Claude
  Code, or similar) access to Lean through
  [lean-lsp-mcp](https://github.com/oOo0oOo/lean-lsp-mcp).
  [Numina-Lean-Agent](https://github.com/project-numina/numina-lean-agent) is a published,
  benchmarked version of the same setup. See
  [ai-mathematics-research-tools.md](ai-mathematics-research-tools.md).
- Problem sets for practice: [miniF2F (Lean 4)](https://github.com/yangky11/miniF2F-lean4),
  [PutnamBench](https://github.com/trishullab/PutnamBench) and, for the ambitious, DeepMind's
  [Formal Conjectures](https://github.com/google-deepmind/formal-conjectures).

**Exercise: keep a lab notebook of the agent.** Ask it to prove a handful of lemmas and record the
attempts, dead ends, any `sorry` or `axiom` it tries to slip in, and whether it ever *weakens the
statement* to make it provable. That last behaviour is the forcing loophole at small scale.

**Exercise: autoformalise a proof you know well.** Take a short, rigorous argument from a paper or
textbook in your area and ask the agent to formalise it. Then check whether the Lean statement says
what the paper says. Have a colleague review it without seeing the original.

## 3. Use the verifier idea on research code (most relevant for RSEs)

This transfers most directly to everyday work.

- **Property-based testing** with [Hypothesis](https://hypothesis.readthedocs.io/) (Python) or
  [proptest](https://github.com/proptest-rs/proptest) (Rust). Let an agent write or refactor a
  numerical function, and let properties be the judge: invariants, round-trips, conservation laws,
  symmetry, and agreement with a slow but obviously correct reference implementation. This is the
  closest everyday equivalent of "checked by Lean".
- **Lightweight formal tools.** [CrossHair](https://github.com/pschanely/CrossHair) checks Python
  contracts and type hints symbolically. [Z3](https://github.com/Z3Prover/z3) handles
  constraint-style claims. [Dafny](https://dafny.org/), [Verus](https://github.com/verus-lang/verus)
  and [Kani](https://github.com/model-checking/kani) are options for anyone writing verified or
  Rust code.
- **Computer algebra as a checker.** Ask an LLM for a closed form, derivative, integral or series
  expansion, then verify it with SymPy, [SageMath](https://www.sagemath.org/) or high-precision
  numerics in [mpmath](https://mpmath.org/).

**Exercise: spec or code?** Ask an agent to write a verified binary search or sort in Dafny. Count
how often the *specification* is wrong or too weak, compared with how often the code is.

**Exercise: plausible but wrong.** Collect ten closed-form answers from an LLM in your area and
check each one by machine. How many were wrong but looked right?

## 4. Generate-and-score search (for data scientists)

- [OpenEvolve](https://github.com/codelion/openevolve) and
  [ShinkaEvolve](https://github.com/SakanaAI/ShinkaEvolve) are open-source systems in the style of
  AlphaEvolve and FunSearch. You supply a seed program and a scoring function, and an LLM evolves
  the code.

**Exercise: evolve against your own objective.** Pick a problem with a computable score, such as a
packing, a scheduling heuristic from your own work, a faster kernel or a rule for setting
hyperparameters. Run a small evolution loop and ask two questions. Did the score improve? Did it
improve by **gaming the evaluator**? The second question is the general lesson about scorers, and
it applies to every ML evaluation.

## 5. Audit, triage and disclose (no code; good for researchers)

**Exercise: a longer Track B.** Pick one [`openai/math`](https://github.com/openai/math) result
family close to someone's field and spend an hour deciding whether it is *correct* and whether it
is *new*. Time it, then multiply by 722 manuscripts.

**Exercise: write a disclosure card** for a piece of your own AI-assisted work. Base it on
Aletheia's "human–AI interaction cards" and the IAS checklist: model, prompts, compute, number of
failed attempts, and what was checked by whom. A good result could become a group template.

**Exercise: find the verifier gap.** Each person names one claim in their research that a machine
can check cheaply and one that no machine can check. This leads into the
[research certificates session](https://github.com/RSE-Sheffield/Agents-Reading-Group/blob/main/sessions/2026-11-10-research-certificates.md) on 10 November.

## 6. Possible follow-up sessions

- **Hands-on Lean with an agent**: a workshop version of sections 1–2, pairing well with the
  [Harmonic Aristotle idea](https://github.com/RSE-Sheffield/Agents-Reading-Group/blob/main/ideas/mathematics-harmonic-aristotle.md).
- **"Property-based testing is the RSE's Lean"**: a practical session on verifiers for scientific
  code, linked to the
  [formal verification in physics & engineering idea](https://github.com/RSE-Sheffield/Agents-Reading-Group/blob/main/ideas/formal-verification-physics-engineering.md).
- **Evolutionary search hack session**: OpenEvolve on problems the group brings along.
