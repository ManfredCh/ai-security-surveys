## Conclusion

This survey reorganizes VLM, VLA, and WAM security evidence around the first-broken system interface. The six-interface main axis places training artifacts, observation, cross-modal semantics, world state, action decoding, and execution feedback on a single chain. It demotes the attack carrier, knowledge, realism, objective, and evidence layer to secondary labels. That avoids repeated classification by paper name and trending terminology.

The common mechanism of the attacks is that untrusted input acquires ever-deeper write privileges. It first changes the observation or state, then controls reasoning, candidate futures, or action dynamics, and finally seeks execution and feedback. Defense must be deployed as a mirror along the same chain. Input purification and model self-checks can only reduce part of the risk. Action authorization, independent physical constraints, state recovery, and forensics are responsible for limiting the consequences after the earlier layers fail. [@A021; @A024; @A033; @A036; @A054]

WAM carries one core warning: "dreaming right" does not guarantee "acting right". When the same attacked model is the only verifier of its own futures, plans, and actions, it produces correlated self-consistency rather than an independent guarantee. High-risk actions require three-way verification across forward imagination, inverse reachability, and real feedback. They must also introduce at least heterogeneous observations or a physical safety set. [@A029; @A033; @A036; @A058]

Quantitatively, the reported descriptive magnitude of the decline in task success is large, but independence, variance, budget, and endpoint do not satisfy the requirements for pooling. The 52/52 meta-analysis units and the 3/3 strict correlations were formally rejected. On the engineering side, the LaTeX, evidence, and static repository contracts can be rechecked. End-to-end reproduction of the paper's numerical results, however, is zero. The most honest conclusion is not a unified risk ranking. It is clarity about which chains have been directly observed, which are only hypotheses, and which still need to be run.

In the end, embodied security is not about making the model never make mistakes. It is about ensuring that, when untrusted states propagate toward action authority, the system has an independent, low-latency, and recoverable authority revocation mechanism. The main manuscript ends here. The concrete algorithms, instances, formulas, boundaries, and core original figures of all 97 papers are preserved paper by paper in the separate algorithm atlas.
---

# Appendix — Post-cutoff update (2026-08-06 → 2026-09-26)

The body's retrieval was frozen on 2026-08-06, auditing 382 screening records and including 97 studies
qualitatively. This appendix registers later material; **the body text is unchanged.**

---

[← Back to contents](index.md)
