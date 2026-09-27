vidence gaps for the two entities. The classification in this survey is not a product safety certification.*

## Application Scenarios and Deployment Risk Mapping

A world model's safety requirements follow from the application's information flow and maximum privilege. Game agents mainly care about adversarial observations, long-horizon policy degradation, and match integrity. Autonomous driving EWMs need cross-modal checks on maps, 3D boxes, vehicle dynamics, and downstream planning. Robotic WAMs must separate visual prediction from action head guarantees. Safety-critical WCMs must additionally fold latency, actuator clamping, fail-safe states, and human takeover into one safety argument. [@guan2024drivingsurvey] [@hou2026robotsurvey]

When a world model serves as a training data generator or a policy evaluator, risk does not necessarily manifest at the same moment. A poisoned generation environment may re-enter the real system through a downstream policy weeks later. A compromised evaluator may approve a policy that is itself unsafe. Deployment records should therefore cover data generation, policy versions, evaluation results, and actual execution, rather than just the last model weights. Approaches such as WorldEval that "evaluate policies with world models"

---

[← Back to contents](index.md)
