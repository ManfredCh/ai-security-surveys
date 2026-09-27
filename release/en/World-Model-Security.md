

<!-- toc:start -->
## Contents

- [World Model Security: Attacks and Defenses across World, Environment, Action, and Control Models](#world-model-security-attacks-and-defenses-across-world-environment-action-and-control-models)
  - [Abstract](#abstract)
  - [Introduction: When Imagination Becomes Decision and Control Infrastructure](#introduction-when-imagination-becomes-decision-and-control-infrastructure)
  - [Conceptual Boundaries and Article Structure](#conceptual-boundaries-and-article-structure)
  - [Retrieval, Screening, and Evidence Methods](#retrieval-screening-and-evidence-methods)
  - [Threat Model and Safety Properties](#threat-model-and-safety-properties)
  - [Attack Surface: From Supply Chain to Real-World Execution](#attack-surface-from-supply-chain-to-real-world-execution)
  - [Defense, Runtime Assurance, and Recovery](#defense-runtime-assurance-and-recovery)
  - [Analysis and Comparison of Representative Papers](#analysis-and-comparison-of-representative-papers)
  - [Happy Oyster and MoWorld: Product/Project Entity Resolution](#happy-oyster-and-moworld-productproject-entity-resolution)
  - [Application Scenarios and Deployment Risk Mapping](#application-scenarios-and-deployment-risk-mapping)
  - [Datasets, Metrics, and Results That Cannot Be Pooled](#datasets-metrics-and-results-that-cannot-be-pooled)
  - [News, Industry Signals, and Governance Integration](#news-industry-signals-and-governance-integration)
  - [Code Audit and Safety Reproduction Status](#code-audit-and-safety-reproduction-status)
  - [Cross-Family Synthesis and Deployment Choices](#cross-family-synthesis-and-deployment-choices)
  - [Future Trends and a Falsifiable Research Agenda](#future-trends-and-a-falsifiable-research-agenda)
  - [Limitations](#limitations)
  - [Conclusion](#conclusion)
  - [Citation and Evidence Notes](#citation-and-evidence-notes)
- [Appendix — Post-cutoff update (2026-08-09 → 2026-09-26)](#appendix--post-cutoff-update-2026-08-09-→-2026-09-26)
  - [A.1 — New world-model security work since the cutoff](#a1--new-world-model-security-work-since-the-cutoff)
  - [A.2 — The terminology gap is still open](#a2--the-terminology-gap-is-still-open)
  - [A.3 — Institutional consequence of the OpenAI–Hugging Face incident](#a3--institutional-consequence-of-the-openaihugging-face-incident)
  - [A.4 — How to use this appendix](#a4--how-to-use-this-appendix)
<!-- toc:end -->
# World Model Security: Attacks and Defenses across World, Environment, Action, and Control Models

> Research materials are current as of 2026-08-09

## Abstract

World models are moving beyond latent dynamics and imagined planning. They now generate environments, drive robot action, and run closed-loop safety control. That reach lets local model errors propagate along the chain of time, planning, and execution. This survey first freezes the article structure, retrieval strategy, evidence tiers, and reproduction boundaries. It then completes academic retrieval, news/entity disambiguation, and code auditing in parallel. Deduplication across three classes of discovery sources yields 991 candidates. Of these, 78 enter high-relevance review, 76 are included in the qualitative synthesis, and 23 form the direct attack-defense or close-bridging core. 35 PDFs are locally verified, and 15 entities and 36 events are organized. The first-broken functional interface in the closed loop is the primary axis of this survey. WM, EWM, WAM, and WCM serve as overlapping secondary axes. The results show that attacks have moved beyond pixel perturbations. They now reach data poisoning, physical conditions, latent states, imagination ranking, objectives/constraints, WAM action mismatch, tool execution, and privacy. Defenses are shifting in the same direction, from input anomaly scores to uncertainty filtering, robust MPC, runtime verification, pre-tool-call blocking, and recoverable control. Dedicated defenses and comparable evidence remain severely lacking. Heterogeneous ASR, returns, and FID/FVD do not satisfy the conditions for meta-analysis. Happy Oyster and MoWorld are confirmed to be distinct entities. Happy Oyster is labeled as a WM+EWM bridge solely on the basis of the vendor's official feature statements. MoWorld is judged as WM+EWM on the basis of its project page and paper. For both, the public evidence is insufficient to classify them as WAM/WCM or to draw product safety conclusions.

## Introduction: When Imagination Becomes Decision and Control Infrastructure

The safety problem of world models is not merely "whether the generated imagery is realistic." A model keeps a latent state from historical observations, predicts how the environment will evolve, and then feeds those predictions into planning, action, or feedback control. A local error may accumulate over time and become an irreversible physical consequence at the execution end. World Models, PlaNet, Dreamer, and MuZero established the technical lineage of "planning or learning in a learned world." Driving video world models, interactive environment generators, world action models, and world-model-based safety control extend the attack surface from pixels to physical conditions, latent dynamics, imagined trajectory ranking, action heads, and tool execution.[@ha2018worldmodels] [@hafner2019planet] [@hafner2020dreamer] [@schrittwieser2020muzero]

The central thesis of this survey is that prediction and action are coupled, and that this coupling multiplies risk. Coupling itself, however, does not equal being unsafe. Risk turns on three things. The first is which functional interface fails first. The second is whether the closed loop amplifies errors. The third is whether the system has an independent observation anchor, action gating, a safety envelope, rollback, and human takeover. This survey therefore takes the first-broken interface along the chain of "supply chain—observation—state—dynamics—objective—planning/action/control—execution and feedback" as its primary axis, and treats WM, EWM, WAM, and WCM as secondary axes.

- Contribution 1: Provides verifiable input-output contracts for the four model classes, so that not every video generator is called a world model and not every action-conditioned video is called a WAM.

- Contribution 2: Analyzes data poisoning, physical-condition perturbation, latent-state contamination, imagined-trajectory hijacking, reward/constraint tampering, action mismatch, tool misuse, and privacy leakage under a unified attack contract.

- Contribution 3: Maps prevention, detection, suppression, recovery, and assurance onto the same closed loop, and writes the residual risk under adaptive attacks into every defense conclusion.

- Contribution 4: Separates academic full texts, official product/repository sources, standards and regulations, and news events, and completes entity disambiguation for Happy Oyster and MoWorld.

- Contribution 5: Provides rerunnable safety toy experiments and code-audit receipts, strictly distinguishing static auditing, mechanism-level partial reproduction, and end-to-end reproduction.

## Conceptual Boundaries and Article Structure

A name alone cannot settle terminology. This survey defines a world model as a system that maintains a state from historical observations and optional actions, and predicts at least one of future states, observations, rewards, or constraints. EWM names a functional class oriented toward external environment evolution or interactive generation. That abbreviation has not yet formed a stable community definition the way WM has. WAM requires that verifiable future prediction be directly coupled with action generation, evaluation, policy improvement, or planning. A system whose only action conditioning is WASD camera input, with navigation decisions still made by a human, is not a WAM. In this survey, WCM is an operational classification: world prediction must enter one of feedback control, trajectory or low-level command generation, or safety filtering. In the frozen retrieval, the exact safety phrase "world control model" has zero hits. This survey therefore does not claim that it is an already established official model category.

| Family | Minimum functional contract | Primary safety focus |
| --- | --- | --- |
| WM | Represent and predict/evaluate the future | Prediction integrity |
| EWM | Generate external evolution | Conditioning and temporal order |
| WAM | Prediction-action coupling | Imagination-action consistency |
| WCM | Prediction enters feedback control | Constraints and execution |

*The minimum verifiable contracts for the four model classes; they can overlap and are not mutually exclusive brand labels.*

```text
\hat{s}_{t+1},\hat{o}_{t+1},\hat{r}_{t+1}=F_{\theta}(s_t,a_t,c_t),a_t=\pi(s_t,\hat{s}_{t+1:t+H},g_t)
```

*Unified functional contract: the coupling of the predictor with the action/controller.*

![World-model closed-loop security contract. The primary code follows the first-broken functional interface, not the appearance of the perturbation.](../figures/fig01_closed_loop_contract.png)

*World-model closed-loop security contract. The primary code follows the first-broken functional interface, not the appearance of the perturbation.*

### From Dyna to Latent Imagination: 1991–2020

Dyna put learning, planning, and reacting in one architecture. That gave an early format for "generating additional experience with a learned model." In World Models, visual encoding, recurrent dynamics, and a controller showed that policies can be trained in imagination. PlaNet and Dreamer coupled latent dynamics tightly with planning and policy learning. The safety hazards of this stage already existed. Long-horizon rollouts amplify model bias, yet the literature of the period focused mainly on performance and sample efficiency rather than on malicious adversaries.[@sutton1991dyna] [@ha2018worldmodels] [@hafner2019planet] [@hafner2020dreamer]

### From Task Models to General Control: 2020–2024

MuZero skips the reconstruction of every observation detail. Instead it learns values, rewards, and dynamics that are useful for planning. World models moved toward multitask, large-scale continuous control with TD-MPC2 and DreamerV3. UniSim, GAIA-1, and Genie arrived in the same period, tying world models to driving sensor simulation, video generation, and interactive environments. The object of safety evaluation widened accordingly, from "policy return" to temporal consistency, the credibility of physical conditions, and downstream planning impact.[@schrittwieser2020muzero] [@hansen2024tdmpc2] [@hafner2025dreamerv3] [@yang2023unisim] [@hu2023gaia1] [@bruce2024genie]

### Physical AI, WAM, and Dedicated Attack-Defense: 2025–2026

After 2025, Cosmos, V-JEPA 2, and DINO-WM tightened the link between video prediction, physical representation, and planning. World action models and runtime verification became new hotspots. As of 2026-08-09, dedicated malicious-safety research covers observational adversarial perturbation, physical-condition attacks, data poisoning, backdoors, imagined-trajectory ranking, WAM jailbreaking, and action mismatch. On the defense side, the field is moving from robust training toward uncertainty filtering, robust MPC, runtime verification, and pre-tool-call blocking.[@nvidia2025cosmos] [@assran2025vjepa2] [@zhou2024dinowm] [@liu2026jailwam] [@li2026badwam] [@nath2026sls2] [@liu2026checkvla]

## Retrieval, Screening, and Evidence Methods

This project froze its research questions, article structure, inclusion/exclusion criteria, evidence tiers, data dictionary, reproduction status, and statistical rejection conditions before starting parallel agents. The work then split into three workflows: academic retrieval, entity/news integration, and code reproduction. The main retrieval covers arXiv, with targeted verification against peer-reviewed pages, official project pages, repositories, corporate announcements, standards, and regulations. Queries use Boolean combinations of world model, environment world model, world action model, and world control model with adversarial, attack, poisoning, backdoor, jailbreak, privacy, robust, safe, assurance, and similar terms. Aliases such as Happy-Oyster, HappyOyster, MoWorldModel, and moworldmodel are expanded separately.

The pipeline starting point contains 851 deduplicated arXiv candidates, 99 historical discovery seeds, and 78 targeted academic candidates. Cross-source deduplication leaves 991. Of these, 78 enter high-relevance review, 76 are included in the qualitative evidence base, and 23 are the direct attack-defense or close-bridging core. 35 core PDFs are locally verified. In addition, 15 entities and 36 event records are established. Broad queries are capped for auditability, so the 913 items serve only as a candidate index. They were not disguised as manual full-text exclusions. This survey is therefore a transparent classification review. It does not claim to have completed a strict dual-independent PRISMA-style systematic review.

![Corpus pipeline. Broad retrieval and core full-text evidence are clearly separated.](../figures/fig02_corpus_flow.png)

*Corpus pipeline. Broad retrieval and core full-text evidence are clearly separated.*

| Tier | Minimum evidence | Permitted statements |
| --- | --- | --- |
| A | First-hand full text/code | Qualified mechanisms and results |
| B | Defensible bridging | Boundary evidence, explicitly stated extrapolation |
| C | Background/foundational sources | Conceptual or historical background |
| Event | Official/independent sources | Timeline, not entered into the effect pool |

*The evidence tiers and statement boundaries of this survey.*

### Unified Coding Contract

Each attack unit records at least the asset, attacker objective, knowledge and privileges, controllable entry points, budget, first-broken interface, temporal propagation, closed-loop consequences, metric denominator, and adaptive-defense status. Each defense unit records at least the protected interface, prevention/detection/suppression/recovery/assurance functions, false positives and false negatives, latency/computational cost, adaptive attacks, and residual risk. A single paper may have multiple entry points. The primary code, however, selects only the first functional interface to fail in the closed loop, which avoids double counting.

### Reproduction and Statistical Boundaries

This survey strictly stratifies repository visibility, dependency installation, module import, toy mechanism execution, scaled-down simulation, and end-to-end results. Outputs are not written as end-to-end reproduction when large weights have not been downloaded, official datasets have not been run, or closed-loop tasks have not been completed. On the quantitative side, pooling is permitted only when at least three independent comparable studies have the same estimand, model/task, attack budget, success-rate denominator, and variance. No unit currently satisfies this condition. The survey therefore generates no pooled ASR, forest plot, I-squared, funnel plot, or causal ranking.

## Threat Model and Safety Properties

The assets of world-model safety are many. They include training data and model artifacts, observations and conditioning signals, long-term memory and latent states, dynamics parameters, rewards/values/constraints, imagined trajectories, actions or control commands, actuators/tools, and user privacy. An attacker may be able to control only the appearance of the environment. Alternatively, the attacker may obtain differing privileges over sensors, conditioning embeddings, training samples, reward interfaces, model gradients, the supply chain, or tool descriptions. "White-box success" cannot be automatically extrapolated to a remote black-box threat. "Black-box transfer" must also state the number of queries, surrogate data, and attack budget.[@nist2024aml]

- Prediction integrity: future states, observations, rewards, and constraints are not maliciously biased.

- Temporal consistency: long-horizon dynamics still do not drift abnormally when local frames appear plausible.

- Imagination-action alignment: actions must be consistent with imagination that is evaluated as safe and effective.

- Constraint satisfaction: uncertainty, safety distance, risk budget, and human intent remain effective in the closed loop.

- Recoverability: after an anomaly occurs, the system can stop, roll back, switch to a safe policy, or hand over to a human.

- Auditability: data, models, configurations, world predictions, actions, and execution results have linkable records.

Malicious attacks and natural failures must be strictly distinguished. Natural distribution shift, occlusion, sensor noise, long-horizon model bias, and computation latency can expose weaknesses at the same interface. They can be called attacks only after the adversary's objective, privileges, and budget are defined. Conversely, natural-robustness methods can serve as safety-assurance bridges, but should not be called attack defenses before they have been validated against an adaptive adversary.

## Attack Surface: From Supply Chain to Real-World Execution

Of the 25 unified attack cards, 16 are direct world-model malicious-safety evidence and 9 are explicitly extrapolatable bridges from VLA, RL, trajectory prediction, MPC, or video dynamics. A card is a mechanism-coding unit, not an independent paper. One source can contribute multiple attack, evaluation, and defense cards. The author groups of Hallucination-Driven and ARB4WM, for example, overlap heavily, so they cannot be treated as independent replication studies. The primary-code distribution of the direct cards is: observation/context 6, supply chain 3, planning/action/control 2, goal/value/constraint 2, state/memory 1, execution/feedback/tool 1, privacy/intellectual property 1. These numbers are not attack effect sizes, nor do they represent real-world incidence rates.

![Distribution of core attack and defense cards by first-broken interface. Each paper is counted only once under its primary interface. ](../figures/fig03_attack_defense_evidence_map.png)

*Distribution of core attack and defense cards by first-broken interface. Each paper is counted only once under its primary interface.*

### Training Artifacts and Supply Chain Attacks

Supply chain attacks work by fixing malicious behavior into data, model, encoder, dynamics, or configuration artifacts. SWAAP first searches for target models that have low return but still stay close to clean dynamics. It then uses gradient matching with stealthiness constraints to modify a small number of fine-tuning transition targets, and it discusses residual/CUSUM and TRIM-like robust training baselines. Targeting World Models places the attack target at the world model stage of the robot learning pipeline. BadDreamer uses a trigger–erase sequence of “keep the yellow rider in the context, erase the rider in future frames” to push future representations toward non-yielding waypoints. Such attacks are dangerous because clean validation performance can be maintained, and the attack only surfaces in long-horizon imagination or actions after the trigger. Environment poisoning and reward poisoning in traditional RL show that even without directly modifying parameters, an attacker can teach a wrong policy through system interaction. These are only bridge evidence, however. [@hu2026swaap] [@rathbun2026targeting] [@shuai2026baddreamer] [@ma2021environmentpoisoning] [@zhang2020rewardpoisoning]

### Observation, Physical Condition, and Context Attacks

Hallucination-Driven Policy Failure applies pixel, latent-space, and temporally augmented perturbations to Dreamer-style continuous control models. It shows that a small input change in one frame can accumulate across frames in the state buffer. PhysCond-WMA does more than change pixels. It optimizes HD Map embeddings and 3D box conditions directly, then maintains a temporally consistent semantic shift through momentum guidance of reverse denoising. BadWorld perturbs the input context image at test time and interferes with early denoising through a velocity objective that uses no ground-truth future labels. It then improves attack stability with a trajectory-adaptive bilevel search oriented toward unknown subsequent control sequences. This is not training poisoning or a backdoor. ARB4WM unifies multiple adversarial perturbations into one robustness benchmark for continuous control world models. CtrlAttack acts as an EWM boundary bridge. It uses a low-dimensional velocity field and temporal integration to disrupt the state evolution of diffusion-based I2V. Its experimental numbers cannot be pooled with closed-loop robot or Dreamer tasks. [@zhang2026hallucination] [@guo2026physcond] [@shen2026badworld] [@zhang2026arb4wm] [@xu2026ctrlattack]

### Latent State, Memory, and Temporal Accumulation

The minimal characteristic of a state/memory attack is not that “the image was changed”. It is that contaminated internal information continues to be used for subsequent rollouts. The attack may look slight in the current frame, yet it keeps latent beliefs, uncertainty, or long-term context drifting. Single-frame perception metrics and internal reconstruction residuals are therefore insufficient to prove safety. Safety requires comparison against independent pose, map, rule, or external sensor anchors. It also requires measuring how error propagates from state to trajectory and then to action. The temporal augmentation design of Hallucination-Driven directly supports this interface. False Prophets serves only as a bridge for system propagation from agent environment simulation and long-horizon context. Its first-broken interface is still manipulable environment simulation/feedback entering the tool decision chain, not direct tampering with internal memory. [@zhang2026hallucination] [@imgrund2026falseprophets]

### Dynamics, World Imagination, and Trajectory Attacks

Dynamics attacks attempt to change “what the system believes will happen next”. Trusted Imagination still applies a bounded infinity-norm PGD perturbation to observations. Its so-called oracle-level setting refers to using a high-quality downstream action selector as an evaluation probe. The purpose is to isolate “whether corrupting world imagination is sufficient to mislead decisions”. It does not mean that the attacker can directly overwrite the oracle or the world state. In the comparison, reactive policies show approximately no effect under attack. The LaDi-WM closed-loop MPC, which actually consumes imagination, exhibits attack-specific failures. That pattern indicates the harm depends on whether the downstream uses imagination. TRAP injects a backdoor through tail imagination trajectory ranking. As a result, the planner systematically favors long-horizon dangerous options when triggered. Traditional trajectory prediction attacks provide a bridge for this problem. Yet a prediction that does not enter the world state and the action closed loop cannot be directly equated with WAM/WCM attacks. [@chen2026trustedimagination] [@duan2026trap] [@tan2022trajectory]

### Goal, Reward, Value, and Constraint Tampering

A world model can predict the future very accurately, yet choose the wrong trajectory because its values or constraints have been tampered with. JailWAM places this problem within WAM jailbreaking for robot control. Its Visual-Trajectory Mapping, Risk Discriminator, and Dual-Path Verification first serve to generate, screen, and physically validate dangerous instruction candidates. They cannot be misdescribed wholesale as a defense. The Stage-I risk discriminator inside JailWAM can be reused as a plug-and-play inference-time filtering defense. Yet it is evaluated only within its simulation, model, and task boundaries. This is not entirely the same as ordinary LLM prompt jailbreaking. After the break, the goal propagates through visual futures, action generation, and robot execution. The reward poisoning literature indicates that the goal channel should be treated as a safety boundary from training time onward. [@liu2026jailwam] [@zhang2020rewardpoisoning]

### Planning, Action, and Control Hijacking

An important new boundary for WAM is that “imagination errors” and “correct imagination but wrong actions” must be tested separately. The core of BadWAM is the latter. It does not implant a trigger during training. Instead, it uses small visual adversarial perturbations generated by queries and an action-only/imagination-preserving objective to directionally shift the action output, while keeping visual futures plausible. FID, FVD, PSNR, or human liking of generated videos are therefore not sufficient proof of action safety. WMAttack, in turn, composes attack families, perturbation budgets, optimization steps, restarts, and allocation rules into a limited-budget search. It uses return degradation, action instability, temporal cost, and rollout variance to improve the proposal distribution. That increases evaluation strength, but it does not amount to providing a robustness certificate for any real-world deployment. [@li2026badwam] [@guo2026wmattack]

### Execution, Feedback, and Toolchain Attacks

An agent system may use a world model for pre-tool-call prediction, post-completion checking, or long-horizon planning. Once it does, tool descriptions, web page content, return values, permission boundaries, and side effects all become new state inputs. False Prophets directly analyzes the safety of world models in agent systems. Its lesson is that a world model cannot simultaneously be the sole predictor, the sole judge, and the sole execution authorizer. Independent lines of defense must be formed from tool least privilege, parameter type checking, external rules, side-effect previews, reversible tests, and post-completion verification. [@imgrund2026falseprophets]

### Privacy, Memorization, and Intellectual Property

World models may memorize training data in videos, robot trajectories, maps, user interactions, or imagination rollouts. Imagined Memorisation places the data leakage problem within the imagination of model-based reinforcement learning. Its evidence is preliminary, however: it comes from a single-author, non-archival workshop, and automated access to the official PDF is restricted. This survey uses its mechanism only as located by the official page and indexing. External users can repeatedly control the initial frame, text, viewpoint, and sampling randomness. When they do, traditional membership inference, data extraction, model extraction, and generated-content provenance problems compound with environment interaction. Direct evidence is currently scarce and protocols are not unified. The attack success rate of that work should therefore not be used to infer the leakage risk of commercial world models. [@ng2026imagined]

### Composite Attack Chains and Physical Consequences

The real attacks most worth attention are often not a single perturbation. They are “poisoned artifact — trigger condition — contaminated state — altered imagination ranking — bypassed constraint — emitted action — concealed feedback”. Only when an attack completes the final segment in a controllable simulation or physical system can a physical attack effect be claimed. Open-loop video quality degradation, reduced downstream detector accuracy, or single-step action errors are only propagation-chain evidence. They do not equal real accidents. Safety red teaming should test these combinations with reversible, isolated simulation protocols that have no third-party impact.

## Defense, Runtime Assurance, and Recovery

This survey organizes 17 defense/assurance cards, of which 14 are direct or runtime-assurance-level evidence. These are still mechanism units, not 17 independent studies. One source can contribute both an attack card and a baseline defense card. Compared with attacks, dedicated closed-loop defenses evaluated under adaptive adversaries remain relatively scarce. Many methods called “safe” mainly address natural OOD, constrained reinforcement learning, or risk-aware planning. They are necessary runtime assurance, but they do not automatically counter attackers who adapt to the detector.

### Prevention: Data Provenance, Artifact Integrity, and Robust Learning

At the supply chain level, datasets, code, model weights, encoders, configurations, and prompt/tool templates should carry versions, provenance, hashes, signatures, licenses, and approval chains. Cleaning, outlier sample trimming, and robust objectives can reduce some poisoning risk. The TRIM-like baselines in SWAAP and robust model-based reinforcement learning belong to this direction. But complete data provenance does not mean that labels, conditional embeddings, or weak-quality data will not cause systematic bias. A signature can only prove “who it came from”, not that “the content is safe”. [@hu2026swaap] [@ye2024robustmbrl]

### Input, Condition, and State Consistency Detection

To be effective, an input defense should span pixels, maps, 3D boxes, text, action history, and device state. A detector should not look only at current-frame semantics. It should also check geometric constraints, dynamics reachability, cross-modal consistency, temporal residuals, and independent sensor anchors. WISER uses world model posterior/prior surprise and reconstruction error to select a more interpretable latent state among multi-sensor masked candidates. In the single-sensor case, it rejects untrusted observations or uses predictive reconstruction to purify them. It directly supports inference-time detect + contain, but it mainly evaluates noise, sensor faults, and natural OOD. It has not yet faced adaptive malicious attacks that jointly optimize surprise, reconstruction, and task return. ARB4WM shows that input processing may be effective under non-adaptive attacks. Yet adaptive attacks that target the defense gradient or pass through the model substantially shrink the benefit. As a sequential decision-making bridge, Illusory Attacks further shows that conventional attacks are often detectable because of trajectory distribution shift. In contrast, epsilon-illusory attacks that deliberately stay close to the environment trajectory distribution can bypass anomaly detection. Therefore, clean pass rate, false alarms, missed detections, latency, and adaptive attacks should be reported together. [@zollicoffer2025worldmodelrobustnesssurprise] [@zhang2026arb4wm] [@franzmeyer2024illusory]

### Uncertainty, Safety Filtering, and Robust Control

UNISafe uses latent-space uncertainty and safety filtering to avoid OOD failures. SafeDreamer learns safety constraints within world model imagination. SLS-squared combines a latent world model with parallel conformal robust MPC. It attempts to connect pixel prediction to probabilistic safe control. These methods are important for WCM because they do not merely produce scores but change actions or trajectories. However, latent uncertainty becomes overconfident under shared model bias. Biased Dreams is precisely a reminder of this assumption. Safety thresholds should work together with external constraints, reachability analysis, and emergency stopping. [@seo2025unisafe] [@huang2023safedreamer] [@nath2026sls2] [@berger2026biaseddreams]

### Runtime Verification, Suppression, and Rollback

CheckVLA uses an action-conditioned world model to preview and verify execution in long-horizon mobile manipulation. DreamGuard uses a risk-aware world model to block high-risk paths before an LLM agent calls a tool. Both kinds of design turn "safety assessment" into closed-loop intervention. If the working model and the checking model share data, encoders, or weaknesses, however, an attacker may deceive both at the same time. More robust deployment requires architectural diversity, independent rules, and a hardware safety envelope. It must also define measurable success conditions for refusal, pause, replanning, rollback, and human takeover. [@liu2026checkvla] [@lin2026dreamguard]

### Adaptive Red Teaming, Continuous Evaluation, and Counterfactual Testing

WMAttack's automatic finite-budget search reminds defenders that fixing a single hand-crafted attack configuration easily overestimates robustness. RoboTrustBench extends trustworthiness testing of video world models to robotic manipulation scenarios. World Models as Adversaries has a role-conditioned world model generate difficult interactions and then fine-tunes a motion planner with multi-agent self-play. This belongs to training-time coverage enhancement, not a formal guarantee against unknown real-world attacks. A complete continuous evaluation should include adaptive attacks against the target defense, reproduction across seeds and tasks, clean performance gating, and attack search budget. It should also cover a holdout set of unknown attacks, closed-loop long horizons, safety envelope intervention rate, recovery time, and post-failure reversibility. "No known attack was triggered" should not be read as "it is already safe." [@guo2026wmattack] [@li2026robotrustbench] [@nie2026wmasadversaries]

## Analysis and Comparison of Representative Papers

This section does not stack summaries by paper title. Instead it compares which stretch of closed-loop safety they answer, and which conclusions cannot be extrapolated.

### Hallucination-Driven and PhysCond-WMA: the Input Is More Than Pixels

The value of Hallucination-Driven lies in dividing world model adversarial attacks into full white-box, latent-space settings that only touch the encoder/dynamics, and cross-frame temporal augmentation settings. That division shows that the same pixel budget is not the same threat under different privileges. Its limitation is that the conclusions depend on continuous control models, data normalization, and the authors' protocol. The perturbation threshold cannot be carried over to driving video generation. PhysCond-WMA, by contrast, shows that the conditioning channel is an independent asset. HD Map and 3D boxes are not imagery to the human eye, yet they directly prescribe world evolution. The FID/FVD, target success rate, and downstream detection/open-loop planning degradation reported in that paper can only be interpreted under its data, normalization, and model. [@zhang2026hallucination] [@guo2026physcond]

### TRAP and WMAttack: From One Backdoor to an Attack Searcher

TRAP's core innovation is not to make all predictions worse, but to change the ranking of tail imagined trajectories. As a result, long-horizon dangerous trajectories under triggered samples are more likely to be selected by the planner. That is closer to the closed-loop objective than measuring only one-step prediction error. WMAttack, for its part, turns "attack evaluation depends heavily on tuning" into a finite-budget optimization problem. It uses task representation retrieval of historical configurations for warm starting. Its advantage is reducing the robustness overestimation caused by weak hand-crafted baselines. Its limitation is that the attack family and the search objective are still defined by the evaluator. Observation-space success is also not complete coverage of the supply chain, tools, or physical control. [@duan2026trap] [@guo2026wmattack]

### JailWAM and BadWAM: Two Orthogonal Failure Modes of WAMs

JailWAM focuses on dangerous intent, risk judgment, and safety bypass of world imagination. BadWAM, in turn, uses small visual adversarial perturbations generated from queries to directionally shift action outputs, while deliberately keeping the visual future apparently correct. It is not a training-time action head backdoor. Only by putting the two together can a complete WAM safety test matrix be derived. One axis tests "whether the imagination is correct," the other axis tests "whether the action is aligned with the imagination and the constraints." Among the four quadrants, only when both imagination and action are correct is it benign. This also shows why video similarity scores cannot replace action consistency, constraint violation, and execution-consequence tests. [@liu2026jailwam] [@li2026badwam]

### SWAAP, Targeting, BadDreamer, and BadWorld: Training Poisoning and Test-Time Manipulation

SWAAP first finds a target model that has low return yet still stays close to the clean dynamics. It then modifies a small number of fine-tuning transition targets with stealthy constrained gradient matching. Targeting places the world model within the entire robot learning supply chain, emphasizing that downstream policies are compromised. BadDreamer uses a trigger sequence that preserves the context / erases the future of the yellow rider, binding the future representation to non-yielding waypoints. BadWorld, by contrast, needs no training-time privilege. At test time it perturbs context images with a future-label-free velocity objective and trajectory-adaptive bi-level optimization. The first three types of evidence mainly test data/model update or backdoor privileges. BadWorld's first-broken interface is observation/context. Without specifying the privileges of training data, model updates, test inputs, and future control knowledge, backdoor success rate or attack success rate cannot be used for engineering risk assessment. [@hu2026swaap] [@rathbun2026targeting] [@shuai2026baddreamer] [@shen2026badworld]

### ARB4WM, RoboTrustBench, and the Runtime Assurance Series

ARB4WM evaluates attacks and basic defenses uniformly on continuous control world models. RoboTrustBench instead asks how trustworthy video world models are for robotic manipulation. Both expose one gap: a benchmark has to test "downstream tasks", not only "generation quality". A benchmark is not a defense, though. UNISafe, SafeDreamer and SLS-squared supply the "how to intervene" layer, through latent uncertainty filtering, safe world model reinforcement learning, and probabilistic robust MPC. CheckVLA and DreamGuard move the intervention point to runtime. Each method still needs further testing against adaptive adversaries that target its filter or judgment model. [@zhang2026arb4wm] [@li2026robotrustbench] [@seo2025unisafe] [@huang2023safedreamer] [@nath2026sls2] [@liu2026checkvla] [@lin2026dreamguard]

## Happy Oyster and MoWorld: Product/Project Entity Resolution

Retrieval easily conflates the user-supplied aliases happy oyster and moworldmodel, yet first-hand evidence shows two different entities. Happy Oyster is the canonical name on the official website. HappyOyster is a spelling variant in Alibaba's fiscal year report, and Happy-Oyster merely a search variant. The official website positions it as an open-ended world model for real-time world creation and interaction. Alibaba's FY2026 annual report places it in the business context related to the Alibaba Token Hub. This survey annotates it as a WM+EWM bridge, based on the vendor's official feature statements rather than papers, model cards, or independent technical verification. No verifiable academic paper, model card, weights, code, or direct attack-defense evidence against this product was found. It cannot therefore be judged a proven WAM/WCM, nor called safe or unsafe. [@happyoyster2026] [@alibaba2026annual]

MoWorld is the official project name of 魔芯/Moxin-Tech. MoWorldModel, moworldmodel, and Mo World were not established as official canonical names as of the cutoff date. The project conditions on an initial frame, text, and WASD camera operations, then predicts latent variables for later frames. The paper explicitly states that navigation decisions are decoupled from visual generation. It is therefore a relatively clear WM+EWM, rather than a proven WAM/WCM. As of 2026-08-09, the official repository holds only a README and 2 commits, with no license metadata. It should be called a repository placeholder, not a complete open-source or reproducible release. MoWorld 3D, a related product from the same publisher, is coded separately; it was not forced into identification as the paper's model version. [@moxin2026moworld] [@moxin2026github]

| Entity | Established | Not established |
| --- | --- | --- |
| Happy Oyster | Alibaba; officially described as an interactive world model | This survey only annotates it as EWM bridging |
| MoWorld | 魔芯; visual generation is decoupled | WAM/WCM; complete open source |

*Official identity, functional contract, and evidence gaps for the two entities. The classification in this survey is not a product safety certification.*

## Application Scenarios and Deployment Risk Mapping

A world model's safety requirements follow from the application's information flow and maximum privilege. Game agents mainly care about adversarial observations, long-horizon policy degradation, and match integrity. Autonomous driving EWMs need cross-modal checks on maps, 3D boxes, vehicle dynamics, and downstream planning. Robotic WAMs must separate visual prediction from action head guarantees. Safety-critical WCMs must additionally fold latency, actuator clamping, fail-safe states, and human takeover into one safety argument. [@guan2024drivingsurvey] [@hou2026robotsurvey]

When a world model serves as a training data generator or a policy evaluator, risk does not necessarily manifest at the same moment. A poisoned generation environment may re-enter the real system through a downstream policy weeks later. A compromised evaluator may approve a policy that is itself unsafe. Deployment records should therefore cover data generation, policy versions, evaluation results, and actual execution, rather than just the last model weights. Approaches such as WorldEval that "evaluate policies with world models" especially need independent verification of the evaluator's own bias and attack surface. [@li2025worldeval]

## Datasets, Metrics, and Results That Cannot Be Pooled

The evidence currently spans Atari, DeepMind Control Suite, Safety-Gym-style continuous control, robotic manipulation, autonomous driving video, trajectory prediction, agent tools, and diffusion video. Models include DreamerV2/V3, TD-MPC2, IRIS, driving EWMs, WAMs, and risk world models. Attack budgets may be pixel norms, conditional embedding perturbations, poisoning ratios, trigger visibility, query counts, or tool privileges. So "ASR" may mean target trajectories, backdoor triggering, task failure, dangerous actions, or video dynamics disruption, depending on the study, with different denominators.

- Generation level: FID, FVD, LPIPS, PSNR, SSIM, and human ratings. They capture visual or distributional quality, not closed-loop safety metrics.

- State level: latent distance, prediction error, temporal consistency, uncertainty, and independent anchor error. Small internal residuals cannot rule out shared drift.

- Planning level: candidate trajectory ranking, value/cost, reachability, constraint violation, and replanning rate. Open loop and closed loop must be distinguished.

- Action level: action deviation, imagination–action consistency, task success, risky action rate, and safety filter intervention.

- Execution level: collisions, boundary violations, tool side effects, stopping distance, recovery time, rollback success, and human takeover.

- System level: latency, compute/energy, false alarms/misses, availability, audit chain integrity, and performance under unknown attacks.

This round's conclusion on meta-analysis is "do not run, because comparability is insufficient." No three independent studies are comparable on the same estimand, model/task, budget, ASR denominator, and variance. A forest plot drawn from the papers' percentages would disguise differences in task difficulty, budget, success definitions, and repeated models as one interpretable overall effect. This survey therefore keeps only study-level metrics, qualitative synthesis, and the number of evidence cards, and it performs no causal ranking.

## News, Industry Signals, and Governance Integration

The 36-event timeline covers 2018-03-27 through 2026-07-30. It spans capability/product, direct attack/red teaming, defense/assurance, and governance/standards. The capability line starts from World Models and passes through latent planning, generative driving worlds, interactive video, and physical AI platforms. In 2026 it enters a phase of WAM, runtime assurance, and high-density safety papers. NVIDIA's Cosmos release shows world foundation models becoming parts of physical AI platforms. Happy Oyster and MoWorld carry the product signal of real-time, open-world creation and rapid interactive generation. But a product release is not safety evidence, and more papers do not equal more real-world attack incidents.[@nvidia2025cosmosblog] [@happyoyster2026] [@moxin2026moworld]

![Timeline of world model capability, attack-defense, and governance events. All events are retained as points, and only time anchors are labeled; labels do not represent influence or evidence strength.](../figures/fig04_news_timeline.png)

*Timeline of world model capability, attack-defense, and governance events. All events are retained as points, and only time anchors are labeled; labels do not represent influence or evidence strength.*

### General AI Risk Management and Adversarial Machine Learning Language

The NIST AI RMF organizes full-lifecycle risk around Govern, Map, Measure, and Manage. ISO/IEC 23894 provides AI risk management guidance; ISO/IEC 42001 defines an AI management system. NIST AI 100-2 provides a general taxonomy of poisoning, evasion, privacy, and mitigation. Such documents can constrain governance, documentation, measurement, and continuous monitoring. They give no benchmarks specific to world models for temporal state contamination, imagination—action mismatch, or closed-loop physical side effects. Nor are they a safety certificate for any product.[@nist2023airmf] [@nist2024aml] [@iso2023ai23894] [@iso2023ai42001]

### Vehicle, High-Risk AI, and Generated Content Rules

UNECE UN R155/R156 bring vehicle cybersecurity management and software update management into the type approval context. ISO/PAS 8800 focuses on AI safety in road vehicles. Both are directly relevant to the supply chain, OTA, safety argumentation, and continuous vulnerability handling of in-vehicle EWM/WAM/WCM. Their scope depends on the vehicle model, manufacturer responsibility, and place of deployment. The EU AI Act must be judged case by case, according to purpose, market placement, and high-risk classification. China's Interim Measures for the Administration of Generative AI Services have relevant requirements for public-facing generative services, audio/video, and virtual scenes. The Measures for Labeling AI-Generated Synthetic Content carry relevant requirements as well. Labeling and provenance can reduce the risk of misidentification and source removal. They cannot prevent latent state attacks, action hijacking, or closed-loop control failure.[@unece2021r155] [@iso2024pas8800] [@eu2024aiact] [@cac2023genai] [@cac2025label]

### How to Interpret News Without Treating It as an Experiment

Each record keeps the event occurrence date, first public date, source date, claiming entity, primary source, independent source, evidence level, correction status, and applicability notes. A corporate website can support "how the company positions a product", but not performance leadership on its own. A preprint can support the authors' results under its trial protocol; it cannot prove that a commercial system has been attacked. An expert blog offers an argumentative perspective, but is not regulation or experimental data.[@york2026safety]

## Code Audit and Safety Reproduction Status

The reproduction workflow first audits the current official repositories of BadWAM, WISER, SafeDreamer, and UNISafe. It also runs first-hand paper/project entry checks for TRAP, PhysCond-WMA, JailWAM, WMAttack, and SWAAP. Audit fields include owner, repository URL, commit, license, dependencies, entry points, configuration, weight/data availability, and actual run receipts. To avoid large weight downloads and high-risk real-device operations, only safe, low-cost core submodules or formula/mechanism proxies are executed.

| Status | Count | Evidence boundary |
| --- | --- | --- |
| Mechanism-level partial reproduction | 6 | Counted by actual evidence |
| Static audit | 3 | Counted by actual evidence |

*Code audit and reproduction ladder, automatically generated from the actual run manifest.*

In this run, END_TO_END=0. The status comes from per-command receipts and output hashes. The existence of a repository, a dependency installation, or a formula proxy does not equal an end-to-end attack or defense reproduction.

![Actual code audit and reproduction status ladder. PARTIAL_MECHANISM only means that a code- or formula-level mechanism has been run on safe toy inputs.](../figures/fig05_reproduction_ladder.png)

*Actual code audit and reproduction status ladder. PARTIAL_MECHANISM only means that a code- or formula-level mechanism has been run on safe toy inputs.*

### What Static Audits and Mechanism-Level Outputs Can Prove

A static audit can prove what entry points, dependencies, and configuration an official repository contains at a given commit. It can also expose license, data, weight, or documentation gaps. A mechanism-level partial reproduction can prove, on constructed inputs, that a submodule changes ranking, safety boundaries, residuals, or actions as expected. Neither can prove that paper numbers, data pipelines, large-model weights, closed-loop environments, or real-robot effects have been reproduced. End-to-end status requires official or verified equivalent weights, data, configuration, closed-loop tasks, multiple seeds, and result alignment, all of which must pass.

### Safety and Rerunnability Controls

All runs are confined to local, isolated toy data or numerical formulas. They do not touch real robots, vehicles, public services, or third-party accounts. For each candidate, the command, standard output/error, exit code, elapsed time, environment information, result JSON, and SHA-256 are retained. For candidates where only a formula proxy can be run, the script is retained with the article. The manifest then explicitly marks that it is not the official end-to-end pipeline.

## Cross-Family Synthesis and Deployment Choices

WM, EWM, WAM, and WCM are not a linear hierarchy from lower to higher level. A system can belong to several classes at once, or use only one of these capabilities in deployment. Safety architecture should be reasoned backward from "worst executable privilege". If a model only generates offline video, the main risks are data, privacy, content provenance, and downstream misuse. If it provides trajectories to a planner, trajectory consistency, uncertainty, and closed-loop evaluation are needed. If it outputs actions or control commands, independent action verification, safety envelopes, least privilege, stop/rollback, and human takeover must be added.

- Offline EWM: prioritize auditing training provenance, conditioning completeness, memorization, watermarking/labeling, sliding-window temporal consistency, and downstream misuse.

- Simulation/digital-twin EWM: add physical conditioning signatures, counterfactual scenarios, real-data anchors, simulation bias boundaries, and downstream policy gating.

- Planning WM: add candidate trajectory ranking stability, uncertainty calibration, worst-case optimization, and emergency safety policies.

- WAM: imagination completeness and imagination—action alignment must be tested separately. Treat the action head, token interface, and semantic decoding as independent supply chain assets.

- WCM: use external constraints, robust MPC/safety filtering, hard real-time latency budgets, actuator saturation, fail-safe modes, and physical stop channels.

- Agentic world models: treat tool descriptions, web pages, and return values as untrusted observations. Enforce least privilege, side-effect previews, and transaction-level approval.

The most easily overlooked issue in engineering is common-cause failure of defense lines. Suppose the predictor, risk discriminator, and action verifier use the same encoder, the same training set, and the same context. Then three "independent modules" may misjudge the same perturbation simultaneously. Diversity among models, data, sensors, logical rules, and actuators should therefore be measured explicitly. The safety envelope should rest on boundaries an attacker finds harder to control at the same time.

## Future Trends and a Falsifiable Research Agenda

The main change in the coming years will not be merely larger parameters. World models will increasingly serve as simulation platforms, data generators, evaluators, planners, action models, and runtime gatekeepers. The same model can act as a defender and generate adversarial scenarios. World Models as Adversaries has already used multi-agent self-play fine-tuning to improve motion planning robustness. That blurs the boundary between "attack generation" and "safety training", so auditable evaluation protocols are all the more necessary.[@nie2026wmasadversaries]

- Agenda One—Executable model contracts: public benchmarks should declare state, future, action, and control interfaces together. The acceptance condition is that different researchers obtain a consistent family encoding for the same model.

- Agenda Two—Imagination—action dual-axis benchmark: construct the four quadrants of imagination wrong/right and action wrong/right at the same time. The acceptance condition is that the metrics can identify the BadWAM-style "dreams right but acts wrong".

- Agenda Three—Long-horizon independent anchors: place internal residuals side by side with external geometric/physical/rule anchors. The acceptance condition is the ability to expose common drift rather than only random noise.

- Agenda Four—Multi-interface adaptive attacks: the attacker jointly optimizes conditioning, state, value, and action. The acceptance condition is unified reporting of budget, queries, privileges, and propagation paths.

- Agenda Five—Adaptive red teaming against safety gates: bring detectors, filters, and rollback policies all into the adversary model. The acceptance condition is simultaneous reporting of post-attack risk, clean pass rate, and worst-case latency.

- Agenda Six—A bridge from prediction to proof: combine conformal intervals, reachability, control barrier functions, and visual latent worlds. The acceptance condition is explicitly stating the guarantee degradation when prediction assumptions fail.

- Agenda Seven—Supply chain and runtime lineage: bind data, weights, configuration, encoders, safety heads and event logs into one chain. The acceptance condition is that every action can be traced back to the world model version and the conditioning used.

- Agenda Eight—Privacy and the right to world reproduction: build memorization/extraction benchmarks for video, maps, indoor environments and user trajectories. The acceptance condition is simultaneous evaluation of utility, membership leakage and scene identifiability.

- Agenda Nine—Multi-agent shared worlds: test whether an adversary can manipulate shared state, the intentions of others or traffic rules. The acceptance condition is to report the safety difference between individual and system levels.

- Agenda Ten—From competition scores to incident recoverability: add metrics for stopping, degradation, rollback, replanning, human takeover and evidence preservation. The acceptance condition is that an evaluation can answer "how does it end after failure".

- Agenda Eleven—Open and limited reproduction packages: release small weights/toy models, attack cards, safety configurations, command receipts and data licenses. The acceptance condition is that third parties can reproduce the core mechanisms without touching real devices.

- Agenda Twelve—Technicalizing governance requirements: map regulatory/standard clauses to data fields, tests, runtime gating and logs. The acceptance condition is a clear distinction between what is applicable, what is not applicable, and obligations that still require legal judgment.

Three directions can be cautiously anticipated from the evidence as of the cutoff date. First, attacks will expand from single-frame observations to multiple interfaces, long horizons and feedback deception. Second, defenses will shift from anomaly scores to runtime assurance and recovery that can change actions. Third, product safety evaluation will increasingly require versioned evidence, event logs and use-specific regulatory mapping. These are research hypotheses drawn from current evidence. They are not facts that have already occurred. Future data should support or falsify them under the acceptance conditions above.

## Limitations

First, publication density in this field was very high in 2026. A considerable share of the direct security evidence is still preprints, so peer review, code and data availability may change after the cutoff date. Second, the broad arXiv search had a preregistered return cap. Not all candidate-level records were screened by hand in full text. Third, the terminological boundaries of EWM and WCM are not yet stable. The functional classification in this survey exists for comparability. It does not replace the original naming used by authors or products. Fourth, the security reproductions remained mainly at static audits and mechanism-level partial runs, to avoid large weights, high cost and real-device risk. They do not prove the authors' numbers or real-world threats. Fifth, heterogeneous metrics make a meta-analysis untenable. The counts in this survey reflect how the evidence is distributed. They are not a ranking of methods or a probability of incidents.

The judgments about Happy Oyster and MoWorld in particular need to be conservative. Official feature descriptions support entity identity and a coarse-grained contract. There is no model card, no complete code/weights, no independent evaluation, and no direct attack or defense papers. This survey did not execute attacks on either of them. It also did not prove that they contain specific vulnerabilities. Any subsequent new official paper, repository, model version or security advisory should be added through entity versions and timestamps. It should not overwrite the historical record.

## Conclusion

World-model security is not about inventing a set of terminology for every new brand. Its core is to find the first-broken interface within a unified closed loop. It is also to measure how errors propagate across time into imagination, action and execution. And it is to establish whether a line of defense can block, recover and retain evidence under an adaptive adversary. Current attack evidence has already expanded beyond observational perturbations. It now covers physical conditions, the supply chain, trajectory ranking, WAM jailbreaking and action heads. Defenses, in turn, are beginning to move away from anomaly scores. They are moving toward uncertainty filtering, robust MPC, runtime verification and blocking before tool invocation.

However, direct, verifiable and cross-study comparable evidence remains scarce. Dedicated defenses in particular lag behind attack methods, and end-to-end open-source reproductions are also insufficient. Therefore the most responsible conclusion at present is not to declare that some model is already safe. It is to build versioned supply chains, independent state anchors, imagination–action dual-axis testing, diverse run gating, physical safety envelopes, recoverable execution and audit receipts. These capabilities push world models from "looking plausible" toward "acting safely within testable boundaries."

## Citation and Evidence Notes

In the main text, `[@citation_key]` points to the `references.bib` in the same-source LaTeX package. Retrieval logs, paper cards, incident tables, code receipts and statistical rejection evidence sit in the corresponding subdirectories at the project root.
---

# Appendix — Post-cutoff update (2026-08-09 → 2026-09-26)

The body's material closes at 2026-08-09. This appendix registers later material; **the body text is unchanged.**

## A.1 — New world-model security work since the cutoff

| Paper | Topic | Body issue |
|---|---|---|
| Denying the World Model: Automated Moving Target Defense as an Architectural Countermeasure to Autonomous AI Agents | architectural countermeasure that keeps a world model from being stably modelled | the defence, runtime assurance and recovery chapter: from detection toward **making the world model unmodellable** |
| UAWM: A Unified Adaptive World Model with Multi-Layered Security for Robust Decision-Making | multi-layer security built into the world model | same chapter: safety constraints inside the architecture rather than bolted on |

Both point the way the body already indicated: **defence is moving from "detect a wrong prediction" to
"design so that a wrong prediction is hard to exploit."** The body's convergence judgement — defence must
be able to fail, intervene and recover — is unaffected, but these give concrete architectural candidates.

## A.2 — The terminology gap is still open

The limitations chapter notes that the boundary between EWM and WCM is unsettled. Later material continues
that instability: new preprints keep coining fresh "world model + security" combinations, which raises the
value of a **functional** classification. Deciding a model's class by its state and its consumer is exactly
what handles this kind of naming drift.

## A.3 — Institutional consequence of the OpenAI–Hugging Face incident

On 2026-09-16 / 17 OpenAI published an account of the incident and announced a safety-incident disclosure
process; reporting describes roughly 700 agents, dozens of third-party systems and 53 leaked user images;
the US Senate opened an investigation (led by Hawley).

**Its relation to this survey**: the incident involves no world model, but it establishes a **post-hoc
disclosure convention for agent overruns**. For world-model security, a hijacked imagination chain inside an
autonomous agent would be reconstructed after the fact through the same mechanism — which gives the body's
demand for falsifiable tests and runtime records an external institutional footing.

## A.4 — How to use this appendix

The four functional boundaries, the attack-surface matrix and the refusal to pool are unaffected. What
changes is the **shape of defence research**: from detectors toward architectural non-exploitability. When
citing the items above, cite both the body cutoff and this appendix's date.