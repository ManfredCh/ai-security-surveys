 especially need independent verification of the evaluator's own bias and attack surface. [@li2025worldeval]

## Datasets, Metrics, and Results That Cannot Be Pooled

The evidence currently spans Atari, DeepMind Control Suite, Safety-Gym-style continuous control, robotic manipulation, autonomous driving video, trajectory prediction, agent tools, and diffusion video. Models include DreamerV2/V3, TD-MPC2, IRIS, driving EWMs, WAMs, and risk world models. Attack budgets may be pixel norms, conditional embedding perturbations, poisoning ratios, trigger visibility, query counts, or tool privileges. So "ASR" may mean target trajectories, backdoor triggering, task failure, dangerous actions, or video dynamics disruption, depending on the study, with different denominators.

- Generation level: FID, FVD, LPIPS, PSNR, SSIM, and human ratings. They capture visual or distributional quality, not closed-loop safety metrics.

- State level: latent distance, prediction error, temporal consistency, uncertainty, and independent anchor error. Small internal residuals cannot rule out shared drift.

- Planning level: candidate trajectory ranking, value/cost, reachability, constraint violation, and replanning rate. Open loop and closed loop must be distinguished.

- Action level: action deviation, imagination–action consistency, task success, risky action rate, and safety filter intervention.

- Execution level: collisions, boundary violations, tool side effects, stopping distance, recovery time, rollback success, and human takeover.

- System level: latency, compute/energy, false alarms/misses, availability, audit chain integrity, and performance under unknown attacks.

This round's conclusion on meta-analysis is "do not run, because comparability is insufficient." No three independent studies are comparable on the same estimand, model/task, budget, ASR denominator, and variance. A forest plot drawn from the papers' percentages would disguise differences in task difficulty, budget, success definitions, and repeated models as one interpretable overall effect. This survey therefore keeps only stud

---

[← Back to contents](index.md)
