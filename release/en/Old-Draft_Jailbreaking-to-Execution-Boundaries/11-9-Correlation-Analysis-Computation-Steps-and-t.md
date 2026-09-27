to a population susceptibility rate for applications.

On the defense side, CaMeL's selected Gemini-2.5-Pro arm reduced successful attack counts from 300/949 to 0/949, but normal task utility dropped at the same time, from 73.2% to 41.2%. FIDES's GPT-4o raw counts dropped from 9/949 to 1/949, though the authors reinterpret the events again under a policy-violation definition. The two share the same 949 AgentDojo attack opportunities, but their models, baselines, policies and event definitions differ. Their risk ratios cannot be pooled either.

The script run produced these results: 5 passed the numerical contract, 29 were rejected because of `include_meta=false`, and 0 groups were successfully pooled. All five groups were skipped because k=1 is below the preset threshold of 3. No forest plot, pooled value, I², or τ² was generated. This is not "the analysis was left unfinished". It is a substantive finding of the poolability audit: current public reporting practices are insufficient to answer the average ASR or the average defense risk ratio. The complete item-by-item rationale is in [Inclusion-Exclusion Audit](~/Codex/综述/LLMSE/checks/荟萃分析纳入排除审计.md) and [Machine Output](~/Codex/综述/LLMSE/analysis/outputs/meta/meta_analysis_report.md).

## 9. Correlation Analysis: Computation Steps and the Logic Behind Them

### 9.1 Why Aggregate by Paper First

A single paper often produces 150 cells across 5 models × 10 attacks × 3 defenses. Those cells share data, prompts, author choices and a judge. They are not 150 independent studies. Correlating them directly would give disproportionate weight to papers with large grids and yield extremely small spurious p-values. The script therefore aggregates by `study_id` first. The within-paper mean of a binary encoding is interpreted as the coverage proportion of that paper's encoded experimental arms, and continuous variables take the mean over reported arms. The unit of the main analysis is always the paper.

Candidate variables include year, ASR, adaptive attack, multimodal, agentic, number of independent defense layers, residual ASR, utility change and evidence tier, along with whether independent replication exists. Missing values are deleted pairwise by variable rather than filled with 0. Each pair requires at least 8 studies, and both variables must vary.

### 9.2 Spearman, Bootstrap, and Permutation Test

Spearman correlation first converts \(X,Y\) into ranks separately, then computes the Pearson correlation of the ranks:

\[
\rho_s=\operatorname{corr}(R_X,R_Y).
\]

When there are no tied ranks it is equivalent to \(1-6\sum d_i^2/[n(n^2-1)]\). The actual data contain many ties at 0/1, so the script assigns average ranks to tied values and computes the rank correlation directly. Spearman is chosen because ASR, year and layer count do not satisfy normality/linearity assumptions and contain many extreme values. It measures only monotonic relationships and does not prove causation.

Uncertainty is cross-checked along two routes. The paper-level bootstrap draws \(n\) papers with replacement 2,000 times and recomputes \(\rho\) each time, and the 2.5% and 97.5% quantiles form the interval. The permutation test holds \(X\) fixed and randomly shuffles \(Y\) across papers 2,000 times. It uses a two-sided \(p=(b+1)/(B+1)\), where \(b\) is the count of \(|\rho_{perm}|\ge|\rho_{obs}|\).

The random seed is fixed at 20260806 to guarantee consistency across repeated runs. The permutation p is not corrected for multiple comparisons and serves only to generate hypotheses for follow-up work. If an interval is very wide or crosses 0, the correct conclusion is that the direction is unstable.

### 9.3 Mechanism Hypotheses Proposed in Advance

The first hypothesis is that **adaptive attack is positively correlated with residual ASR**, because an attacker who knows the defense can re-optimize. More mature papers, however, are also more likely to conduct adaptive testing proactively, so evidence quality constitutes a confounder. The second hypothesis is that **the number of independent defense layers is negatively correlated with residual ASR**. Permissions, information flow and sandboxes can still block an attack after the model layer fails. High-risk systems, however, may deploy more layers because they face stronger attacks, which gives rise to reverse causation.

The third hypothesis is that **defense strength trades off against the change in normal utility**. Refusal, isolated parsing, repeated inference and human confirmation reduce task completion or increase cost. Also, "layer count" does not represent the quality of each layer. The fourth hypothesis holds that **the relationship between multimodal and attack success rate is unstable**. Differences in image typography, white-box perturbation, direct audio input and GUI actions far exceed a single binary label. Finally, **year is expected to be positively correlated with automated or agentic encoding**. A more likely reading is a shift in research topics and changes in models and benchmarks, not risk caused by the year itself.

### 9.4 Interpretation Prohibitions

A correlation coefficient cannot answer "how much does adding one defense layer reduce ASR". Nor can it estimate real-world incident rates from a sample of selected papers. Paper-level means conceal internal heterogeneity, and pairwise deletion changes direction when missingness is non-random. Closed-model versions, attack budgets, judges and publication bias may all jointly affect X and Y. If the effective sample is insufficient, the script does not output that variable pair. If it does output one, that pair serves only as a clue for subsequent stratified experiments, not as a causal conclusion.

### 9.5 Actual Correlation Results: Mainly a Reflection of a Research-Landscape Shift

Across 34 independent studies, 20 variable pairs reached n≥8. The clearest observation concerns year and agentic encoding, which are positively correlated. The statistics are Spearman ρ=0.532, bootstrap 95% interval 0.277—0.748, and permutation p=0.0010. The correct interpretation is that newer studies in this evidence table more often evaluate tool agents. That is consistent with the trajectory of research shifting from chat output to action systems after 2023. It does not mean that the year causes safety risk, nor that the number of agents in real-world deployments grows according to this coefficient.

The result for adaptive attack and residual ASR is n=9, ρ=0.274, interval -0.143—0.839, permutation p=0.667. The direction matches the mechanism hypothesis that "knowing the defense makes bypass easier". The interval, however, is extremely wide, and the current data provide no robust evidence. For ASR and multimodal the result is n=19, ρ=0.295, interval -0.166—0.648, p=0.227. It therefore cannot be claimed that multimodal is inherently easier to attack. Year and ASR give n=19, ρ=-0.279, interval -0.588—0.125, p=0.241, which likewise provides no evidence of a monotonic trend.

ASR and evidence tier give n=19, ρ=-0.438. The bootstrap interval -0.761—-0.020 appears not to cross zero, but the permutation p=0.0615, so the

---

[← Back to contents](index.md)
