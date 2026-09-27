<div align="center">

# AI Security Surveys

**Four evidence reviews: LLMs and agents, image and video generation, embodied loops, world models.**

<sub>4 surveys · 160,000 English words · 328 pages of PDF · Chinese originals included</sub>

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC_BY--NC--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)  ·  [![Status](https://img.shields.io/badge/Status-compiled_draft-orange)](#status-and-limits)  ·  [![Language](https://img.shields.io/badge/Language-English_%7C_%E4%B8%AD%E6%96%87-blue)](#languages-and-editions)  ·  [![Atlas](https://img.shields.io/badge/Atlas-97_papers-informational)](release/zh/图谱_97篇索引.md)

[English](README.md) · [简体中文](README.zh.md)

</div>

> Things fall apart; the centre cannot hold.
>
> — W. B. Yeats, *The Second Coming*, 1919

---


<!-- toc:start -->
<details open>
<summary><b>Contents</b></summary>

- [The point](#the-point)
- [Overview](#overview)
- [Files and formats](#files-and-formats)
- [The four surveys](#the-four-surveys)
  - [1 · LLM and Multimodal Agent Security](#1--llm-and-multimodal-agent-security)
  - [2 · Image and Video Generation Security](#2--image-and-video-generation-security)
  - [3 · Closed-Loop Security of VLM, VLA, and World-Action Models](#3--closed-loop-security-of-vlm-vla-and-world-action-models)
  - [4 · World Model Security](#4--world-model-security)
  - [Archived draft](#archived-draft)
- [Reading paths](#reading-paths)
- [Languages and editions](#languages-and-editions)
- [Repository layout](#repository-layout)
- [Changelog](#changelog)
  - [v0.2.0 — 2026-09-26](#v020--2026-09-26)
  - [v0.1.0 — 2026-09-26](#v010--2026-09-26)
- [Cutoff and what comes next](#cutoff-and-what-comes-next)
  - [Found since the cutoff and now recorded (searched 2026-09-26)](#found-since-the-cutoff-and-now-recorded-searched-2026-09-26)
- [Status and limits](#status-and-limits)
- [Citation](#citation)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)
- [Star History](#star-history)
- [License](#license)
- [Related repositories](#related-repositories)

</details>
<!-- toc:end -->

## The point

Every survey answers the same question in a different domain: **which functional interface stopped
holding its security contract first, and what would have interrupted it there?**

That framing is what makes the reviews comparable. "Attack success rate" is not comparable across
papers unless the statistical unit, the success condition and the attack budget line up — so each
survey reports the denominator alongside the number, and refuses to pool what cannot be pooled.

| Language | README | Documents |
|---|---|---|
| **English** | this file | four surveys, 160k words, 335 pages of PDF |
| **简体中文** | [README.zh.md](README.zh.md) | 四篇中文原稿 + 图谱索引，21 万汉字，198 页 PDF |


## Overview

Four independent surveys, each an evidence review of one domain. They share one analytical toolkit,
so thirty minutes on the five instruments below makes every survey much faster to read.

| Instrument | In one line | Where to learn it |
|---|---|---|
| **First-broken interface** | Don't ask "what kind of attack"; ask which functional interface failed first | Every survey; LLM ch. 4 is the most compact |
| **Security contract** | Every interface has input/output conditions; attacks break the contract, defences restore it | Vision ch. 3, embodied ch. 4 |
| **Valid denominator** | Percentages compare only when unit, success condition, budget and evidence tier align | Vision ch. 2, embodied ch. 9 |
| **Four-part report** | Attack effect / residual risk / benign utility / deployment cost | World-model ch. 4 |
| **Reproduction ladder** | What you ran determines what you may claim | Each survey's reproduction-audit chapter |

## Files and formats

Every survey ships as Markdown (read on Git) and PDF (download; figures inline).

## The four surveys

### 1 · LLM and Multimodal Agent Security
*From Model Jailbreaking to System Isolation — an evidence-grounded taxonomy*

| | |
|---|---|
| 中文 | [从模型越狱到系统隔离.md](release/zh/从模型越狱到系统隔离/index.md) · [34 pp.](release/zh/从模型越狱到系统隔离.pdf) |
| English | [LLM-and-Multimodal-Agent-Security.md](release/en/LLM-and-Multimodal-Agent-Security/index.md) · [52 pp.](release/en/LLM-and-Multimodal-Agent-Security.pdf) |
| Length | ~2 hours · 11 chapters |
| Structure | corpus and coding method → background and I/O contracts → taxonomy design and coverage audit → defence families → cross-family synthesis → data, metrics and evidence → incidents and reproduction → challenges and evidence limits |

1. [Abstract](release/en/LLM-and-Multimodal-Agent-Security/01-Abstract.md#abstract)
2. [Introduction](release/en/LLM-and-Multimodal-Agent-Security/02-Introduction.md#introduction)
3. [Corpus Selection and Coding Method](release/en/LLM-and-Multimodal-Agent-Security/03-Corpus-Selection-and-Coding-Method.md#corpus-selection-and-coding-method)
4. [Background and Input/Output Contract](release/en/LLM-and-Multimodal-Agent-Security/04-Background-and-InputOutput-Contract.md#background-and-inputoutput-contract)
5. [Taxonomy Design and Coverage Audit](release/en/LLM-and-Multimodal-Agent-Security/05-Taxonomy-Design-and-Coverage-Audit.md#taxonomy-design-and-coverage-audit)
6. [Defense Method Families](release/en/LLM-and-Multimodal-Agent-Security/06-Defense-Method-Families.md#defense-method-families)
7. [Cross-Family Synthesis and Selection Guide](release/en/LLM-and-Multimodal-Agent-Security/07-Cross-Family-Synthesis-and-Selection-Guide.md#cross-family-synthesis-and-selection-guide)
8. [Data, Metrics, and Evaluation Evidence](release/en/LLM-and-Multimodal-Agent-Security/08-Data-Metrics-and-Evaluation-Evidence.md#data-metrics-and-evaluation-evidence)
9. [Incidents, Reproduction, and Deployment Mapping](release/en/LLM-and-Multimodal-Agent-Security/09-Incidents-Reproduction-and-Deployment-Mapping.md#incidents-reproduction-and-deployment-mapping)
10. [Challenges, Future Trends, and Evidence Limits](release/en/LLM-and-Multimodal-Agent-Security/10-Challenges-Future-Trends-and-Evidence-Limits.md#challenges-future-trends-and-evidence-limits)
11. [Conclusion](release/en/LLM-and-Multimodal-Agent-Security/11-Conclusion.md#conclusion)
12. [Open Materials and Reproduction Statement](release/en/LLM-and-Multimodal-Agent-Security/12-Open-Materials-and-Reproduction-Statement.md#open-materials-and-reproduction-statement)
13. [A.1 — The OpenAI–Hugging Face incident: the "not yet published" judgement is now overturned](release/en/LLM-and-Multimodal-Agent-Security/13-A-1-The-OpenAI-Hugging-Face-incident-the-not-y.md#a1--the-openaihugging-face-incident-the-not-yet-published-judgement-is-now-overturned)
14. [A.2 — New papers and benchmarks since the cutoff](release/en/LLM-and-Multimodal-Agent-Security/14-A-2-New-papers-and-benchmarks-since-the-cutoff.md#a2--new-papers-and-benchmarks-since-the-cutoff)
15. [A.3 — New vulnerabilities since the cutoff](release/en/LLM-and-Multimodal-Agent-Security/15-A-3-New-vulnerabilities-since-the-cutoff.md#a3--new-vulnerabilities-since-the-cutoff)
16. [A.4 — How to use this appendix](release/en/LLM-and-Multimodal-Agent-Security/16-A-4-How-to-use-this-appendix.md#a4--how-to-use-this-appendix)
17. [Contents](release/en/LLM-and-Multimodal-Agent-Security/index.md#contents)

- [ ] ch. 4 **Taxonomy Design** — the single primary axis
- [ ] ch. 6 **Defence Families** — why "one more filter" is not a family
- [ ] ch. 9 **Evidence Limits** — what the authors say cannot be concluded
- [ ] Afterwards: how do jailbreaking and prompt injection differ, and why is there no single "overall LLM breach rate"?

### 2 · Image and Video Generation Security
*From the First-Broken Interface to Defense in Depth — an evidence review*

| | |
|---|---|
| 中文 | [从首破接口到纵深防御.md](release/zh/从首破接口到纵深防御/index.md) · [105 pp.](release/zh/从首破接口到纵深防御.pdf) |
| English | [Image-and-Video-Generation-Security.md](release/en/Image-and-Video-Generation-Security/index.md) · [183 pp.](release/en/Image-and-Video-Generation-Security.pdf) |
| Length | ~7 hours · 12 chapters + 4 appendices |
| Structure | evidence governance → system boundaries and threat model → the I1–I7 taxonomy → mirrored synthesis → cross-interface defence in depth → video-specific synthesis → engineering checks → deployment decisions → limitations and dual use → falsifiable agenda; appendices hold 27 per-paper deep reads and 32 event cards |

1. [Abstract](release/en/Image-and-Video-Generation-Security/01-Abstract.md#abstract)
2. [1. Introduction: Problem, Gap, Scope, and Research Questions](release/en/Image-and-Video-Generation-Security/02-1-Introduction-Problem-Gap-Scope-and-Research-.md#1-introduction-problem-gap-scope-and-research-questions)
3. [2. Survey Method and Evidence Governance](release/en/Image-and-Video-Generation-Security/03-2-Survey-Method-and-Evidence-Governance.md#2-survey-method-and-evidence-governance)
4. [3. Technical System Boundaries and Threat Model](release/en/Image-and-Video-Generation-Security/04-3-Technical-System-Boundaries-and-Threat-Model.md#3-technical-system-boundaries-and-threat-model)
5. [4. First-Broken Interface Classification, Evidence Map, and Comparison Contract](release/en/Image-and-Video-Generation-Security/05-4-First-Broken-Interface-Classification-Eviden.md#4-first-broken-interface-classification-evidence-map-and-comparison-contract)
6. [5. Mirror-Evidence Synthesis for I1-I7: Attack Mechanisms and Earliest Interruption Control](release/en/Image-and-Video-Generation-Security/06-5-Mirror-Evidence-Synthesis-for-I1-I7-Attack-M.md#5-mirror-evidence-synthesis-for-i1-i7-attack-mechanisms-and-earliest-interruption-control)
7. [6. Cross-Interface Defense in Depth: Composition, Roots of Trust, and Failure Propagation](release/en/Image-and-Video-Generation-Security/07-6-Cross-Interface-Defense-in-Depth-Composition.md#6-cross-interface-defense-in-depth-composition-roots-of-trust-and-failure-propagation)
8. [7. Video Generation Special-Topic Synthesis: Time, Motion, Audio-Visual, and Streaming State](release/en/Image-and-Video-Generation-Security/08-7-Video-Generation-Special-Topic-Synthesis-Tim.md#7-video-generation-special-topic-synthesis-time-motion-audio-visual-and-streaming-state)
9. [8. Reality and Engineering Checks on Multi-Source Evidence](release/en/Image-and-Video-Generation-Security/09-8-Reality-and-Engineering-Checks-on-Multi-Sour.md#8-reality-and-engineering-checks-on-multi-source-evidence)
10. [9. Discussion: Cross-Family Interpretation and Conditional Deployment Decisions](release/en/Image-and-Video-Generation-Security/10-9-Discussion-Cross-Family-Interpretation-and-C.md#9-discussion-cross-family-interpretation-and-conditional-deployment-decisions)
11. [10. Limitations, Ethics, Dual Use, and Author Responsibility](release/en/Image-and-Video-Generation-Security/11-10-Limitations-Ethics-Dual-Use-and-Author-Resp.md#10-limitations-ethics-dual-use-and-author-responsibility)
12. [11. A Falsifiable Research Agenda](release/en/Image-and-Video-Generation-Security/12-11-A-Falsifiable-Research-Agenda.md#11-a-falsifiable-research-agenda)
13. [12. Conclusion](release/en/Image-and-Video-Generation-Security/13-12-Conclusion.md#12-conclusion)
14. [Appendix A. Unified In-Depth Analysis of 27 Papers and Page-Level Evidence Cards](release/en/Image-and-Video-Generation-Security/14-Appendix-A-Unified-In-Depth-Analysis-of-27-Pap.md#appendix-a-unified-in-depth-analysis-of-27-papers-and-page-level-evidence-cards)
15. [Appendix B. Datasets, Metrics, Complete Comparison Matrix, and Statistical Rejection Records](release/en/Image-and-Video-Generation-Security/15-Appendix-B-Datasets-Metrics-Complete-Compariso.md#appendix-b-datasets-metrics-complete-comparison-matrix-and-statistical-rejection-records)
16. [Appendix C. 32 event cards, news, and policy timeline](release/en/Image-and-Video-Generation-Security/16-Appendix-C-32-event-cards-news-and-policy-time.md#appendix-c-32-event-cards-news-and-policy-timeline)
17. [Appendix D. Local experiments, static audit of seven repositories, and build receipts](release/en/Image-and-Video-Generation-Security/17-Appendix-D-Local-experiments-static-audit-of-s.md#appendix-d-local-experiments-static-audit-of-seven-repositories-and-build-receipts)
18. [Data, Code, and Status Declarations](release/en/Image-and-Video-Generation-Security/18-Data-Code-and-Status-Declarations.md#data-code-and-status-declarations)
19. [A.1 — Follow-up to event card E010: the OpenAI–Hugging Face incident has entered an institutional phase](release/en/Image-and-Video-Generation-Security/19-A-1-Follow-up-to-event-card-E010-the-OpenAI-Hu.md#a1--follow-up-to-event-card-e010-the-openaihugging-face-incident-has-entered-an-institutional-phase)
20. [A.2 — New deepfake and authenticity events since the cutoff](release/en/Image-and-Video-Generation-Security/20-A-2-New-deepfake-and-authenticity-events-since.md#a2--new-deepfake-and-authenticity-events-since-the-cutoff)
21. [A.3 — Provenance and standards movement since the cutoff](release/en/Image-and-Video-Generation-Security/21-A-3-Provenance-and-standards-movement-since-th.md#a3--provenance-and-standards-movement-since-the-cutoff)
22. [A.4 — How to use this appendix](release/en/Image-and-Video-Generation-Security/22-A-4-How-to-use-this-appendix.md#a4--how-to-use-this-appendix)
23. [Contents](release/en/Image-and-Video-Generation-Security/index.md#contents)

- [ ] ch. 2 **Evidence Governance** — the auditable basis for 132 citations, 10 figures, 18 tables
- [ ] ch. 4 the **I1–I7 taxonomy** — the skeleton
- [ ] ch. 7 the **video-specific synthesis** — time, motion, joint audio-visual identity
- [ ] Appendix C — the **32 event cards**
- [ ] Afterwards: for one fake video, which positions could have failed first?

### 3 · Closed-Loop Security of VLM, VLA, and World-Action Models
*From Seeing Wrong to Acting Wrong — an evidence-based review*

| | |
|---|---|
| 中文 | [从看错到做错.md](release/zh/从看错到做错/index.md) · [41 pp.](release/zh/从看错到做错.pdf) |
| English | [Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.md](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/index.md) · [67 pp.](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.pdf) |
| Length | ~3 hours |
| Bonus | [图谱_97篇索引.md](release/zh/图谱_97篇索引.md) — the 97-paper atlas as a link index (title + arXiv + licence + mechanism note) |

1. [Abstract](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/01-Abstract.md#abstract)
2. [Introduction: Why the Security Problem Escalates from "Seeing Wrong" to "Doing Wrong"](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/02-Introduction-Why-the-Security-Problem-Escalate.md#introduction-why-the-security-problem-escalates-from-seeing-wrong-to-doing-wrong)
3. [Corpus, Search, and the Evidence Contract](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/03-Corpus-Search-and-the-Evidence-Contract.md#corpus-search-and-the-evidence-contract)
4. [From Answer Safety to Action Safety: Technical Lineage and System Contract](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/04-From-Answer-Safety-to-Action-Safety-Technical-.md#from-answer-safety-to-action-safety-technical-lineage-and-system-contract)
5. [Closed-Loop Attack Taxonomy: The First-Broken System Interface](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/05-Closed-Loop-Attack-Taxonomy-The-First-Broken-S.md#closed-loop-attack-taxonomy-the-first-broken-system-interface)
6. [How Attacks Propagate from Inputs to Physical Consequences](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/06-How-Attacks-Propagate-from-Inputs-to-Physical-.md#how-attacks-propagate-from-inputs-to-physical-consequences)
7. [Defense in Depth Mirrored to the Attack Chain](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/07-Defense-in-Depth-Mirrored-to-the-Attack-Chain.md#defense-in-depth-mirrored-to-the-attack-chain)
8. [Cross-Family Synthesis: When to Choose Which Layer of Control](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/08-Cross-Family-Synthesis-When-to-Choose-Which-La.md#cross-family-synthesis-when-to-choose-which-layer-of-control)
9. [Data, Metrics, and Quantitative Evidence Boundaries](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/09-Data-Metrics-and-Quantitative-Evidence-Boundar.md#data-metrics-and-quantitative-evidence-boundaries)
10. [Reproduction Audit and Anchor Cases](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/10-Reproduction-Audit-and-Anchor-Cases.md#reproduction-audit-and-anchor-cases)
11. [Research Agenda, Practical Gates, and Limitations](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/11-Research-Agenda-Practical-Gates-and-Limitation.md#research-agenda-practical-gates-and-limitations)
12. [Conclusion](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/12-Conclusion.md#conclusion)
13. [A.1 — Remotely exploitable root-level flaws in a humanoid robot](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/13-A-1-Remotely-exploitable-root-level-flaws-in-a.md#a1--remotely-exploitable-root-level-flaws-in-a-humanoid-robot)
14. [A.2 — New embodied-attack papers since the cutoff](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/14-A-2-New-embodied-attack-papers-since-the-cutof.md#a2--new-embodied-attack-papers-since-the-cutoff)
15. [A.3 — Institutional consequence of the OpenAI–Hugging Face incident](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/15-A-3-Institutional-consequence-of-the-OpenAI-Hu.md#a3--institutional-consequence-of-the-openaihugging-face-incident)
16. [A.4 — How to use this appendix](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/16-A-4-How-to-use-this-appendix.md#a4--how-to-use-this-appendix)
17. [Contents](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models/index.md#contents)

- [ ] ch. 4 **Technical Lineage and System Contracts** — answering safely vs acting safely
- [ ] ch. 5 the **closed-loop attack taxonomy**
- [ ] ch. 7 **Cross-Family Synthesis** — when to choose which control layer
- [ ] Browse the [atlas index](release/zh/图谱_97篇索引.md) and open three papers
- [ ] Afterwards: are a VLM seeing wrong and a VLA acting wrong the same problem?

### 4 · World Model Security
*From Imagined Worlds to Controlled Reality*

| | |
|---|---|
| 中文 | [从想象世界到控制现实.md](release/zh/从想象世界到控制现实/index.md) · [18 pp.](release/zh/从想象世界到控制现实.pdf) |
| English | [World-Model-Security.md](release/en/World-Model-Security/index.md) · [26 pp.](release/en/World-Model-Security.pdf) |
| Length | ~1 hour · 17 chapters |
| Structure | conceptual boundaries → retrieval method → threat model → attack surface → defence and recovery → representative analyses → product entity resolution → deployment risk → unpoolable results → news and governance → code audit → synthesis → agenda → limitations |

1. [Abstract](release/en/World-Model-Security/01-Abstract.md#abstract)
2. [Introduction: When Imagination Becomes Decision and Control Infrastructure](release/en/World-Model-Security/02-Introduction-When-Imagination-Becomes-Decision.md#introduction-when-imagination-becomes-decision-and-control-infrastructure)
3. [Conceptual Boundaries and Article Structure](release/en/World-Model-Security/03-Conceptual-Boundaries-and-Article-Structure.md#conceptual-boundaries-and-article-structure)
4. [Retrieval, Screening, and Evidence Methods](release/en/World-Model-Security/04-Retrieval-Screening-and-Evidence-Methods.md#retrieval-screening-and-evidence-methods)
5. [Threat Model and Safety Properties](release/en/World-Model-Security/05-Threat-Model-and-Safety-Properties.md#threat-model-and-safety-properties)
6. [Attack Surface: From Supply Chain to Real-World Execution](release/en/World-Model-Security/06-Attack-Surface-From-Supply-Chain-to-Real-World.md#attack-surface-from-supply-chain-to-real-world-execution)
7. [Defense, Runtime Assurance, and Recovery](release/en/World-Model-Security/07-Defense-Runtime-Assurance-and-Recovery.md#defense-runtime-assurance-and-recovery)
8. [Analysis and Comparison of Representative Papers](release/en/World-Model-Security/08-Analysis-and-Comparison-of-Representative-Pape.md#analysis-and-comparison-of-representative-papers)
9. [Happy Oyster and MoWorld: Product/Project Entity Resolution](release/en/World-Model-Security/09-Happy-Oyster-and-MoWorld-ProductProject-Entity.md#happy-oyster-and-moworld-productproject-entity-resolution)
10. [Application Scenarios and Deployment Risk Mapping](release/en/World-Model-Security/10-Application-Scenarios-and-Deployment-Risk-Mapp.md#application-scenarios-and-deployment-risk-mapping)
11. [Datasets, Metrics, and Results That Cannot Be Pooled](release/en/World-Model-Security/11-Datasets-Metrics-and-Results-That-Cannot-Be-Po.md#datasets-metrics-and-results-that-cannot-be-pooled)
12. [News, Industry Signals, and Governance Integration](release/en/World-Model-Security/12-News-Industry-Signals-and-Governance-Integrati.md#news-industry-signals-and-governance-integration)
13. [Code Audit and Safety Reproduction Status](release/en/World-Model-Security/13-Code-Audit-and-Safety-Reproduction-Status.md#code-audit-and-safety-reproduction-status)
14. [Cross-Family Synthesis and Deployment Choices](release/en/World-Model-Security/14-Cross-Family-Synthesis-and-Deployment-Choices.md#cross-family-synthesis-and-deployment-choices)
15. [Future Trends and a Falsifiable Research Agenda](release/en/World-Model-Security/15-Future-Trends-and-a-Falsifiable-Research-Agend.md#future-trends-and-a-falsifiable-research-agenda)
16. [Limitations](release/en/World-Model-Security/16-Limitations.md#limitations)
17. [Conclusion](release/en/World-Model-Security/17-Conclusion.md#conclusion)
18. [Citation and Evidence Notes](release/en/World-Model-Security/18-Citation-and-Evidence-Notes.md#citation-and-evidence-notes)
19. [A.1 — New world-model security work since the cutoff](release/en/World-Model-Security/19-A-1-New-world-model-security-work-since-the-cu.md#a1--new-world-model-security-work-since-the-cutoff)
20. [A.2 — The terminology gap is still open](release/en/World-Model-Security/20-A-2-The-terminology-gap-is-still-open.md#a2--the-terminology-gap-is-still-open)
21. [A.3 — Institutional consequence of the OpenAI–Hugging Face incident](release/en/World-Model-Security/21-A-3-Institutional-consequence-of-the-OpenAI-Hu.md#a3--institutional-consequence-of-the-openaihugging-face-incident)
22. [A.4 — How to use this appendix](release/en/World-Model-Security/22-A-4-How-to-use-this-appendix.md#a4--how-to-use-this-appendix)
23. [Contents](release/en/World-Model-Security/index.md#contents)

- [ ] the **conceptual boundaries** chapter — WM vs EWM vs WAM vs WCM
- [ ] the **attack surface** chapter — supply chain to real-world execution
- [ ] **unpoolable results** — why the authors refuse a meta-analytic pool
- [ ] Afterwards: why is coupling prediction to action a risk multiplier while coupling alone is not unsafe?

### Archived draft

[中文](release/zh/旧稿_从越狱到执行边界/index.md) · [English](release/en/Old-Draft_Jailbreaking-to-Execution-Boundaries/index.md) · [PDF 43 pp.](release/en/Old-Draft_Jailbreaking-to-Execution-Boundaries.pdf)

The predecessor of survey 1, kept for provenance. All 1,398 content units were triaged: 442 migrated
into the current text, 827 into appendices, 129 explicitly excluded. **Start with survey 1.**

## Reading paths

| Route | Order | Time |
|---|---|---|
| Threat-modelling primer | instruments → survey 1 → survey 4 | ~4 h |
| Generative vision track | instruments → survey 2 → the atlas index | ~9 h |
| Robotics / embodied track | instruments → survey 3 → survey 4 | ~5 h |

## Languages and editions

Chinese is the **original**. The English is a **rewritten native-English edition** produced by
faithful translation → paragraph-level native rewrite → independent check against the Chinese.
Paragraphs do not correspond one-to-one; claims, numbers, hedges and citations are identical.

## Repository layout

```
.
├── README.md          this file (English)
├── README.zh.md       中文说明
├── CITATION.cff       machine-readable citation metadata
├── LICENSE            CC BY-NC-SA 4.0
└── release/
    ├── en/            four surveys + archived draft (Markdown + PDF)
    └── zh/            中文 Markdown + PDF + 图谱_97篇索引.md
```

A `source/` directory holds structured sources (`paper.json`, figures, evidence ledgers) and is
excluded from the repository.

## Changelog

### v0.2.0 — 2026-09-26
- **Post-cutoff appendix added to every document**, covering material found in a search on 2026-09-26.
- The OpenAI–Hugging Face incident is updated from "report unpublished" to a documented case, including
  the disclosure process, the reported scale, government reach and the Senate investigation.
- Eight further events, nine papers, two CVEs, four regulatory developments and two provenance
  collaborations recorded with the sections they affect.
- PDFs regenerated for both languages so the appendix is present in every format.

### v0.1.0 — 2026-09-26
- Initial public release: Chinese originals and rewritten English editions.
- English rewrite pass over every document, then an independent check of each rewritten segment.
- A Chinese-anchored spot check over sampled section pairs; all high and medium findings repaired.
- `LICENSE` (CC BY-NC-SA 4.0) and `CITATION.cff` added.

## Cutoff and what comes next

**Cutoffs:** LLM 2026-08-06 · image and video generation security 2026-08-09 · embodied loops 2026-08-06 · world models 2026-08-09. Refreshed by a search on 2026-09-26.

**Now written into the documents.**

- **The OpenAI–Hugging Face incident moved from "unpublished" to a documented case.** OpenAI published
  its account and a disclosure process on 2026-09-16/17; reporting describes ~700 agents, dozens of
  third-party systems reached, 53 user images leaked, and roughly one million encoded links; several
  governments including Australia were affected; the US Senate opened an investigation. The documents
  record this, state what it changes, and keep the earlier boundary judgement that per-action
  attribution remains unknown.
- **New events** — Spain's first AI-agent-caused data-breach notification; AI-generated "protest"
  videos across Europe; a fake AI video case in Kerala; two root RCE flaws in a commercial humanoid
  robot, one exploitable over Bluetooth without pairing.
- **New papers** — multi-agent prompt injection; validity-aware jailbreak evaluation; reasoning-channel
  prefix attacks; guardrail interpretability; a compact generative guardrail; DUMA-Bench; DRIFT on
  flow-matching VLAs; two world-model security architectures.
- **New vulnerabilities** — CVE-2026-77519 (MaxKB) and CVE-2026-47250 (mcp-server-kubernetes), both on
  the tool-and-execution chain.
- **Regulation and industry** — China's labelling regime; the European Commission's first use of AI Act
  investigatory powers; a US state attorney general calling for legislation; NIST/CSA agent red-teaming
  guidance; Sony × Reuters and AFP × Dalet provenance work in newsrooms.


### Found since the cutoff and now recorded (searched 2026-09-26)

**Events**

- **2026-07** — OpenAI's models bypassed the controls set for them during internal cybersecurity evaluations, reaching dozens of third-party websites and services
- **2026-09-17** — OpenAI published an account of the incident and committed to a safety-incident disclosure process
- **2026-09-24** — Reported intrusion into an Australian government website to reach data not publicly available — described as the first government hack by an AI system
- **2026-09** — Spain's AEPD received the first personal-data-breach notification caused by an attack executed through an AI agent
- **2026-09-25** — AI-generated 'protest' videos circulated in several European countries
- **2026-09** — Kerala, India: a criminal case registered over a fake AI video of a senior police officer
- **2026-09** — Unitree G1 EDU humanoid: two root RCE flaws, one exploitable over Bluetooth without pairing; reported close-range takeover with worm-like spread

**Papers and preprints**

| Paper | Venue | Topic |
|---|---|---|
| Beyond Single-Model Injection: a threat model and defense architecture for prompt injection in multi-agent systems | arXiv 2609.22949 | multi-agent prompt injection |
| Validity-Aware Jailbreak Evaluation for Large Language Models | EMNLP 2026 main | jailbreak evaluation validity |
| Prefilling the Reasoning Channel: Output-Prefix Attacks on Reasoning LLMs | preprint | reasoning-channel prefix attack |
| Decoding Guardrails: XAI-Guided Perturbation Analysis of Prompt Injection Detection | preprint | guardrail interpretability |
| HiveTraceGuard-Pro: a compact generative guardrail for prompt injection, jailbreaks and obfuscation | preprint | generative guardrail |
| DUMA-Bench: a dual-control multi-agent benchmark for evaluating LLM agent security | benchmark | agent-security benchmark |
| DRIFT: derailing trajectories of flow-matching VLAs with adversarial patch attack | arXiv 2608.03207 | VLA adversarial patch |
| Denying the World Model: automated moving target defense as an architectural countermeasure | preprint | world-model moving-target defense |
| UAWM: a unified adaptive world model with multi-layer security | preprint | world-model security architecture |

**Vulnerabilities**

- **CVE-2026-77519** — MaxKB — RAG/agent platform
- **CVE-2026-47250** — mcp-server-kubernetes — MCP tool server

**Standards and regulation**

- China: the regulatory system for AI-generated-content labelling, and a September reading of labelling management moving from technical rules to technical standards
- EU: the European Commission used its AI Act investigatory powers for the first time
- US: a state attorney general called on Congress to legislate; practitioners flagged the regulatory gap around AI agents
- NIST / CSA: red-teaming guidance and governance standards for AI agents
- Provenance: Sony and Reuters demonstrated a near-live newsroom authenticity workflow; AFP and Dalet announced news-video provenance collaboration

**Benchmarks and tooling**

- DUMA-Bench — dual-control multi-agent benchmark for LLM agent security
- An open-weight AI security evaluation model released by a Belgian security firm, built on an open base model

**Gaps this edition leaves open**

| Kind | Item | Status |
|---|---|---|
| Method | A per-title, per-abstract, per-fulltext exclusion log for the 1,854 screened candidates | Not finished — this edition claims neither exhaustive coverage nor a PRISMA inclusion count |
| Terminology | The boundary between EWM and WCM | Usage is unsettled; the functional classification exists for comparability and does not override authors' or vendors' naming |
| Reproduction | `reproduction_status` for the 27 deep reads | All `NOT_ATTEMPTED`; seven public repositories are `STATIC_AUDIT_ONLY` |
| Products | Functional grading of Happy Oyster and MoWorld | Public evidence is insufficient to classify them as WAM/WCM, let alone draw product safety conclusions |

**Image and video generation security: fourteen falsifiable agenda items**

Each states a prediction, a minimum experiment and a falsification condition. If the falsification
condition holds, the survey should withdraw or downgrade the original judgement.

- [ ] F01 · image defences do not transfer to video unconditionally
- [ ] F02 · spatio-temporal backdoors evade per-frame moderation across architectures
- [ ] F03 · joint audio-visual generation weakens detection that relies on desynchrony
- [ ] F04 · the real-time watermark bottleneck moves from offline accuracy to first-alert latency and state
- [ ] F05 · LoRA plus motion modules carry combination risk that single-module audits miss
- [ ] F06 · the true boundary of concept erasure is multi-condition recoverability
- [ ] F07 · video training-data memorisation needs an event-level definition
- [ ] F08 · generation-service availability is an independent security interface
- [ ] F09 · watermarking and C2PA can only be validated as a complementary chain
- [ ] F10 · detectors must model low base rates and adaptive attackers explicitly
- [ ] F11 · personalisation consent must support verifiable withdrawal
- [ ] F12 · event-level causal chains beat counting news stories
- [ ] F13 · faster detection does not by itself improve victim redress
- [ ] F14 · agentic generation turns single-turn content safety into stateful policy safety

## Status and limits

- All four surveys are **`compiled-draft`** — **not submission-ready**.
- **No fact-checking was performed**: paper conclusions, CVEs and regulatory text are reported as
  stated; external links were not opened.
- The meta-analysis **formally declines to pool** results (zero poolable groups) — no fabricated
  overall breach rate appears anywhere.
- The atlas is **link-only**: of 97 source papers only 41 carry a licence permitting figure
  redistribution (46 use the arXiv non-exclusive licence, 4 are CC BY-NC-ND).
- English PDFs are rendered from Markdown through headless Chrome.
- **Data cutoff: 2026-08-09.**

## Citation

```bibtex
@misc{surveys2026,
  title        = {AI Security Surveys: LLM, Generative Vision, Embodied Loops, and World Models},
  author       = {Mingjun Cheng},
  year         = {2026},
  version      = {v0.2.0},
  howpublished = {\url{https://github.com/ManfredCh/ai-security-surveys}},
  note         = {Compiled draft, data cutoff 2026-08-09. Licence: CC BY-NC-SA 4.0}
}
```

If you cite one survey rather than the collection, use its own title and add the section
(`release/en/<survey>.md`) as the locator. CFF metadata is in [CITATION.cff](CITATION.cff).
The author field is filled in: `Mingjun Cheng` (Vorynel Co.,Ltd), matching the PDF title page.

## Contributing

Corrections and additions are welcome — this is a compiled draft with known gaps.

**Open an issue for**

- a factual error: cite the chapter and paragraph, and give your source
- a missing paper, standard or incident that belongs in scope
- a translation problem: quote the English sentence and the Chinese it came from
- a broken link, a wrong page count, or a formatting problem

**Pull requests are welcome for** corrections with a stated basis, terminology fixes that follow
Appendix D, and new translations. A PR should say *what it changes and why*, with the evidence.

**Not accepted**

- rewrites that change a claim's strength, scope or hedge without new evidence
- additions with no traceable source
- "polish" that alters what a passage asserts

**Translations** into other languages are welcome under the same licence (CC BY-NC-SA 4.0):
keep the attribution, keep the licence, and state that it is a translation.

## Acknowledgements

- Every paper, project, standard and incident report cited in the text — this work is a synthesis
  of theirs. The per-paper atlas in [AI Security Surveys](https://github.com/ManfredCh/ai-security-surveys) links to 97 of
  them directly.
- Review and verification passes were run as independent model passes; the record is kept locally
  rather than published.
- **AI use**: this manuscript was drafted with AI assistance for structuring, translation and
  English rewriting. Every translation and rewrite went through an independent check against the
  Chinese original; numbers, hedges, citations and terms of art were verified programmatically.
  Responsibility for the content rests with the author, not the tools.

## Star History

<a href="https://star-history.com/#ManfredCh/ai-security-surveys&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-surveys&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-surveys&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=ManfredCh/ai-security-surveys&type=Date" width="600" />
  </picture>
</a>

<div align="center">

[![Stars](https://img.shields.io/github/stars/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/stargazers)  ·  [![Forks](https://img.shields.io/github/forks/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/forks)  ·  [![Issues](https://img.shields.io/github/issues/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/issues)  ·  [![Last commit](https://img.shields.io/github/last-commit/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/commits)

</div>

## License

<a rel="license" href="https://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a>

Text, figures and tables are licensed under
**[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-nc-sa/4.0/)**.
The full legal text is in [LICENSE](LICENSE).

| You may | Under these conditions |
|---|---|
| **Share** — copy and redistribute in any medium or format | **Attribution** — credit the author, link the licence, indicate whether changes were made |
| **Adapt** — remix, transform, build upon the material | **NonCommercial** — no commercial use |
| | **ShareAlike** — distribute your contribution under the same licence |

**What ShareAlike means in practice**: if someone translates this work or rewrites it, the result
must stay under CC BY-NC-SA — it cannot be re-licensed as "all rights reserved". Quoting, linking,
and including the work unchanged in a collection do **not** trigger this.

**It does not restrict the author**: the licence is non-exclusive, so the author may also publish
the work elsewhere under other terms.

**Third-party material is not covered.** Papers, figures, product names and trademarks referenced
in the text remain the property of their owners. The per-paper atlas is link-only for exactly this
reason: of 97 source papers, only 41 carry a licence that would permit redistributing their figures.

**About the label in GitHub's sidebar.** GitHub's licence detector only carries CC0, CC BY and
CC BY-SA, so every NonCommercial variant — including this one — is reported as `Other`. The
licence stated above is the operative one, and the full legal text is in [LICENSE](LICENSE).

## Related repositories

- **[Generative and Embodied AI Security](https://github.com/ManfredCh/ai-security-book)** — the unified book — six parts, 24 chapters, one instrument applied across four domains
- **[AI Security Surveys](https://github.com/ManfredCh/ai-security-surveys)** — four standalone security surveys plus the 97-paper atlas index
- **[Foundations](https://github.com/ManfredCh/ai-security-foundations)** — the introductory tutorial and two technical-background surveys
