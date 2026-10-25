# Erdős 30: reusable Sidon counting bounds

[Portfolio index](../README.md) · [Merged contribution #3935](https://github.com/google-deepmind/formal-conjectures/pull/3935)

## Contribution

I contributed five proved classical counting variants and supporting finite-set lemmas. A Sidon set is a set whose pair sums have unique representations up to order. The work separates reusable counting interfaces from their applications to the problem file.

| Proved variant | Result |
|---|---|
| `elementary_difference_count` | For a Sidon set in `0,...,N`, `|A|(|A|-1) ≤ 2N`. |
| `distinct_sums_card` | The sumset has `|A|(|A|+1)/2` elements. |
| `distinct_sums_in_range` | A set in `0,...,N` has its sumset in `0,...,2N`. |
| `erdos_turan_counting` | Combining cardinality and containment gives `|A|(|A|+1)/2 ≤ 2N+1`. |
| `lindstrom_weak` | The elementary difference bound gives `|A| ≤ floor(sqrt(2N)) + 1`. |

These are classical bounds, not new extremal mathematics. The submission discloses Claude/Codex assistance with drafting and source checking, and Perplexity assistance with citation lookup.

## Inspectable implementation

- [Immutable problem proofs](https://github.com/google-deepmind/formal-conjectures/blob/f8445f0146557fdcbafb84f170ede2d88e295307/FormalConjectures/ErdosProblems/30.lean): all five theorem bodies and the separate open conjectures.
- [Finite-set product counting lemmas](https://github.com/google-deepmind/formal-conjectures/blob/f8445f0146557fdcbafb84f170ede2d88e295307/FormalConjecturesForMathlib/Data/Finset/Prod.lean): reusable strict-triangle cardinality results.
- [Pointwise finite-set addition lemma](https://github.com/google-deepmind/formal-conjectures/blob/f8445f0146557fdcbafb84f170ede2d88e295307/FormalConjecturesForMathlib/Algebra/Group/Pointwise/Finset/Basic.lean): the interval-addition interface used in the containment proof.
- [Merged contribution and review history](https://github.com/google-deepmind/formal-conjectures/pull/3935).

## Validation evidence

The final contribution spans five files and passed the upstream `Build project` check at submitted revision `970674931854d921b4a7e2729722a64531d268ab`. The immutable merge source linked above contains the five proved variants.

The checked contribution pins are Lean **4.33.1** and Mathlib **0df444a360eaa60ab8c11dca51a86af692955474**. After following the upstream setup at the linked revision, the narrow problem target is:

```sh
lake --wfail build 'FormalConjectures.ErdosProblems.«30»'
```

The submission description includes an earlier two-file build and axiom record. That record is historical, not an exact receipt for the final five-file layout. The portfolio audit uses the final source and final-head successful build; it did not freshly rerun final-head compilation or axiom inspection.

## Scope and engineering relevance

The main asymptotic Sidon conjecture remains outside this contribution. This work demonstrates decomposition into reusable interfaces, finite-cardinality reasoning, arithmetic edge cases and integration through upstream review. The successful build is evidence of checked formal code, not mathematical novelty.
