## Cross-Family Synthesis and Selection Guide

Under the unified trust-boundary axis, cross-family comparison is not about whose single ASR is lowest. It asks which layer of control changes reachability, state control, dangerous intent, action authorization or final harm.

Despite the proliferation of attack names, six categories of root cause can be summarized across topics. Where instructions and data lack a strong boundary, natural language carries content and control at the same time, so the model can only judge priority probabilistically. Where authorization is completed at the wrong layer, the model both decides the action and decides whether it is itself authorized to execute it, rather than an independent policy judging according to the user, the task, the resources and the consequences. Where provenance and identity are lost during transformations, only plain text remains after retrieval, OCR, summarization, compression and cross-agent forwarding, with no provenance, tenant or sensitivity labels.

The other three categories of root cause lie in state, isolation and evaluation. When state writes are more permissive than reads, a single web page or tool output is allowed into long-term memory, an index, a cache or a code repository. Isolation boundaries have uncounted exits. Package proxies, debugging tools, metadata services, shared volumes, long-lived tokens and third-party sandboxes can still cross trust domains, so "no public network" or "already isolated" must be subject to end-to-end verification. When evaluation treats correlated cells as independent evidence, model versions, prompts, judges and sample reuse produce spurious statistical precision and conceal cross-scenario failures.

The defense chapters that follow will be organized around these root causes, rather than providing easily outdated string rules for each attack name one by one.

### Four Layers of Defense in Depth and Their Failure Modes

There is no single "safety prompt" that solves jailbreaks, indirect injection, memory poisoning, malicious weights and sandbox escapes at once. A more useful way to organize the discussion is to ask whether the next layer can still limit the consequences after one layer of control fails. The unified taxonomy figure already draws the relationships among the four layers, and they are explained paragraph by paragraph below.

The first layer is probabilistic model defense. Safety fine-tuning, refusal policies, input/output classifiers, randomized smoothing and multi-model review can reduce the frequency of known harmful content, of some jailbreaks and of obvious injections. They cannot on their own guarantee permanent robustness against adaptive attacks. Nor can they grant real permissions or prove the absence of side effects.

The second layer is structured control and information flow. Instruction/data channels, provenance labels, taint propagation, typed variables, task-alignment checks and RAG ACLs stop data from being promoted into instructions, prevent cross-tenant reads and keep sensitive values from flowing to the wrong tool. Their guarantees still depend on whether the labels, policies, adapters and underlying code are correct.

The third layer is system isolation and capability constraints. Least privilege, action gates, short-lived tokens, network egress, secret brokers, microVM/gVisor/WASM and resource budgets separate dangerous intent from dangerous execution, and they limit lateral movement, exfiltration and runaway resource consumption. They still cannot automatically identify business-logic abuse inside the allowed set, nor can they guarantee that the allowed domain and trusted tools will never be compromised.

The fourth layer is operational governance and response. Signed supply chains, version gates, continuous red teaming, end-to-end traces, alerting, revocation, forensics and disclosure address drift, unknown attacks and persistent impact after compromise. They cannot provide absolute prevention in advance, but they determine whether a team can reconstruct the true history, narrow the impact and turn remediation into a long-term gate.

The first layer reduces attack frequency and manual burden. The second and third layers determine whether an attack can cross data, identity and execution boundaries. The fourth layer determines whether the system can detect and recover from unknown failures. High-impact actions require at least independent controls from the latter three layers. A second self-judgment by the same model does not count as an "independent line of defense".

### Cross-Paper Synthesis: What Can Be Compared and What Must Be Kept Separate

Mechanisms are what can be compared stably. Adaptive search usually weakens static string defenses. An independent policy closer to the action constrains actual consequences more effectively. If provenance and tenant labels do not propagate with data transformations, later layers cannot restore them. There are also genuine trade-offs among safety, utility and cost. What cannot be compared directly is violation generation rates under different policies, the fraction of compromised applications, word-level corpus recovery rates, tool goal completion rates, memory survival rounds, detection accuracy and real incident counts.

This survey therefore does not declare the "strongest attack/defense" on the basis of a cross-paper ASR leaderboard. For every number, three questions are asked first. What is the denominator? At which layer does success occur? Does the attacker know the defense? If any item is unclear, the result can at most enter a descriptive evidence map, and it cannot enter a merged effect.

---

[← Back to contents](index.md)
