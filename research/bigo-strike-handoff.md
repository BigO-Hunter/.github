# BigO strike workspace — condensed handoff

Retired the local `~/.multiaim/bigo_strike` workspace on 2026-11-25. This is the map for continuing the research without resurrecting that directory. Full source/evidence snapshots are in private `campaign-archive`; this page intentionally carries only the useful next context.

## Current public state

- No open `bigospeedrun` PRs or issues authored by or mentioning `darkhipo` at the final check (2026-11-24).
- All 29 public boards returned successfully and had no new posts since 2026-11-20. Do not repost old drafts or answer questions that are not there.
- Mathlib PRs [#45771](https://github.com/leanprover-community/mathlib4/pull/45771), [#45906](https://github.com/leanprover-community/mathlib4/pull/45906), and [#45909](https://github.com/leanprover-community/mathlib4/pull/45909) remain open, green, and have no reviewer comments requiring action.
- `bigo_scan` is disabled. The retired notes directory is not a live work queue.

## Verified results worth keeping straight

- **Average sensitivity:** issue #66 is Lean Verified at `18807273/5000000`. The proof uses the charged coupling and sharp tail; the accepted source is `darkhipo/average-sensitivity-lean@9602aafd8d7d` on `sharpen-37614546`. Issue #66 is not an unfinished submission.
- **Catalan 295:** issue #187 closed Lean Verified at `588b7d649184ed7c8c761db73ff1542932614fb3`. Lean and the axiom audit passed. NanoDa was incomplete/OOM and is advisory under the verifier's admission rule, not a proof rejection.
- **Subset sum:** issue #94 completed Lean Verified at `3/4`, the board's first Lean-Verified row. A proof of exactly `1/2` is not a first row under the classic statement; do not self-censor an above-classic proof either.
- **Catalan 528-series:** #95 completed Lean Verified at `5282327/10000`; #103 subsequently reached a Lean-Verified checkpoint at `1056463/2000`. Read each issue's final verdict rather than treating the checkpoint as a final result.
- **Verifier #194:** the receipt-status defect was fixed upstream in `b43198221`. `status` now comes from `admission()` and `check_summary`; both interim and final receipts for the #187 defect cases independently re-evaluate to `passed`.

## Research seams that remain useful

### Average sensitivity

The former strike target is closed; do not retune it. The larger open direction is the asymptotic route behind rank 1:

1. **L1 — sharp central-binomial asymptotics.** The local analysis identifies Wallis bounds as the available Mathlib route. `MADMonotone.lean` reduces a tail supremum to evaluation at `N` or `N+1`; this removes the old window search from the critical path.
2. **L2 — compensated coupling.** Remove the `a²` loss in `RefinedCoupling.displacement_majorant`. With the current additive term still present, even a perfect `K = 32/π` does not reach rank 1; both pieces are required.
3. Preserve the accepted #66 provenance before editing. The old strike target was infeasible by `2.18e-14` at its own supremum; further ladder tweaks to that exact constant are wasted work.

Start from `average-sensitivity-lean`, `recovery/average-sensitivity-local`, and the archived R5/M1 reports, not from the retired prose thread.

### Catalan 410 and large Lean builds

The source is public in `catalan-irrationality-measure-410` at merge commit `0738347daeba402dc1315e1d01467301e0e1be29`, but **it is not yet validated as a completed build/docs pair**. The exact outstanding state is published on branch `validation/unverified-0738347` in `VALIDATION.md`.

The useful engineering lesson from #187 is not “increase every deadline”: three OOM-killed build attempts consumed 5,093.6s before the one-worker build passed. Build memory pressure and swap posture are the first-order levers. Read `build.attempts[]` and final receipts; a job step labelled `success` is not evidence that only one attempt ran.

Do not open duplicate submissions or bump the judged Lean pin merely to silence the intentionally non-gating comparator.

### SSSP / APSP

- The former APSP R2 margin analysis is closed at optimum within about `1e-13`; new structure is needed rather than another constant shave.
- The SSSP/CHD dependency pin is `bigospeedrun/c-hd-proof@98c53acc`. The local t3-cap-param extension was evaluated and deliberately left as a frozen artifact rather than upstreamed without a need.
- Audit and replay evidence is under `volume-gaps/sssp-audit/` in `campaign-archive`, with exact recovery refs for the five local repositories.

### Verifier and evidence handling

- Read final receipts, not interim `verification_stage=lean` receipts or the top-level job conclusion alone.
- NanoDa incompleteness due to OOM/timeout/disk limits is advisory when Lean and the axiom audit pass; a NanoDa **rejection** is different.
- A green `check` job is not the posted verdict; the `report` job carries it.
- Verify live artifacts and source paths, not cached issue bodies or scoped repo listings. A missing item in `user/repos` does not prove it does not exist in a sibling org.
- All source snapshots preserve useful unfinished work without upgrading it to “proved.”

## Recovery map

`BigO-Hunter/campaign-archive` is the broad private safety net. Current archive head: `160fd44c5ea61714096346ce664361e0aa709fd5`.

- `multiaim-bigo-strike/` — the retired notes, R-series analyses, review reports, patches, Lean modules and scripts.
- `volume-gaps/bigo3sum/` — 3SUM/APSP/average-sensitivity repositories and evidence.
- `volume-gaps/sssp-audit/` — the SSSP audit, replay, CHD evidence ZIP and build configuration.
- `volume-gaps/weil-verify/` — Weil gate/source notes and build research.
- `volume-gaps/bigo-lake-rehash/` — independent 22,001-file exact-copy receipt used before cache deletion.
- `outliers/prove2me-staircase/` — R8 measurements explicitly marked **unverified**; named `/tmp/r8_diag*.py` harnesses were not found and were not rerun.
- `refs/heads/recovery/*` — exact local-only or detached histories, including bonifaci, staircase N2B, snaky-20, bigo3sum lanes, SSSP lanes, verifier, Weil, and Terminal-RSI.

Example read-only recovery:

```bash
git clone --filter=blob:none --no-checkout \
  https://github.com/BigO-Hunter/campaign-archive.git bigo-recovery
cd bigo-recovery
git config core.autocrlf false
git sparse-checkout set --no-cone '/volume-gaps/' '/MANIFEST.json' '/ARCHIVE_STATS.json'
git checkout main
```

The final verification pass independently checked all **1,502 volume-gap entries**: zero missing files, zero broken links, zero hash mismatches. All **21 recovery refs** passed `git fsck --full` after the Terminal-RSI addition. No fresh Lean build is claimed for the broad snapshot.

## Terminal-RSI remains a local flock member

Terminal-RSI is local model-serving engineering, not a BigO research result. The canonical flock roster lists `terminal-rsi-27b-domo` as a live local resident on port 8095. Its model, goal, launchd service and workspace remain in place. Only its Git history is preserved as `refs/heads/recovery/terminal-rsi`, with its final untracked report included in the wrap-up receipts release. Do not treat its benchmarks as mathematical evidence, and do not retire it as BigO cleanup.

## Space reclamation

Approximately **276 GB** of generated caches, remote-covered checkouts and temporary staging was removed with zero failures. Raw OpenCode transcripts were retained separately and ingested through the body's native `OpenCodeAdapter`; they were not treated as research-proof uploads.
