# Proving Is Programming: Lean 4 from First Principles

A 345-slide deck on formal theorem proving in Lean 4 (version 4.33.0). It follows the twelve chapters of *Theorem Proving in Lean 4* and adds background material for newcomers, step-by-step walkthroughs, summaries and further problems.

| File | Format |
| --- | --- |
| [Proving-Is-Programming-Lean4-English.pdf](Proving-Is-Programming-Lean4-English.pdf) | PDF (vector text) |

## Compiled by

[hohieuai](https://github.com/hohieuai), as part of [awesome-formal-verification](https://github.com/hohieuai/awesome-formal-verification). The compiler is not an author of the original book.

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

Background, history and further reading draw on other works: papers (for example Howard 1980, Girard 1972, Diaconescu 1975, Leroy 2009, Gonthier 2008, Hales et al. 2017, de Moura and Ullrich 2021), Lean books and documentation (*Functional Programming in Lean*, *Mathematics in Lean*, *Metaprogramming in Lean 4*, the Lean reference manual, Mathlib) and community resources. They are cited as [3]–[22] on the deck's References slides and marked [n] in slide footers. These works are cited for facts and ideas; their text and code are not reproduced.

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
