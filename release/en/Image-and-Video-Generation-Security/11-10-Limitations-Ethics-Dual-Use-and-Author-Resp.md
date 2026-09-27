## 10. Limitations, Ethics, Dual Use, and Author Responsibility

### 10.1 Retrieval, Screening, Language, Geography, and Version Limitations

<!-- new_id=A-V2-10-001 origins=L00622,L00623 evidence=LF-R201-LF-R205 action=merge -->

This project is a taxonomy survey with an audit trail, not a strict systematic review in the PRISMA sense. The OpenAlex candidate pool, together with targeted web pages, official conference pages, system cards, standards, regulations, and incident sources, constitutes only the current evidence package. Search engines lack a stable total hit count, and some `raw_count` are `NR`. The project did not perform native exports of all databases, two-person independent title-and-abstract screening, dual review of every full text, or complete forward and backward citation convergence. Source scale therefore cannot prove exhaustiveness, and missing sources may change the coverage and discussion weight of the taxonomy.

<!-- new_id=A-V2-10-002 origins=L00623,L00624 evidence=LF-R201-LF-R205 action=merge -->

Version, language, and geographic bias further limit external validity. Some current fine-grained quantitative results sometimes depend on the authors' full text. Dynamic system cards, platform policies, product pages, and preprints will continue to change, so time-sensitive conclusions are bound only to the current `checked_at`. They are not facts that remain valid indefinitely. English conference papers and preprints have a high share. Jurisdictions outside China, the US, and Europe, low-resource languages, small creators, and domestic platform transparency and judicial materials are undercovered. Governance recommendations may therefore disproportionately reflect the capabilities and preferences of institutions with high public disclosure.

### 10.2 Evidence, Attribution, Statistics, and Low-Base-Rate Limitations

<!-- new_id=A-V2-10-003 origins=L00625,L00626 evidence=LF-E096-LF-E192;LF-R201-LF-R205 action=merge -->

Most current mechanisms and results are reports by paper authors on limited models, data, triggers, and judges. This survey preserves the conditions and locations, but it did not carry out third-party experimental validation of every number. System cards and vendor announcements can only prove their claims. Regulatory materials can only prove textual obligations. Platform announcements can only prove that a feature or rule was announced. None of them alone proves independent safety effectiveness, enforcement effectiveness, or coverage. The generator, attacker, real-time status, propagation volume, and harm chain in an incident often contain unknown fields. This survey does not fill them in by guessing from appearance or detectors, so real-world attribution must remain limited.

<!-- new_id=A-V2-10-004 origins=L00627 evidence=LF-E188-LF-E192;LF-R205 action=rewrite -->

These qualifications are statistical boundaries, and greater length cannot resolve them. Heterogeneous studies lack a common endpoint, valid denominators, independent research units, and variance, so meta-analysis, I², and cross-protocol ranking are not performed. News, reports, law enforcement, and institutional statistics are affected by public disclosure, classification criteria, selection mechanisms, and duplicate reporting. They can describe only observations of the corresponding system, and they cannot infer incidence, growth rates, or the number of independent victims [@L-S005]. At a low base rate, even offline AUC is insufficient to estimate precision, the volume of manual review, and the cost of false positives. It therefore cannot directly support claims about platform handling.

### 10.3 Reproduction, Engineering, and Production Extrapolation Limitations

<!-- new_id=A-V2-10-005 origins=L00628,L00630 evidence=LF-R203-LF-R204 action=merge -->

Reproduction status strictly limits the engineering statements this survey can support. The main protocols of the unified paper deep dives are all `NOT_ATTEMPTED`. The seven public repositories are only `STATIC_AUDIT_ONLY`. The local DCT-QIM/HMAC harmless submodule is only `PARTIAL_RUN`, and `end_to_end_runs=0`. The existence of repositories, readable READMEs, present dependency files, recorded pinned commits, or page-level mechanism audits does not prove that training, weight acquisition, data construction, service queries, and metric computation were executed. This cannot be summarized as a "successful reproduction".

<!-- new_id=A-V2-10-006 origins=L00629,L00630 evidence=LF-R203-LF-R204 action=merge -->

Weight and data licensing, GPU budget, closed-source service versions, the real-world risk of attack queries, and time dependence all mean that speculation cannot fill in the parts that were not run. Future runs can likewise upgrade the corresponding status, but only in an isolated environment. Such a run needs pinned commits and hashes, recorded hardware, random seeds, and valid response denominators, and it must maintain harmless, authorized output boundaries. Even after an upgrade to controlled end-to-end running, extrapolation to unseen models, production traffic, organizational processes, and actual victim outcomes still requires independent evidence.

