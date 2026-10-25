# Research engineering portfolio

Selected public contributions by [bengoechea](https://github.com/bengoechea), focused on formal verification, scientific-software integration and reusable proof libraries.

As of **25 October 2026**:

> Contributed 22 merged pull requests to google-deepmind/formal-conjectures, including Lean proofs of specific identities and classical bounds, reusable library lemmas, statement formalizations and corrections.

The count covers several contribution types; it is not a count of solved research problems.

## Selected case studies

| Case study | Engineering contribution | Public outcome |
|---|---|---|
| [External-proof integration: Erdős 604](case-studies/erdos604.md) | Compatibility port, counting adapter, exact-target bridge and reproducible packaging | [Merged #7340](https://github.com/google-deepmind/formal-conjectures/pull/7340); [public proof package](https://github.com/MendozaLab/erdos-experiments/tree/09f72c57ed2d98906b9cf03bff2091f6fe73807f/proofs/erdos604) |
| [Prime-series identity: Erdős 69/257](case-studies/erdos69.md) | Convergence arguments, arithmetic-function lemmas and a reusable Lean library | [Merged #7062](https://github.com/google-deepmind/formal-conjectures/pull/7062) |
| [Classical Sidon counting bounds: Erdős 30](case-studies/erdos30.md) | Five proved textbook variants and reusable finite-set lemmas | [Merged #3935](https://github.com/google-deepmind/formal-conjectures/pull/3935) |

Each case study identifies my contribution, the underlying mathematical work, source code, verification evidence and limitations. Start with Erdős 604 for integration and reproducibility, Erdős 69 for infinite-series formalization, or Erdős 30 for combinatorial library design.

## How to inspect the work

1. Read a case study and follow its immutable source links.
2. Inspect the merged changes and the successful `Build project` check on the submitted revision.
3. Follow the original project's pinned setup and reproduction instructions. The case studies distinguish saved build receipts from checks freshly run for this portfolio.

Lean is a proof assistant that checks formal arguments. Mathlib is its shared mathematics library. Formal Conjectures also contains statements with proof placeholders; a merged contribution does not by itself mean that the associated research problem was solved.

## Attribution and evidence boundaries

- The Erdős 604 mathematical theorem is credited to OpenAI. My work is the compatibility port, adapter and integration package.
- The prime-series identity is attributed to Terence Tao. Its formalization does not prove the separate irrationality conjecture.
- The Sidon bounds are classical results. The main asymptotic conjecture is outside the contribution.
- The contributions used AI assistance, disclosed in the original submissions and case studies. Source inspection, compiler checks and mathematical novelty are separate claims.
- These are community contributions to public repositories. They do not imply employment by or endorsement from Google DeepMind or OpenAI.

Evidence was checked on **25 October 2026**. This repository contains case-study documentation and links to the original implementations. The linked projects retain their own licenses and attribution.
