## 1. Why We Need to Move from "Model Security" to "System Security"

### 1.1 An Answer and an Action Are Not the Same Kind of Risk

Dialogue-model evaluations often define "attack success" as generating some class of text that policy prohibits. In agent settings, the same output may be read downstream as a function name, a Shell command, a payment instruction, an email recipient, a browser click, or a memory write. At least four layers must therefore be separated. **Content violation** is the model generating text, images, or audio that violate the usage policy. **Control hijacking** is untrusted input changing the original task or the priority of instructions. **Dangerous intent** is the model proposing actions such as reading secrets, sending data externally, deleting files, or expanding privileges. **Dangerous execution** is the harness, tool, or host environment actually letting them through and producing observable side effects.

The first three layers can appear in pure model benchmarks. The fourth cannot, because it must take the model's external architecture into account. A model may be "jailbroken" at the output level while a capability gate prevents actual harm. Conversely, it may generate no conspicuous violating text and still perform unauthorized actions through well-formed tool arguments. Engineering risk can therefore only be approached by reporting model intent, execution results, and benign utility on normal tasks together.

### 1.2 The End-to-End System and Trust Boundaries

This survey adopts the following reference chain:

```text
Data/code/weight supply chain
        ↓
Base model and alignment layer
        ↓
System prompt, user input, session context
        ↓
Web/email/PDF/image/audio/RAG retrieval results
        ↓
Planning loop and agent harness
        ↓
Tool descriptions, function arguments, credentials, network, files, and code execution
        ↓
Short-term state, long-term memory, user profiles, and cross-agent messages
        ↓
Sandbox, container/virtual machine, host, cloud control plane, and downstream users
```

Every arrow may cross a trust domain. Security design does not turn on how smart the model is. It turns on questions answered item by item: who can write, whether provenance is verifiable, what the model can see, what the model can suggest, what the executor will allow, how long state can be kept, and how large the blast radius is after a failure.

### 1.3 Five Amplifiers of Risk

Five dimensions explain why the same injection string causes vastly different harm in different systems. **Reachability** describes whether retrieval, OCR, transcription, summarization, or a tool return value brings the attack content into context. **Privilege** describes which capabilities the model or tool holds among reading, writing, executing, outbound connections, payment, and identity delegation. **Persistence** distinguishes whether the effect lasts one turn or enters memory, caches, indexes, code repositories, or release artifac

---

[← Back to contents](index.md)