### 10.4 Dual Use, Ethics, Fairness, and Stakeholders

<!-- new_id=A-V2-10-007 origins=L00631,L00632,L00633 evidence=LF-R201-LF-R205 action=merge -->

Backdoors, jailbreaking, privacy extraction, watermark removal, and identity impersonation are dual-use, and that limits how much mechanism detail this survey discloses. This survey explains only threat models, security contracts, and defense positions. It does not provide executable bypass strings against in-use services, non-consensual identity generation procedures, exploits for unpatched vulnerabilities, or large-scale query automation. Experiments should be limited to synthetic, authorized, public-benchmark, or ethics-reviewed data. For illegal or highly harmful material, the project uses textual placeholders, hashes, official statistics, and harmless proxy tasks. It does not download, regenerate, or redistribute the raw material.

<!-- new_id=A-V2-10-008 origins=L00634,L00635,L00636 evidence=LF-E188-LF-E192;LF-R201-LF-R205 action=merge -->

Model scores also cannot represent the costs to all stakeholders. That list spans victims' remedies and evidence preservation, creators' licensing, attribution and withdrawal, users' understanding of labels and appeals, moderators' false positives and harmful exposure, and journalists' and researchers' source verification. Existing benchmarks do not measure these jointly to a sufficient standard. The same holds for detector differences with respect to camera, compression, skin tone, age, cultural dress and low-resource languages, and for group-level collateral harm from identity systems and concept erasure. In the current evidence, both fall short of supporting generalized fairness claims. The counterexample of mislabeled real photographs goes further, requiring that appealability be treated as a deployment boundary [@O080].

### 10.5 Author Responsibility, Updatability, and Conclusion Downgrading

<!-- new_id=A-V2-10-009 origins=L00637 evidence=LF-E188-LF-E192;LF-R201-LF-R205 action=rewrite -->

Author responsibility means, first, that every key claim keeps a source ID, version, page number or location, access date, evidence level and claim type. Every number keeps its numerator, denominator, statistical unit and judge. Every run status keeps its code commit, environment, command, log and failure. Appendices must not hide negative results or statistical refusals. The permissions, budget, denominator and failure conditions that support a claim must stay visible near that claim.

<!-- new_id=A-V2-10-010 origins=L00638,L00639 evidence=LF-E188-LF-E192;LF-R201-LF-R205 action=merge -->

Conclusions should be downgraded proactively once new evidence breaks the original conditions. That covers the case where an independent third party cannot reproduce the result under equal permissions and budget. It also covers a changed model or service version. It covers systematic bias in the judge, and production false positives at a low base rate that exceed handling capacity. Further triggers are a watermark that fails under attacks which meet reasonable quality constraints, provenance credentials lost in major platform pipelines, and enforcement data that does not match governance design assumptions. Each trigger narrows the interpretations and deployment recommendations stated above. An update should retain the old version, the reasons for change and the claims it affects, rather than silently rewriting history. For now this survey can claim only that it has established auditable coding and a bounded synthesis. It cannot claim complete systematic retrieval, a unified best defense, real-world incidence or successful end-to-end reproduction.

### 10.E1 Evidence Expansion: Limitations, Ethics, Dual Use, and Author Responsibility

#### 10.E1.1 Retrieval, Screening, and Version Limitations

<!-- new_id=M-L00622 origins=L00622 evidence=LF-R201-LF-R205 action=move -->
This project is a taxonomy survey with an audit trail. It is not a systematic review in the PRISMA sense. OpenAlex supplied a broad-coverage candidate pool. Targeted web pages, official conference pages, system cards, standards, regulations and incident sources then reinforced it. Search engines, however, have no stable total hit count, and for some queries `raw_count` is `NR`. Native exports of all databases were not performed. Neither was two-person independent title-and-abstract screening, dual review of every full text, or complete forward and backward citation convergence. The number of sources can therefore prove only the scale of the current evidence package. It cannot prove that the literature as a whole has been exhausted.

<!-- new_id=M-L00623 origins=L00623 evidence=LF-R201-LF-R205 action=move -->
Version deduplication prioritizes official conference/publisher versions, followed by author manuscripts or arXiv. Where the official page has only an abstract, fine-grained results still depend on the authors' full text. Dynamic system cards, platform policies and product pages will be updated. Papers new in 2026 may also move from preprint to official version. The strength of each conclusion is therefore bound to `checked_at=2026-08-09`. Before finalization or publication, dynamic sources must be re-accessed, versions locked and snapshots/hashes saved.

