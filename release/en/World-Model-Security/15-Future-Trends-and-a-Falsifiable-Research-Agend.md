licitly. The safety envelope should rest on boundaries an attacker finds harder to control at the same time.

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

Three directions can be cautiously anticipated from the evidence as of the cutoff date. First, attacks will expand from single-frame observations to multiple interfaces, long horizons and feedback deception. Second, defenses will shift from anomaly scores to runtime assurance and recovery that can change actions. Third, product safety evaluation will increasingly require versioned evidence, event logs and use-specific regulatory mapping. These are research hypotheses drawn from current evidence. They are not facts t

---

[← Back to contents](index.md)
