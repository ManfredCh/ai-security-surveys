## Introduction: When Imagination Becomes Decision and Control Infrastructure

The safety problem of world models is not merely "whether the generated imagery is realistic." A model keeps a latent state from historical observations, predicts how the environment will evolve, and then feeds those predictions into planning, action, or feedback control. A local error may accumulate over time and become an irreversible physical consequence at the execution end. World Models, PlaNet, Dreamer, and MuZero established the technical lineage of "planning or learning in a learned world." Driving video world models, interactive environment generators, world action models, and world-model-based safety control extend the attack surface from pixels to physical conditions, latent dynamics, imagined trajectory ranking, action heads, and tool execution.[@ha2018worldmodels] [@hafner2019planet] [@hafner2020dreamer] [@schrittwieser2020muzero]

The central thesis of this survey is that prediction and action are coupled, and that this coupling multiplies risk. Coupling itself, however, does not equal being unsafe. Risk turns on three things. The first is which functional interface fails first. The second is whether the closed loop amplifies errors. The third is whether the system has an independent observation anchor, action gating, a safety envelope, rollback, and human takeover. This survey therefore takes the first-broken interface along the chain of "supply chain—observation—state—dynamics—objective—planning/action/control—execution and feedback" as its primary axis, and treats WM, EWM, WAM, and WCM as secondary axes.

- Contribution 1: Provides verifiable input-output contracts for the four model classes, so that not every video generator is called a world model and not every action-conditioned video is called a WAM.

- Contribution 2: Analyzes data poisoning, physical-condition perturbation, latent-state contamination, imagined-trajectory hijacking, reward/constraint tampering, action mismatch, tool misuse, and privacy leakage under a unified attack contract.

- Contribution 3: Maps prevention, detection, suppression, recovery, and assurance onto the same closed loop, and writes the residual risk under adaptive attacks into every defense conclusion.

- Contribution 4: Separates academic full texts, official product/repository sources, standards and regulations, and news events, and completes entity disambiguation for Happy Oyster and MoWorld.

- Contribution 5: Provides rerunnable safety toy experiments and code-audit receipts, strictly distinguishing static auditing, mechanism-level partial reproduction, and end-to-end reproduction.

---

[← Back to contents](index.md)
