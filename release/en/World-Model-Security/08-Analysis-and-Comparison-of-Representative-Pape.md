ld not be read as "it is already safe." [@guo2026wmattack] [@li2026robotrustbench] [@nie2026wmasadversaries]

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

ARB4WM evaluates attacks and basic defenses uniformly on continuous control world models. RoboTrustBench instead asks how trustworthy video world models are for robotic manipulation. Both expose one gap: a benchmark has to test "downstream tasks", not only "generation quality". A benchmark is not a defense, though. UNISafe, SafeDreamer and SLS-squared supply the "how to intervene" layer, through latent uncertainty filtering, safe world model reinforcement learning, and probabilistic robust MPC. CheckVLA and DreamGuard move the intervention point to runtime. Each method still needs further testing against adaptive adversaries that target its filter or judgment model. [@zhang2026arb4wm] [@li2026robot

---

[← Back to contents](index.md)
