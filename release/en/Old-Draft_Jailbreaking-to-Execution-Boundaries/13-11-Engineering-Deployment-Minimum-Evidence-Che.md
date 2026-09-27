udit in this survey yields zero poolable groups. That shows precisely that common reporting today is not yet sufficient to estimate the average true effect. Only as independent replications across multiple organizations, across models and at identical endpoints gradually appear will random effects, prediction intervals and causal stratification become more meaningful than a descriptive map.

### 10.9 Which Popular Narratives Should Not Be Taken as Trend Conclusions

“Smarter models are naturally safer” and “stronger models are necessarily more dangerous” both lack monotonic evidence. Capability, alignment, tool permissions and deployment boundaries all change at the same time. The so-called “end of universal jailbreaks” usually holds only under a fixed policy, a fixed model version and a fixed attack budget. Adaptive retesting may rewrite the result. So-called “fully automated AI defending against AI” is merely a loop of correlated failure when the same kind of model generates, executes, scores and approves at once. A more credible direction is for models to take on discovery, explanation and candidate planning. Independent identity, policy, information flow, execution isolation and human accountability keep the final authorization.

## 11. Engineering Deployment, Minimum Evidence Checklist, and Conclusions

### 11.1 Write Actions and Assets First, Then Prompts

Before deployment, first enumerate the real changes the system can cause. Work through the data it reads, the state it writes and the parties it sends to. Then check whether it can pay, whether it can run code, whether it can modify release artifacts and whether it can acquire new identities. Bind every class of action to a calling principal, tenant, object, parameters, network, secrets, resource budget, reversibility and approver. The threat model then enumerates entry points, failure boundaries and consequences along a unified taxonomy. Suppose a team knows only how to “prevent prompt injection.” If it cannot say what the model could do after a successful injection, security design has not yet begun.

### 11.2 Data, RAG, and Memory Must Be Identity-Isolated Before Entering the Model

ACL, tenant and purpose filtering must be enforced before retrieval. Do not put unauthorized data into the prompt and then rely on the model to keep it secret. External web pages, documents, OCR, tool outputs and automatic summaries are low-integrity by default. They carry their provenance into downstream variables, summaries and cross-agent messages. Memory writes require an independent policy, and the model cannot approve its own trust escalation. Deletion requires synchronized tombstones, index withdrawal, derivative tracking and backup-restore replay. Benign utility testing must confirm that security filtering has not stripped out facts the task needs.

### 11.3 The Release Standard for a Harness Is That Actions Cannot Self-Authorize

Model output first enters a read-only plan object. It then passes review of registration, task, data flow, parameters and consequences. High-impact actions use dry-run and two-phase commit. Approval is bound to canonicalized parameters, tool version and expiry time, and any change invalidates the approval. An external policy computes permissions as a minimal allow set. The model has no ability to expand scope, extend tokens, change tenants or disable logging. Safety classifiers may participate in scoring and escalation. They cannot, however, form the sole authorization chain together with the same model that generated the action.

### 11.4 Verify Execution, Network, Secrets, and Budget Separately

Sandbox acceptance should rely on real probes, not on the names in a configuration. At a minimum, the probes must verify in-scope reads and writes, out-of-scope reads and writes, process creation, DNS/redirection, loopback/private network/link-local/IMDS, device and host mounts, resource exhaustion and residue after destruction. Secrets do not enter the model context. Once an action is approved, a broker issues short-lived, audience-bound, minimal-scope credentials. Code execution and network evaluation should preferably run in disposable, strongly isolated units with no long-lived secrets and default-deny egress. Those units should be destroyed immediately when the task ends.

### 11.5 Release Gates Must Have Security, Utility, and Cost Thresholds Simultaneously

