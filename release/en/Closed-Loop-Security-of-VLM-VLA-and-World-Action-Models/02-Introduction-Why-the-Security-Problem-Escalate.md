## Introduction: Why the Security Problem Escalates from "Seeing Wrong" to "Doing Wrong"

In an ordinary vision–language model, an adversarial patch, a piece of environment text or a poisoned demonstration may change only the answer. In an embodied system, that same input is written into state, plans, action chunks, candidate futures and execution feedback. The question that needs explanation is therefore not whether the model occasionally makes a mistake. It is when untrusted input acquires the power to change the physical world, and whether the system can revoke that power before real side effects occur. [@B003; @B004; @A001; @A036]

Existing VLM security research explains cross-modal representations, visual jailbreaking, poisoning and privacy well, yet it usually stops at text, retrieval or embeddings. VLA research advances the endpoint to action tokens, action chunks and closed-loop tasks. WAM in turn connects predicted futures, inverse dynamics or candidate ranking into decision-making. Surveying the three separately by model name would sever upstream mechanisms from downstream consequences. It would also mistake a seemingly reasonable world prediction for evidence of a safe action. [@B001; @B005; @A003; @A029; @A036]

This survey organizes the full text around four research questions. First, how do the safety endpoints of VLM, VLA and WAM escalate level by level? Second, at which interface does an attack first break the contract? How does it then propagate to action authorization and real feedback? Third, at which layer does a defense reduce reachability, detect anomalies, revoke authorization, limit execution, or restore the system? Fourth, how strong a cross-study conclusion do the numbers, code and physical experiments of heterogeneous papers actually permit?

This survey does not produce another set of attack names. It establishes a single main axis of six interfaces, same-coordinate mirror defenses, metric discontinuities and the statistical rejection contract. It also fixes the static reproduction boundary of four repositories and the separate "Atlas of Per-Paper Algorithms and Core Original Figures for 97 Papers". The main manuscript covers mechanisms and decisions. The atlas covers per-paper algorithms, instances, formulas, evidence boundaries and screenshots from the original papers.

---

[← Back to contents](index.md)
