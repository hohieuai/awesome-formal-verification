# Awesome Formal Verification [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

A curated collection of formal verification tools, languages, verified systems, research papers, and learning resources for proving that software and hardware behave correctly.

Contributions are welcome; see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contents

- [Getting Started](#getting-started)
- [Theorem Provers](#theorem-provers)
- [SMT / SAT Solvers](#smt--sat-solvers)
- [Program Verification](#program-verification)
- [Model Checkers](#model-checkers)
- [Specification Languages & Frameworks](#specification-languages--frameworks)
- [Hardware Verification](#hardware-verification)
- [Smart Contract Verification](#smart-contract-verification)
- [Verified Systems & Case Studies](#verified-systems--case-studies)
- [AI for Formal Verification](#ai-for-formal-verification)
- [Learning Resources](#learning-resources)
- [Research](#research)
- [Conferences & Events](#conferences--events)

## Getting Started

| If you want to verify             | Start with                                                                            |
| --------------------------------- | ------------------------------------------------------------------------------------- |
| Rust code                         | Kani for automated bounded checking; Verus or Creusot for full functional correctness |
| C code                            | Frama-C with ACSL annotations, or CBMC for bounded model checking                     |
| Distributed systems and protocols | TLA+ with the Learn TLA+ tutorial, then Apalache for symbolic checking                |
| Hardware (RTL)                    | SymbiYosys with the ZipCPU tutorials                                                  |
| Mathematics                       | Lean 4 with Theorem Proving in Lean 4 and Mathlib                                     |
| Programming language theory       | Rocq with Software Foundations, or Agda with PLFA                                     |
| Smart contracts                   | Certora Prover for EVM; Kontrol for Foundry projects                                  |

### Terminology

| Term        | Meaning                                                                                          |
| ----------- | ------------------------------------------------------------------------------------------------ |
| Interactive | The user writes the proof step by step, with tactic support                                      |
| Auto-active | The user writes specifications and invariants; an SMT solver discharges the proofs               |
| Automated   | No annotations are needed beyond the property to check                                           |
| Theories    | Logics a solver accepts; quantifiers and nonlinear integer arithmetic are undecidable in general |
| Language    | The user-facing language, followed by the implementation language when they differ               |

## Theorem Provers

| Name                                     | Description                                                                 | Logic                               | Automation              | Language       | Domain                                            |
| ---------------------------------------- | --------------------------------------------------------------------------- | ----------------------------------- | ----------------------- | -------------- | ------------------------------------------------- |
| [Rocq](https://rocq-prover.org/)         | Proof assistant for interactive development of formal proofs (formerly Coq) | Calculus of Inductive Constructions | Interactive             | Rocq / OCaml   | Software, math, PL theory                         |
| [Lean 4](https://lean-lang.org/)         | Dependently typed theorem prover with fast elaboration                      | Dependent type theory               | Interactive + tactics   | Lean           | Math, software, compilers                         |
| [Isabelle](https://isabelle.in.tum.de/)  | Generic proof assistant with powerful automation (Sledgehammer)             | Higher-order logic                  | Interactive + automated | Isabelle/ML    | Software, math, security                          |
| [Agda](https://github.com/agda/agda)     | Dependently typed functional language and proof assistant                   | Dependent types                     | Interactive             | Agda / Haskell | PL theory, math                                   |
| [HOL4](https://hol-theorem-prover.org/)  | Proof assistant for higher-order logic                                      | HOL                                 | Interactive             | Standard ML    | Compilers (CakeML), ISA and binary code, hardware |
| [Metamath](https://us.metamath.org/)     | Minimalist framework for formalizing mathematics                            | Logic-agnostic (set.mm: ZFC)        | Interactive             | Metamath / C   | Mathematics                                       |
| [F*](https://github.com/FStarLang/FStar) | Dependently typed language for program verification and crypto              | Dependent types                     | SMT-backed              | F*             | Crypto (HACL*), TLS, parsers, systems             |
| [Idris 2](https://idris-lang.org/)       | General-purpose language with dependent types                               | Dependent types                     | Interactive             | Idris          | PL research, theorem proving                      |

## SMT / SAT Solvers

| Name                                                | Description                                                                                      | Input                   | Theories                                                                              | Language   | Typical Use                          |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ----------------------- | ------------------------------------------------------------------------------------- | ---------- | ------------------------------------ |
| [Z3](https://github.com/Z3Prover/z3)                | High-performance SMT solver from Microsoft Research                                              | SMT-LIB                 | Linear and nonlinear arithmetic, bit-vectors, arrays, strings, quantifiers            | C++ / APIs | Program analysis, symbolic execution |
| [cvc5](https://github.com/cvc5/cvc5)                | SMT solver supporting many theories and proof production                                         | SMT-LIB, SyGuS-IF       | Arithmetic, bit-vectors, arrays, strings, sets, quantifiers                           | C++        | Verification, synthesis              |
| [Yices 2](https://github.com/SRI-CSL/yices2)        | Efficient SMT solver for software verification                                                   | SMT-LIB, Yices language | Linear and nonlinear arithmetic (MCSAT), bit-vectors, arrays, uninterpreted functions | C          | BMC, invariant generation            |
| [Bitwuzla](https://github.com/bitwuzla/bitwuzla)    | SMT solver for bit-precise reasoning, successor of Boolector                                     | SMT-LIB, BTOR2          | Bit-vectors, floating-point, arrays, uninterpreted functions                          | C++        | Hardware, low-level code             |
| [Boolector](https://github.com/Boolector/boolector) | SMT solver for bit-vectors, arrays and uninterpreted functions (archived; succeeded by Bitwuzla) | SMT-LIB, BTOR, BTOR2    | Bit-vectors, arrays, uninterpreted functions                                          | C          | Hardware, low-level code             |
| [MiniSat](https://github.com/niklasso/minisat)      | Minimalist SAT solver (unmaintained; widely used as an embeddable reference)                     | CNF                     | Propositional                                                                         | C++        | BMC, planning, scheduling            |
| [Kissat](https://github.com/arminbiere/kissat)      | State-of-the-art CDCL SAT solver                                                                 | CNF                     | Propositional                                                                         | C          | Competition-grade SAT solving        |
| [STP](https://github.com/stp/stp)                   | Simple Theorem Prover for bit-vectors, arrays and floating-point                                 | SMT-LIB                 | Bit-vectors, arrays, floating-point                                                   | C++        | Symbolic execution (KLEE)            |

## Program Verification

| Name                                                            | Description                                                                | Approach                                   | Target Language                             | Automation              | Output                                            |
| --------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------ | ------------------------------------------- | ----------------------- | ------------------------------------------------- |
| [Dafny](https://github.com/dafny-lang/dafny)                    | Verification-aware programming language with built-in verifier             | Deductive                                  | Dafny                                       | Auto-active             | Verified programs                                 |
| [Why3](https://why3.org/)                                       | Platform for deductive program verification via VC generation              | Deductive                                  | WhyML                                       | SMT + provers           | Proof obligations                                 |
| [Frama-C](https://frama-c.com/)                                 | Extensible platform for analyzing C programs                               | Abstract interpretation, deductive         | C                                           | Plugin-dependent        | Annotations, proofs                               |
| [CBMC](https://github.com/diffblue/cbmc)                        | Bounded model checker for C and C++ (Java bytecode via the companion JBMC) | BMC                                        | C, C++                                      | Automated               | Counterexamples                                   |
| [Cameleer](https://github.com/ocaml-gospel/cameleer)            | Deductive verifier for OCaml programs using GOSPEL specs                   | Deductive                                  | OCaml                                       | SMT + interactive       | Proof obligations                                 |
| [Verus](https://github.com/verus-lang/verus)                    | Verification tool for Rust using SMT and linear types                      | Deductive                                  | Rust                                        | Auto-active             | Verified programs                                 |
| [Liquid Haskell](https://ucsd-progsys.github.io/liquidhaskell/) | Refinement types for Haskell programs                                      | Refinement types                           | Haskell                                     | Auto-active             | Type-level proofs                                 |
| [SPARK](https://github.com/AdaCore/spark2014)                   | Ada subset with contracts, verified by the open-source GNATprove           | Deductive                                  | Ada/SPARK                                   | Automated + interactive | Absence of runtime errors, functional correctness |
| [Viper](https://www.pm.inf.ethz.ch/research/viper.html)         | Verification infrastructure for permission-based reasoning                 | Permission-based (implicit dynamic frames) | Viper IVL (front-ends for Rust, Go, Python) | Automated               | Verified heap-manipulating programs               |
| [Prusti](https://github.com/prusti/prusti)                      | Static verifier for Rust based on Viper                                    | Deductive                                  | Rust                                        | Auto-active             | Panic/overflow freedom, functional correctness    |
| [Kani](https://github.com/model-checking/kani)                  | Rust model checker built on CBMC                                           | BMC                                        | Rust                                        | Automated               | Counterexamples                                   |
| [Creusot](https://github.com/creusot-rs/creusot)                | Deductive verifier for Rust using Why3                                     | Deductive                                  | Rust                                        | Auto-active             | Functional correctness                            |

## Model Checkers

| Name                                                | Description                                                                          | Model Type                   | Properties                                | Language    | Domain                         |
| --------------------------------------------------- | ------------------------------------------------------------------------------------ | ---------------------------- | ----------------------------------------- | ----------- | ------------------------------ |
| [TLA+](https://github.com/tlaplus/tlaplus)          | Specification language and model checker for concurrent systems                      | State machines               | Safety, liveness                          | TLA+        | Distributed systems, protocols |
| [Alloy](https://alloytools.org/)                    | Relational modeling language with SAT-based analyzer                                 | Relational                   | Structural, temporal (LTL, since Alloy 6) | Alloy       | Software design, architecture  |
| [SPIN](https://spinroot.com/)                       | Model checker for multi-threaded software and protocols                              | Concurrent processes         | Assertions, LTL, deadlocks, progress      | Promela / C | Concurrent software            |
| [UPPAAL](https://uppaal.org/)                       | Tool for timed automata and real-time systems                                        | Timed automata               | Timed properties                          | UPPAAL      | Real-time, embedded            |
| [PRISM](https://www.prismmodelchecker.org/)         | Probabilistic model checker for stochastic systems                                   | DTMC, CTMC, MDP, PTA, POMDP  | Probabilistic                             | PRISM       | Security, biology, protocols   |
| [nuXmv](https://nuxmv.fbk.eu/)                      | Extension of NuSMV for symbolic model checking of finite- and infinite-state systems | Transition systems           | CTL, LTL, invariants, PSL                 | SMV         | Hardware, software             |
| [Ivy](https://github.com/kenmcmil/ivy)              | Language and tool for interactive verification of distributed protocols              | Transition systems           | Safety, liveness                          | Ivy         | Distributed protocols          |
| [Apalache](https://github.com/apalache-mc/apalache) | Symbolic model checker for TLA+ and Quint specifications                             | State machines (SMT-encoded) | Safety, bounded liveness                  | TLA+, Quint | Distributed systems            |

## Specification Languages & Frameworks

- [K Framework](https://kframework.org/) - Rewrite-based executable semantics framework for defining programming languages and verifying programs.
- [ACSL](https://frama-c.com/html/acsl.html) - ANSI/ISO C Specification Language used by Frama-C and other C verifiers.
- [JML](https://www.openjml.org/) - Java Modeling Language for specifying behavior of Java programs.
- [Gospel](https://ocaml-gospel.github.io/gospel/) - Tool-agnostic behavioral specification language for OCaml, used for deductive verification and runtime checking.
- [Sail](https://github.com/rems-project/sail) - Language for specifying instruction set architectures (ISAs).

## Hardware Verification

| Name                                                    | Description                                                      | Approach                                   | Input                                                    | Automation     | Domain        |
| ------------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------ | -------------------------------------------------------- | -------------- | ------------- |
| [SymbiYosys](https://github.com/YosysHQ/sby)            | Front-end for Yosys-based formal hardware verification flows     | BMC, k-induction, PDR/IC3, cover, liveness | Verilog, SystemVerilog (full SVA and VHDL via Tabby CAD) | Automated      | RTL designs   |
| [Yosys](https://github.com/YosysHQ/yosys)               | Open synthesis suite with formal verification support            | SMT, SAT                                   | Verilog, SystemVerilog (synthesizable subset)            | Semi-automated | RTL, netlists |
| [riscv-formal](https://github.com/YosysHQ/riscv-formal) | Reusable formal verification framework for RISC-V CPU designs    | BMC, induction                             | Verilog, SystemVerilog (SVA)                             | Semi-automated | CPU cores     |
| [ABC](https://github.com/berkeley-abc/abc)              | System for sequential logic synthesis and formal verification    | CEC, SEC, BMC, PDR/IC3, interpolation      | AIGER, BLIF, BENCH, structural Verilog                   | Automated      | Gate-level    |
| [EBMC](https://www.cprover.org/ebmc/)                   | Model checker for hardware designs (Verilog, SystemVerilog, SMV) | BMC, k-induction, IC3, BDD                 | Verilog, SystemVerilog, SMV                              | Automated      | RTL           |

### Simulation & Testbenches

- [cocotb](https://www.cocotb.org/) - Python-based testbench framework for HDL simulators.
- [Verilator](https://www.veripool.org/verilator/) - Fast Verilog simulator with assertion and coverage support.
- [chiselverify](https://github.com/chiselverify/chiselverify) - UVM-like verification library for Chisel HDL.

## Smart Contract Verification

- [Certora Prover](https://github.com/Certora/CertoraProver) - Formal verification tool for EVM, Solana, and Stellar smart contracts, with specifications written in CVL (open source since 2025).
- [Slither](https://github.com/crytic/slither) - Static analysis framework for Solidity, often used alongside formal verification workflows.
- [Mythril](https://github.com/ConsenSysDiligence/mythril) - Security analysis tool for EVM bytecode using symbolic execution.
- [Halmos](https://github.com/a16z/halmos) - Symbolic testing tool for EVM smart contracts, compatible with Foundry tests.
- [HEVM](https://github.com/argotorg/hevm) - Symbolic execution engine for EVM bytecode.
- [Solc-verify](https://github.com/SRI-CSL/solidity) - Solidity compiler extension for SMT-based verification via Boogie (supports Solidity up to 0.7; inactive since 2021).
- [VeriSol](https://github.com/microsoft/verisol) - Formal correctness analyzer for Solidity via Boogie translation (archived; no longer actively maintained since 2021).
- [Kontrol](https://github.com/runtimeverification/kontrol) - Formal verification for Solidity using K Framework semantics (KEVM) and Foundry.
- [Verity](https://github.com/lfglabs-dev/verity) - Lean 4 framework for formally specified and verified smart contracts.
- [Move Prover (Aptos)](https://github.com/aptos-labs/aptos-core/tree/main/third_party/move/move-prover) - Formal verification for Move smart contracts on Aptos.
- [Sui Prover](https://github.com/asymptotic-code/sui-prover) - Formal verification tool for Move smart contracts on Sui, built on Boogie and Z3.

## Verified Systems & Case Studies

- [seL4](https://sel4.systems/) - Microkernel with end-to-end proof of implementation correctness and security enforcement.
- [CompCert](https://compcert.org/) - Formally verified optimizing compiler for almost all of the C language (ISO C 2011).
- [CertiKOS](https://flint.cs.yale.edu/certikos/) - Certified concurrent OS kernel with verified C compiler toolchain.
- [Ironclad / IronFleet](https://github.com/microsoft/Ironclad) - Verified distributed systems and applications in Dafny (Microsoft Research).
- [miTLS](https://github.com/project-everest/mitls-fstar) - Partially verified reference implementation of TLS 1.3 in F* (verified record layer).
- [HACMS](https://www.darpa.mil/research/programs/high-assurance-cyber-military-systems) - Completed DARPA program that applied formal methods, including seL4, to high-assurance software for unmanned vehicles.
- [HACL* / EverCrypt](https://github.com/hacl-star/hacl-star) - Verified cryptographic library in F* (HACL*) with the EverCrypt provider that combines it with Vale verified assembly.
- [Vale](https://github.com/project-everest/vale) - Tool for generating verified assembly language.

## AI for Formal Verification

### Libraries & Tools

- [Mathlib](https://github.com/leanprover-community/mathlib4) - Community library of formalized mathematics for Lean 4, and the main training corpus for AI provers.
- [LeanDojo](https://github.com/lean-dojo/LeanDojo) - Toolkit for extracting training data from Lean projects and letting models interact with Lean programmatically.
- [Lean Copilot](https://github.com/lean-dojo/LeanCopilot) - Runs LLMs inside Lean 4 to suggest tactics, search for proofs, and select premises.

### Models & Results

- [OpenAI math collection](https://github.com/openai/math) - Mathematical manuscripts produced by an internal OpenAI model on open research problems, with Lean formalizations for part of the results; unformalized results are not independently verified.
- [DeepSeek-Prover-V2](https://github.com/deepseek-ai/DeepSeek-Prover-V2) - Open-weight language model for theorem proving in Lean 4, trained with reinforcement learning on subgoal decomposition.
- [AlphaProof](https://deepmind.google/blog/ai-solves-imo-problems-at-silver-medal-level/) - DeepMind's reinforcement-learning system for proving competition problems in Lean (silver-medal level at IMO 2024).

### Benchmarks

- [miniF2F](https://github.com/openai/miniF2F) - Olympiad-level formal mathematics benchmark in Lean, Isabelle, and Metamath (archived; still the standard reference set).
- [PutnamBench](https://github.com/trishullab/PutnamBench) - Putnam competition problems formalized in Lean 4, Isabelle, and Rocq.
- [DafnyBench](https://github.com/sun-wendy/DafnyBench) - Benchmark of Dafny programs for evaluating LLMs on software verification.

## Learning Resources

### Books

- [Software Foundations](https://softwarefoundations.cis.upenn.edu/) - Interactive textbook series on Coq/Rocq and PL theory (Pierce et al.).
- [Certified Programming with Dependent Types](http://adam.chlipala.net/cpdt/) - Practical engineering with Rocq/Coq (Adam Chlipala).
- [The Little Prover](https://mitpress.mit.edu/books/little-prover) - Gentle introduction to inductive proofs (Friedman & Eastlund).
- [Concrete Semantics](http://concrete-semantics.org/) - Semantics course using Isabelle (Nipkow & Klein).
- [Programming Language Foundations in Agda](https://plfa.github.io/) - Introduction to programming language theory using the proof assistant Agda (Wadler, Kokke & Siek).
- [Homotopy Type Theory: Univalent Foundations of Mathematics](https://homotopytypetheory.org/book/) - Research-level text on homotopy type theory and univalent foundations (The Univalent Foundations Program, 2013).

### Courses & Tutorials

- [DeepSpec Summer School](https://www.youtube.com/channel/UC5yB0ZRgc4A99ttkwer-dDw) - Lectures on deep specification and interactive theorem proving.
- [Theorem Proving in Lean 4](https://lean-lang.org/theorem_proving_in_lean4/) - Official Lean 4 tutorial.
- [Learn TLA+](https://learntla.com/) - Practical introduction to TLA+ for system design.
- [Dan Gisselquist's Formal Verification Blog](https://zipcpu.com/formal/formal.html) - Hands-on FPGA/RTL formal verification tutorials.
- [Software Foundations in Coq (Pierce, OPLSS 2012)](https://www.cs.uoregon.edu/research/summerschool/summer12/curriculum.html) - Video lectures from the Oregon Programming Languages Summer School.

## Research

- [Propositions as Types](https://homepages.inf.ed.ac.uk/wadler/papers/propositions-as-types/propositions-as-types.pdf) - Accessible survey of the Curry–Howard correspondence between proofs and programs (Wadler, CACM 2015).
- [An Axiomatic Basis for Computer Programming](https://doi.org/10.1145/363235.363259) - Introduces Hoare logic for program correctness (Hoare, CACM 1969).
- [seL4: Formal Verification of an OS Kernel](https://sel4.systems/Research/pdfs/sel4-formal-verification-os-kernel.pdf) - First machine-checked proof of functional correctness of a general-purpose OS kernel, from abstract specification down to C (Klein et al., SOSP 2009).
- [Formal Verification of a Realistic Compiler](https://xavierleroy.org/publi/compcert-CACM.pdf) - Overview of CompCert, a C compiler with a machine-checked proof of semantic preservation (Leroy, CACM 2009).
- [A Calculus of Mobile Processes, Part I](https://www.lfcs.inf.ed.ac.uk/reports/89/ECS-LFCS-89-85/) - Pi-calculus foundation for reasoning about concurrent systems (Milner, Parrow & Walker, 1989).
- [Model Checking](https://mitpress.mit.edu/9780262038836/model-checking/) - Foundational textbook on model checking (Clarke, Grumberg & Peled, MIT Press 1999; 2nd edition with Kroening & Veith, 2018).
- [A Survey of Smart Contract Formal Specification and Verification](https://arxiv.org/abs/2008.02712) - Survey of formal methods for smart contracts (Tolmach et al., ACM Computing Surveys 2021).
- [PropertyGPT: LLM-driven Formal Verification of Smart Contracts through Retrieval-Augmented Property Generation](https://www.ndss-symposium.org/ndss-paper/propertygpt-llm-driven-formal-verification-of-smart-contracts-through-retrieval-augmented-property-generation/) - Retrieval-augmented property generation for contract verification (Liu et al., NDSS 2025).
- [Olympiad-level Formal Mathematical Reasoning with Reinforcement Learning](https://doi.org/10.1038/s41586-025-09833-y) - The AlphaProof paper: reinforcement learning with a language model for theorem proving in Lean (Hubert et al., Nature 2025).

## Conferences & Events

- [CAV](https://i-cav.org/) - International Conference on Computer-Aided Verification.
- [FM](https://www.fmeurope.org/) - International Symposium on Formal Methods (Formal Methods Europe).
- [ITP](https://itp-conference.github.io/) - International Conference on Interactive Theorem Proving.
- [CPP](https://sigplan.org/Conferences/CPP/) - Certified Programs and Proofs (co-located with POPL).
- [TACAS](https://tacas.info/) - Tools and Algorithms for the Construction and Analysis of Systems.
- [FMCAD](https://www.fmcad.org/) - Formal Methods in Computer-Aided Design.
- [FMBC](https://fmbc.gitlab.io/) - Formal Methods for Blockchains workshop.
- [ORConf](https://fossi-foundation.org/orconf/) - Open Source Digital Design Conference.

## Related Lists

- [awesome-formal-verification (ElNiak)](https://github.com/ElNiak/awesome-formal-verification) - Comprehensive list covering software and hardware verification.
- [awesome-open-hardware-verification](https://github.com/ben-marshall/awesome-open-hardware-verification) - Open-source hardware verification tools and flows.
- [ethereum_formal_verification_overview](https://github.com/leonardoalt/ethereum_formal_verification_overview) - Overview of formal verification tools for Ethereum smart contracts.
- [Formal methods (Wikipedia)](https://en.wikipedia.org/wiki/Formal_methods) - Encyclopedia overview of formal methods and verification.
