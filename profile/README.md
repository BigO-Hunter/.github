# BigO-Hunter

Tracking & packaging org for the darkhipo swarm's contributions toward the
[BigO Speedrun](https://github.com/bigospeedrun) initiative — Lean 4 formalizations,
certificates, audits and verification receipts for improved algorithmic and mathematical
bounds. Companion to the project, never the project itself.

**The initiative we contribute toward** — these are *not* our sites; we are a contributing
org working toward that initiative:

- Project site: <https://bigospeedrun.com>
- GitHub org: <https://github.com/bigospeedrun>
- Boards & forums: <https://board.bigospeedrun.com>

## Rows

Every repo carries the `big-o-speedrun` umbrella topic plus one row topic, so the org is
filterable by row. Private repos hold in-progress work. Consolidated 2026-11-26: 59 repos
(was 77); folded shells were deleted only after every ref was verified preserved in a
successor (see the consolidation record below).

- **Directed SSSP** (`sssp`) — `sssp-chd-row` (n ; n log^(2/3)), `sssp-nlogn` (n log ; n log^2),
  `sssp-n2` (n²), `sssp-dmsy-stack` *(private)*, `relax-completeness` (capped engine spec in `engine-spec/`)
- **APSP & dynamics** (`apsp`) — `apsp-bound`, `minplus-widgets`, `bonifaci-lane`, `aft-lane`
- **3-SAT** (`3sat`) — `sat-decision-program`
- **Snaky** (`snaky`) — `snaky-nineteen` (19-move; scout recon folded in `scout/`),
  `snaky-twenty` (20-move; Bound-20 staging folded in `conditional/`)
- **Subset Sum** (`subset-sum`) — `subset-sum` (α=1/2 deterministic + MITM package in `mitm/`,
  HS74 historical ref in `hs74-historical/`, v2 lanes at `refs/heads/archive/subset-sum-mitm/*`),
  `subset-sum-l25` *(private)*
- **Matroid Prophet** (`matroid-prophet`) — `matroid-prophet-tight-corner` (superseded exact-B
  certificate folded in `superseded/exact-B/`), `matroid-statement` *(private)*
- **Matmul** (`matmul`) — `matmul-frobenius` *(private)* — Frobenius lane, ω < 9/4
- **Combinatorics** (`combinatorics`) — `ramsey-5-5-lean-certificate` (R(5,5) ≥ 42),
  `schur-number-8-lean` (S(8) ≥ 5372), `admissible-tuples-lean`,
  `van-der-waerden` (c = 1/20000; original c = 1/100000 baseline in `baseline/`, rung-2 receipt
  at `refs/heads/archive/vdw-first-rung/rung-2` + tags `rung-1`, `rung-2-1/20000`),
  `sidorenko-counterexample-lean`, `prime-gaps-246-lean` (H1 ≤ 246)
- **Prime gaps 182** (`prime-gaps`) — `prime-gaps-182` *(private)* — C0/D1/D2 + Kloosterman/Weil
  lanes folded into named lane directories
- **Number Theory** (`number-theory`) — `pi-irrationality-measure` *(archived in place — historical
  cert, superseded by μ(π)=2)*, `catalan-295-litsey-port` (μ(G) ≤ 295; superseded 410 port folded in
  `archive/410/` + its research branches at `refs/heads/archive/410/*`),
  `catalan-irrationality-measure-411` *(pending fold — see below)*,
  `catalan-constant-gen5` (μ(G) ≤ 528.2315, GEN-6), `dft-halitziyav6-rate`, `heilbronn-triangle-lean`
  (exact-K η ≈ 7.2144e-237, verifier#184), `heilbronn-triangle-ten237` (1/10^237, board pin),
  `heilbronn-bar` *(private)*
- **Z is Diophantine in Q** (`z-diophantine`) — `z-diophantine-research`, `dzq-lean` *(private)*
- **Zeta / Riemann** (`zeta`) — `quasi-riemann-baseline-rerun` (PR#103 rerun folded in `pr103-rerun/`),
  `QuasiRiemannTracker`, `zeta-zeros-submission` (original proposal in `proposal/`),
  `zeta-measure-certificates`, `critical-line-269-400` *(archived in place — only public H ≥ 269/400
  bridge, never merged)*, `weil-verify` *(private)*, `knausgard-cert` *(private)*, `clz-cert` *(private)*
- **Physics** (`physics`) — `haldane-gap-beta13` (certified γ_L > 0.06743; the 0.1542 / 771/5000
  claim is RETRACTED — see its CORRECTION.md)
- **Sensitivity** (`sensitivity`) — `average-sensitivity-lean` (org-sharpened AS ≤ 3.7614546·d·√n)
- **Integer Multiplication** (`integer-mult`) — `integer-mult-bounds` (κ > 2⁻¹⁵)
- **Support & tooling** (`support`) — `bigospeedrun-agent-kit` (the methodology), `campaign-archive` *(private)*,
  `lemma-library`, `bochner-lane`, `leaps-in-bounds`, `omr-statement`, `mathlib4` (dependency pin;
  mathlib4-1 history at `refs/archive/mathlib4-1/*`), `staircase-port` *(private)*, `verifier`, `site`,
  `c-hd-proof`, `prove2me_workspace`
- **Org identity** (`support`) — `.github` (this manifest), `bigo-hunter.github.io` (org page / GitHub Pages)

## Repository lifecycle

Each repository is one self-contained artifact, verification lane or explicitly marked upstream pin.
Same-topic repositories are not automatically duplicates: baseline and improved certificates remain
side by side when both are reproducible evidence — after the 2026-11-26 consolidation the baseline
lives *inside* its successor rather than as a separate shell (for example
`van-der-waerden/baseline/` + `refs/heads/archive/vdw-first-rung/rung-2`, and
`matroid-prophet-tight-corner/superseded/exact-B/`). Their READMEs name the successor
or the reason the baseline is retained. Two artifacts are archived in place rather than folded
(`critical-line-269-400`, `pi-irrationality-measure`): each is unique public evidence with no natural
successor, so the repo stays read-only with a retention note.

`verifier-1` was consolidated into `verifier` on 2026-11-20: its mainline was merged at
`1d01f6e4eeb6bc84617fd5d1a7ca4bcfd231bc7c`, both automation branches were fast-forwarded, and
`verify-chain-jobs` was already identical. Every source branch was verified as an ancestor of the
corresponding target branch before `verifier-1` was archived read-only; there were no source tags.
No lossy same-topic merges. (The `verifier-1` shell was deleted 2026-11-26 after re-verification.)

### 2026-11-20 umbrella consolidation (first wave — historical)

- `zeta-zeros-proposal` is archived in `zeta-zeros-submission/proposal/`.
- `dzq-lean-formal` is archived in `dzq-lean/formal/`.
- `pg182-frame` was renamed `prime-gaps-182`; `pg182-c0`, `pg182-d1`, `pg182-d2` and
  `kloosterman-sheaf` are archived in its named lane directories.
- `subset-sum-half` was renamed `subset-sum`; `subset-sum-mitm` is archived in `mitm/`.
- `clz-frontier` is archived in `clz-cert/frontier/`.
- `capped-relax-sssp` is archived in `relax-completeness/engine-spec/`.
- `vdw-first-rung` is archived in `van-der-waerden/baseline/`.
- `matroid-prophet-exact-B`, `snaky-scout` and `critical-line-269-400` are archived as
  completed or explicitly superseded artifacts.
- `mathlib4-1` is archived after all 453 of its refs were preserved in `mathlib4`: 70 shared
  branches were already identical, `bump/v4.37.0` and `staging` were fast-forwarded,
  `marginal_itp` was created, seven daily tags were copied, and the divergent `master` and
  `shake` histories were preserved at `refs/archive/mathlib4-1/master` and
  `refs/archive/mathlib4-1/shake`.

Every source commit was verified as an ancestor of its umbrella's remote main before archival.
The umbrella READMEs map active proof work versus historical proposal/frontier material and name
any optional external regeneration datasets. These were history-preserving merges, not file dumps.
The 2026-11-26 consolidation (below) re-verified every fold lossless and then deleted the archived
shells — except `critical-line-269-400`, which stays archived in place as unique public evidence.

### 2026-11-26 consolidation (E1–E8 — current shape, 77 → 59 repos)

Mandate: every repo in the org must make sense why it is there and not merged or archived; each
survivor gets a tight README + the usual GitHub categories (description, topics, license, README).
Pattern: **preserve-first, verify lossless, then delete the shell** — per repo, never bulk.
`campaign-archive` (private) is the safety net and stays. Execution proofs: `/tmp/bigo_exec/E{1..8}.md`.

**Folded then deleted (content + history verified in the successor before each delete):**

| shell | successor location |
|---|---|
| `clz-frontier` | `clz-cert/frontier/` |
| `zeta-zeros-proposal` | `zeta-zeros-submission/proposal/` |
| `capped-relax-sssp` | `relax-completeness/engine-spec/` |
| `subset-sum-mitm` | `subset-sum/mitm/` + `refs/heads/archive/subset-sum-mitm/{v2-alpha-half,v2-budget}` |
| `pg182-c0`, `pg182-d1`, `pg182-d2`, `kloosterman-sheaf` | `prime-gaps-182` named lane directories |
| `dzq-lean-formal` | `dzq-lean/formal/` |
| `mathlib4-1` | `mathlib4` `refs/archive/mathlib4-1/*` (444 tips verbatim) |
| `verifier-1` | `verifier` (merge `1d01f6e4`, parent `6872df12`) |
| `vdw-first-rung` | `van-der-waerden/baseline/` + `refs/heads/archive/vdw-first-rung/rung-2` @20961db4d1 + tags |
| `matroid-prophet-exact-B` | `matroid-prophet-tight-corner/superseded/exact-B/` (source tip d4284e17afd8) |
| `snaky-scout` | `snaky-nineteen/scout/` |
| `qrt-exec` | `quasi-riemann-baseline-rerun/pr103-rerun/` (redacted clean import; full unredacted history in `campaign-archive`) |
| `snaky-conditional` | `snaky-twenty/conditional/` |
| `subsetsum-lean` | `subset-sum/hs74-historical/` |
| `catalan-irrationality-measure-410` | `catalan-295-litsey-port/archive/410/` + `refs/heads/archive/410/*` (OOM/elab research branches) |

**Archived in place (kept read-only, NOT deleted — unique public value):**
`critical-line-269-400` (only public H ≥ 269/400 bridge, never merged) and
`pi-irrationality-measure` (historical cert superseded by μ(π)=2, independent reproduction evidence).

**Pending fold — `catalan-irrationality-measure-411`:** byte-identical twin of the folded 410
(main SHA 0738347d; README states μ(G) ≤ 410 — no distinct 411 bound exists). Its only unique content
is the CI-sharding engineering on PR #1, already preserved in `catalan-295-litsey-port` at
`refs/heads/archive/411/ci-sharded-lean-build-2125613832` @295044b. **Fold-after-PR#1**: zero writes
to 411 while the merge watcher is armed on head 295044b; once PR #1 merges, fold into the 295 archive
lineage, verify lossless, delete the shell. A genuine future 411 bound (new math) would earn a
separate repo — not today's content. Its description/topics are deliberately left until the fold.

**Visibility decisions pending (Emissary):** 9 private repos carry "Public …" why-up boilerplate
(`clz-cert`, `heilbronn-bar`, `knausgard-cert`, `matroid-statement`, `prime-gaps-182`,
`sssp-dmsy-stack`, `staircase-port`, `subset-sum-l25`, `weil-verify`) — content framed as public
evidence while the repo is private. These are visibility decisions, not defects; no visibility was
changed unilaterally. `dzq-lean` and `matmul-frobenius` were already re-worded to private;
`campaign-archive` is private by design.

### Local preservation snapshot

`campaign-archive` is the broad private safety net for unique and unfinished local research, not a
new active proof lane. It contains 128,838 entries: 87,702 canonical files and 41,136 relative
duplicate links, totaling 4,697,765,345 canonical bytes. Source paths and SHA256 are recorded in
`MANIFEST.json`; all 125,844 earlier Git blobs passed exact content verification, as did the two
later additions — the 1,502-entry volume-gap set and the 1,490-entry retired-notes set (the latter
re-verified file-by-file against the remote tree on 2026-11-25). `RESTORE.md` and
`verify_archive.py` provide byte-exact recovery. Build caches, raw transcript databases, oversized
artifacts and credential-pattern files are excluded and documented in `SKIPPED.md`. The historical
CLZ certificate is preserved as a hash-verified compressed asset in the private `preservation-extras`
release, outside the Git snapshot. No fresh build is claimed for the snapshot. The 2026-11-26
consolidation added fold-provenance refs (E4 redacted-source recovery, E7 v2-lane sources) to the
archive before each shell delete. See the
[condensed BigO strike handoff](../research/bigo-strike-handoff.md) for the research map and current
validation caveats.

## Upstreams & projects we work with

- [Mathlib](https://leanprover-community.github.io/mathlib4_docs) ([github](https://github.com/leanprover-community/mathlib4)) — the Lean 4 library every proof pins against; mirrored as a dependency pin.
- [bigospeedrun/verifier](https://github.com/bigospeedrun/verifier) — the project's verifier; mirrored for isolated public reruns and receipts.
- [Leaps in Bounds](https://leapsinbounds.org) — bounds-tracking project we mirror and cross-file against.
- [Prove2me](https://prove2.me) — Lean formalization platform; agent workspace mirrored.
- [QuasiRiemannTracker](https://gtimg.github.io/QuasiRiemannTracker/) (GTimG) — quasi-Riemann tracker; our independent reruns feed its reuse flow.
- [openai/math](https://github.com/openai/math) — solution corpus drawn from in several filings (attributed per artifact).
- [AxiomMath/PrimeGapsLib](https://github.com/AxiomMath/PrimeGapsLib) + [kimihiro64/bombieri-vinogradov](https://github.com/kimihiro64/bombieri-vinogradov) — composed in the prime-gaps H1 ≤ 246 formalization.
- [Anthropic Zeta23](https://github.com/bigospeedrun/verifier) — critical-line-zeros breakthrough proof; our zeta packages adapt its results (attributed per filing).
- [spicylemonade/c-hd-proof](https://github.com/spicylemonade/c-hd-proof) — Frontier/C-HD comparator our SSSP submissions stage (dependency pin: `bigospeedrun/c-hd-proof@98c53acc`); our t3-cap-param extension stays local — upstreaming evaluated 2026-11-08, not warranted (frozen artifact).

## Policy

Constructions are credited to their original authors first; filings cite provenance.
Contributions flow **upstream** to [`bigospeedrun`](https://github.com/bigospeedrun) as PRs —
this org is the working collection, not the destination. Work is AI-assisted and disclosed
(darkhipo swarm). The methodology lives in
[`bigospeedrun-agent-kit`](https://github.com/BigO-Hunter/bigospeedrun-agent-kit).

Contact: dima@darkhipo.info · Org page: <https://bigo-hunter.github.io>
