suspected boundary violation, first freeze new actions, revoke short-lived capabilities, block egress and preserve forensic snapshots. Then rotate credentials, rebuild affected environments, clean memory/index derivatives and replay the scope of impact. Finally, turn the fix into an automated gate and canary. NIST's generative AI risk framework, MITRE ATLAS and OWASP can provide control and threat vocabulary, but the actual pass criteria must land on this system's actions, assets and logs.

## 6. Representative Paper Analyses: Compare Mechanisms, Not a Numeric Leaderboard

### 6.1 A Unified Analysis Template

This survey answers eight questions uniformly for each anchor paper. What asset does the research protect? Is the attacker black-box, gray-box or white-box? Which entry point can be written to? What are the attack budget and whether the attack is adaptive? What are the sampling unit and the definition of success? What are the main results and benign utility? Can the work be reproduced? How far can the conclusions be extrapolated? Below, only the anchors that determine the research thread are retained. Complete per-paper records appear in [attack-surface search](~/Codex/综述/LLMSE/research/01_学术攻击面检索.md) for the 23 attack papers, and in [defense-engineering search](~/Codex/综述/LLMSE/research/02_防御_harness_沙盒_memory_检索.md) for the 14 groups of defense/engineering anchors.

### 6.2 From "Why Safety Training Fails" to Adaptive Jailbreaking

