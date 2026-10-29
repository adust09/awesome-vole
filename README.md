# Awesome VOLE　[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

VOLE (Vector Oblivious Linear Evaluation) is a fundamental cryptographic primitive that extends Oblivious Linear Evaluation to vectors, enabling efficient secure multi-party computation and zero-knowledge proof systems.

Contributions are welcome! Please read our [contribution guidelines](CONTRIBUTING.md) first.

- [Awesome VOLE　 ](#awesome-vole-)
  - [1. Research Papers](#1-research-papers)
    - [1.1 VOLE and PCG Constructions](#11-vole-and-pcg-constructions)
    - [1.2 Security of LPN and RSD Assumptions](#12-security-of-lpn-and-rsd-assumptions)
    - [1.3 VOLE-based Zero-Knowledge Proofs](#13-vole-based-zero-knowledge-proofs)
    - [1.4 VOLE-in-the-Head and Post-Quantum Signatures](#14-vole-in-the-head-and-post-quantum-signatures)
    - [1.5 FAEST Implementation and Physical Security](#15-faest-implementation-and-physical-security)
    - [1.6 PSI, OPRF and MPC Applications](#16-psi-oprf-and-mpc-applications)
  - [2. Applications](#2-applications)
  - [3. Implementations](#3-implementations)
  - [4. Tutorials and Resources](#4-tutorials-and-resources)

## 1. Research Papers

Years follow the IACR ePrint year; the publication venue is mentioned where the ePrint page lists one.

### 1.1 VOLE and PCG Constructions

- **[Compressing Vector OLE](https://eprint.iacr.org/2019/273)** (2019) - CCS 2018 paper constructing VOLE generators with sublinear communication from function secret sharing for multi-point functions and LPN-style assumptions over large fields.

- **[Efficient Pseudorandom Correlation Generators: Silent OT Extension and More](https://eprint.iacr.org/2019/448)** (2019) - CRYPTO 2019 paper introducing practical pseudorandom correlation generators (PCGs) for silent OT extension, VOLE and multiparty correlations.

- **[Fast Vector Oblivious Linear Evaluation from Ring Learning with Errors](https://eprint.iacr.org/2020/685)** (2020) - VOLE protocol based on the standard RLWE assumption with concrete efficiency comparable to the fastest coding-based VOLE protocols, extending naturally to batch OLE.

- **[Ferret: Fast Extension for coRRElated oT with small communication](https://eprint.iacr.org/2020/924)** (2020) - CCS 2020 LPN-based correlated OT extension with sublinear communication, at least 9x faster than the prior PCG-based protocol on networks above 50 Mbps.

- **[Silver: Silent VOLE and Oblivious Transfer from Hardness of Decoding Structured LDPC Codes](https://eprint.iacr.org/2021/1150)** (2021) - CRYPTO 2021 silent VOLE/OT protocol using structured LDPC codes that generates 10 million random OTs in about 300 ms on one core (the code's minimum distance was later shown to be problematic by the Expand-Convolute paper).

- **[Correlated Pseudorandomness from Expand-Accumulate Codes](https://eprint.iacr.org/2022/1014)** (2022) - CRYPTO 2022 PCG design for OT and VOLE based on expand-accumulate codes, which apply a sparse expander and then a prefix sum.

- **[SoftSpokenOT: Quieter OT Extension From Small-Field Silent VOLE in the Minicrypt Model](https://eprint.iacr.org/2022/192)** (2022) - CRYPTO 2022 OT extension built from small-field silent VOLE that improves on IKNP using only Minicrypt assumptions.

- **[Moz$\mathbb{Z}_{2^k}$arella: Efficient Vector-OLE and Zero-Knowledge Proofs Over $\mathbb{Z}_{2^k}$](https://eprint.iacr.org/2022/819)** (2022) - CRYPTO 2022 VOLE extension and ZK proof system (QuarkSilver) over the rings $\mathbb{Z}_{2^k}$, generating 13-50 million VOLEs per second for 64- to 256-bit rings.

- **[Half-Tree: Halving the Cost of Tree Expansion in COT and DPF](https://eprint.iacr.org/2022/1431)** (2022) - EUROCRYPT 2023 optimization that halves the GGM-tree cost in COT and sVOLE (and in DPF/DCF) protocols.

- **[Expand-Convolute Codes for Pseudorandom Correlation Generators from LPN](https://eprint.iacr.org/2023/882)** (2023) - CRYPTO 2023 LPN-friendly codes whose convolution step greatly increases minimum distance, giving about 3x faster PCGs for OT and VOLE at comparable security.

- **[Highly Efficient Server-Aided Multiparty Subfield VOLE Distribution Protocol](https://eprint.iacr.org/2025/029)** (2025) - Server-aided distribution of random subfield VOLE in three- and four-party honest-majority settings with lower communication and storage.

- **[Stationary Syndrome Decoding for Improved PCGs](https://eprint.iacr.org/2025/295)** (2025) - CRYPTO 2025 PCG technique based on a stationary variant of syndrome decoding that improves running time by about 1.5x or reduces communication by 6-18x.

- **[Committed Vector Oblivious Linear Evaluation and Its Applications](https://eprint.iacr.org/2025/1037)** (2025) - CCS 2025 notion of committed VOLE, letting a party holding a pre-committed vector generate VOLE correlations with multiple parties, applied to ZK and consistent-input PSI.

- **[Dory: Streaming PCG with Small Memory](https://eprint.iacr.org/2025/1660)** (2025) - IEEE S&P 2026 malicious streaming PCG for subfield VOLE and COT that matches Ferret-level performance while cutting memory from hundreds of MB to about 20 MB.

- **[Two-party ECDSA Signing at Constant Communication Overhead](https://eprint.iacr.org/2025/1813)** (2025) - Two-party ECDSA with bandwidth linear in the security parameter, enabled by a new PCF for VOLE over a large ring from one-way functions alone.

- **[Block-Accumulate Codes: Accelerated Linear Codes for PCGs and ZK](https://eprint.iacr.org/2025/1828)** (2025) - CRYPTO 2026 linear codes that speed up PCG encoding by 2.5x on CPU and 15x on GPU (projected 200+ million OTs per second) and also accelerate the Blaze ZK scheme.

- **[Faster Pseudorandom Correlation Generators via Walsh-Hadamard Transform](https://eprint.iacr.org/2026/196)** (2026) - CRYPTO 2026 PCG for (V)OLE reaching over 5 million VOLEs per second over a 64-bit prime field, about 4x faster than EA- or EC-code PCGs.

- **[Compressing Correlations via Secret Replication: PCFs from Symmetric Cryptography](https://eprint.iacr.org/2026/1355)** (2026) - General blueprint for PCFs from symmetric cryptography that re-derives two-party small-domain VOLE/subfield-VOLE PCFs and yields new multiparty ones.

- **[LogVOLE: Succinct and Efficient Chosen-Input VOLE for ZK and Beyond](https://eprint.iacr.org/2026/925)** (2026) - CCS 2026 chosen-input VOLE protocol that avoids sending a linear-size derandomization vector, with a GPU implementation processing over 500 million $\mathbb{Z}_p$ correlations per second.

- **[Subring VOLE over Galois Rings with Applications to ZK over $\mathbb{Z}_{p^k}$](https://eprint.iacr.org/2026/1864)** (2026) - ASIACRYPT 2026 subring VOLE over Galois rings yielding ZK over $\mathbb{Z}_{p^k}$ with one subring element per multiplication gate and support for arbitrary low-degree relations.

- **[Pairing-based Succinct Half-Chosen VOLE](https://eprint.iacr.org/2026/1922)** (2026) - Pairing-based succinct non-interactive half-chosen VOLE, including a designated-receiver variant with only 3 group elements of online communication.

- **[Efficient Pseudorandom Correlation Generators over Binary Extension Fields and More](https://eprint.iacr.org/2026/1940)** (2026) - ASIACRYPT 2026 nearly linear-time PCGs over binary extension fields producing about 5 million VOLEs per second over $\mathbb{F}_{2^{128}}$, faster than EA, BA and EC code-based PCGs.

- **[New Pseudorandom Correlation Functions and Exponent VRFs from DCR](https://eprint.iacr.org/2026/2030)** (2026) - ASIACRYPT 2026 first PCFs for COT and VOLE over $\mathbb{Z}_M$ for arbitrary $M$ from the DCR assumption, used to build a designated-verifier exponent VRF.

- **[Batch IT-MAC: Program the Randomness in Succinct VOLE](https://eprint.iacr.org/2026/2159)** (2026) - Succinct batch IT-MACs (VOLE with a key fixed in advance) from DCR or LWE, with applications to constrained PRFs, 2-message 2PC and succinct ZK.

- **[Firebolt: Fast, Lightweight, Malicious Non-Interactive Vector-OLE](https://eprint.iacr.org/2026/2549)** (2026) - ASIACRYPT 2026 maliciously secure Paillier-based non-interactive VOLE (535 bytes and about 5 ms per entry) used to build a concurrently secure two-round two-party ECDSA.

### 1.2 Security of LPN and RSD Assumptions

- **[A Hybrid Algorithm for the Regular Syndrome Decoding Problem](https://eprint.iacr.org/2025/1284)** (2025) - ASIACRYPT 2025 hybrid ISD/algebraic attack on RSD that lowers Wolverine's 128-bit target to about 111 bits and Ferret slightly below 128 bits.

- **[AGB 2.0: Refined Algebraic Attack against Regular Syndrome Decoding for PCG Applications](https://eprint.iacr.org/2025/1476)** (2025) - Refined algebraic (AGB) attack on RSD with an asymptotic analysis of parameter regimes relevant to PCGs.

- **[Regular Syndrome Decoding Is Easier Than Previously Estimated](https://eprint.iacr.org/2026/2563)** (2026) - New RSD cryptanalysis placing at least one parameter set of Ferret, Wolverine and committed VOLE below its 128-bit target, with losses approaching 67 bits.

### 1.3 VOLE-based Zero-Knowledge Proofs

- **[Wolverine: Fast, Scalable, and Communication-Efficient Zero-Knowledge Proofs for Boolean and Arithmetic Circuits](https://eprint.iacr.org/2020/925)** (2020) - IEEE S&P 2021 VOLE-based ZK protocol for Boolean and arithmetic circuits with an improved maliciously secure sVOLE protocol.

- **[Mac'n'Cheese: Zero-Knowledge Proofs for Boolean and Arithmetic Circuits with Nested Disjunctions](https://eprint.iacr.org/2020/1410)** (2020) - CRYPTO 2021 VOLE-based ZK whose communication for disjunctions grows only with the largest branch.

- **[Line-Point Zero Knowledge and Its Applications](https://eprint.iacr.org/2020/1446)** (2020) - Introduces line-point zero knowledge (LPZK), where the witness is encoded as an affine line queried at one random point, and applies it to reusable non-interactive secure computation from VOLE.

- **[QuickSilver: Efficient and Affordable Zero-Knowledge Proofs for Circuits and Polynomials over Any Field](https://eprint.iacr.org/2021/076)** (2021) - CCS 2021 VOLE-based ZK for circuits and polynomials over any field, proving a 1024x1024 matrix multiplication in 10 seconds with 1 GB of memory.

- **[Mystique: Efficient Conversions for Zero-Knowledge Proofs with Applications to Machine Learning](https://eprint.iacr.org/2021/730)** (2021) - USENIX Security 2021 conversions between arithmetic and Boolean values and between committed and authenticated values in VOLE-based ZK, enabling ZK inference on ResNet-101.

- **[AntMan: Interactive Zero-Knowledge Proofs with Sublinear Communication](https://eprint.iacr.org/2022/566)** (2022) - CCS 2022 first VOLE-based ZK protocol with sublinear communication for arbitrary circuits ($O(|C|^{3/4})$).

- **[SoK: Vector OLE-Based Zero-Knowledge Protocols](https://eprint.iacr.org/2023/857)** (2023) - Survey of recent developments in practical VOLE-based zero-knowledge proofs of knowledge.

- **[Batchman and Robin: Batched and Non-batched Branching for Interactive ZK](https://eprint.iacr.org/2023/1257)** (2023) - CCS 2023 VOLE-based ZK for disjunctions that improves over Mac'n'Cheese by up to 6x and over QuickSilver by up to 70x for batched arithmetic disjunctions.

- **[An Efficient ZK Compiler from SIMD Circuits to General Circuits](https://eprint.iacr.org/2023/1610)** (2023) - Journal of Cryptology 2024 compiler from SIMD ZK to general circuits that, applied to AntMan, reduces communication from $O(C^{3/4})$ to $O(C^{1/2})$.

- **[Tight ZK CPU: Batched ZK Branching with Cost Proportional to Evaluated Instruction](https://eprint.iacr.org/2024/456)** (2024) - CCS 2024 VOLE-based ZK CPU whose cost scales with the executed instruction rather than the whole instruction set.

- **[LogRobin++: Optimizing Proofs of Disjunctive Statements in VOLE-Based ZK](https://eprint.iacr.org/2024/1427)** (2024) - ASIACRYPT 2024 disjunction proof with up to 170x less communication than Robin.

- **[Interactive Line-Point Zero-Knowledge with Sublinear Communication and Linear Computation](https://eprint.iacr.org/2024/1431)** (2024) - ASIACRYPT 2024 interactive LPZK achieving sublinear communication while keeping linear prover computation.

- **[JesseQ: Efficient Zero-Knowledge Proofs for Circuits over Any Field](https://eprint.iacr.org/2025/533)** (2025) - IEEE S&P 2025 VOLE-based ZK that improves on QuickSilver by 40-200% for inner products, matrix multiplication and lattice problems.

- **[Justvengers: Batched VOLE ZK Disjunctions in $\mathcal{O}(R{+}B{+}C)$ Communication](https://eprint.iacr.org/2025/936)** (2025) - TCC 2025 batched disjunction protocol using AHE and VOLE with $O(R+B+C)$ communication.

- **[Succinct Line-Point Zero-Knowledge Arguments from Homomorphic Secret Sharing](https://eprint.iacr.org/2025/1866)** (2025) - ASIACRYPT 2025 succinct LPZK arguments from HSS, giving a new route to designated-verifier zkSNARKs.

- **[ZKBoost: Zero-Knowledge Verifiable Training for XGBoost](https://eprint.iacr.org/2026/202)** (2026) - Zero-knowledge proof of XGBoost training with a VOLE-based instantiation and a fixed-point XGBoost variant.

- **[RainHash2.0: Hardware- and Arithmetization-friendly Hash Function](https://eprint.iacr.org/2026/1441)** (2026) - Cryptographic permutation defined over binary extension fields, targeting $\mathbb{F}_{2^n}$-native proof systems such as Binius and VOLEitH.

- **[PRISM: Efficient zkSNARKs for RNS-Based Homomorphic Encryption](https://eprint.iacr.org/2026/1956)** (2026) - CCS 2026 verifiable homomorphic encryption for RNS-based schemes that uses VOLE correlations to add zero knowledge.

- **[Wasp: Succinct Non-Interactive Zero-Knowledge Proofs from VOLE](https://eprint.iacr.org/2026/1988)** (2026) - CCS 2026 succinct VOLE-based NIZK with sub-millisecond verification and 122 KB proofs.

### 1.4 VOLE-in-the-Head and Post-Quantum Signatures

- **[Publicly Verifiable Zero-Knowledge and Post-Quantum Signatures From VOLE-in-the-Head](https://eprint.iacr.org/2023/996)** (2023) - CRYPTO 2023 paper introducing VOLE-in-the-Head, which makes VOLE-based ZK publicly verifiable, and the AES-based FAEST signature (5.6-6.6 kB signatures at the 128-bit level).

- **[ReSolveD: Shorter Signatures from Regular Syndrome Decoding and VOLE-in-the-Head](https://eprint.iacr.org/2024/040)** (2024) - PKC 2024 RSD-based signature in the VOLEitH framework with 3.99 KB signatures.

- **[Faster VOLEitH Signatures from All-but-One Vector Commitment and Half-Tree](https://eprint.iacr.org/2024/097)** (2024) - ACISP 2025 faster all-but-one vector commitment based on Half-Tree that makes FAEST 1.11-1.57x faster.

- **[Efficient Multi-instance Vector Commitment and Application to Post-quantum Signatures](https://eprint.iacr.org/2024/465)** (2024) - ACISP 2025 multi-instance vector commitment for MPCitH/VOLEitH signatures, plus a VOLEitH MQ signature with 3.1-3.6 KB signatures.

- **[One Tree to Rule Them All: Optimizing GGM Trees and OWFs for Post-Quantum Signatures](https://eprint.iacr.org/2024/490)** (2024) - ASIACRYPT 2024 GGM-tree and OWF optimizations for VOLEitH signatures, yielding FAESTER, KuMQuat and MandaRain.

- **[Code-Based Zero-Knowledge from VOLE-in-the-Head and Their Applications: Simpler, Faster, and Smaller](https://eprint.iacr.org/2024/1414)** (2024) - ASIACRYPT 2024 code-based ZK from VOLEitH with a signature whose "signature + public key" size is 3.05 KB.

- **[VOLE-in-the-head signatures from Subfield Bilinear Collisions](https://eprint.iacr.org/2024/1537)** (2024) - ASIACRYPT 2025 VOLEitH signature from the subfield bilinear collision problem that introduces the correlated GGM forest.

- **[Post-Quantum Threshold Ring Signature Applications from VOLE-in-the-Head](https://eprint.iacr.org/2025/113)** (2025) - Post-quantum threshold and linkable ring signatures from AES one-wayness and VOLEitH.

- **[Shorter VOLE-in-the-Head-based Signatures from Vector Semi-Commitment](https://eprint.iacr.org/2025/1077)** (2025) - ACM CCS 2026 adaptation of vector semi-commitment to VOLEitH for shorter signatures, plus a forgery attack on a variant of the SBC signature.

- **[Representations of Elementary Vectors in VOLE-in-the-head-based Schemes](https://eprint.iacr.org/2025/1336)** (2025) - New elementary-vector representations that shrink VOLEitH signatures based on RSD (SDitH) and PKP.

- **[BACON: An Improved Vector Commitment Construction with Applications to Signatures](https://eprint.iacr.org/2025/1411)** (2025) - Batched all-but-one vector commitment with aborts built from a large correlated GGM tree, with FAEST version 2 as an application.

- **[VOLE-in-the-Head Signatures Based on the Linear Code Equivalence Problem](https://eprint.iacr.org/2025/1436)** (2025) - Cryptography and Communications paper giving VOLE-friendly proofs of knowledge for code equivalence that are faster than LESS.

- **[Concretely Efficient Blind Signatures Based on VOLE-in-the-Head Proofs and the MAYO Trapdoor](https://eprint.iacr.org/2026/109)** (2026) - Post-quantum blind signatures (6.7 KB) from VOLEitH and MAYO, including the first VOLEitH proof for SHA-3.

- **[Shorter, Tighter, FAESTer: Optimizations and Improved (QROM) Analysis for VOLE-in-the-Head Signatures](https://eprint.iacr.org/2026/164)** (2026) - CRYPTO 2025 optimizations and a new QROM security analysis and Fiat-Shamir transform for FAEST.

- **[Efficient, UC-secure and Publicly Auditable MPC from OLE & VOLE-in-the-head](https://eprint.iacr.org/2026/337)** (2026) - Publicly auditable MPC using a VOLEitH-based homomorphic commitment that needs only random oracle calls.

- **[Cryptanalysis of the Subfield Bilinear Collision Problem](https://eprint.iacr.org/2026/916)** (2026) - Algebraic cryptanalysis of the SBC problem underlying recent VOLEitH signatures, without breaking the proposed parameters.

- **[Lynx: Symmetric Primitive for Shorter and Faster VOLE-in-the-Head Signatures](https://eprint.iacr.org/2026/1099)** (2026) - VOLEitH-friendly symmetric primitive whose signature Lynxer reduces "public key + signature" size by 25-51% versus Rainier, AIMer and FAESTv2.

- **[SM4th and uBlockith: VOLE-based Post-Quantum Signature Schemes from Chinese Block Ciphers](https://eprint.iacr.org/2026/1506)** (2026) - FAEST-style VOLEitH signatures instantiated with the SM4 and uBlock block ciphers.

- **[AES-Based Grinding for MPC-in-the-Head Signatures](https://eprint.iacr.org/2026/1625)** (2026) - AES-based grinding (proof of work in Fiat-Shamir) with a security proof, proposed as a faster alternative to Keccak-based grinding in FAEST, MQOM and SDitH.

- **[Elementary-Vector Modeling for Shorter VOLE-Based Signatures from SD and PKP](https://eprint.iacr.org/2026/1722)** (2026) - Optimized VOLE-based SD and PKP signatures (3,496 and 3,341 bytes) that are smaller than SDitH v2.0 and PERK v2.2.

- **[Practical Adaptor Signatures for NP from Online/Offline NIZK](https://eprint.iacr.org/2026/2155)** (2026) - ASIACRYPT 2026 adaptor signatures for NP instantiated with VOLEitH and FAEST, with 11.6 kB signatures.

- **[Practical Null-Branch Witness Attacks on In-the-Head Signatures](https://eprint.iacr.org/2026/2235)** (2026) - Attacks exploiting relation encodings that accept witnesses that are not OWF preimages, affecting AIMer and vulnerable Lynxer variants.

- **[PoP! Goes the VOLE: Shorter Proofs of Possession for KEM Certificates](https://eprint.iacr.org/2026/2375)** (2026) - VOLEitH-based proofs of possession for KEM (HQC) certificates with smaller proofs.

- **[edaBits in the Exponent (edaBitE) and Issuer-Hiding Blind Signatures from ML-DSA and VOLE-in-the-Head](https://eprint.iacr.org/2026/2473)** (2026) - Issuer-hiding blind signatures that prove knowledge of an ML-DSA signature with VOLEitH, using a new binary/prime-field consistency check.

### 1.5 FAEST Implementation and Physical Security

- **[Side-Channel and Fault Injection Attacks on VOLEitH Signature Schemes: A Case Study of Masked FAEST](https://eprint.iacr.org/2025/378)** (2025) - TCHES 2026 side-channel and fault attacks on masked FAEST that target VOLEitH-specific components, with countermeasures.

- **[FAEST for Memory-Constrained Devices](https://eprint.iacr.org/2025/1261)** (2025) - Compact constant-time FAEST v1.1 implementation for Arm Cortex-M4 that recomputes VOLEs on demand, cutting memory by at least an order of magnitude.

- **[Accelerating FAEST Signatures on ARM: NEON SIMD AES and Parallel VOLE Optimization](https://eprint.iacr.org/2026/499)** (2026) - ARM NEON-optimized FAEST with up to 330x speedups over the pure-C reference.

- **[Accelerating FAEST Signing on GPU via Fused AES Constraint Generation and Batched Leaf Hashing](https://eprint.iacr.org/2026/1409)** (2026) - GPU acceleration of FAEST signing by fusing AES constraint generation and batching leaf hashing.

- **[GPU-Assisted FAEST v3 Signing: Challenge Grinding and CPU–GPU Pipelining](https://eprint.iacr.org/2026/2355)** (2026) - GPU-assisted FAEST v3 signing with challenge grinding on the GPU and a CPU–GPU pipeline.

- **[FAEST on GPUs: Addressing Field Multiplication as a Bottleneck](https://eprint.iacr.org/2026/2489)** (2026) - GPU FAEST implementation showing that native carry-less multiplication is key to OWF proving throughput.

- **[DPA-style Attacks on VOLE-in-the-Head Signature Schemes](https://eprint.iacr.org/2026/2519)** (2026) - Six classes of DPA-style attacks on FAEST and SDitH, validated on ARM Cortex-M4 devices.

- **[Enjoy FAEST on Hardware: Efficient and Novel Hardware Acceleration of Emerging Post-Quantum Digital Signature Scheme FAEST](https://eprint.iacr.org/2026/2525)** (2026) - First hardware accelerator for FAEST.

### 1.6 PSI, OPRF and MPC Applications

- **[VOLE-PSI: Fast OPRF and Circuit-PSI from Vector-OLE](https://eprint.iacr.org/2021/266)** (2021) - EUROCRYPT 2021 batched OPRF from VOLE and PaXoS, giving PSI and circuit-PSI with $O(n)$ cost.

- **[Blazing Fast PSI from Improved OKVS and Subfield VOLE](https://eprint.iacr.org/2022/320)** (2022) - CCS 2022 semi-honest and malicious PSI from an improved OKVS and subfield VOLE, several times faster than prior work.

- **[PICS: Private Intersection over Committed (and reusable) Sets](https://eprint.iacr.org/2025/1071)** (2025) - USENIX Security 2026 PSI over committed, reusable sets that prevents inconsistent inputs across sessions.

- **[VCR: Fast Private Set Intersection with Improved VOLE and CRT-Batching](https://eprint.iacr.org/2025/1114)** (2025) - OLE-based PSI using improved VOLE generation and CRT batching, with large communication and runtime gains over Kerschbaum et al. (NDSS 2023).

- **[Fuzzy Private Set Intersection from VOLE](https://eprint.iacr.org/2025/911)** (2025) - ASIACRYPT 2025 VOLE-based fuzzy PSI, including the first infinity-distance fuzzy PSI without assumptions on the point sets.

- **[Efficient Fuzzy Labeled PSI from Vector Ring-OLE](https://eprint.iacr.org/2025/1470)** (2025) - CANS 2025 fuzzy labeled PSI from vector ring-OLE with up to 4.6x less communication than prior work.

- **[Faster Than Ever: A New Lightweight Private Set Intersection and Its Variants](https://eprint.iacr.org/2026/024)** (2026) - NDSS 2026 lightweight PSI paradigm about 1.5x faster than the fastest VOLE-based PSI, with circuit-PSI variants.

- **[JAGUAR: Efficient and Secure Unbalanced PSI under Malicious Adversaries in the Client-Server Setting](https://eprint.iacr.org/2026/025)** (2026) - Maliciously secure unbalanced PSI using a fixed VOLE-based OPRF with reusable preprocessing across clients.

- **[A Maliciously-Secure Post-Quantum OPRF from Crypto Dark Matter](https://eprint.iacr.org/2026/533)** (2026) - IEEE S&P 2026 post-quantum OPRF made maliciously secure with VOLE-based cut-and-choose correlated randomness.

- **[Revisiting DKLs Threshold ECDSA: Enhanced OT-based VOLE and Two-Party Signing](https://eprint.iacr.org/2026/976)** (2026) - Security and efficiency analysis of the OT-based VOLE in DKLs threshold ECDSA, with three VOLE variants and a 0.2 KB online phase.

- **[Just-in-Time-OPRFs and a Modular Framework for Fast Private Set Intersection](https://eprint.iacr.org/2026/1532)** (2026) - CRYPTO 2026 framework deriving PSI from a new Just-In-Time OPRF primitive, comparing the concrete security of OT- and VOLE-based PSI.

- **[Paras: Actively Secure Two-Server Private Histograms](https://eprint.iacr.org/2026/1600)** (2026) - IACR CiC 2026 two-server private histograms robust to malicious parties, using VOLE-based consistency checks.

- **[High-throughput Verifiable Distributed OPRF from Gold PRF](https://eprint.iacr.org/2026/1953)** (2026) - ACM CCS 2026 verifiable distributed OPRF whose dealer consistency proofs are instantiated with VOLE-in-the-Head and Ligero.

- **[Vespa: Efficient Secure Aggregation with Integrity Defense under Server Privacy](https://eprint.iacr.org/2026/2183)** (2026) - NDSS 2027 secure aggregation with VOLE-based ZK norm and similarity checks on committed inputs.

## 2. Applications

- **[FAEST Signature Scheme](https://faest.info)** - AES-based post-quantum signature built on VOLE-in-the-Head; it is one of the [third-round candidates](https://www.nist.gov/news-events/news/2026/05/nine-candidates-advance-third-round-additional-digital-signatures-pqc) in NIST's Additional Digital Signatures process (May 2026), and its round-3 specification is v3.0 ([code](https://github.com/faest-sign)).

- **[TLSNotary](https://github.com/tlsnotary/tlsn)** - Rust implementation of the TLSNotary protocol for TLS data provenance; its MPC backend ([mpz2](https://github.com/tlsnotary/mpz2)) includes sVOLE-based zero-knowledge proofs.

- **[zkPass](https://github.com/zkPassOfficial)** - zkTLS oracle protocol for private web data whose prover and verifier use VOLE-in-the-Head ([packages](https://github.com/zkPassOfficial/zkPass-VOLEitH-Packages)).

## 3. Implementations

- **[EMP-ZK](https://github.com/emp-toolkit/emp-zk)** - C++ implementation of the Wolverine, QuickSilver and Mystique VOLE-based ZK protocols for Boolean and arithmetic circuits and polynomial relations.

- **[EMP-OT](https://github.com/emp-toolkit/emp-ot)** - C++ OT and OT extension library from EMP-toolkit, including SoftSpoken, Ferret and subfield-VOLE generators built on Ferret.

- **[libOTe](https://github.com/osu-crypto/libOTe)** - Fast C++20 OT extension library that includes silent OT and generic subfield silent/noisy VOLE.

- **[FAEST reference implementation](https://github.com/faest-sign/faest-ref)** - Reference C implementation of FAEST specification v3.0; an optimized x86-64/AArch64 implementation is in [faest-arch-opt](https://github.com/faest-sign/faest-arch-opt).

- **[Holonym VOLE ZK Prover](https://github.com/holonym-foundation/vole-zk-prover)** - Fast, memory-efficient (non-succinct) NIZK prover using QuickSilver with VOLE-in-the-Head, with an adapter for Circom circuits.

- **[Actively Secure Vector OLE](https://github.com/NivKonst/Actively-Secure-Vector-OLE)** - Python implementation of an actively secure variant of the Applebaum et al. VOLE protocol.

- **[Swanky](https://github.com/GaloisInc/swanky)** - Suite of Rust libraries for secure computation, including the Diet Mac'n'Cheese VOLE-based ZK protocol.

## 4. Tutorials and Resources

- **[VOLE-Based ZK - Chainlink Blog](https://blog.chain.link/vole-based-zk/)** - Accessible introduction to VOLE-based ZK with practical applications and benefits.

- **[VOLE-Based Zero-Knowledge Proof - Medium Article](https://medium.com/4hours/vole-based-zero-knowledge-proof-7f15ff2245f3)** - Technical deep dive into VOLE-based ZK protocols with implementation insights and practical considerations.

- **[VOLE-in-the-Head - NIST PQC Seminar](https://csrc.nist.gov/csrc/media/Projects/post-quantum-cryptography/documents/pqc-seminars/presentations/15-vole-in-the-head-06182024.pdf)** - NIST presentation on VOLE-in-the-Head constructions for post-quantum cryptography applications.

- **[NIST Construction of Digital Signatures from VOLE-in-the-Head](https://www.nist.gov/video/constructions-digital-signatures-part-ii-vole-head-and-faest)** - NIST video presentation on digital signature constructions using VOLE-in-the-Head and FAEST.

- **[Carsten Baum - VOLE-in-the-head and FAEST](https://www.youtube.com/watch?v=9ToR-IfZXb4)** - Talk (PQShield channel) on VOLE-in-the-Head and the FAEST signature scheme.

- **[Peter Scholl - ZK Proofs From VOLE and VOLE-in-the-Head](https://www.youtube.com/watch?v=n6ovbe8rm3I)** - Talk (ICMS) on zero-knowledge proofs from VOLE and VOLE-in-the-Head.

- **[NIST IR 8610: Status Report on the Second Round of the Additional Digital Signature Schemes](https://nvlpubs.nist.gov/nistpubs/ir/2026/NIST.IR.8610.pdf)** - NIST report explaining why FAEST, MQOM and SDitH were selected from the MPC-in-the-Head category for the third round.
