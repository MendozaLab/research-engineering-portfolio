# Erdős 69/257: a reusable prime-series identity

[Portfolio index](../README.md) · [Merged contribution #7062](https://github.com/google-deepmind/formal-conjectures/pull/7062)

## Contribution

I contributed an AI-assisted Lean proof of an existing prime-series identity, with reusable arithmetic-function and convergence lemmas. The library establishes convergence before exchanging infinite sums; the problem-level application then becomes a short proof.

The identity rewrites the sum of `omega(n) / 2^n`, where `omega(n)` counts distinct prime divisors, as a sum over primes `p` of `1 / (2^p - 1)`. The mathematical identity is attributed to Terence Tao in the source. The contribution formalizes it rather than proposes a new identity.

## Inspectable implementation

- [Immutable reusable library](https://github.com/google-deepmind/formal-conjectures/blob/23805f9b3d12de44cbd281bd362027cb32aa0d64/FormalConjecturesForMathlib/NumberTheory/ArithmeticFunction/PrimeSeries.lean): arithmetic-function bridge, summability and the infinite-series identity.
- [Immutable problem application](https://github.com/google-deepmind/formal-conjectures/blob/23805f9b3d12de44cbd281bd362027cb32aa0d64/FormalConjectures/ErdosProblems/69.lean): the proved `specialisation_of_erdos_257` variant and the separate irrationality statement.
- [Merged submission and verification records](https://github.com/google-deepmind/formal-conjectures/pull/7062): review history, exact build commands, source hashes and standard-axiom reports. The submission discloses Codex assistance.

## Validation evidence

The final submitted revision passed the upstream `Build project` check. The contribution also includes recorded warning-fatal library and problem-module builds, with axiom inspections listing only `propext`, `Classical.choice` and `Quot.sound` for the named targets.

The checked contribution pins are Lean **4.33.1** and Mathlib **0df444a360eaa60ab8c11dca51a86af692955474**. After following the upstream project's dependency setup at the linked revision, the narrow targets are:

```sh
lake --wfail build   FormalConjecturesForMathlib.NumberTheory.ArithmeticFunction.PrimeSeries   'FormalConjectures.ErdosProblems.«69»'
```

The 25 October 2026 portfolio audit inspected the merged source and live build result. It did not freshly rerun the compiler or the recorded axiom inspections. These historical pins should not be assumed to match the latest upstream branch.

## Scope and engineering relevance

The main irrationality statement remains a proof placeholder and is outside this contribution. This is a checked identity and reusable library work, not a resolution of Erdős 69 or 257.

This example demonstrates convergence reasoning, precise use of library abstractions and separation of a reusable implementation from a small application.
