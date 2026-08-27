---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

My research asks a practical question: **how can we use the structure already present in scientific data to compute less, communicate less, and discover more?**

Matrices arising in simulation, graphs, inverse problems, and machine learning are often sparse or compressible. General-purpose dense methods ignore that structure. My work develops representations, algorithms, and runtime systems that expose it—from a single GPU to distributed supercomputers.

## Research directions

### Sparse matrix computation

I design sparsity-aware data structures and algorithms for operations such as sparse matrix–matrix multiplication and sparse factorization. The goal is to balance arithmetic, memory traffic, and irregular workloads without losing scalability.

### Parallel numerical linear algebra

High-level algebraic operations must be mapped onto multicore processors, GPUs, and distributed-memory systems. I study communication-avoiding algorithms, load balancing, scheduling, and runtimes that make these mappings efficient.

### Algorithm–architecture co-design

Emerging accelerators change the cost of arithmetic, memory, and communication. I redesign algorithms around those constraints, including GPU-resident solvers, tensor-core methods, and systems that use algebraic compression.

### Scientific computing and efficient ML

The techniques above support applications in seismic imaging, adaptive optics, graph analytics, and machine learning. Applications are not an afterthought: their structure guides the algorithm and system design.

## Research goals

1. Develop new data structures that represent matrices according to their sparsity patterns.
2. Design scalable sparsity-aware algorithms and runtime systems for high-level algebraic operations.
3. Optimize sparse matrix computation on GPUs and emerging hardware accelerators.

## Selected themes

| Theme | Questions we study | Typical tools |
|---|---|---|
| Sparse computation | How do structure and ordering reduce work? | C/C++, sparse formats, graph models |
| Performance engineering | Where are time and bandwidth actually spent? | Profilers, roofline analysis, benchmarking |
| Parallel algorithms | How should work and data move across processors? | OpenMP, MPI, CUDA, task runtimes |
| Scientific applications | Which approximations preserve useful accuracy? | Numerical linear algebra, low-rank methods |

See [Projects](/projects/) for software and current directions, or [Publications](/publications/) for research results.

