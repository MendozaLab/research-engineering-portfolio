# Erdős 698: classical gcd bounds on binomial coefficients

[Portfolio index](../README.md) · [Merged contribution #6872](https://github.com/google-deepmind/formal-conjectures/pull/6872)

## Contribution

I contributed AI-assisted Lean proofs of two classical variants attached to Erdős 698, replacing their proof placeholders. The statements were left unchanged.

| Proved variant | Result |
|---|---|
| `erdos_698.variants.erdos_szekeres` | For `1 ≤ i < j ≤ n/2`, `gcd(C(n,i), C(n,j)) ≥ C(n,i) / C(j,i) ≥ 2^i`. |
| `erdos_698.variants.erdos_szekeres_sharp` | For an odd prime `p`, the bound is attained at `i = 1`, `j = p`, `n = 2p`, where the gcd equals 2. |

Here `C(n,k)` is the binomial coefficient and `gcd` the greatest common divisor. The bound is credited in the source to Erdős and Szekeres, and the source notes that it is sharp in the prime case. Neither is new mathematics.

- **Erdős–Szekeres bound:** the identity `C(n,j) C(j,i) = C(n,i) C(n-i,j-i)` shows that `C(n,i)` divides `gcd(C(n,i), C(n,j)) C(j,i)`, which gives the first inequality. The second follows by induction from `2j ≤ n`, which gives `2^k C(j,k) ≤ C(n,k)`.
- **Sharp prime case:** Lucas' theorem gives `C(2p,p) ≡ 2 (mod p)`, so `p` does not divide the central binomial coefficient, which is even. Hence `gcd(2p, C(2p,p)) = 2`, matching the lower bound `2^1`.
- **Side finding:** the library statement keeps the hypothesis `1 ≤ i`, but the proof turned out not to need it.

The library records the elementary Erdős–Szekeres bound. The stronger lower bound attributed in the source to Bergman, which resolves the problem as posed, is outside this contribution.

## Inspectable implementation

- [Immutable problem file](https://github.com/google-deepmind/formal-conjectures/blob/7736f8e822c7afb283fd96203f8c01cff76a6e08/FormalConjectures/ErdosProblems/698.lean): the two proved variants and the separate statements whose proof placeholders (`sorry`) remain outside this contribution.
- [Merged contribution and review history](https://github.com/google-deepmind/formal-conjectures/pull/6872): proof outline, recorded build command and axiom report. The submission discloses Codex/Claude assistance.

## Validation evidence

The contribution changes one file and passed the upstream `Build project` check on the pull request. The submission description records a narrow build of the problem module with exit status 0 and the message "Build completed successfully (8934 jobs)", run against upstream `main` at `89294ea02bd7cd678d59984add52cb4baef3dbf4`. The axiom report for both proved declarations lists only `propext`, `Classical.choice` and `Quot.sound`.

The recorded pins are Lean **4.33.1** and Mathlib **0df444a360eaa60ab8c11dca51a86af692955474**. After following the upstream setup at the linked revision, the narrow target is:

```sh
lake build 'FormalConjectures.ErdosProblems.«698»'
```

The submission's build used a local check script (`fc_check.sh`, not part of the upstream repository) with a setting that lets the check pass while the two remaining `sorry` placeholders (outside this contribution) are present; the command above is the plain module build, not a copy of that script. The 27 October 2026 portfolio audit inspected the merged source, the merge record and the pull request's recorded checks. It did not freshly rerun the compiler or the axiom inspection. These historical pins should not be assumed to match the latest upstream branch.

## Scope and engineering relevance

Two `sorry` placeholders remain in the same file, outside this contribution: the main `erdos_698` statement and `erdos_698.variants.bergman`, both of whose attributes link external Lean proofs in the public plby/lean-proofs repository. This work does not solve Erdős 698; it proved two classical variants in the library.

This example demonstrates elementary divisibility and induction arguments, use of Lucas' theorem through library abstractions, and a small, reviewable change that leaves the surrounding statements untouched.
