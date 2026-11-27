# BigO-Hunter

Lean 4 formalizations, certificates, audits and verification receipts for improved
algorithmic and mathematical bounds, contributed toward the
[BigO Speedrun](https://github.com/bigospeedrun) initiative.

- Project site: <https://bigospeedrun.com>
- Initiative org: <https://github.com/bigospeedrun>
- Boards & forums: <https://board.bigospeedrun.com>

Every repo carries the `big-o-speedrun` topic plus one row topic, so the org is filterable
by row. Private repos hold in-progress work. Each repo's README states its result, evidence
and next steps.

## Rows

- **Directed SSSP** (`sssp`) — `sssp-chd-row` (n ; n log^(2/3)), `sssp-nlogn` (n log ; n log²),
  `sssp-n2` (n²), `relax-completeness` (capped relaxation engine spec), `sssp-dmsy-stack` *(private)*
- **APSP & dynamics** (`apsp`) — `apsp-bound`, `minplus-widgets`, `bonifaci-lane`, `aft-lane`
- **3-SAT** (`3sat`) — `sat-decision-program`
- **Snaky** (`snaky`) — `snaky-nineteen` (19-move), `snaky-twenty` (20-move)
- **Subset Sum** (`subset-sum`) — `subset-sum` (α = 1/2 deterministic + MITM), `subset-sum-l25` *(private)*
- **Matroid Prophet** (`matroid-prophet`) — `matroid-prophet-tight-corner`, `matroid-statement`
- **Matmul** (`matmul`) — `matmul-frobenius` *(private)* — Frobenius lane, ω < 9/4
- **Combinatorics** (`combinatorics`) — `ramsey-5-5-lean-certificate` (R(5,5) ≥ 42),
  `schur-number-8-lean` (S(8) ≥ 5372), `admissible-tuples-lean`, `van-der-waerden` (c = 1/20000),
  `sidorenko-counterexample-lean`, `prime-gaps-246-lean` (H1 ≤ 246)
- **Prime gaps 182** (`prime-gaps`) — `prime-gaps-182` *(private)* — C0/D1/D2 + Kloosterman/Weil lanes
- **Number Theory** (`number-theory`) — `catalan-295-litsey-port` (μ(G) ≤ 295, Litsey port),
  `catalan-irrationality-measure-411` (sharded Lean build), `catalan-constant-gen5` (μ(G) ≤ 528.2315),
  `pi-irrationality-measure` *(archived)*, `dft-halitziyav6-rate`, `heilbronn-triangle-lean`
  (exact-K η ≈ 7.2144e-237), `heilbronn-triangle-ten237` (1/10²³⁷), `heilbronn-bar` *(private)*
- **Z is Diophantine in Q** (`diophantine`) — `z-diophantine-research`, `dzq-lean` *(private)*
- **Zeta / Riemann** (`zeta`) — `quasi-riemann-baseline-rerun`, `QuasiRiemannTracker`,
  `zeta-zeros-submission`, `zeta-measure-certificates`, `critical-line-269-400` *(archived — H ≥ 269/400 bridge)*,
  `weil-verify` *(private)*, `knausgard-cert` *(private)*, `clz-cert` *(private)*
- **Physics** (`physics`) — `haldane-gap-beta13` (certified γ_L > 0.06743)
- **Sensitivity** (`sensitivity`) — `average-sensitivity-lean` (AS ≤ 3.7614546·d·√n)
- **Integer Multiplication** (`integer-mult`) — `integer-mult-bounds` (κ > 2⁻¹⁵)
- **Support & tooling** (`support`) — `bigospeedrun-agent-kit` (methodology), `lemma-library`,
  `bochner-lane`, `leaps-in-bounds`, `omr-statement`, `mathlib4` (dependency pin), `verifier`,
  `site`, `c-hd-proof`, `prove2me_workspace`, `campaign-archive` *(private preservation snapshot)*,
  `staircase-port` *(private)*
- **Org identity** (`support`) — `.github` (this manifest), `bigo-hunter.github.io` (org page)

## Upstreams & projects we work with

- [Mathlib](https://github.com/leanprover-community/mathlib4) — the Lean 4 library every proof pins against.
- [bigospeedrun/verifier](https://github.com/bigospeedrun/verifier) — the project's verifier, mirrored for public reruns and receipts.
- [Leaps in Bounds](https://leapsinbounds.org) — bounds-tracking project we cross-file against.
- [Prove2me](https://prove2.me) — Lean formalization platform; agent workspace mirrored.
- [QuasiRiemannTracker](https://gtimg.github.io/QuasiRiemannTracker/) (GTimG) — independent reruns feed its reuse flow.
- [openai/math](https://github.com/openai/math) — solution corpus, attributed per artifact.
- [AxiomMath/PrimeGapsLib](https://github.com/AxiomMath/PrimeGapsLib) + [kimihiro64/bombieri-vinogradov](https://github.com/kimihiro64/bombieri-vinogradov) — composed in the H1 ≤ 246 formalization.
- [spicylemonade/c-hd-proof](https://github.com/spicylemonade/c-hd-proof) — C-HD comparator our SSSP submissions stage.

## Method

Constructions are credited to their original authors; filings cite provenance. Contributions
flow upstream to [`bigospeedrun`](https://github.com/bigospeedrun) as PRs. Work is AI-assisted
and disclosed (darkhipo swarm). Methodology:
[`bigospeedrun-agent-kit`](https://github.com/BigO-Hunter/bigospeedrun-agent-kit).

Contact: dima@darkhipo.info · Org page: <https://bigo-hunter.github.io>