<!-- new_id=M-L00624 origins=L00624 evidence=LF-R201-LF-R205 action=move -->
Language and geography introduce bias as well. English conferences and preprints dominate the academic evidence. Chinese materials cover the national labeling regime, but domestic platform transparency, judicial documents and Chinese model cards remain insufficient. Experience from jurisdictions outside China, the US and Europe is markedly scarce, and so are Global South platforms, low-resource languages and small creators. Governance recommendations therefore skew toward institutions with high public disclosure.

#### 10.E1.2 Evidence, Attribution, and Statistical Limitations

<!-- new_id=M-L00625 origins=L00625 evidence=LF-R201-LF-R205 action=move -->
Paper author reports often rest on limited models, data, triggers and judges. This survey preserves page numbers and conditions, but did not perform third-party experimental validation of all numbers. System cards and vendor announcements can prove vendor claims, not independent safety effectiveness. Regulations can prove obligations, not enforcement. Platform announcements can prove that a feature launched, not coverage, false positives and remedy outcomes.

<!-- new_id=M-L00626 origins=L00626 evidence=LF-R201-LF-R205 action=move -->
Incident attribution is especially fragile. Among the 32 event cards, some are confirmed by government or judicial records, and some have only vendor/platform materials. For events such as the Taylor Swift and Pentagon images, only highly credible media are available as limited evidence. The specific generator, whether generation was real-time, the attacker and the total propagation volume are often unknown. This survey did not fill these in by guessing from image appearance or detectors. Nor did it write an indictment as a conviction. It did not write a procedural ruling as final liability, or a product takedown as a safety incident.

<!-- new_id=M-L00627 origins=L00627 evidence=LF-E197 action=move -->
Statistically, heterogeneous papers lack a common endpoint, valid denominators, independent research units and variance. No meta-analysis, no I² and no cross-protocol ranking are therefore performed. News, reports and law enforcement records are affected by public disclosure, classification criteria and selection mechanisms. They are never used to infer incidence or growth rates. Updated statistics from institutions such as NCMEC can describe what their reporting systems observe. A report, however, is not equal to an independent victim or a judicially confirmed incident.[@L-S005]

#### 10.E1.3 Reproduction and Engineering Limitations

<!-- new_id=M-L00628 origins=L00628 evidence=LF-R201-LF-R205 action=move -->
The `reproduction_status` of all 27 deep dives in this chapter is `NOT_ATTEMPTED`. Of these, 25 preserve a local PDF and have completed page-level localization. DeepfakeBench relies on the official online full text. The approximate-caching work relies on the official conference page and verified pre-publication materials. Neither has a local PDF. All 27 completed source identity verification and static mechanism analysis. A code repository, a readable README, dependency files or a recorded pinned commit can all be present. None of that proves that training, weight download, data construction, service queries and metric computation were run. The main project additionally has a local DCT-QIM/HMAC toy experiment and a static audit of seven repositories, and their status must remain `PARTIAL_RUN` and `STATIC_AUDIT_ONLY`, `end_to_end_runs=0`.

<!-- new_id=M-L00629 origins=L00629 evidence=LF-R201-LF-R205 action=move -->
The main reasons for non-reproduction include weight and data licensing, GPU budget, closed-source service versions, the real-world risk of attack queries, and time dependence. Even for future runs, an isolated environment, pinned commits and hashes, and recorded hardware, random seeds and valid response denominators should be established first. Outputs should be limited to aggregate results. For closed-source platforms, we should not run attacks that may violate terms of service or produce genuinely harmful content merely to make the paper look more complete.

<!-- new_id=M-L00630 origins=L00630 evidence=LF-R201-LF-R205 action=move -->
Reproduction statements uniformly use a six-state enumeration. `NOT_ATTEMPTED` means not run. `STATIC_AUDIT_ONLY` means read-only code and configuration. `ENVIRONMENT_PROBE` verifies dependencies and entry points. `PARTIAL_RUN` runs harmless submodules. `CONTROLLED_END_TO_END` completes the run on authorized data and isolated models. `EXTERNAL_SERVICE_VALIDATION` additionally requires service authorization and version evidence. `paper_main_protocol_run` separately records whether the paper's main configuration was run. No lower state can be summarized as a "successful reproduction."

#### 10.E1.4 Dual-Use Boundaries and Risk Minimization

<!-- new_id=M-L00631 origins=L00631 evidence=LF-R201-LF-R205 action=move -->
Backdoors, jailbreaking, privacy extraction, watermark removal and identity impersonation are clearly dual-use. This survey needs to explain threat models and defense positions. It does not provide directly executable recipes that would significantly lower the threshold for real-world abuse. Such recipes would include bypass strings targeting services in use, runnable non-consensual identity generation pipelines, exploit scripts for unpatched cache vulnerabilities, real victim material and large-scale query automation. Numerical reporting prioritizes stating the denominator and boundaries, and does not display harmful samples.

