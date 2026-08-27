---
layout: single
title: "Projects"
permalink: /projects/
author_profile: true
---

These projects connect research ideas with reproducible software and teaching material. The repositories below are useful entry points for students.

<div class="project-grid">
  <article class="project-card featured">
    <p class="project-label">TEACHING · CMAKE</p>
    <h3><a href="https://github.com/hongyx11/iusparse">IU Sparse</a></h3>
    <p>A sparse-kernel library created for teaching. This is the recommended capstone for the HPC Starter path: read the formats, benchmark a kernel, and explain the performance.</p>
    <p><a href="https://github.com/hongyx11/iusparse">View repository →</a></p>
  </article>
  <article class="project-card">
    <p class="project-label">BENCHMARKING</p>
    <h3><a href="https://github.com/hongyx11/SparseComputationBenchmark">Sparse Computation Benchmark</a></h3>
    <p>Experiments and visualization for comparing sparse computation kernels across data sets and systems.</p>
  </article>
  <article class="project-card">
    <p class="project-label">SPGEMM</p>
    <h3><a href="https://github.com/hongyx11/OuterSpGEMM">OuterSpGEMM</a></h3>
    <p>An outer-product approach to sparse matrix–matrix multiplication and a starting point for studying intermediate products and accumulation.</p>
  </article>
  <article class="project-card">
    <p class="project-label">GPU LEARNING</p>
    <h3><a href="https://github.com/hongyx11/CUDAKernels">CUDA Kernels</a></h3>
    <p>Exercises for learning how CUDA kernels map work to GPU threads and memory.</p>
  </article>
  <article class="project-card">
    <p class="project-label">TOOLCHAIN</p>
    <h3><a href="https://github.com/hongyx11/ToolChainExamples">Toolchain Examples</a></h3>
    <p>Small compilation and toolchain examples for C++ and CUDA development.</p>
  </article>
  <article class="project-card">
    <p class="project-label">LOW-RANK METHODS</p>
    <h3><a href="https://github.com/hongyx11/TLR-MVM_Perf">TLR-MVM Performance</a></h3>
    <p>Performance records for tile low-rank matrix–vector and matrix–matrix multiplication.</p>
  </article>
</div>

## A good first contribution

Choose a small kernel, make the baseline reproducible, and measure before optimizing. A useful student contribution usually contains:

1. a clear hypothesis;
2. a correctness test;
3. a repeatable benchmark;
4. a profiler trace or performance model; and
5. a short explanation of what was learned.

Follow the [HPC Starter path](/hpc-starter/) if any of those steps are unfamiliar.

