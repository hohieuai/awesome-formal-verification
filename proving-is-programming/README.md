# Proving Is Programming: Lean 4 from First Principles

A 345-slide deck on formal theorem proving in Lean 4 (version 4.33.0). It follows the twelve chapters of *Theorem Proving in Lean 4* and adds background material for newcomers, step-by-step walkthroughs, summaries and further problems.

| File | Format |
| --- | --- |
| [Proving-Is-Programming-Lean4-English.pdf](Proving-Is-Programming-Lean4-English.pdf) | PDF (vector text) |

## Compiled by

[hohieuai](https://github.com/hohieuai), maintainer of [awesome-formal-verification](https://github.com/hohieuai/awesome-formal-verification). The compiler is not an author of the original book.

## Sources

### Primary source

The structure, concepts and Lean code of this deck are adapted from:

> Jeremy Avigad, Leonardo de Moura, Soonho Kong and Sebastian Ullrich, with contributions from the Lean Community. *Theorem Proving in Lean 4*. Online edition for Lean 4.33.0. Apache License 2.0.
> Book: <https://lean-lang.org/theorem_proving_in_lean4/>
> Source: <https://github.com/leanprover/theorem_proving_in_lean4>

The deck follows the online edition for Lean 4.33.0. Code examples come from the book's source files (`book/TPiL/*.lean`) and were compared against commit [`4e28129`](https://github.com/leanprover/theorem_proving_in_lean4/tree/4e28129fdd58037f8f5857548d5e99fe4fb0cc57) (14 August 2026).

To cite the original book:

```bibtex
@misc{tpil4,
  author       = {Avigad, Jeremy and de Moura, Leonardo and Kong, Soonho and Ullrich, Sebastian},
  title        = {Theorem Proving in {Lean} 4},
  howpublished = {\url{https://lean-lang.org/theorem_proving_in_lean4/}},
  note         = {With contributions from the Lean Community. Edition for Lean 4.33.0. Apache License 2.0},
  urldate      = {2026-10-31}
}
```

### Other cited works

In addition to the primary source, the deck draws on the works listed below for background, historical context and further reading. Numbering follows the References slides of the deck, and citations appear as [n] in slide footers. These works are cited for facts and ideas only; none of their text or code is reproduced.

#### Lean documentation and community resources

- [3] *Functional Programming in Lean*. <https://lean-lang.org/functional_programming_in_lean/>
- [4] J. Avigad and P. Massot. *Mathematics in Lean*. <https://leanprover-community.github.io/mathematics_in_lean/>
- [5] *Metaprogramming in Lean 4*. <https://github.com/arthurpaulino/lean4-metaprogramming-book>
- [6] *The Lean Language Reference*. <https://lean-lang.org/doc/reference/latest/>
- [7] Mathlib, source code. <https://github.com/leanprover-community/mathlib4>
- [8] Mathlib, API documentation. <https://leanprover-community.github.io/mathlib4_docs/>
- [9] *Natural Number Game*. <https://adam.math.hhu.de/#/g/hhu-adam/NNG4>
- [10] Loogle, a search engine for Mathlib lemmas. <https://loogle.lean-lang.org/>
- [11] Lean Zulip, community discussion forum. <https://leanprover.zulipchat.com/>
- [12] Lean community, index of learning resources. <https://leanprover-community.github.io/learn.html>

#### Research literature and formalization projects

- [13] A. Edelman. "The Mathematics of the Pentium Division Bug." *SIAM Review* 39(1):54–67, 1997.
- [14] X. Leroy. "Formal Verification of a Realistic Compiler." *Communications of the ACM* 52(7):107–115, 2009.
- [15] X. Yang, Y. Chen, E. Eide and J. Regehr. "Finding and Understanding Bugs in C Compilers." In *Proceedings of the 32nd ACM SIGPLAN Conference on Programming Language Design and Implementation (PLDI)*, 2011.
- [16] G. Gonthier. "Formal Proof — The Four-Color Theorem." *Notices of the AMS* 55(11):1382–1393, 2008.
- [17] T. Hales et al. "A Formal Proof of the Kepler Conjecture." *Forum of Mathematics, Pi* 5:e2, 2017.
- [18] Lean Community. Liquid Tensor Experiment, completed 2022. <https://github.com/leanprover-community/lean-liquid>
- [19] L. de Moura and S. Ullrich. "The Lean 4 Theorem Prover and Programming Language." In *Automated Deduction – CADE 28*, LNCS 12699, 2021.
- [20] W. A. Howard. "The Formulae-as-Types Notion of Construction." In *To H. B. Curry: Essays on Combinatory Logic, Lambda Calculus and Formalism*, Academic Press, 1980.
- [21] R. Diaconescu. "Axiom of Choice and Complementation." *Proceedings of the AMS* 51(1):176–178, 1975.
- [22] J.-Y. Girard. *Interprétation fonctionnelle et élimination des coupures de l'arithmétique d'ordre supérieur*. Thèse d'État, Université Paris VII, 1972.

## Notice of changes

This deck is a modified work. Relative to the original book:

- Code examples are copied from the book's source files (`book/TPiL/*.lean`); some lines are re-wrapped to fit the slides.
- Examples labelled "(illustration)" are original and were checked with Lean 4.33.0.
- Explanations, background material (Part 0), summaries, questions and error walkthroughs are newly written; the book's prose was not copied.
- The material is reorganised into slides, with citations to the other works listed above.

This deck is not affiliated with or endorsed by the authors of the book or by the Lean project.

## License

The contents of this folder are distributed under the Apache License, Version 2.0, the same license as the original book. Modifications copyright 2026 hohieuai. A copy of the License is in [LICENSE](LICENSE) and is also reproduced in the Appendix at the end of the deck. Attribution notices are in [NOTICE](NOTICE).

The rest of this repository is dedicated to the public domain under CC0 1.0 (see the repository's top-level LICENSE). That dedication does not apply to this folder. Licensing per path is declared in the repository's `REUSE.toml` following the [REUSE Specification](https://reuse.software/).

The PDF embeds the fonts Source Serif 4 and JetBrains Mono, both under the SIL Open Font License 1.1, which permits embedding in documents.
