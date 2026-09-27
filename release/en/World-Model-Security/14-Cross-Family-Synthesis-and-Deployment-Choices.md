tained with the article. The manifest then explicitly marks that it is not the official end-to-end pipeline.

## Cross-Family Synthesis and Deployment Choices

WM, EWM, WAM, and WCM are not a linear hierarchy from lower to higher level. A system can belong to several classes at once, or use only one of these capabilities in deployment. Safety architecture should be reasoned backward from "worst executable privilege". If a model only generates offline video, the main risks are data, privacy, content provenance, and downstream misuse. If it provides trajectories to a planner, trajectory consistency, uncertainty, and closed-loop evaluation are needed. If it outputs actions or control commands, independent action verification, safety envelopes, least privilege, stop/rollback, and human takeover must be added.

- Offline EWM: prioritize auditing training provenance, conditioning completeness, memorization, watermarking/labeling, sliding-window temporal consistency, and downstream misuse.

- Simulation/digital-twin EWM: add physical conditioning signatures, counterfactual scenarios, real-data anchors, simulation bias boundaries, and downstream policy gating.

- Planning WM: add candidate trajectory ranking stability, uncertainty calibration, worst-case optimization, and emergency safety policies.

- WAM: imagination completeness and imagination—action alignment must be tested separately. Treat the action head, token interface, and semantic decoding as independent supply chain assets.

- WCM: use external constraints, robust MPC/safety filtering, hard real-time latency budgets, actuator saturation, fail-safe modes, and physical stop channels.

- Agentic world models: treat tool descriptions, web pages, and return values as untrusted observations. Enforce least privilege, side-effect previews, and transaction-level approval.

The most easily overlooked issue in engineering is common-cause failure of defense lines. Suppose the predictor, risk discriminator, and action verifier use the same encoder, the same training set, and the same context. Then three "independent modules" may misjudge the same perturbation simultaneously. Diversity among models, data, sensors, logical rules, and actuators should therefore be measured exp

---

[← Back to contents](index.md)
