## Conclusion

This survey's most stable conclusion is that high-privilege LLM/VLM agents should be regarded as planning components that are not fully trusted. The security boundary must then come jointly from provenance, identity, action authorization, memory governance, sandbox, network, secrets, and replayable auditing.

This draft is a generic, general-purpose Chinese compiled-draft target, not a submission bound to any specific journal template. Heterogeneous public evidence and the missing valid answer from the local VLM still limit the strength of the conclusions. Successful typesetting will not cover those limits over.

### Conclusion

The core contradiction in LLM security is not "how to find a prompt that will never be jailbroken." It is that natural language planners operate in contexts that are incomplete, contaminable, and probabilistic, while real systems tend to give them persistent state and high-privilege capabilities. Jailbreaking, RAG poisoning, indirect injection, VLM attacks, memory poisoning, malicious tools, and supply chain vulnerabilities look scattered. Ultimately they all come down to three things. The first is whether untrusted data gains control influence. The second is whether model proposals can cross authorization on their own. The third is whether the impact is isolated and discovered after a failure.

Model alignment remains necessary. Less dangerous intent can take pressure off the later lines of defense. The most robust security gains, however, come from independent boundaries outside the model. Provenance and tenant are enforced before retrieval, and model output is only a proposal. Capability and information flow policies approve actions. Network and secrets are minimized. Arbitrary code enters short-lived isolated units. Memory is traceable and deletable, and the entire trajectory is forensically auditable. The 2026 HF incident reminds us of one point. Calling an environment a "sandbox" does not by itself shut down package proxies, third-party harnesses, long-term credentials, and lateral networks. A security conclusion stands only if the allow/deny matrix, real probes, utility cost, and failure records can all be reviewed.

The most important quantitative conclusion of this survey is therefore a restrained one. The existing evidence is insufficient to compute a trustworthy "overall LLM breach rate," and among the 34 independent studies no same-scope group reached three poolable studies. The exploratory correlations mainly show that research topics are shifting toward agentic systems. More useful than a striking average is to state where the attack chain is cut off. It matters equally whether benign tasks are preserved and how residual risk reaches real assets. It also matters whether it can be re-verified after the next update of the model, tools, or policy.

---

[← Back to contents](index.md)