Report results separately for each action family: dangerous intent, dangerous execution, actual side effects or strict simulation, benign task success, false refusal, latency, token, tool steps and cost. For small samples, use intervals rather than reporting only zeros. Before-and-after comparisons on the same case must retain paired transitions. Never treat multiple cells from the same paper or the same seed as independent samples. For high-impact actions, acceptance turns on the one-sided upper bound of the dangerous execution rate and on the blast radius. The average refusal rate is not the test. If a test yields a request error or an empty response, that cell is recorded as undecidable or as an availability failure. It must not automatically count as safe.

### 11.6 Monitoring and Incident Response Must Be Able to Reconstruct the Entire Causal Chain

A unified trace must at minimum link the original user goal, context provenance, planning, model and prompt versions, tool schema, canonicalized parameters and policy decisions. It must also link human approval, credential issuance, network, files, memory writes and deletions, sandbox events and resource budget. After a detection fires, first freeze new actions, revoke identities, block egress and preserve forensic evidence. Then rotate credentials, rebuild the environment and purge index and memory derivatives. Finally, convert known entry points and detection signals into regression gates. Alerts with no on-call escalation, or logs with no action-ID correlation, do not add up to response capability.

### 11.7 Evidence Limitations of This Survey

Search candidates have been deduplicated and the raw API responses saved. No completed PRISMA log yet excludes all 1,854 candidates by title, abstract and full text. This survey therefore does not claim to be exhaustive over all papers. The attack, defense and incident base tables use different units and cannot be summed into a total paper count. If backfilling for the formal version continues, evidence-level statistics may still change. Most papers lack direct incident counts, paired transitions, independent replication and production side effects. The formal meta-analysis therefore yields zero pooled groups. The correlation is exploratory, over 34 selected studies. It does not represent the distribution of real-world incidents, nor a causal effect.

We used the local text-based harness and the macOS sandbox experiments to validate mechanisms. The harness is constrained by a single seed across six scenarios; the macOS sandbox is constrained by the deprecated sandbox-exec. The former does not execute real side effects, and the latter does not test escape. The VLM experiment obtained no valid responses, so it can only report a runtime timeout. Technical retrospectives from both sides of the 2026 OpenAI–HF incident have already provided substantial facts. OpenAI's more complete technical report had still not been published as of the materials cutoff, and some attribution and control details may continue to be updated.

### 11.8 Conclusions

The core tension in LLM security is not “how to find a prompt that can never be jailbroken.” It is that a natural-language planner works on incomplete, corruptible and probabilistic context, while real systems tend to give it persistent state and high-privilege capabilities. Jailbreaks, RAG poisoning, indirect injection, VLM attacks, memory poisoning, malicious tools and supply chain vulnerabilities appear scattered. Yet all of them come down to three questions. Does untrusted data gain control influence? Can a model proposal cross authorization on its own? Is the impact of a failure isolated and detected?

Model alignment remains necessary, because reducing dangerous intent eases the pressure on downstream lines of defense. But the most robust security gains come from independent boundaries outside the model. Provenance and tenancy are enforced before retrieval. Model output is only a proposal. Each action is approved by capability and information-flow policy. Network and secrets are minimized. Arbitrary code enters short-lived isolated units. Memory is traceable and deletable, and the entire trace is forensically auditable. The 2026 HF incident reminds us that naming an environment a “sandbox” does not automatically shut down package proxies, third-party harnesses, long-lived credentials and lateral networking. Security conclusions hold only when the allow/deny matrix, real probes, utility cost and failure records are all reviewable.

The most important quantitative conclusion of this survey is therefore restrained. Existing evidence is insufficient to compute a trustworthy “overall LLM compromise rate.” No like-for-like group among the 34 independent studies reaches three poolable studies. The exploratory correlation mainly shows research topics migrating toward agentic systems. More useful than a striking average is clarity. Which link of the attack chain is cut, and are normal tasks preserved? How does residual risk reach real assets, and can the conclusion be re-verified after the next model, tool or policy update?

---

[← Back to contents](index.md)
