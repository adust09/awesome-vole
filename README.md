# Awesome VOLE　[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

VOLE (Vector Oblivious Linear Evaluation) is a fundamental cryptographic primitive that extends Oblivious Linear Evaluation to vectors, enabling efficient secure multi-party computation and zero-knowledge proof systems.

Contributions are welcome! Please read our [contribution guidelines](CONTRIBUTING.md) first.

- [Awesome VOLE　 ](#awesome-vole-)
  - [1. Research Papers](#1-research-papers)
  - [2. Applications](#2-applications)
  - [3. Implementations](#3-implementations)
  - [4. Tutorials and Resources](#4-tutorials-and-resources)

## 1. Research Papers

- **[Compressing Vector OLE](https://eprint.iacr.org/2019/273)** (2019) - Fundamental compression techniques for VOLE with efficiency improvements for practical deployment.

- **[Fast Vector Oblivious Linear Evaluation from Ring Learning with Errors](https://eprint.iacr.org/2020/685)** (2020) - RLWE-based VOLE construction bridging standard assumptions and practical efficiency.

- **[Wolverine: Fast, Scalable, and Communication-Efficient Zero-Knowledge Proofs for Boolean and Arithmetic Circuits](https://eprint.iacr.org/2020/925)** (2020) - Semi-honest VOLE-based ZK protocol with high concrete efficiency based on the LPN assumption.

- **[Mac'n'Cheese: Zero-Knowledge Proofs for Boolean and Arithmetic Circuits with Nested Disjunctions](https://eprint.iacr.org/2020/1410)** (2020) - Efficient ZK proofs for statements with branches where communication is linear only in the largest branch.

- **[Line-Point Zero Knowledge and Its Applications](https://eprint.iacr.org/2020/1446)** (2020) - Foundational protocol for consistency checks with efficient verification of committed values.

- **[QuickSilver: Efficient and Affordable Zero-Knowledge Proofs for Circuits and Polynomials over Any Field](https://eprint.iacr.org/2021/076)** (2021) - Commit-and-prove ZK protocol that processes tens of millions of gates per second with minimal memory requirements.

- **[Mystique: Efficient Conversions for Zero-Knowledge Proofs with Applications to Machine Learning](https://eprint.iacr.org/2021/730)** (2021) - Efficient conversion between Boolean and arithmetic values with seamless integration of different computation types.

- **[Moz$\mathbb{Z}_{2^k}$arella: Efficient Vector-OLE and Zero-Knowledge Proofs Over $\mathbb{Z}_{2^k}$](https://eprint.iacr.org/2022/819)** (2022) - Extension from finite fields to integers enabling integer-based computations and real-world applications.

- **[SoK: Vector OLE-Based Zero-Knowledge Protocols](https://eprint.iacr.org/2023/857)** (2023) - Comprehensive survey of VOLE-based ZK protocols with systematic comparison and analysis.

- **[Publicly Verifiable Zero-Knowledge and Post-Quantum Signatures From VOLE-in-the-Head](https://eprint.iacr.org/2023/996)** (2023) - Transforms designated-verifier protocols to publicly verifiable with only 2x communication overhead.

- **[Code-Based Zero-Knowledge from VOLE-in-the-Head](https://eprint.iacr.org/2024/1414)** (2024) - Applications to code-based cryptography with simpler, faster, and smaller constructions.

- **[LogRobin++: Optimizing Proofs of Disjunctive Statements in VOLE-Based ZK](https://dl.acm.org/doi/10.1007/978-981-96-0935-2_12)** (2024) - Optimization for disjunctive statements with enhanced efficiency for complex logic.

- **[Committed Vector Oblivious Linear Evaluation and Its Applications](https://eprint.iacr.org/2025/1037)** (2025) - VOLE correlations with pre-committed vectors enabling correlations between multiple parties.

## 2. Applications

- **[FAEST Signature Scheme](https://github.com/faest-sign)** - Fast AES-based post-quantum signature from VOLE-in-the-Head with 5.6-6.6kB signatures, 8x-40x faster signing than SPHINCS+, and NIST standardization candidate status.

- **[TLSNotary](https://github.com/tlsnotary/tlsn)** - Protocol for proving TLS session data provenance using VOLE-based Interactive Zero-Knowledge proofs, achieving 100x communication reduction compared to garbled circuits.

- **[zkPass](https://github.com/zkPassOfficial)** - zkTLS oracle protocol for verifiable web private data using VOLE-in-the-Head technology, enabling sub-second ZKP generation in browsers with memory-efficient hybrid approach.

## 3. Implementations

- **[EMP-ZK](https://github.com/emp-toolkit/emp-zk)** - Fast, scalable zero-knowledge proof protocol implementation in C++ supporting Wolverine, QuickSilver, and Mystique protocols with Boolean/arithmetic circuits and polynomial support.

- **[Holonym VOLE ZK Prover](https://github.com/holonym-foundation/vole-zk-prover)** - Very fast and memory-efficient NIZK prover using QuickSilver with VOLE-in-the-Head, featuring Circom circuit adapter and ~300k constraints/second performance.

- **[Actively Secure Vector OLE](https://github.com/NivKonst/Actively-Secure-Vector-OLE)** - Implementation focused on active security guarantees for high-security multi-party computation applications.

- **[Swanky](https://github.com/GaloisInc/swanky)** - Suite of Rust libraries for secure multi-party computation including mac-n-cheese-vole and VOLE-in-the-Head.

## 4. Tutorials and Resources

- **[VOLE-Based ZK - Chainlink Blog](https://blog.chain.link/vole-based-zk/)** - Accessible introduction to VOLE-based ZK with practical applications and benefits.