<!-- new_id=M-L00632 origins=L00632 evidence=LF-R201-LF-R205 action=move -->
Security research experiments should use synthetic, authorized, public benchmark or ethics-reviewed data. Do not download, regenerate or redistribute illegal or harmful material where likeness, minors, non-consensual intimate imagery or CSAM are involved. Text placeholders, hashes, official statistics and controlled harmless proxy tasks may be used instead. Where creator style and copyright are at stake, technical similarity does not substitute for rights judgment. Experiments must respect licensing and withdrawal.

<!-- new_id=M-L00633 origins=L00633 evidence=LF-R201-LF-R205 action=move -->
Disclosure should follow coordinated principles. If an undisclosed high-impact vulnerability turns up, contact the maintainer first and give a remediation window. Remove weaponizable details from public materials. If the platform does not respond, still evaluate user protection and the public interest. Provenance research must also prevent turning signing infrastructure into surveillance. Minimize identity data, allow creators to choose their declarations, and support key revocation and privacy-preserving soft binding.

#### 10.E1.5 Stakeholders, False Positives, and Fairness Limitations

<!-- new_id=M-L00634 origins=L00634 evidence=LF-R201-LF-R205 action=move -->
Generative visual security does not involve only model providers and attackers. Victims need rapid redress and evidence preservation. Creators need licensing, attribution and withdrawal. Ordinary users need to understand labels and to be able to appeal. Platform moderators bear false positives and harmful exposure. Researchers and journalists need verifiable provenance. Regulators need rules that are enforceable without excessively expanding surveillance. If an evaluation optimizes only model AUC, these costs are hidden.

<!-- new_id=M-L00635 origins=L00635 evidence=LF-E186 action=move -->
False positives may be unequal. Detectors may perform differently for particular cameras, compression, skin tone, age, cultural dress or low-resource languages. Identity systems may impose different harms on public figures, minors and transgender people. Concept erasure may inadvertently harm artistic, educational, medical or minority-group expression. Future reports need to stratify by legitimate use context and by affected group. They should also introduce appeals for authentic content that has been mislabeled. E013 shows a real-world counterexample in which real photographs were incorrectly labeled.[@O080]

<!-- new_id=M-L00636 origins=L00636 evidence=LF-R201-LF-R205 action=move -->
User studies in this survey's evidence pool are limited. Glaze includes a survey of creator acceptability, but it cannot represent all cultures, occupations and work types. Most watermark, jailbreak and video benchmarks have no victim or moderator participation. Deployment recommendations can therefore only be control combinations under risk conditions. They cannot claim to represent the preferences of all stakeholders.

#### 10.E1.6 Author Responsibility, Updatability, and Rules for Downgrading Conclusions

<!-- new_id=M-L00637 origins=L00637 evidence=LF-R201-LF-R205 action=move -->
For each key claim, authors are responsible for retaining the source ID, version, page numbers, access date, evidence level and claim type. For each number they must retain the numerator, denominator, statistical unit and adjudicator. For each reproduction they must retain the code commit, environment, command, logs and failures. The main text should not treat the appendix as a place to hide negative results. Failure conditions must appear near the claim.

<!-- new_id=M-L00638 origins=L00638 evidence=LF-R201-LF-R205 action=move -->
Downgrade conclusions proactively when the following evidence appears. A third party cannot reproduce the result under equal permissions and budget. A change in model version invalidates the result. The adjudicator is shown to have systematic bias. The false-positive rate at the low base rate of a real platform exceeds handling capacity. A watermark fails under attacks that meet reasonable quality constraints. Provenance credentials are largely lost in major platform pipelines. Regulatory enforcement data does not match the design assumptions. When updating, retain the old version and a change log rather than silently rewriting history.

<!-- new_id=M-L00639 origins=L00639 evidence=LF-R201-LF-R205 action=move -->
This survey can ultimately claim to have established an auditable first-broken-interface taxonomy and a representative research lineage. It has also established a metric contract, a 32-event evidence map and a falsifiable agenda. It cannot claim a complete systematic search or a unified best defense. Nor can it claim cross-paper causal ranking, real-world attack incidence or end-to-end reproduction success. Writing these boundaries into the conclusion does not weaken the work. It lets readers know which judgments can be acted on and which still require experiments.

---

[← Back to contents](index.md)
