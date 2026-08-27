---
layout: single
title: "HPC Starter"
permalink: /hpc-starter/
author_profile: true
---

**HPC Starter** is a practical learning path for students who want to work in high-performance scientific computing. It starts with the daily tools of a researcher and builds toward parallel sparse matrix kernels.

You will learn best by running the examples, changing them, measuring the result, and writing down what surprised you. Reading alone is not enough.

<div class="notice--info">
<strong>Suggested pace:</strong> one module per week. Keep a public repository containing your code, job scripts, results, and short lab notes.
</div>

## Learning path

<div class="learning-path">
  <a class="lesson-card" href="/hpc-starter/roadmap/"><span>00</span><div><strong>How to use this path</strong><small>Set up a reproducible performance notebook.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/linux-cluster-workflow/"><span>01</span><div><strong>Linux and cluster workflow</strong><small>SSH, files, processes, modules, and Slurm.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/cpp-build-tools/"><span>02</span><div><strong>C++ and build tools</strong><small>Compilers, warnings, optimization, and CMake.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/performance-foundations/"><span>03</span><div><strong>Performance foundations</strong><small>Latency, bandwidth, locality, and roofline thinking.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/openmp/"><span>04</span><div><strong>Shared-memory parallelism</strong><small>OpenMP, races, reductions, and scaling.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/mpi/"><span>05</span><div><strong>Distributed-memory parallelism</strong><small>MPI decomposition, collectives, and communication.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/cuda/"><span>06</span><div><strong>GPU programming</strong><small>CUDA execution and memory hierarchy.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/sparse-matrices/"><span>07</span><div><strong>Sparse matrix computation</strong><small>CSR, SpMV, arithmetic intensity, and irregularity.</small></div></a>
  <a class="lesson-card" href="/hpc-starter/capstone/"><span>08</span><div><strong>Capstone: study a sparse kernel</strong><small>Correctness, benchmarking, profiling, and reporting.</small></div></a>
</div>

## What you should be able to do afterward

- Build and run a C++ project on a Linux cluster.
- Submit reproducible jobs through a scheduler.
- Explain whether a kernel is limited by compute, memory, or communication.
- Parallelize a small kernel with OpenMP, MPI, or CUDA.
- Read a sparse matrix kernel and reason about its data movement.
- Present a benchmark with enough evidence for someone else to reproduce it.

## Further reading

The series is an orientation, not a substitute for a full course. Each lesson ends with exercises and pointers for deeper study. When you are ready, explore [my projects](/projects/) and [publications](/publications/).

