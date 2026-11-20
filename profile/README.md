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
filterable by row. Private repos hold in-progress work.

- **Directed SSSP** (`sssp`) — `sssp-chd-row` (n · n log^(2/3)), `sssp-nlogn` (n log n · n log²),
  `sssp-n2` (n²), `sssp-dmsy-stack` *(private)*, `capped-relax-sssp`, `relax-completeness`
- **APSP & dynamics** (`apsp`) — `apsp-bound`, `minplus-widgets`, `bonifaci-lane`
- **Snaky** (`snaky`) — `snaky-nineteen` (19-move), `snaky-twenty` (20-move), `snaky-conditional`,
  `snaky-scout` *(private)*
- **Subset Sum** (`subset-sum`) — `subset-sum-mitm`, `subset-sum-half` (α=1/2 deterministic MITM),
  `subsetsum-lean` *(private)*, `subset-sum-l25` *(private)*
- **Matroid Prophet** (`matroid-prophet`) — `matroid-prophet-exact-B` (exact C(B)),
  `matroid-prophet-tight-corner`, `matroid-statement` *(private)*
- **Matmul** (`matmul`) — `matmul-frobenius` *(private)* — Frobenius lane, ω < 9/4
- **Combinatorics** (`combinatorics`) — `ramsey-5-5-lean-certificate` (R(5,5) ≥ 42),
  `schur-number-8-lean` (S(8) ≥ 5372), `admissible-tuples-lean`, `vdw-first-rung`,
  `van-der-waerden` (c = 1/20000), `sidorenko-counterexample-lean`, `prime-gaps-246-lean` (H1 ≤ 246)
- **Prime gaps 182** (`prime-gaps`) — `pg182-frame`, `pg182-c0`, `pg182-d1`, `pg182-d2`,
  `kloosterman-sheaf` *(all private)*
- **Number Theory** (`number-theory`) — `pi-irrationality-measure`,
  `catalan-irrationality-measure-410` (μ(G) ≤ 410), `catalan-295-litsey-port` (μ(G) ≤ 295),
  `catalan-constant-gen5` (μ(G) ≤ 528), `dft-halitziyav6-rate`, `heilbronn-triangle-lean`,
  `heilbronn-triangle-ten237` (1/10^237), `heilbronn-bar` *(private)*
- **Z is Diophantine in Q** (`z-diophantine`) — `z-diophantine-research`, `dzq-lean`,
  `dzq-lean-formal` *(the latter two private)*
- **Zeta / Riemann** (`zeta`) — `critical-line-269-400`, `quasi-riemann-baseline-rerun`,
  `QuasiRiemannTracker`, `zeta-zeros-submission`, `zeta-zeros-proposal`, `zeta-measure-certificates`,
  `weil-verify`, `knausgard-cert`, `clz-frontier`, `clz-cert`, `qrt-exec` *(the last five private)*
- **Physics** (`physics`) — `haldane-gap-beta13` (γ_L > 771/5000)
- **Sensitivity** (`sensitivity`) — `average-sensitivity-lean`
- **Integer Multiplication** (`integer-mult`) — `integer-mult-bounds` (κ > 2⁻¹⁵)
- **Support & tooling** (`support`) — `bigospeedrun-agent-kit` (the methodology),
  `lemma-library`, `bochner-lane`, `leaps-in-bounds`, `omr-statement`, `mathlib4` (dependency pin),
  `staircase-port` *(private)*, `verifier`, `site`, `c-hd-proof`, `prove2me_workspace`

## Repository lifecycle

Each repository is one self-contained artifact, verification lane or explicitly marked upstream pin.
Same-topic repositories are not automatically duplicates: baseline and improved certificates remain
side by side when both are reproducible evidence (for example `vdw-first-rung` / `van-der-waerden`
and `matroid-prophet-exact-B` / `matroid-prophet-tight-corner`). Their READMEs name the successor
or the reason the baseline is retained.

`verifier-1` was consolidated into `verifier` on 2026-11-20: its mainline was merged at
`1d01f6e4eeb6bc84617fd5d1a7ca4bcfd231bc7c`, both automation branches were fast-forwarded, and
`verify-chain-jobs` was already identical. Every source branch was verified as an ancestor of the
corresponding target branch before `verifier-1` was archived read-only; there were no source tags.
No lossy same-topic merges.

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
