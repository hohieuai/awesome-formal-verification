# [Awesome Formal Verification](https://github.com/hohieuai/awesome-formal-verification) [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re) [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Awesome%20Formal%20Verification%20-%20a%20curated%20collection%20of%20tools%2C%20papers%2C%20and%20resources%20for%20proving%20software%20and%20hardware%20correctness&url=https://github.com/hohieuai/awesome-formal-verification&hashtags=FormalVerification,TheoremProving,OpenSource)

A curated collection of **formal verification** tools, languages, verified systems, research papers, and learning resources — for proving that software and hardware behave correctly, not just hopefully.

Your contributions are always welcome! See [CONTRIBUTING.md](CONTRIBUTING.md).

## Theorem Provers

| Repository | Description | Logic | Automation | Language | Domain |
| ---------- | ----------- | ----- | ---------- | -------- | ------ |
| [Rocq](https://rocq-prover.org/) | Proof assistant for interactive development of formal proofs | Higher-order logic | Interactive | Rocq / OCaml | Software, math, PL theory |
| [Lean 4](https://leanprover.github.io/) | Dependently typed theorem prover with fast elaboration | Dependent type theory | Interactive + tactics | Lean | Math, software, compilers |
| [Isabelle](https://isabelle.in.tum.de/) | Generic proof assistant with powerful automation (Sledgehammer) | Higher-order logic | Interactive + automated | Isabelle/ML | Software, math, security |
| [Agda](https://github.com/agda/agda) | Dependently typed functional language and proof assistant | Dependent types | Interactive | Agda | PL theory, math |
| [HOL4](https://hol-theorem-prover.org/) | Proof assistant for higher-order logic | HOL | Interactive | Standard ML | Hardware, OS, math |
| [Metamath](https://us.metamath.org/) | Minimalist framework for formalizing mathematics | Set theory | Interactive | Metamath | Mathematics |
| [F*](https://github.com/FStarLang/FStar) | Dependently typed language for program verification and crypto | Dependent types | SMT-backed | F* | Crypto, systems, WebAssembly |
| [Idris 2](https://www.idris-lang.org/) | General-purpose language with dependent types | Dependent types | Interactive | Idris | PL research, theorem proving |

## SMT / SAT Solvers

| Repository | Description | Input | Decidability | Language | Typical Use |
| ---------- | ----------- | ----- | ------------ | -------- | ----------- |
| [Z3](https://github.com/Z3Prover/z3) | High-performance SMT solver from Microsoft Research | SMT-LIB | Decidable fragments | C++ / APIs | Program analysis, symbolic execution |
| [cvc5](https://github.com/cvc5/cvc5) | SMT solver supporting many theories and proof production | SMT-LIB | Decidable fragments | C++ | Verification, synthesis |
| [Yices 2](https://github.com/SRI-CSL/yices2) | Efficient SMT solver for software verification | SMT-LIB | Decidable fragments | C | BMC, invariant generation |
| [Boolector](https://github.com/Boolector/boolector) | SMT solver for bit-vectors and arrays (archived; consider cvc5) | SMT-LIB | Bit-vectors | C | Hardware, low-level code |
| [MiniSat](https://github.com/niklasso/minisat) | Minimalist SAT solver | CNF | SAT | C++ | BMC, planning, scheduling |
| [Kissat](https://github.com/arminbiere/kissat) | State-of-the-art CDCL SAT solver | CNF | SAT | C | Competition-grade SAT solving |
| [STP](https://github.com/stp/stp) | Simplifying theorem prover for bit-vectors and arrays | SMT-LIB | Bit-vectors | C++ | Symbolic execution (KLEE) |

## Program Verification

| Repository | Description | Approach | Target Language | Automation | Output |
| ---------- | ----------- | -------- | --------------- | ---------- | ------ |
| [Dafny](https://github.com/dafny-lang/dafny) | Verification-aware programming language with built-in verifier | Deductive | Dafny | Auto-active | Verified programs |
| [Why3](https://www.why3.org/) | Platform for deductive program verification via VC generation | Deductive | WhyML | SMT + provers | Proof obligations |
| [Frama-C](https://frama-c.com/) | Extensible platform for analyzing C programs | Abstract interpretation, deductive | C | Plugin-dependent | Annotations, proofs |
| [CBMC](https://github.com/diffblue/cbmc) | Bounded model checker for C/C++ and Java bytecode | BMC | C, C++, Java | Automated | Counterexamples |
| [Cameleer](https://github.com/ocaml-gospel/cameleer) | Deductive verifier for OCaml programs using GOSPEL specs | Deductive | OCaml | SMT + interactive | Proof obligations |
| [Verus](https://github.com/verus-lang/verus) | Verification tool for Rust using SMT and linear types | Deductive | Rust | Auto-active | Verified programs |
| [Liquid Haskell](https://ucsd-progsys.github.io/liquidhaskell/) | Refinement types for Haskell programs | Refinement types | Haskell | Automated | Type-level proofs |
| [SPARK](https://www.adacore.com/sparkpro) | Subset of Ada for high-integrity software with proof | Deductive | Ada/SPARK | Automated + interactive | Proven absence of runtime errors |
| [Viper](https://www.pm.inf.ethz.ch/research/viper.html) | Verification infrastructure for permission-based reasoning | Separation logic | Silver, Java-like | Automated | Heap-manipulating programs |
| [Prusti](https://github.com/viperproject/prusti-dev) | Static verifier for Rust based on Viper | Deductive | Rust | Automated | Memory safety, functional props |
| [Kani](https://github.com/model-checking/kani) | Rust model checker built on CBMC | BMC | Rust | Automated | Counterexamples |
| [Creusot](https://github.com/creusot-rs/creusot) | Deductive verifier for Rust using Why3 | Deductive | Rust | Interactive | Functional correctness |

## Model Checkers

| Repository | Description | Model Type | Properties | Language | Domain |
| ---------- | ----------- | ---------- | ---------- | -------- | ------ |
| [TLA+](https://github.com/tlaplus/tlaplus) | Specification language and model checker for concurrent systems | State machines | Safety, liveness | TLA+ | Distributed systems, protocols |
| [Alloy](https://alloytools.org/) | Relational modeling language with SAT-based analyzer | Relational | Structural | Alloy | Software design, architecture |
| [SPIN](https://spinroot.com/) | Model checker for multi-threaded software and protocols | Promela | LTL | Promela / C | Concurrent software |
| [UPPAAL](https://uppaal.org/) | Tool for timed automata and real-time systems | Timed automata | Timed properties | UPPAAL | Real-time, embedded |
| [PRISM](https://www.prismmodelchecker.org/) | Probabilistic model checker for stochastic systems | DTMC, MDP, CTMC | Probabilistic | PRISM | Security, biology, protocols |
| [nuXmv](https://nuxmv.fbk.eu/) | Extension of NuSMV for symbolic model checking | Kripke structures | CTL, LTL | SMV | Hardware, software |
| [Ivy](https://github.com/microsoft/ivy) | Language and tool for interactive verification of protocols | Transition systems | Safety | Ivy | Network protocols |
| [Apalache](https://github.com/apalache-mc/apalache) | Symbolic model checker for TLA+ specifications | TLA+ | Safety, liveness | TLA+ | Distributed systems |

## Specification Languages & Frameworks

- [K Framework](http://www.kframework.org/) - Rewrite-based executable semantics framework for defining programming languages and verifying programs.
- [ACSL](https://frama-c.com/acsl.html) - ANSI/ISO C Specification Language used by Frama-C and other C verifiers.
- [JML](https://www.openjml.org/) - Java Modeling Language for specifying behavior of Java programs.
- [Gospel](https://ocaml-gospel.github.io/gospel/) - OCaml specification language for deductive verification.
- [Sail](https://github.com/rems-project/sail) - Language for specifying instruction set architectures (ISAs).

## Hardware Verification

| Repository | Description | Approach | Input | Automation | Domain |
| ---------- | ----------- | -------- | ----- | ---------- | ------ |
| [SymbiYosys](https://github.com/YosysHQ/sby) | Front-end for Yosys-based formal hardware verification flows | BMC, induction | Verilog, SystemVerilog | Automated | RTL designs |
| [Yosys](https://github.com/YosysHQ/yosys) | Open synthesis suite with formal verification support | SMT, SAT | Verilog | Semi-automated | RTL, netlists |
| [riscv-formal](https://github.com/SymbioticEDA/riscv-formal) | Reusable formal verification framework for RISC-V CPU designs | BMC, induction | Verilog | Semi-automated | CPU cores |
| [ABC](https://github.com/berkeley-abc/abc) | System for logic synthesis and combinational/sequential equivalence checking | CEC, SEC | AIG, BLIF | Automated | Gate-level |
| [EBMC](http://www.cprover.org/ebmc/) | Model checker for hardware designs (Verilog, SystemVerilog, SMV) | BMC | Verilog, SV | Automated | RTL |

### Simulation & Testbenches

- [cocotb](https://www.cocotb.org/) - Python-based testbench framework for HDL simulators.
- [Verilator](https://www.veripool.org/verilator/) - Fast Verilog simulator with assertion and coverage support.
- [chiselverify](https://github.com/chiselverify/chiselverify) - UVM-like verification library for Chisel HDL.

## Smart Contract Verification

- [Certora Prover](https://www.certora.com/) - Formal verification tool for EVM smart contracts using CVL (Certora Verification Language). [Open-source components](https://github.com/Certora).
- [Slither](https://github.com/crytic/slither) - Static analysis framework for Solidity, often used alongside formal verification workflows.
- [Mythril](https://github.com/ConsenSysDiligence/mythril) - Security analysis tool for EVM bytecode using symbolic execution.
- [Halmos](https://github.com/a16z/halmos) - Symbolic testing tool for Solidity smart contracts.
- [HEVM](https://github.com/argotorg/hevm) - Symbolic execution engine for EVM bytecode.
- [Solc-verify](https://github.com/SRI-CSL/solidity) - Solidity compiler extension for SMT-based verification.
- [VeriSol](https://github.com/microsoft/verisol) - Formal correctness analyzer for Solidity via Boogie translation (archived; no longer actively maintained since 2021).
- [Kontrol](https://github.com/runtimeverification/kontrol) - Formal verification for Solidity using K Framework semantics.
- [Verity](https://github.com/lfglabs-dev/verity) - Lean 4 framework for formally specified and verified smart contracts.
- [Move Prover (Aptos)](https://github.com/move-language/move-on-aptos) - Formal verification for Move smart contracts on Aptos.
- [Move Prover (Sui)](https://github.com/move-language/move-sui) - Formal verification for Move smart contracts on Sui.

## Verified Systems & Case Studies

- [seL4](https://sel4.systems/) - Microkernel with end-to-end proof of implementation correctness and security enforcement.
- [CompCert](https://compcert.org/) - Formally verified optimizing compiler for a large subset of C.
- [CertiKOS](http://flint.cs.yale.edu/certikos/) - Certified concurrent OS kernel with verified C compiler toolchain.
- [Ironclad / IronFleet](https://github.com/microsoft/Ironclad) - Verified distributed systems and applications in Dafny (Microsoft Research).
- [miTLS](https://github.com/project-everest/mitls-fstar) - Verified reference implementation of TLS 1.3 in F*.
- [HACMS](https://www.darpa.mil/program/high-assurance-cyber-military-systems) - DARPA program demonstrating formally verified unmanned vehicles.
- [EverCrypt](https://github.com/hacl-star/hacl-star) - Verified cryptographic library in F*.
- [Vale](https://github.com/project-everest/vale) - Tool for generating verified assembly language.

## Learning Resources

### Books

- [Software Foundations](https://softwarefoundations.cis.upenn.edu/) - Interactive textbook series on Coq/Rocq and PL theory (Pierce et al.).
- [Certified Programming with Dependent Types](http://adam.chlipala.net/cpdt/) - Practical engineering with Rocq/Coq (Adam Chlipala).
- [The Little Prover](https://mitpress.mit.edu/books/little-prover) - Gentle introduction to inductive proofs (Friedman & Eastlund).
- [Concrete Semantics](http://concrete-semantics.org/) - Semantics course using Isabelle (Nipkow & Klein).
- [Programming and Proving in Agda](https://plfa.github.io/) - Introduction to dependent types and Agda (Wadler et al.).
- [Homotopy Type Theory](https://homotopytypetheory.org/book/) - Univalent foundations of mathematics.

### Courses & Tutorials

- [DeepSpec Summer School](https://www.youtube.com/channel/UC5yB0ZRgc4A99ttkwer-dDw) - Lectures on deep specification and interactive theorem proving.
- [Logical Foundations (Software Foundations Vol. 1)](https://softwarefoundations.cis.upenn.edu/lf-current/) - Self-paced Coq/Rocq course.
- [Theorem Proving in Lean 4](https://leanprover.github.io/theorem_proving_in_lean4/) - Official Lean 4 tutorial.
- [Learn TLA+](https://learntla.com/) - Practical introduction to TLA+ for system design.
- [Dan Gisselquist's Formal Verification Blog](https://zipcpu.com/formal/formal.html) - Hands-on FPGA/RTL formal verification tutorials.
- [Benjamin Pierce Software Foundations Lectures](https://www.youtube.com/playlist?list=PLGCr8P_YncjUT7gXUVJWSoefQ40gTOz89) - Video lectures accompanying Software Foundations.

## Research

- Propositions as Types (Wadler, 2015): Accessible survey of the Curry–Howard correspondence between proofs and programs. [[Paper]](https://homepages.inf.ed.ac.uk/wadler/papers/propositions-as-types/propositions-as-types.pdf)
- An Axiomatic Basis for Computer Programming (Hoare, 1969): Introduces Hoare logic for program correctness. [[Paper]](https://doi.org/10.1145/363235.363259)
- The seL4 Microkernel: Formal Verification of an OS Kernel (SOSP'09): End-to-end verification of a production OS kernel. [[Paper]](https://sel4.systems/Info/Docs/SEL4.pdf)
- CompCert: A Formally Verified Optimizing Compiler (POPL'09): Verified C compiler preserving program semantics. [[Paper]](https://xavierleroy.org/publi/compcert-backend.pdf)
- A Calculus of Mobile Processes, Part I (Milner, 1989): Pi-calculus foundation for concurrent system reasoning. [[Paper]](http://www.lfcs.inf.ed.ac.uk/reports/89/ECS-LFCS-89-85/)
- Model Checking (1997): Clarke, Grumberg, and Peled's foundational model checking text. [[Book]](https://mitpress.mit.edu/9780262032706/model-checking/)
- Formal Verification of Smart Contracts (2018): Survey of formal methods for blockchain contracts. [[Paper]](https://arxiv.org/abs/1806.08608)
- PropertyGPT: LLM-driven Formal Verification of Smart Contracts (NDSS'24): Retrieval-augmented property generation for contract verification. [[Paper]](https://www.ndss-symposium.org/ndss-paper/propertygpt-llm-driven-formal-verification-of-smart-contracts-through-retrieval-augmented-property-generation/)
- AlphaProof: AI for formal mathematical reasoning at IMO level (2024): DeepMind's RL + language model approach to theorem proving. [[Blog]](https://deepmind.google/discover/blog/ai-solves-imo-problems-at-silver-medal-level/)
- Lean-based Auto-Formalized Mathematics (2025–2026): Lecture notes on LLM-assisted formalization in Lean 4. [[Notes]](https://www.cs.virginia.edu/~rmw7my/Courses/AgenticAISpring2026/Major%20Breakthroughs%20in%20Lean%204-Based%20Auto-Formalized%20Mathematics.html)

## Conferences & Events

- [CAV](https://i-cav.org/) - International Conference on Computer-Aided Verification.
- [FM](https://www.fmeurope.org/) - International Symposium on Formal Methods (Formal Methods Europe).
- [ITP](https://itp-conference.github.io/) - International Conference on Interactive Theorem Proving.
- [CPP](https://sigplan.org/Conferences/CPP/) - Certified Programs and Proofs (co-located with POPL).
- [TACAS](https://etaps.org/) - Tools and Algorithms for Construction and Analysis of Systems.
- [FMBC](https://sites.google.com/view/fmbc) - Formal Methods for Blockchains workshop.
- [ORCONF](https://orconf.org/) - Open Source Digital Design Conference.
- [CHIPS Alliance DV Workshop](https://www.chipsalliance.org/) - Open-source design verification workshop.

## Related Lists

- [awesome-formal-verification (ElNiak)](https://github.com/ElNiak/awesome-formal-verification) - Comprehensive list covering software and hardware verification.
- [awesome-open-hardware-verification](https://github.com/ben-marshall/awesome-open-hardware-verification) - Open-source hardware verification tools and flows.
- [ethereum_formal_verification_overview](https://github.com/leonardoalt/ethereum_formal_verification_overview) - Overview of formal verification tools for Ethereum smart contracts.
- [Formal Methods Wiki](https://en.wikipedia.org/wiki/Formal_methods) - Wikipedia entry on formal methods and verification.
