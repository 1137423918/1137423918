<div align="center">

# Junzhe Wang · A_Zhe

**Efficient computer vision · Reliable Agent workflows · Reproducible engineering**

[Personal website](https://1137423918.github.io/) · [Research paper](https://doi.org/10.1109/LGRS.2025.3575615)

</div>

I study lightweight visual models and build practical Agent tooling, with a focus on observable behavior, reproducible experiments, and reliable execution.

### Research

**LS-DETR: Lightweight Transformer for Object Detection in Forward-Looking Sonar Images**<br>
**Junzhe Wang**, Xinke Chen, Anbang Dai, Yan Liu, Guanying Huo<br>
*IEEE Geoscience and Remote Sensing Letters*, vol. 22, 2025.<br>
[Paper](https://doi.org/10.1109/LGRS.2025.3575615) · [Code](https://github.com/1137423918/LS-DETR)

### Engineering projects

| Project | Focus | Status |
| --- | --- | --- |
| [LS-DETR](https://github.com/1137423918/LS-DETR) | Lightweight end-to-end detection in forward-looking sonar imagery | Published research |
| [Agent Reliability Lab](https://github.com/1137423918/AgentReliabilityLab) | Tool contracts, regression evidence, and reliable software-maintenance workflows | In development |

The Agent project includes a recoverable maintenance worker with SQLite checkpoints, isolated Git worktrees, and explicit patch verification. In a real Deep Agents repository task, normal execution and three SIGKILL recovery scenarios produced the same patch, each passing 119 upstream tests; 33 project tests passed, including explicit fake-HTTP transport checks. A further worker-only SIGKILL during a running upstream pytest process confirmed verifier cleanup before lock release and the same patch after resume. These are scripted infrastructure tests. [Evidence and limits](https://1137423918.github.io/notes/recovery.html) are public; autonomous model evaluation is pending. A separate path-tool candidate fix passed 380 related upstream tests and is available on a personal fork, without an upstream PR yet.

### Current work

- Build framework adapters and reproducible tool-level checks.
- Extend recovery validation to model-driven maintenance tasks and broader fault coverage.
- Contribute small, verifiable fixes to the upstream Agent ecosystem.

Project outcomes are updated with their source versions, test records, and PR links as they become available.

An additional [OpenHands SDK draft PR #7032](https://github.com/OpenHands/software-agent-sdk/pull/7032) preserves undo history when a file restoration write fails. A real Linux permissions reproduction fails before the fix and succeeds afterward; 185 related tests pass on the candidate. [Reproduction and limits](https://1137423918.github.io/notes/openhands-undo.html). Submitted, awaiting human input and maintainer review; not merged.

The worker also completes an OpenHands maintenance task: normal execution and three SIGKILL recovery cases produce the same 1,795-byte patch, each passing 184 existing upstream tests plus an operator-owned permissions check. [Task, acceptance and evidence](https://1137423918.github.io/notes/openhands-undo.html#maintenance). This uses a fixed tool plan; neural-model task evaluation is pending.

An optional [bounded repair workflow](https://1137423918.github.io/notes/recovery.html#repair) retains each failed candidate and sends hash-checked verification feedback into the next round. The real OpenHands reference workflow passes after its first candidate fails, including recovery after a feedback-boundary SIGKILL. This is scripted workflow evidence; 33 project tests pass.

[Real CPU model pilot](https://1137423918.github.io/notes/model-cpu.html): pinned Qwen3-4B FP32 and dynamic INT8 each attempted normal and checkpoint-resume modes on one public maintenance problem. All four attempts yielded no patch. Protocols, raw generated outputs and failure logs are published; generation time limits and tool-format incompatibility remain unresolved. No autonomous repair success is claimed.
