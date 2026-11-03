# Collaborative SLAM — Team Status

> **Public status mirror only.** The canonical research repository remains Gitee `sy2513306/lidar_slam_work` (`master`). This GitHub repository is not a second research master.
>
> Publish only concise progress summaries, commit identifiers, and already-public evidence references. Never publish source code, datasets, raw logs, unpublished manuscript text, credentials, SSH keys, tokens, local absolute paths, device identifiers, or personal information.

## Ownership

- **Gitee:** sole source of truth for research records, code references, decisions, and handoffs.
- **Windows Codex:** literature review, Zotero, proposal/review writing, and research-decision records.
- **Ubuntu Codex:** Swarm-LIO2 source/configuration facts, experiment execution, and experiment evidence.
- **ChatGPT:** research coordination, evidence review, task prioritization, and this public status summary.
- **GitHub:** public status mirror only.

## Snapshot — 2026-11-03 (Asia/Tokyo)

| Field | Status |
|---|---|
| Gitee HEAD | `50372fa58e3847ba1e53a11d2df0d792a4c1ea14` — reported by Ubuntu U18; not independently live-verified by ChatGPT |
| Ubuntu local/remote sync | Ubuntu U18 reported local HEAD, `origin/master`, and Gitee master equal; working tree clean |
| Windows handoff | Ubuntu U18 reported W12 safely received; W12 source revision shown as `d4ad1a48…` (abbreviated in the report) |
| ChatGPT live Gitee read | BLOCKED — Gitee pages/raw files were not accessible through the current web reader; do not treat this as proof that Gitee itself is unavailable |
| Cross-platform status | LAST REPORTED CONSISTENT; independent live verification BLOCKED |
| GitHub mirror | Initialized; this file is the first public snapshot |

## Windows workstream

- Latest handoff read by Ubuntu U18: W12.
- Ubuntu reported that W12 had been safely received after the prior shared revision `2c82046`.
- The Windows workstream owns literature review, Zotero organization, proposal/review writing, and research decisions.
- Current detailed writing progress and exact source commit: **not independently verified in this snapshot**.
- Next action: continue the literature review using verified papers and update `handoff/WINDOWS_TO_UBUNTU.md` in Gitee with source commit, completed work, evidence, open questions, and next task.

## Ubuntu workstream

- Latest reported commit: `50372fa58e3847ba1e53a11d2df0d792a4c1ea14`.
- U18 added `tools/run_b2_isolated.sh`; default mode is `--check-only`, and `--run` is required to start a replay.
- U18 reported the final static entry-point check as PASS and did not rerun B2. Earlier check-only attempts in the same transcript reported SSD-writability and topic-count errors; these discrepancies still need a clean, reproducible explanation.
- U18 re-reviewed active/passive collaborative residuals, covariance propagation, the 0.5 s observation-age gate, and the shared iterated Kalman update. Candidate research questions remain hypotheses, not confirmed defects.
- B1 and B2 were previously reported PASS in U11/U12. They were not rerun in U18.
- C1-NET and real online dual-UAV C1 remain BLOCKED / NOT TESTED.
- Next task: U19 — audit the B2 check-only discrepancies, then prepare passive collaborative-observation event logging and a deterministic message-relay experiment design. Do not alter the filter or run a new B2 replay without explicit approval.

## Experiment status

| Test | Status | Evidence / notes |
|---|---|---|
| A — LiDAR/IMU-only baseline | PASS (historical report) | U11/U12 records in Gitee; not rerun in U18 |
| B1 — four-topic collaborative replay | PASS (historical report) | U11 record; not rerun in U18 |
| B2 — official original bag replay | PASS (historical report) | U12 record; not rerun in U18 |
| B2 wrapper `--check-only` | REPORTED PASS, RE-VERIFY | U18 final summary says static check passed, but earlier invocations showed SSD/topic-count errors |
| C1-NET — isolated dual-instance network | BLOCKED / NOT TESTED | UDP bridge build/security/network isolation gates remain |
| C — real online dual-UAV collaboration | NOT TESTED | Requires isolated networking, live sensor inputs, synchronization, and quantitative reference |

## Synchronization rules

1. Gitee `master` is the only research source of truth.
2. Windows and Ubuntu update only their own handoff files in Gitee; neither overwrites the other platform's records.
3. After a successful Gitee push, each Codex reports the exact full Gitee commit and updates its own handoff with the source commit.
4. Update this file only from current Gitee evidence. Record the exact Gitee HEAD and each handoff's source commit.
5. If Gitee cannot be read, preserve the last verified snapshot, mark the verification BLOCKED/STALE, and state the exact limitation. Never fill gaps from memory.
6. Never force-push, disable TLS/SSL verification, publish credentials, or claim a test/sync succeeded without evidence.
7. Do not publish raw data, raw experiment logs, unpublished manuscript text, or local machine paths.

## Next checkpoint

**U19 — Ubuntu:** resolve the B2 check-only discrepancy; inspect the exact source call sites; prepare passive event logging (message receipt → freshness/gating → residual assembly → filter update) and deterministic relay test design. Use an isolated fifth copy only. No filter changes, full B2 replay, UDP bridge, or real UAV operation without approval.

**Windows:** continue literature-review V0.x; map each candidate method to original papers, implementation evidence, limitations, and relevance to collaborative LiDAR SLAM. Keep proposal direction and innovation claims provisional until jointly reviewed.
