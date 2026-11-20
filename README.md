<div align="center">

# Junzhe Wang · A_Zhe

**Efficient computer vision · Reliable Agent workflows · Reproducible engineering**

[Personal website](https://1137423918.github.io/) · [Research paper](https://doi.org/10.1109/LGRS.2025.3575615) · [Experiment records](https://1137423918.github.io/#lab)

</div>

I study lightweight visual models and build Agent tooling around recoverable execution, explicit acceptance and reproducible failure analysis.

### Research

**LS-DETR: Lightweight Transformer for Object Detection in Forward-Looking Sonar Images**<br>
**Junzhe Wang**, Xinke Chen, Anbang Dai, Yan Liu, Guanying Huo<br>
*IEEE Geoscience and Remote Sensing Letters*, vol. 22, 2025.<br>
[Paper](https://doi.org/10.1109/LGRS.2025.3575615) · [Code](https://github.com/1137423918/LS-DETR)

### Engineering projects

| Project | Focus | Status |
| --- | --- | --- |
| [LS-DETR](https://github.com/1137423918/LS-DETR) | Lightweight detection in forward-looking sonar imagery | Published research |
| [Agent Reliability Lab](https://github.com/1137423918/AgentReliabilityLab) | Recoverable software-maintenance workflows, tool contracts and evidence | In development |

**Agent Reliability Lab** uses Deep Agents / LangGraph, SQLite checkpoints and isolated Git worktrees. It currently includes:

- **Recovery and process supervision:** normal execution and three SIGKILL recovery scenarios produce identical reference patches in two real maintenance repositories. Each Deep Agents case passes 119 upstream tests; each OpenHands case passes 184 existing tests plus an independent permissions check. Worker-only interruption during pytest also verifies old verifier cleanup before lock release. [Recovery evidence](https://1137423918.github.io/notes/recovery.html).
- **Protected acceptance and bounded repair:** fixed original tests run against candidate production code; tracked verification views, logs and feedback are hash checked. Declared Python files receive syntax checks before export, and failed candidates remain available for review. [Grading](https://1137423918.github.io/notes/protected-grading.html) · [Repair workflow](https://1137423918.github.io/notes/recovery.html#repair).
- **Current-source navigation:** Python AST outlines and symbol pages read current checkpointed virtual files, with an 8,192-byte response bound and hashes rejecting stale reads after edits. A production-edit SIGKILL control resumes with source hashes matching edited content. [Interface and evidence](https://1137423918.github.io/notes/source-navigation.html).

- **Full-request context accounting:** 14 actual HTTP JSON bodies include prompts, tool schemas and history. Three operator-planned controls retrieve the same 86 source lines: sequential / known-name grep / AST use 43,990 / 11,341 / 19,054 logical reference input tokens. Grep is cheaper for these known names; reference rendering is not observed inference usage or a speed/repair score. [Protocol and evidence](https://1137423918.github.io/notes/context-budget.html).

- **Persistent model-request budgets:** reserve HTTP attempts and serialized-body bytes durably before send; failures and interrupted requests remain charged across restart and repair rounds. Real-repository normal/SIGKILL controls each use three HTTP calls and retain identical request bodies and patches. [Configuration and evidence](https://1137423918.github.io/notes/model-request-budget.html).

The current dedicated server suite has **74 passed / zero skipped**, including 11 budget checks. The new environment installs jsonschema, so 14 previously skipped parser checks now execute. Reference editing and recovery controls use explicit scripted plans; overlapping acceptance counts are not added together. These results validate infrastructure, not autonomous repair capability or a hostile-code OS sandbox.

### Open-source contributions

| Upstream | Change and validation | State |
| --- | --- | --- |
| [Deep Agents](https://1137423918.github.io/notes/path-normalization.html) | Normalize mixed path separators; seven new regressions recover and 380 related tests pass | [Candidate branch](https://github.com/1137423918/deepagents/tree/1137423918/sdk/normalize-backslash-paths); no upstream PR |
| [OpenHands SDK](https://1137423918.github.io/notes/openhands-undo.html) | Preserve undo history after a failed restoration write; real permissions reproduction and 185 related tests | [Draft PR #7032](https://github.com/OpenHands/software-agent-sdk/pull/7032); human input / review pending |
| [Google ADK](https://1137423918.github.io/notes/adk-artifact-cleanup.html) | Handle missing entries during concurrent artifact deletion; Python 3.11 / 3.13 each pass the same 2,021 related tests with 26 expected failures | [Draft PR #8278](https://github.com/google/adk-python/pull/8278); CLA account matching / human review pending |
| [Semantic Kernel](https://1137423918.github.io/notes/semantic-kernel-cancellation.html) | Release the experimental Python runtime token lock before callbacks; six original regressions, 103 related checks pass, real runtime cancellation completes; 12 existing broader failures disclosed | [Draft PR #14845](https://github.com/microsoft/semantic-kernel/pull/14845); not merged |
| [Langflow / LFX](https://1137423918.github.io/notes/lfx-checkpoint-numeric.html) | Mark non-finite checkpoint state for recomputation; real SQLite graph resume and 105 related tests pass (5 existing warnings); broader graph suite retains failures | [Validated patch](https://github.com/1137423918/AgentReliabilityLab/blob/main/evidence/lfx-checkpoint-numeric/fix.patch); push and PR blocked by workflow-token scope, no PR created |
| [AutoGen](https://1137423918.github.io/notes/autogen-cancellation.html) | Release the token lock before cancellation callbacks; six original failures reproduced, candidate core suite 233 passed / 3 existing warnings | [Fork candidate](https://github.com/1137423918/autogen/tree/fix/cancellation-callback-deadlock); upstream archived, PR creation rejected |

The draft PRs are not merged. AutoGen is archived/read-only; its tested fork candidate has no upstream PR. Two Python versions exercise overlapping tests; ADK's 20 observed cleanup rounds are a bounded real-filesystem probe, not a general reliability rate. ADK storage work does not add another Agent-runtime adapter.

### Real-model experiments

Pinned Qwen3-4B and Qwen3.5-9B CPU maintenance attempts, model/runtime hashes, fixed budgets and failure logs are public. **No neural trial has produced a verified maintenance patch.** Some checkpoints preserve read-only tool progress; edited-file recovery is currently demonstrated by scripted reference controls. The new source-navigation model preset is prepared but has not run neural inference; net token, cost and latency gains are unmeasured.

[FP32 / INT8 attempts and tool-format diagnostics](https://1137423918.github.io/notes/model-cpu.html) · [Native Q4_K_M trials](https://1137423918.github.io/notes/native-cpu.html) · [Qwen3.5 request-budget analysis](https://1137423918.github.io/notes/qwen35-maintenance.html)

Current work focuses on source localization, context selection and independently verified maintenance tasks. Outcomes are published with pinned versions, test records and clearly stated limits.
