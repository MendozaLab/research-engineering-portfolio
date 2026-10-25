# Erdős 604: integrating an external proof

[Portfolio index](../README.md) · [Merged contribution #7340](https://github.com/google-deepmind/formal-conjectures/pull/7340)

## Contribution

> Integrated OpenAI’s weak pinned-distance theorem with the Erdős 604 benchmark through a compatibility port and counting adapter, with pinned dependencies, reproducible build receipts and an exact-target bridge; the underlying mathematics is credited to OpenAI.

The engineering task was to connect an existing theorem to a benchmark's exact definitions and dependency versions. The package adapts the relevant OpenAI source from Lean 4.34.1 to Lean 4.33.1 and the receiving Mathlib revision, supplies a finite-counting and asymptotic adapter, and proves that its copied definitions match the upstream target.

The port, adapter and packaging were prepared under my direction with Codex assistance. OpenAI supplied the underlying theorem and its formal proof. The package does not claim an original mathematical solution.

## Inspectable implementation

- [Immutable source package and README](https://github.com/MendozaLab/erdos-experiments/tree/09f72c57ed2d98906b9cf03bff2091f6fe73807f/proofs/erdos604): source code, pinned configuration and reproduction commands.
- [Attribution and compatibility changes](https://github.com/MendozaLab/erdos-experiments/blob/09f72c57ed2d98906b9cf03bff2091f6fe73807f/proofs/erdos604/PROVENANCE.md): original revisions, modified files and licensing.
- [Final theorem application](https://github.com/MendozaLab/erdos-experiments/blob/09f72c57ed2d98906b9cf03bff2091f6fe73807f/proofs/erdos604/Erdos604Proof/ExternalApplication.lean): derives the weak statement by applying the imported `OAI.WeakPinned.main`.
- [Exact-target bridge](https://github.com/MendozaLab/erdos-experiments/blob/09f72c57ed2d98906b9cf03bff2091f6fe73807f/proofs/erdos604/verification/CurrentTargetBridge.lean.txt): matches the upstream definitions and proves the target without using its placeholder proof.

## Validation evidence

The [verification record](https://github.com/MendozaLab/erdos-experiments/blob/09f72c57ed2d98906b9cf03bff2091f6fe73807f/proofs/erdos604/VERIFICATION.md) documents 58 compiled package modules, 27 selected transitive axiom reports, a successful standalone Lake build and a separate upstream-target bridge check. The axiom reports list only the standard Lean axioms `propext`, `Classical.choice` and `Quot.sound`.

The recorded toolchain is Lean **4.33.1**, with Mathlib **0df444a360eaa60ab8c11dca51a86af692955474**. Follow the original package's setup; its documented build command is:

```sh
lake --wfail build OAI Erdos604Proof Erdos604Proof.Audit
```

The 25 October 2026 portfolio audit checked merge status, the successful upstream `Build project` check, relevant saved source/log hashes and receipt consistency. It did not perform a fresh 58-module compilation. The public reproduction guide describes the earlier successful runs and their limits.

## Scope and engineering relevance

The weak result gives the fixed-positive-epsilon asymptotic pinned-distance bound. The sharper logarithmic and average variants are outside this contribution. The upstream merge adds the external proof link, status metadata and attribution while retaining the repository's statement placeholder.

This example demonstrates dependency compatibility work, theorem-interface integration, provenance preservation and reproducibility packaging. It is not a benchmark measurement of agent performance or a claim of independent validation of every argument in OpenAI's paper. The unchanged original release and official Comparator workflow were not replayed by this package's recorded checks.
