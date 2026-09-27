ition. The survey therefore generates no pooled ASR, forest plot, I-squared, funnel plot, or causal ranking.

## Threat Model and Safety Properties

The assets of world-model safety are many. They include training data and model artifacts, observations and conditioning signals, long-term memory and latent states, dynamics parameters, rewards/values/constraints, imagined trajectories, actions or control commands, actuators/tools, and user privacy. An attacker may be able to control only the appearance of the environment. Alternatively, the attacker may obtain differing privileges over sensors, conditioning embeddings, training samples, reward interfaces, model gradients, the supply chain, or tool descriptions. "White-box success" cannot be automatically extrapolated to a remote black-box threat. "Black-box transfer" must also state the number of queries, surrogate data, and attack budget.[@nist2024aml]

- Prediction integrity: future states, observations, rewards, and constraints are not maliciously biased.

- Temporal consistency: long-horizon dynamics still do not drift abnormally when local frames appear plausible.

- Imagination-action alignment: actions must be consistent with imagination that is evaluated as safe and effective.

- Constraint satisfaction: uncertainty, safety distance, risk budget, and human intent remain effective in the closed loop.

- Recoverability: after an anomaly occurs, the system can stop, roll back, switch to a safe policy, or hand over to a human.

- Auditability: data, models, configurations, world predictions, actions, and execution results have linkable records.

Malicious attacks and natural failures must be strictly distinguished. Natural distribution shift, occlusion, sensor noise, long-horizon model bias, and computation latency can expose weaknesses at the same interface. They can be called attacks only after the adversary's objective, privileges, and budget are defined. Conversely, natural-robustness methods can serve as safety-assurance brid

---

[← Back to contents](index.md)
