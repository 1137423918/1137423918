<div align="center">

# Junzhe Wang · A_Zhe

**Efficient computer vision · Reliable Agent workflows · Reproducible engineering**

[Personal website](https://1137423918.github.io/) · [Project brief & PDF · 2026-11-22](https://1137423918.github.io/project-brief.html) · [Research paper](https://doi.org/10.1109/LGRS.2025.3575615) · [Experiment records](https://1137423918.github.io/#lab)

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

- **Recovery and process supervision:** historical normal execution and three SIGKILL recovery scenarios produce identical reference patches in three target repositories; latest admitted-ext4 revalidation covers only Deep Agents normal/first-checkpoint cases. Per case: Deep Agents 119 upstream tests; OpenHands 184 plus a permissions check; Google ADK 1863 with 26 expected failures plus four reused filesystem contracts. These are explicit reference plans, not autonomous repair scores. Worker-only interruption during pytest also verifies old verifier cleanup before lock release. [Recovery evidence](https://1137423918.github.io/notes/recovery.html).
- **Protected acceptance and bounded repair:** fixed original tests run against candidate production code; tracked verification views, logs and feedback are hash checked. Declared Python files receive syntax checks before export, and failed candidates remain available for review. [Grading](https://1137423918.github.io/notes/protected-grading.html) · [Repair workflow](https://1137423918.github.io/notes/recovery.html#repair).
- **Current-source navigation:** Python AST outlines and symbol pages read current checkpointed virtual files, with an 8,192-byte response bound and hashes rejecting stale reads after edits. A production-edit SIGKILL control resumes with source hashes matching edited content. [Interface and evidence](https://1137423918.github.io/notes/source-navigation.html).

- **Hints through the existing read tool:** optional first-page Python indexes preserve the original source page, refresh after edits and survive a real SIGKILL checkpoint. Three paired reference controls retain identical patches; a separately declared CPU trial later reads the relevant function span but times out with no edits or acceptance, without a token or repair-gain claim. [Contracts and evidence](https://1137423918.github.io/notes/source-navigation.html#read-index).

- **Local checkpoint storage:** reject network/unknown filesystems before creating or resuming worker/repair state, and check existing control files. Real NFS new/resume rejection preserves old state; two Deep Agents ext4 reference cases retain identical patches after a real SIGKILL. Private SQLite backup reconstructs identical audit metadata, with no executable relocation claim. [Policy and evidence](https://1137423918.github.io/notes/local-state.html).

- **Read-only run inspection:** reconstruct checkpoint delta messages without invoking a model or resuming work; bounded metadata excludes prompts, arguments and source. Actual live runs, historical checkpoints and the wheel entry point are checked. SQLite coordination-file and legacy NFS limitations are disclosed. [Command and evidence](https://1137423918.github.io/notes/recovery.html#inspection).

- **Full-request context accounting:** 14 actual HTTP JSON bodies include prompts, tool schemas and history. Three operator-planned controls retrieve the same 86 source lines: sequential / known-name grep / AST use 43,990 / 11,341 / 19,054 logical reference input tokens. Grep is cheaper for these known names; reference rendering is not observed inference usage or a speed/repair score. [Protocol and evidence](https://1137423918.github.io/notes/context-budget.html).

- **Persistent model-request budgets:** reserve HTTP attempts and serialized-body bytes durably before send; failures and interrupted requests remain charged across restart and repair rounds. Real-repository normal/SIGKILL controls each use three HTTP calls and retain identical request bodies and patches. [Configuration and evidence](https://1137423918.github.io/notes/model-request-budget.html).
- **Async SDK integration:** a standalone asyncio/HTTPX2 budget wheel plugs into Pydantic AI. Four real SDK/tool cases use explicit fake HTTP replies to check cancellation/reopen, concurrent runs and SDK retries under one durable cap: eight POSTs / 3,250 body bytes. The existing maintenance worker remains synchronous. [Install and evidence](https://1137423918.github.io/notes/model-request-budget.html#async-budget).

**Real Agent/MCP consumer:** LlamaIndex FunctionAgent uses the external report service; audit capabilities and receipts stay outside model prompts. Four real-SDK/TCP controls pass using nine scripted model replies. A real 9B CPU first query times out at 600 seconds: six reservations, five complete replies and one charged unknown; four reports read but no final submission. The second query is not run. Shared core remains the earlier 130-check snapshot, with no added total. [Actual outcome and full dual-channel trace](https://1137423918.github.io/notes/mcp-agent.html).

**Installable MCP evidence service:** standalone starter includes a 9,033-byte wheel, frozen runtime lock and nine historical public reports. The actual wheel passes eight installed-artifact controls outside the source checkout; the original 130 core tests pass again with zero skips. No Deep Agents/LlamaIndex dependency, model key or inference is required. [Download and measured scope](https://1137423918.github.io/notes/mcp-evidence.html#installable).

**MCP audit cleanup:** status-query errors no longer skip closing the same audit. Cleanup uses a fresh transport with a ten-second aggregate budget and a two-second optional status step. Ten distinct real-MCP/LlamaIndex controls pass with 21 scripted model POSTs; expired contexts remain explicit failures, interrupted model requests stay charged, and external cancellation propagates. These include the previous four consumer controls; no addition to the 130 core snapshot or rerun of the timed-out 9B experiment. [Baseline, source and measured boundaries](https://1137423918.github.io/notes/mcp-agent.html#cleanup).

**MCP evidence service:** a runnable loopback MCP 2.3.0 endpoint exposes fixed reports with separate audit capabilities, read receipts, TTL and shared operation caps. Six real SDK/TCP controls cover cross-context receipts, invalid inputs, concurrency, reconnect and cancellation after a completed read response is withheld. No model/GPU calls; the 130 engineering checks include six new core checks, with network cases separate. Capabilities are not user authentication; verdict truth and free prose remain unchecked. [Run and evidence](https://1137423918.github.io/notes/mcp-evidence.html).

**LlamaIndex report auditing:** an optional validated submission tool checks exact JSON facts, source hashes and actual reads over eight pinned reports. In three known fixed real 9B CPU questions, 2 satisfy the unchanged structured contract; the GPU question has a correct verdict and verified facts but omits two required fields, so it still fails. The test-scope explanation still has ambiguous wording about 319 core checks; structured passes do not validate all prose. All 124 engineering checks and six separate fake-reply SDK controls pass. The original two-step 600s timeout is retained; no general accuracy or autonomous repair claim. [Cases and saved evidence](https://1137423918.github.io/notes/evidence-audit.html#submit-tool).

**Task-local tool scope:** complete file inventories hide and reject ls, preserve default graphs sharing the same model alias, and retain the existing source-index, restart quota and export checks. Actual HTTP, backend probes, SIGKILL and wheel-entrypoint checks use an explicitly fake model. [Contract and evidence](https://1137423918.github.io/notes/file-inventory.html).

**Deployment and GPU transport:** a pinned 9B model loaded 33/33 layers on one RTX 3090. Three HTTP replies: forced tool arguments and constrained result JSON passed; raw READY included empty think tags and failed the original check. The overall smoke remains failed; no autonomous repository repair is claimed. [Evidence and earlier startup failures](https://1137423918.github.io/notes/cuda-preparation.html#gpu-smoke).

**Earlier 9B maintenance CPU trial:** a predeclared Qwen3.5-9B ADK inventory run reads successive pages 1–800, then stops at eight requests after 1721.383 seconds. No edit, patch or acceptance; existing 106 engineering checks were not rerun. A separate GPU transport check is recorded above; GPU repository maintenance has not started because fresh admission found no eligible idle device. [Evidence and provenance limits](https://1137423918.github.io/notes/file-inventory.html#trial-9b).

The current dedicated server suite has **130 passed / zero skipped**, including six new evidence-service checks and the earlier evidence, async, verification lifecycle, inventory, storage, parser and budget checks. Three existing lifecycle checks now use new-session children. Linux supervisors reclaim double-forked descendants before releasing the worker lock and start the exact loaded supervisor source. The initial integration failures are retained. [Measured lifecycle fix](https://1137423918.github.io/notes/recovery.html#verification-tree). These are infrastructure checks; some earlier model interfaces use explicit fake replies, while the MCP service uses real reports and network transport. They do not establish autonomous repair or hostile-code isolation. Overlapping checks are not added together.

### Open-source contributions

| Upstream | Change and validation | State |
| --- | --- | --- |
| [Deep Agents](https://1137423918.github.io/notes/path-normalization.html) | Normalize mixed path separators; seven new regressions recover and 380 related tests pass | [Candidate branch](https://github.com/1137423918/deepagents/tree/1137423918/sdk/normalize-backslash-paths); no upstream PR |
| [OpenHands SDK](https://1137423918.github.io/notes/openhands-undo.html) | Preserve undo history after a failed restoration write; real permissions reproduction and 185 related tests | [Draft PR #7032](https://github.com/OpenHands/software-agent-sdk/pull/7032); human input / review pending |
| [OpenHands SDK: apply_patch](https://1137423918.github.io/notes/openhands-undo.html#apply-move) | Reject moves resolving to their source before queued writes; real file-loss reproduction in three aliases, 203 related tests pass (22 focused tests included) | [Draft PR #7050](https://github.com/OpenHands/software-agent-sdk/pull/7050); CI authorization / human review pending |
| [Google ADK](https://1137423918.github.io/notes/adk-artifact-cleanup.html) | Handle missing entries during concurrent artifact deletion; Python 3.11 / 3.13 each pass the same 2,021 related tests with 26 expected failures | [Draft PR #8278](https://github.com/google/adk-python/pull/8278); CLA account matching / human review pending |
| [Semantic Kernel: late send errors](https://1137423918.github.io/notes/cancelled-send.html) | Preserve queue completion after caller cancellation and later handler/factory errors; four before/after cases and 97 related passes; 12 broader baseline failures retained | [Draft PR #14853](https://github.com/microsoft/semantic-kernel/pull/14853); human review / full CI pending |
| [Semantic Kernel](https://1137423918.github.io/notes/semantic-kernel-cancellation.html) | Release the experimental Python runtime token lock before callbacks; six original regressions, 103 related checks pass, real runtime cancellation completes; 12 existing broader failures disclosed | [Open PR #14845](https://github.com/microsoft/semantic-kernel/pull/14845); externally non-draft, Copilot COMMENTED review; human approval pending, not merged |
| [Langflow / LFX](https://1137423918.github.io/notes/lfx-checkpoint-numeric.html) | Mark non-finite checkpoint state for recomputation; real SQLite graph resume and 105 related tests pass (5 existing warnings); broader graph suite retains failures | [Validated patch](https://github.com/1137423918/AgentReliabilityLab/blob/main/evidence/lfx-checkpoint-numeric/fix.patch); push and PR blocked by workflow-token scope, no PR created |
| [AutoGen](https://1137423918.github.io/notes/autogen-cancellation.html) | Release the token lock before cancellation callbacks; six original failures reproduced, candidate core suite 233 passed / 3 existing warnings | [Fork candidate](https://github.com/1137423918/autogen/tree/fix/cancellation-callback-deadlock); upstream archived, PR creation rejected |

The draft PRs are not merged. AutoGen is archived/read-only; its tested fork candidate has no upstream PR. Two Python versions exercise overlapping tests; ADK's 20 observed cleanup rounds are a bounded real-filesystem probe, not a general reliability rate. ADK storage work does not add another Agent-runtime adapter.

### Real-model experiments

Pinned Qwen3-4B and Qwen3.5-9B CPU maintenance attempts, model/runtime hashes, fixed budgets and failure logs are public. **No neural trial has produced a verified maintenance patch.** Some checkpoints preserve read-only tool progress; edited-file recovery is currently demonstrated by scripted reference controls. Source-navigation and read-index variants have separately reported CPU trials; net token, cost and latency gains remain unproven.

[FP32 / INT8 attempts and tool-format diagnostics](https://1137423918.github.io/notes/model-cpu.html) · [Native Q4_K_M trials](https://1137423918.github.io/notes/native-cpu.html) · [Qwen3.5 request-budget analysis](https://1137423918.github.io/notes/qwen35-maintenance.html)

Current work focuses on source localization, context selection and independently verified maintenance tasks. Outcomes are published with pinned versions, test records and clearly stated limits.
