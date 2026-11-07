# Hunting for BigO

An organization for organizing the repositories working on **[Big O Speedrun](https://github.com/bigospeedrun)** contributions — Lean 4 formalizations and certificates for improved algorithmic and mathematical bounds.

Every repo here targets one or more rows of the [bigospeedrun board](https://bigospeedrun.com). Each repo is tagged with the `big-o-speedrun` umbrella topic plus one row topic, so the org is filterable by row.

## Rows

### Directed SSSP — `sssp`
| Repo | Target |
|---|---|
| [sssp-chd-row](https://github.com/Hunting-for-BigO/sssp-chd-row) | `n` · `n log^(2/3)` |
| [sssp-nlogn](https://github.com/Hunting-for-BigO/sssp-nlogn) | `n log n` · `n log²` (binary-heap) |
| [sssp-n2](https://github.com/Hunting-for-BigO/sssp-n2) | `n²` |
| [sssp-dmsy-stack](https://github.com/Hunting-for-BigO/sssp-dmsy-stack) | DMSY stack *(private)* |
| [capped-relax-sssp](https://github.com/Hunting-for-BigO/capped-relax-sssp) | capped relaxation |
| [relax-completeness](https://github.com/Hunting-for-BigO/relax-completeness) | relaxation completeness |

### Snaky — `snaky`
- [snaky-nineteen](https://github.com/Hunting-for-BigO/snaky-nineteen) — 19-move
- [snaky-twenty](https://github.com/Hunting-for-BigO/snaky-twenty) — 20-move
- [snaky-conditional](https://github.com/Hunting-for-BigO/snaky-conditional)

### Subset Sum — `subset-sum`
- [subset-sum-mitm](https://github.com/Hunting-for-BigO/subset-sum-mitm)
- [subset-sum-half](https://github.com/Hunting-for-BigO/subset-sum-half) — α=1/2 deterministic MITM
- [subsetsum-lean](https://github.com/Hunting-for-BigO/subsetsum-lean) *(private)*

### Matroid Prophet — `matroid-prophet`
- [matroid-prophet-exact-B](https://github.com/Hunting-for-BigO/matroid-prophet-exact-B) — exact constant C(B)
- [matroid-prophet-tight-corner](https://github.com/Hunting-for-BigO/matroid-prophet-tight-corner) — one-sample tight corner

### Combinatorics — `combinatorics`
- [ramsey-5-5-lean-certificate](https://github.com/Hunting-for-BigO/ramsey-5-5-lean-certificate) — R(5,5) ≥ 42
- [schur-number-8-lean](https://github.com/Hunting-for-BigO/schur-number-8-lean) — S(8) ≥ 5372
- [admissible-tuples-lean](https://github.com/Hunting-for-BigO/admissible-tuples-lean) — wheel-admissibility
- [vdw-first-rung](https://github.com/Hunting-for-BigO/vdw-first-rung) — van der Waerden first rung
- [van-der-waerden](https://github.com/Hunting-for-BigO/van-der-waerden)
- [sidorenko-counterexample-lean](https://github.com/Hunting-for-BigO/sidorenko-counterexample-lean)
- [prime-gaps-246-lean](https://github.com/Hunting-for-BigO/prime-gaps-246-lean)

### Number Theory — `number-theory`
- [pi-irrationality-measure](https://github.com/Hunting-for-BigO/pi-irrationality-measure)
- [catalan-irrationality-measure-410](https://github.com/Hunting-for-BigO/catalan-irrationality-measure-410) — μ(G) ≤ 410
- [catalan-constant-gen5](https://github.com/Hunting-for-BigO/catalan-constant-gen5) — μ(G) ≤ 528
- [dft-halitziyav6-rate](https://github.com/Hunting-for-BigO/dft-halitziyav6-rate)
- [z-diophantine-research](https://github.com/Hunting-for-BigO/z-diophantine-research) — Z is Diophantine in Q
- [heilbronn-triangle-lean](https://github.com/Hunting-for-BigO/heilbronn-triangle-lean)
- [heilbronn-triangle-ten237](https://github.com/Hunting-for-BigO/heilbronn-triangle-ten237)

### Zeta / Riemann — `zeta`
- [critical-line-269-400](https://github.com/Hunting-for-BigO/critical-line-269-400)
- [quasi-riemann-baseline-rerun](https://github.com/Hunting-for-BigO/quasi-riemann-baseline-rerun)
- [QuasiRiemannTracker](https://github.com/Hunting-for-BigO/QuasiRiemannTracker)
- [zeta-zeros-submission](https://github.com/Hunting-for-BigO/zeta-zeros-submission)
- [zeta-zeros-proposal](https://github.com/Hunting-for-BigO/zeta-zeros-proposal)
- [zeta-measure-certificates](https://github.com/Hunting-for-BigO/zeta-measure-certificates)

### Physics — `physics`
- [haldane-gap-beta13](https://github.com/Hunting-for-BigO/haldane-gap-beta13) — Haldane gap γ_L > 771/5000

### Sensitivity — `sensitivity`
- [average-sensitivity-lean](https://github.com/Hunting-for-BigO/average-sensitivity-lean) — polynomial-threshold average sensitivity

### Integer Multiplication — `integer-mult`
- [integer-mult-bounds](https://github.com/Hunting-for-BigO/integer-mult-bounds) — κ > 2⁻¹⁵

## Support & infrastructure — `support`
- [bigospeedrun-agent-kit](https://github.com/Hunting-for-BigO/bigospeedrun-agent-kit) — board activation playbook + verified-package engine
- [leaps-in-bounds](https://github.com/Hunting-for-BigO/leaps-in-bounds) — progress on mathematical unknowns
- [omr-statement](https://github.com/Hunting-for-BigO/omr-statement)
- [mathlib4](https://github.com/Hunting-for-BigO/mathlib4) — Lean 4 math library (dependency fork)
- [staircase-port](https://github.com/Hunting-for-BigO/staircase-port) *(private)*

## Conventions

- Every repo carries the `big-o-speedrun` topic.
- Contributions flow **upstream** to [`bigospeedrun`](https://github.com/bigospeedrun) as PRs; this org is the working collection, not the destination.
- Private repos hold in-progress work not yet ready for public review.
