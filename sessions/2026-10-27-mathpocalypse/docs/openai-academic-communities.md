# Research note: OpenAI, "Working with academic communities to build scientific understanding"

**Source:** OpenAI, [Working with academic communities to build scientific understanding](https://openai.com/index/building-scientific-understanding-with-academic-communities/),
26 October 2026 (research publication, author "OpenAI")

**Added:** 19 November 2026 (from [issue #1](https://github.com/Joe-Heffer-Shef/mathpocalypse/issues/1))

> **What was checked.** This note was written from the post's full text. Automated fetches got a
> 403, so the text was copied in by hand. All the mathematical, computer-science and physics results
> below are **OpenAI's claims**. None had independent confirmation when this note was written. Each
> group's own conclusions, once published, take precedence over this summary.

## 1. A new release process: shepherds and three strategies

- **Manuscripts as "raw research data".** OpenAI describes its manuscripts as "best understood as a
  form of raw research data". To turn that data into understanding, it asked outside experts to act
  as **shepherds**, organising groups to understand each result.
- **The shepherds chose three different release strategies:**

  | Field | Strategy |
  | --- | --- |
  | Mathematics | Release the AI output and leave researchers to organise themselves (the same as the 6 Oct [bulk release](https://openai.com/index/sharing-ai-progress-in-mathematics/)) |
  | Computer science | An external group explains the result. The AI output is public for anyone to examine |
  | Physics | An external group decides on release, and the AI artefacts are **held back** while the group writes the result up itself |

- OpenAI says it does "not yet know which of these three approaches will be most useful" and asks
  for feedback.

## 2. Four principles for the collaborations

1. **Transparency.** The collaborations are public. Participants sign no NDAs and are free to
   discuss and publish.
2. **No academic credit.** "We do not seek academic credit for the discoveries produced by our
   internal models." Shepherding a result doesn't mean the shepherds discovered it.
3. **Recognition.** The groups get credit for the understanding, write-ups and materials they
   produce. They also help make sure prior work is credited properly.
4. **Independence.** Taking part is voluntary and **unpaid**. Groups speak for themselves, not for
   OpenAI.

OpenAI names the costs itself: "choosing initial shepherds necessarily shapes who gets involved
first and creates asymmetry of information."

## 3. The three claimed results

### Mathematics: local smoothing, and hence Kakeya and restriction

- **The claim.** Sogge's 1991 **local smoothing conjecture** holds in every dimension. The proof
  uses "a novel auxiliary partial differential equation".
- **What it would settle.** Local smoothing implies the **Kakeya** and **Stein restriction**
  conjectures in all dimensions.
- **Prior human work.**
  - Guth, Wang and Zhang proved the 2D case ([Annals 2020](https://annals.math.princeton.edu/2020/192-2/p06)).
  - Wang and Zahl proved 3D Kakeya in 2025.
- **Timeline.** AI output on 18 Oct, formalised in Lean on 19 Oct.
- **Released.** A [natural-language write-up](https://github.com/openai/math/blob/main/preprints/Local-smoothing-for-the-Euclidean-wave-equation-October-25-2026/paper.pdf)
  and a [Lean proof](https://github.com/openai/math/blob/main/lean/docs/079.md), both in `openai/math`.

### Computer science: "The Exponential Time Hypothesis is false"

- **The claim.** The **ETH**, widely believed and used for conditional hardness results in hundreds
  of papers, is false.
- **Timeline.** Disproof found on 16 Oct, formalised in Lean on 17 Oct.
- **Shepherds.** **Russell Impagliazzo** and **Ramamohan Paturi** (UC San Diego), who proposed ETH
  (with Francis Zane), and **Ryan Williams** (MIT).
- **What the group asked for, and OpenAI agreed to:**
  - All raw data made public, so the community can verify it independently.
  - OpenAI to **fund a conference** on what the result means for the field.
- **Released.** A [write-up](https://github.com/openai/math/blob/main/preprints/The-Exponential-Time-Hypothesis-is-False-October-25-2026/paper.pdf)
  and a [Lean proof](https://github.com/openai/math/blob/main/lean/docs/378.md).
- **OpenAI's own caveat.** Faster practical algorithms "will require significant further research".

### Physics: existence of QCD, a Standard Model completion and Yang–Mills

- **The claim.** A rigorous existence proof for interacting 4D quantum field theories with gauge
  fields and fermions. The theories covered are **QCD** and the simplest grand unified completion of
  the Standard Model.
- **Includes Yang–Mills.** The proof contains the existence of pure **Yang–Mills** theory, which is
  part of the Clay Millennium problem. It builds on Balaban's constructive QFT programme.
- **Timeline.**
  - Yang–Mills proof on 9 Sep.
  - QCD proof on 18 Sep.
  - Yang–Mills Lean formalisation finished on 16 Oct. OpenAI postponed release until the
    formalisation was done.
- **Shepherds.** **David Gross** leads, with Michael Douglas, Arthur Jaffe (co-author of the Clay
  problem statement), Igor Klebanov and Nikita Nekrasov.
- **Release.** The group is **not releasing the AI artefacts** for now.

## 4. Funding

The collaborations complement OpenAI's **$5M** contribution to the Simons Foundation's **$15M**
initiative ([Simons announcement](https://www.simonsfoundation.org/news/simons-foundation-launches-15m-effort-to-help-mathematicians-navigate-ai-era/)).
Simons manages that money and awards it for workshops, conferences and programmes. OpenAI says it is
"committed to ensuring funding for researchers to independently examine, explain, and build on" these
results.

## Relevance to the session

- **A visible response to the criticism of 6 October.** Compare it with the IAS Advisory Group's
  [recommendations](https://agmai.org/general-sep29/) (29 Sep):
  - **Partly met:** it adds more human involvement, public Lean artefacts, and dates for when each
    result was found and formalised.
  - **Not addressed:**
    - Results are still produced on an unreleased proprietary model (rec. 1).
    - There are no prompts, compute figures or failed-attempt counts (recs. 4 and 6).
    - Results are still deposited in OpenAI's own GitHub repository (rec. 2).
- **"Raw research data" is the same framing as elsewhere.** It matches 3Blue1Brown's "proofs as raw
  data" ([note](3blue1brown-better-time-for-math.md)) and Tao's
  [Math 2.0](tao-math-2-0.md): the understanding is the product, and humans build it.
- **"No academic credit"** is new and bears on the [priority disputes](claude-mathpocalypse-research-brief.md).
  - **Ask the group:** does recognition for the groups that explain a result give the credit to the
    right people? Who gets credit for the *discovery*?
- **Unpaid shepherding.** The Association for Human Mathematics (AHM) "power" critique and the
  "who pays for verification?" prompt both apply. The shepherds are unpaid, yet they are doing
  checking work that is worth a lot to OpenAI. The promised conference and the Simons money are the
  answer OpenAI offers.
- **Three strategies in one post work as a natural experiment** in releasing results. They suit an
  extension of the "What would we want?" prompt: which strategy would *your* field choose, and why?
- **Scale of the claims.** If they hold, refuting ETH would change a large part of complexity
  theory, and Yang–Mills existence is part of a second Millennium problem. The reaction will matter
  more than the post. Track the shepherd groups' statements, Lean audits of the statements (the
  [translation gap](https://arxiv.org/abs/2610.08144)), and the Clay Mathematics Institute's
  response. The Yang–Mills claim drew criticism, reportedly including from OpenAI's own
  [advisory group](https://openai.com/index/advisory-group-on-mathematics-and-ai/). This has not
  been checked against primary sources.
- **Post-session update.** This post came after the 27 October session. Use it for the next deck
  refresh.
