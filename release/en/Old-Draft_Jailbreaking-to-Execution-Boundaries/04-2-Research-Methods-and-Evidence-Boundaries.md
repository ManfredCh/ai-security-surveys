ts. **Observability** examines whether unified traces, provenance labels, tool audits, kernel/network logs, and timely alerts exist. **Iteration speed** indicates whether an attacker or autonomous agent can make parallel attempts at low cost, adapt based on feedback, and persist for hours or days.

This is not a fitted risk formula but a conceptual framework for checking for missing controls. Asset value, attack cost, detection probability, and recovery capability also influence real risk.

## 2. Research Methods and Evidence Boundaries

### 2.1 Pre-search Protocol

Before the large-scale search began, the research questions, article skeleton, search strings, inclusion/exclusion criteria, quality grades, data fields, and the meta-analysis and correlation-analysis plan went into the [research design document](~/Codex/综述/LLMSE/00_研究设计_结构_检索策略_概要.md). If later evidence overturns an earlier judgment, a correction is appended only in `STAGE_SUMMARY.md`. The process record is never silently rewritten.

### 2.2 Automated Candidate Retrieval and Manual Verification

For each of 12 topics, the OpenAlex pipeline retrieved up to 200 relevance-ranked results, yielding 2,400 API returns in total. Deduplication by OpenAlex ID/DOI left 1,854 candidates. Transparent keyword rules labeled these as 701 high-priority, 297 medium-priority, and 856 low-priority. The labels serve ranking only and cannot be treated as final screening decisions. The complete queries, hit counts, retrieval counts, and raw responses are in `data/openalex/`.

The first round of the manual evidence baseline table contains 65 attack studies. After backfilling from completed formal versions, the current grades are 40 at level A and 25 at level C. This coding may still underestimate existing conference versions. Before freezing, it is not equated with a final "peer-reviewed/preprint" publication status. The defense and engineering table contains 62 sources, with A/B/C levels of 23/23/16. It includes papers, protocol specifications, system documentation, and security advisories, none of which may be added to the attack papers to form a "total number of papers". In addition, the survey compiled 33 paper-model-attack configuration experimental arms and 32 incident/vulnerability/controlled-study records, the latter with A/B/C levels of 28/3/1. Unified template parsing was completed for 23 representative attack papers.

The attack baseline is given in [academic attack-surface retrieval](~/Codex/综述/LLMSE/research/01_学术攻击面检索.md). The incident baseline is given in [incident and HF case verification](~/Codex/综述/LLMSE/research/03_事件新闻与HF案例核验.md). The statistics in the main text will rest on the frozen master table once defense evidence, final-version deduplication, and citation verification are complete.

### 2.3 Why No Single "Overall Attack Success Rate" Can Be Given

Of the current 33 attack experimental arms, only 3 rows have had precise event counts and denominators extracted from primary pages and verified. This does not mean the remaining papers' main text necessarily lacks denominators. It means the current baseline table cannot yet support a binomial pooling on that basis. More importantly, the three rows differ in sampling unit and attack target. For example, "31/36 applications are susceptible to prompt injection" is application-level coverage, not a per-prompt ASR. A model's violation generation rate over 100 harmful requests is likewise not equivalent to an agent's real data-exfiltration rate across 100 enterprise tasks. Other papers may use other metrics: keyword matching, an LLM judge, human review, target prefixes, tool-call success, or performance degradation.

This survey therefore follows three rules. Only studies whose threat model, sampling unit, and effect definition can be mapped enter the same meta-analysis group. When an abstract gives only "over 90%", 0.90 is not disguised as an exact point estimate, nor is the denominator back-inferred. Studies with high heterogeneity or missing denominators appear through an evidence map and a stratified narrative, rather than sacrificing interpretability for a single total.

This treatment is consistent with the PRISMA 2020 requirements for trans

---

[← Back to contents](index.md)
