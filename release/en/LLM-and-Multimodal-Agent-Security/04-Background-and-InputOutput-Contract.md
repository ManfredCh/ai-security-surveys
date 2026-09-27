## Background and Input/Output Contract

This chapter separates model outputs, system actions and actual harm. It fixes the end-to-end data flow, assets, adversary capabilities and five risk amplifiers. That contract is the shared input for the taxonomy and evaluation that follow.

### A Response and an Action Are Not the Same Kind of Risk

Dialogue-era evaluations often defined "attack success" as generating some class of policy-prohibited text. In the agent era, downstream parsers may read the same output as a function name, a shell command, a payment instruction, an email recipient, a browser click or a memory write. At least four layers therefore need separating. A content violation is text, images or audio the model generates in breach of the usage policy. Control hijacking is untrusted input that changes the original task or instruction priority. Dangerous intent is the model proposing actions such as reading secrets, sending data outward, deleting files or expanding privileges. Dangerous execution is the harness, tools or host environment actually letting an action through and causing an observable side effect.

The first three layers can appear in model-only benchmarks. The fourth must incorporate the architecture outside the model. A model may be jailbroken at the output level, yet the capability gate blocks the actual harm. It may also avoid conspicuous violating text while exceeding its authority through well-formed tool parameters. One therefore comes close to engineering risk only when model intent, execution results and benign task utility are reported together.

### The End-to-End System and Trust Boundaries

The reference chain this survey adopts appears below.

**Text structure representation in the earlier draft**
\begin{verbatim}
Data/code/weights supply chain
v
Base model and alignment layer
v
System prompt, user input, and conversation context
v
Web pages/email/PDF/images/audio/RAG retrieval results
v
Planning loop and agent harness
v
Tool descriptions, function parameters, credentials, network, file, and code execution
v
Short-term state, long-term memory, user profiles, and cross-agent messages
v
Sandbox, containers/VMs, host, cloud control plane, and downstream users
\end{verbatim}

Any arrow may cross a trust domain. Security design does not ask "is the model clever". It answers a list of questions item by item. Who can write? Is provenance verifiable? What can the model see? What can the model suggest? What will the executor allow? How long can state be kept? How large is the blast radius after a failure?

### Five Amplifiers of Risk

For engineering discussion, this survey uses five dimensions. They explain why the same injection string produces vastly different harm in different systems. Reachability describes whether retrieval, OCR, transcription, summarization or tool return values bring attack content into context. Privilege describes which of read, write, execute, outbound network, payment and identity delegation capabilities the model or tools possess. Persistence distinguishes whether the impact lasts a single turn or enters memory, caches, indexes, code repositories or release artifacts. Observability examines whether unified traces, provenance labels, tool audits, kernel/network logs and timely alerts exist. Iteration speed indicates whether an adversary or an autonomous agent can attempt in parallel at low cost, adapt on feedback and continue for hours or days.

This is not a fitted risk formula. It is a conceptual framework for checking for missing controls. Asset value, attack cost, detection probability and recovery capability affect real risk as well.

---

[← Back to contents](index.md)
