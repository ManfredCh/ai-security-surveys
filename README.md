<div align="center">

# AI Security Surveys

**Four evidence reviews: LLMs and agents, image and video generation, embodied loops, world models.**

<sub>4 surveys · 160,000 English words · 335 pages of PDF · Chinese originals included</sub>

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC_BY--NC--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)  ·  [![Status](https://img.shields.io/badge/Status-compiled_draft-orange)](#status-and-limits)  ·  [![Language](https://img.shields.io/badge/Language-English_%7C_%E4%B8%AD%E6%96%87-blue)](#languages-and-editions)  ·  [![Atlas](https://img.shields.io/badge/Atlas-97_papers-informational)](release/zh/图谱_97篇索引.md)

[English](README.md) · [简体中文](README.zh.md)

</div>

> Things fall apart; the centre cannot hold.
>
> — W. B. Yeats, *The Second Coming*, 1919

---

## The point

Every survey answers the same question in a different domain: **which functional interface stopped
holding its security contract first, and what would have interrupted it there?**

That framing is what makes the reviews comparable. "Attack success rate" is not comparable across
papers unless the statistical unit, the success condition and the attack budget line up — so each
survey reports the denominator alongside the number, and refuses to pool what cannot be pooled.

| Language | README | Documents |
|---|---|---|
| **English** | this file | four surveys, 160k words, 335 pages of PDF |
| **简体中文** | [README.zh.md](README.zh.md) | 四篇中文原稿 + 图谱索引，21 万汉字，251 页 PDF |

[The point](#the-point) · [Overview](#overview) · [Files](#files-and-formats) · [Reading paths](#reading-paths) · [Citation](#citation) · [Roadmap](#cutoff-and-what-comes-next) · [License](#license) · [Contributing](#contributing)

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
| 中文 | [从模型越狱到系统隔离.md](release/zh/从模型越狱到系统隔离.md) · [47 pp.](release/zh/从模型越狱到系统隔离.pdf) |
| English | [LLM-and-Multimodal-Agent-Security.md](release/en/LLM-and-Multimodal-Agent-Security.md) · [50 pp.](release/en/LLM-and-Multimodal-Agent-Security.pdf) |
| Length | ~2 hours · 11 chapters |
| Structure | corpus and coding method → background and I/O contracts → taxonomy design and coverage audit → defence families → cross-family synthesis → data, metrics and evidence → incidents and reproduction → challenges and evidence limits |

- [ ] ch. 4 **Taxonomy Design** — the single primary axis
- [ ] ch. 6 **Defence Families** — why "one more filter" is not a family
- [ ] ch. 9 **Evidence Limits** — what the authors say cannot be concluded
- [ ] Afterwards: how do jailbreaking and prompt injection differ, and why is there no single "overall LLM breach rate"?

### 2 · Image and Video Generation Security
*From the First-Broken Interface to Defense in Depth — an evidence review*

| | |
|---|---|
| 中文 | [从首破接口到纵深防御.md](release/zh/从首破接口到纵深防御.md) · [136 pp.](release/zh/从首破接口到纵深防御.pdf) |
| English | [Image-and-Video-Generation-Security.md](release/en/Image-and-Video-Generation-Security.md) · [203 pp.](release/en/Image-and-Video-Generation-Security.pdf) |
| Length | ~7 hours · 12 chapters + 4 appendices |
| Structure | evidence governance → system boundaries and threat model → the I1–I7 taxonomy → mirrored synthesis → cross-interface defence in depth → video-specific synthesis → engineering checks → deployment decisions → limitations and dual use → falsifiable agenda; appendices hold 27 per-paper deep reads and 32 event cards |

- [ ] ch. 2 **Evidence Governance** — the auditable basis for 132 citations, 10 figures, 18 tables
- [ ] ch. 4 the **I1–I7 taxonomy** — the skeleton
- [ ] ch. 7 the **video-specific synthesis** — time, motion, joint audio-visual identity
- [ ] Appendix C — the **32 event cards**
- [ ] Afterwards: for one fake video, which positions could have failed first?

### 3 · Closed-Loop Security of VLM, VLA, and World-Action Models
*From Seeing Wrong to Acting Wrong — an evidence-based review*

| | |
|---|---|
| 中文 | [从看错到做错.md](release/zh/从看错到做错.md) · [46 pp.](release/zh/从看错到做错.pdf) |
| English | [Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.md](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.md) · [64 pp.](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.pdf) |
| Length | ~3 hours |
| Bonus | [图谱_97篇索引.md](release/zh/图谱_97篇索引.md) — the 97-paper atlas as a link index (title + arXiv + licence + mechanism note) |

- [ ] ch. 4 **Technical Lineage and System Contracts** — answering safely vs acting safely
- [ ] ch. 5 the **closed-loop attack taxonomy**
- [ ] ch. 7 **Cross-Family Synthesis** — when to choose which control layer
- [ ] Browse the [atlas index](release/zh/图谱_97篇索引.md) and open three papers
- [ ] Afterwards: are a VLM seeing wrong and a VLA acting wrong the same problem?

### 4 · World Model Security
*From Imagined Worlds to Controlled Reality*

| | |
|---|---|
| 中文 | [从想象世界到控制现实.md](release/zh/从想象世界到控制现实.md) · [22 pp.](release/zh/从想象世界到控制现实.pdf) |
| English | [World-Model-Security.md](release/en/World-Model-Security.md) · [22 pp.](release/en/World-Model-Security.pdf) |
| Length | ~1 hour · 17 chapters |
| Structure | conceptual boundaries → retrieval method → threat model → attack surface → defence and recovery → representative analyses → product entity resolution → deployment risk → unpoolable results → news and governance → code audit → synthesis → agenda → limitations |

- [ ] the **conceptual boundaries** chapter — WM vs EWM vs WAM vs WCM
- [ ] the **attack surface** chapter — supply chain to real-world execution
- [ ] **unpoolable results** — why the authors refuse a meta-analytic pool
- [ ] Afterwards: why is coupling prediction to action a risk multiplier while coupling alone is not unsafe?

### Archived draft

[中文](release/zh/旧稿_从越狱到执行边界.md) · [English](release/en/Old-Draft_Jailbreaking-to-Execution-Boundaries.md) · [PDF 43 pp.](release/en/Old-Draft_Jailbreaking-to-Execution-Boundaries.pdf)

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
