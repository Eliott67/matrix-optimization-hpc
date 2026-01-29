# matrix-optimization-hpc
High-Performance C++ Matrix Multiplication using OpenMP &amp; Cache Blocking. Achieved 60 GFlops/s.

# Optimization and OpenMP Parallelization of Matrix Operations

![C++](https://img.shields.io/badge/C++-17-blue)
![OpenMP](https://img.shields.io/badge/OpenMP-Enabled-orange)
![Performance](https://img.shields.io/badge/Performance-60_GFlops/s-brightgreen)

## Overview

This project focuses on the low-level optimization of dense matrix operations (Addition and Multiplication) on CPU. The goal was to maximize computational throughput ($GFlops/s$) by leveraging hardware capabilities.

We compared naive implementations against highly optimized versions using **OpenMP parallelization** and **Cache Blocking**, benchmarking the results against **BLAS** routines (Level 1, 2, and 3).

## Key Results

* **Baseline (Naive):** < 1 GFlops/s
* **Parallelized (OpenMP):** ~35-40 GFlops/s
* **Cache Blocking + OpenMP:** **60 GFlops/s** (Peak Performance)

## Optimization Techniques

1.  **Memory Access:** Analysis of Row-major vs Column-major traversal to minimize cache misses.
2.  **Parallelization:** Implementation of `#pragma omp parallel for` with dynamic scheduling analysis.
3.  **Cache Blocking:** Tiling the matrix multiplication loops to improve temporal and spatial locality, fitting working sets into L1/L2 cache.

## Project Structure

```bash
├── plots/
│   ├── generate_plots.py     # Python visualization script
│   └── dot_vs_blocking.png   # Performance graph
├── report/
│   └── HPC_Report.pdf        # Full technical report
└── README.md
