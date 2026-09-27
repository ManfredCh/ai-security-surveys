ould test these combinations with reversible, isolated simulation protocols that have no third-party impact.

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

WMAttack's automatic finite-budget search reminds defenders that fixing a single hand-crafted attack configuration easily overestimates robustness. RoboTrustBench extends trustworthiness testing of video world models to robotic manipulation scenarios. World Models as Adversaries has a role-conditioned world model generate difficult interactions and then fine-tunes a motion planner with multi-agent self-play. This belongs to training-time coverage enhancement, not a formal guarantee against unknown real-world attacks. A complete continuous evaluation should include adaptive attacks against the target defense, reproduction across seeds and tasks, clean performance gating, and attack search budget. It should also cover a holdout set of unknown attacks, closed-loop long horizons, safety envelope intervention rate, recovery time, and post-failure reversibility. "No known attack was triggered" shou

---

[← Back to contents](index.md)
