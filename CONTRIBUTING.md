# Contributing to the Lite Ecosystem

Thank you for your interest in contributing! This repository is part of a broader ecosystem of micro-libraries built on strict architectural principles. To ensure every library remains exceptionally fast and lightweight, please review our core development philosophy before opening a pull request.

## Core Architectural Principles

1. **Zero External Dependencies:** We do not rely on third-party NPM packages for core logic. Every library is entirely self-contained.
2. **Zero-GC Hot Paths:** Memory allocations during steady-state execution (game loops, reactive propagation, rendering) are strictly forbidden. Use pre-allocated arrays, object pools, and flat topologies to avoid triggering the Garbage Collector.
3. **Bare-Metal Performance:** We optimize for CPU cache locality and predictable execution. Monomorphic functions and bitwise operations are preferred where they yield measurable JIT benefits.
4. **Legacy Hardware Validation:** High-end machines hide performance flaws. Code must remain highly performant when benchmarked on legacy devices (e.g., ten-year-old laptops or older mobile hardware).

## Submitting a Pull Request

1. **Discuss Architecture First:** For significant changes or new features, please open an Issue first to discuss the approach.
2. **Prove the Performance:** If your PR touches a hot path, you must include benchmark results demonstrating the impact. Regressions in ops/sec or steady-state memory retention will not be merged.
3. **Keep it Focused:** PRs should do one thing. Do not mix refactoring with feature additions.
4. **Pass the Tests:** Ensure all existing unit tests and correctness verifications pass. 

## Setting up for Development

1. Clone the repository.
2. Run `npm install` to grab the development dependencies (testing and coverage tools).
3. Ensure you have the test runner configured correctly for your environment.
4. If submitting benchmark changes, please run the suite with `--expose-gc` enabled to ensure memory tracking is accurate.

We appreciate your time and effort in helping keep these tools uncompromisingly fast!