[Jailbroken, NeurIPS 2023](https://proceedings.neurips.cc/paper_files/paper/2023/hash/fd6613131889a4b656206c50a8bd7790-Abstract-Conference.html) studies the competing objectives and mismatched generalization of safety training through black-box manual prompts. Its lasting value is to show that jailbreaking is not a magic string. It is a structural tension between task objectives and safety generalization. It does not establish that the prompts in the paper remain individually effective on all new versions. Nor does it provide a unified denominator that could serve as an overall ASR.

[GCG](https://arxiv.org/abs/2307.15043) uses white-box token gradients and coordinate search to optimize transferable suffixes. It demonstrates that out-of-distribution discrete strings can be found automatically, and it has become an important baseline for later adaptive attacks. It requires probability or weight access, so the cost differs for an ordinary API attacker. If judging only by an affirmative opening, it may also miscount refusals, truncations or harmless text as successes.

[PAIR](https://arxiv.org/abs/2310.08419) has an attacker model perform few-query black-box iterations based on feedback from the target model and the judge. This turns manual prompt attempts into a repeatable optimization loop and makes the query budget a core metric. PAIR also brings correlated error. If similar models do both the attack and the judging, the errors do not cancel each other out. Drift in the target API and in policy can also change reproduction results.

[Tensor Trust, ICLR 2024](https://openreview.net/forum?id=fsW7wJGLBd) comes from an online human attack-and-defense game. It contains roughly 563,000 attacks and 118,000 defense prompts. It is well suited to studying the speed of adaptation and the lifetime of strategies after a defense is made public. It is not a random sample of ordinary deployed users, and the attack frequency in the game cannot be taken as a real-world incident rate.

[Constitutional Classifiers](https://arxiv.org/abs/2501.18837) pairs a classifier-style constitutional defense with long-duration red-teaming. Under its own model and policy, it substantially reduces the reported ASR, and it also reports false refusals and inference cost. The result shows that the model's probability layer still has value, but it cannot replace action authorization. A single set of results from a closed-source vendor also does not reproduce automatically across models.

This line of work has a thread. Early manual attacks explained "why it fails". GCG/PAIR turned attacks into an optimization problem. Tensor Trust observed human adaptation after public release. Defense research then used training, classification, and perturbation to raise the cost of attack. All of it shares one boundary: the primary endpoint is still model output. Once a model can execute actions, the argument has to move on to the next group of evidence, at the system level.

### 6.3 From Indirect Injection to Executable Agents

[Not What You've Signed Up For](https://arxiv.org/abs/2302.12173) puts attacker instructions in web pages, emails, or retrieved content that the user application then reads on its own initiative. It establishes a remote indirect injection threat model in which "external data becomes control flow". The paper is an early systematic analysis of feasibility and impact classification. It does not provide cross-application incident rates.

[Prompt Injection Unified Benchmark, USENIX Security 2024](https://www.usenix.org/conference/usenixsecurity24/presentation/liu-yupei) cross-evaluates 5 attacks, 10 defenses, 10 LLMs, and 7 task types. Its most important finding is not some best number. It is that the ranking of defenses changes with the model, the task, the attack, and the metric. All configuration cells share data and methods, so they cannot be treated as independent studies and averaged.

[AgentDojo, NeurIPS 2024](https://proceedings.neurips.cc/paper_files/paper/2024/hash/97091a5177d8dc64b1da8bf3e1f6fb54-Abstract-Datasets_and_Benchmarks_Track.html) places injection through external tool results into 97 benign tasks and 629 security cases. It measures benign completion and attack-goal completion, and it lays the foundation for the security-utility two-axis evaluation. Its tools and user data are still a simulated environment. They cannot represent incident rates for real OAuth, production data, and irreversible transactions.

[InjecAgent, ACL Findings 2024](https://aclanthology.org/2024.findings-acl.624/) uses 1,054 cases, 17 user tools, 62 attacker tools, and 30 agent configurations. It shows that tool return values and tool selection can push indirect injection down to the action layer. A tool call string from the model still does not equal successful authorization or a completed real side effect. Reproduction must therefore check the executor state.

[Task Shield, ACL 2025](https://aclanthology.org/2025.acl-long.1435/) judges whether a candidate call serves the original user task, and does so before the action. That moves the detection locus from the attack string to goal-action consistency. On its own it still cannot handle the case where the action type is correct but the recipient, amount, or data reader is wrong. It must therefore be combined with an argument policy.

[CaMeL](https://arxiv.org/abs/2503.18813) and [FIDES](https://arxiv.org/abs/2505.23643) use trusted planning, isolated parsing, capability or information-flow policies, and a reference monitor. Together, these move the security boundary from model self-discipline to an auditable interpreter. They also turn labels, tool read/write sets, policies, and adapters into a new trusted computing base. Their utility and token cost must therefore be reported together with the security results.

The evaluation endpoint in this group has shifted fundamentally. It is no longer "did the model obey the injection" but "did the application complete the attack action". The most desirable direction is not to guess more cleverly which sentence is malicious. It is to make untrusted data unable to create control flow on its own. Nor should control flow be able to cross independent permission and information-flow policies.

### 6.4 RAG and Memory: From Corpora to Cross-Session State

For attacker-chosen queries, [PoisonedRAG, USENIX Security 2025](https://www.usenix.org/conference/usenixsecurity25/presentation/zou-poisonedrag) injects malicious documents that pursue both retrieval hits and the target answer. It shows that a small number of targeted records can significantly affect specific queries. The analysis must separate whether a document enters the top-k, whether the generator adopts it, and whether the final answer hits the target. 5 targeted documents per target question is not the same as 5 documents being able to control the whole knowledge base without a target.

[Spill the Beans, ICLR 2025](https://proceedings.iclr.cc/paper_files/paper/2025/hash/79cafa874121a3435d8a54f454b646b4-Abstract-Conference.html) uses black-box repeated elicitation to make a production RAG retrieve and output private verbatim text. It recovers 41% from a corpus of roughly 77,000 words and 3% in a larger-corpus configuration. The unit here is word coverage rather than prompt ASR. The conclusion is that a knowledge base should be protected as a queryable database, rather than treating the system prompt as a confidentiality boundary.

[AgentPoison, NeurIPS 2024](https://proceedings.neurips.cc/paper_files/paper/2024/hash/eb113910e9c3f6242541c1652e30dfd6-Abstract-Conference.html) uses a low ratio of knowledge or memory poisoning, so that a trigger query retrieves malicious experience. The official page reports an average ASR of no less than 80% across three classes of agents. The impact on clean performance is no more than 1%. The precondition for the attack is obtaining a write path. A cross-agent aggregate cannot be taken as the probability for any single model.

[MINJA, NeurIPS 2025](https://proceedings.neurips.cc/paper_files/paper/2025/hash/42a97bbd9844d2bf68596730af80bcdf-Abstract-Conference.html) influences long-term memory only through ordinary conversation. It advances the attack entry point from directly writing to the store to the product's automatic save policy. That calls for measuring writing, future recall, the attack action, and the number of surviving rounds separately. A single overall ASR is not sufficient to characterize persistence.

[A-MemGuard](https://arxiv.org/abs/2510.02373) attempts to reduce memory contamination with multi-path consensus. [FragFuse](https://www.usenix.org/conference/usenixsecurity26/presentation/rao) splits a violating goal into benign fragments across turns. The second result shows that per-item checking can still be bypassed by combination. For this new group of results the key is whether the sources are independent and whether the derivation chain is preserved. Long-term utility and token cost matter as well. It is not enough to compare only the lowest and the highest ASR.

RAG and memory have one property in common: state can first be contaminated and then triggered. The difference is that RAG revolves mainly around shared knowledge and retrieval permissions, whereas memory is also bound to user identity, time, preferences, and system learning. Both need to store provenance/ACL outside of summaries and embeddings, and to re-check them at action time. Neither should mistake "already stored" for "already trusted".

### 6.5 Multimodality: typographic, representation, and temporal attacks cannot be lumped into one class

[FigStep, AAAI 2025](https://ojs.aaai.org/index.php/AAAI/article/view/34568) typesets a harmful request into an image and asks the text side only to complete the steps. It reports an average ASR of 82.5% across six open-source LVLMs. That exposes how poorly textual safety alignment transfers to the visual channel. Its mechanism, however, is closer to an OCR/typographic carrier, and the cross-model average has no unified binomial denominator either.

[Image Hijacks, ICML 2024](https://proceedings.mlr.press/v235/bailey24a.html) optimizes pixels or representations in a white-box manner, so that an image controls generation at runtime and transfers across prompts. That shows an image can play a role similar to a program. Its practicality depends on white-box cost, perturbation constraints, and the specific preprocessing. It therefore cannot be placed in the same effect group as typographic text images that are clearly legible to the human eye.

[SpeechGuard, ACL Findings 2024](https://aclanthology.org/2024.findings-acl.596/) studies audio adversarial perturbations and cross-model transfer. There, the gap between white-box direct input and black-box transfer is very large. Volume, environment, codec, ASR front end, and real playback/recording add further variables. Neither text nor static-image ASR can be extrapolated to audio.

[AdaShield](https://arxiv.org/abs/2403.09513) retrieves defense prompts for structured visual jailbreaks. It greatly reduces the reported ASR in QR/FigStep configurations with only a small change in utility. Yet it is still a probabilistic prompting layer. It does not exhaust the white-box case in which the attacker jointly optimizes the image, the text, the similarity threshold, and the guard.

[VLGuard](https://arxiv.org/abs/2402.02207) uses safety image-text data for post-hoc or mixed fine-tuning. That repairs the safety forgetting after visual fine-tuning and brings multiple FigStep configurations close to 0. Yet safety-only training clearly causes severe over-refusal. It must therefore be evaluated jointly with helpfulness data, normal visual tasks, and out-of-model action control.

Multimodal evidence must record human visibility, attack constraints, font/resolution, OCR/ASR, preprocessing, fusion method, and whether it is physically deployed. A PDF is a composite container that holds a visible layer, hidden text, object order, and OCR all at once. A GUI is perception plus action. Video and audio additionally involve composition across time. Using a single `multimodal=true` label for stratification is fine. Effects, however, must not be merged on that account.

### 6.6 Privacy, backdoors, supply chain, and execution isolation

Training-data extraction research shows that a model leaks training sequences under specific repetition, prefix, and sampling budgets. That differs from exfiltrating directly from the current context or a RAG database. [Sleeper Agents](https://arxiv.org/abs/2401.05566) shows that conditionally triggered deceptive behavior may survive supervised fine-tuning, reinforcement learning, and adversarial training. It is a controlled backdoor experiment, though, and cannot prove that real-world models generally harbor an "autonomous conspiracy." Both lines of research require behavioral evaluation before release, not merely verification of file hashes.

[Firecracker](https://www.usenix.org/conference/nsdi20/presentation/agache), gVisor, and WASM papers/documentation mainly make arguments about isolation mechanisms, performance, and attack surface. They do not directly test LLM injection ASR. Papers such as AgentDojo mainly test model and harness behavior, yet they usually have no real kernel, cloud credentials, or network egress. The largest current cross-domain gap is precisely putting the two into the same end-to-end experiment. The attacker controls the agent through untrusted content. The agent attempts to read secrets, reach out, move laterally, and exhaust resources. The system simultaneously reports dangerous intent, actual blocking, benign utility, cost, and escape surface.

Supply-chain evidence likewise falls into three classes. Malicious repository/weight incidents prove feasibility. CVEs such as PyTorch prove specific implementation defects. Specifications and tools such as safetensors/SLSA/in-toto define control mechanisms. The combination "traceable provenance + codeless format + isolated loading + behavioral gate + revocation" must be in place. Only then are both the execution path and the behavior path covered at the same time.

### 6.7 Cross-paper synthesis: what can be compared and what must be kept separate

What can be compared stably is mechanisms. Adaptive search usually weakens static string defenses. An independent policy closer to the action constrains actual consequences more effectively. If provenance and tenant labels do not propagate with data transformations, later layers cannot restore them. There are also genuine trade-offs among safety, utility, and cost. Several other quantities cannot be compared directly: violation generation rates under different policies, the fraction of compromised applications, and word-level corpus recovery rates. Nor can tool goal completion rates, memory survival rounds, detection accuracy, or real incident counts.

Therefore, this survey does not declare the "strongest attack/defense" on the basis of a cross-paper ASR leaderboard. For every number, three questions are asked first. What is the denominator? At which layer does success occur? And does the attacker know the defense? If any item is unclear, the result can at most enter a descriptive evidence map. It cannot enter a merged effect.

### 6.8 Four methods decomposed into input, state, output, and scoring

**Case A: how GCG can search out a garbled suffix.** The input is an aligned model \(f_\theta\), a set of harmful target requests, a modifiable discrete suffix token, and a target prefix. The internal state is the gradient of the target loss with respect to each suffix position. The algorithm does not directly publish an answer on continuous vectors. Instead it uses the gradient to screen several candidate tokens at each position. It replaces them one by one, and it uses the true forward loss to select the candidate with the largest decrease. The loop runs until the budget is exhausted. The output is a suffix, and scoring usually looks at both the target prefix and the final content. The underlying logic is that safety training constrains the common semantic distribution. It does not make every discrete token combination satisfy the same refusal boundary. Reproduction must freeze the tokenizer, the chat template, the target prefix, and the number of steps. Otherwise "GCG with the same name" is not the same experiment. Looking only at an affirmative opening will overestimate harmful completion.

```text
request u + learnable suffix s
        ↓ objective loss L(fθ(u‖s), target)
compute the gradient for each position of s, producing top-k token candidates
        ↓ true forward scoring of each candidate
accept the best replacement, repeat for B steps
        ↓
candidate suffix + full answer of the target model + independent/human scoring
```

**Case B: why CaMeL/FIDES is not "just add another guard model."** The input is divided into an immutable user goal \(U\) and untrusted external data \(D\). A privileged planner looks only at \(U\) to produce a restricted plan. A tool-free parser converts \(D\) into typed values. The runtime maintains the provenance, integrity, confidentiality, and permitted recipients of values. The output is not a shell that the model executes directly. It is a set of actions, and the interpreter passes each one through capability and information flow policies. Security comes from a condition: "\(D\) cannot create new control flow, and low-integrity or high-confidentiality values cannot enter a sink that does not permit them." It does not come from the parsing model always being correct. In the Gemini-2.5-Pro configuration of CaMeL, the successful attack count is 300/949→0/949. Normal task completion, however, is 73.2%→41.2%, and the median input/output token is about 2.73×/2.82×. The conclusion must therefore include blocking, utility, and cost at the same time. It cannot state only "0 attacks."

```text
trusted user goal U ──> privileged planner ──> restricted plan/capability bound
untrusted data D ──> tool-free parser ──> labeled structured values
                          the two paths meet at the reference monitor
                                   ↓
                    policy allow / deny / ask / redact
                                   ↓
                          tool adapters produce real side effects
```

**Case C: why memory attacks require at least three endpoints.** AgentPoison assumes the attacker can write a small number of optimized records into the knowledge/memory store. MINJA narrows the entry point to automatic saving triggered by an ordinary conversation. Neither one amounts to "successful after a single input". The pattern is rather `write success W → future recall R → dangerous action A`. When a paper reports only the final ASR, the reader cannot tell where the defense intervenes. It may block the write, lower top-k hits, or reject at the action gate. A more reasonable record therefore lists \(P(W)\), \(P(R\mid W)\), \(P(A\mid R,W)\), survival time, cross-tenant leakage, and change on clean tasks. End-to-end risk can be conceptualized as the product of three conditional probabilities, but actual multiplication is permitted only for stag

---

[← Back to contents](index.md)
