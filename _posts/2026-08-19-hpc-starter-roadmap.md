---
title: "HPC Starter 00: How to use this learning path"
date: 2026-08-19
permalink: /hpc-starter/roadmap/
tags: [HPC Starter, reproducibility, benchmarking]
excerpt: "Set up a reproducible notebook and learn the experimental habits behind performance engineering."
---

High-performance computing is not simply “making code faster.” It is the practice of explaining **why** a program performs as it does on a particular machine, then changing the algorithm or implementation based on evidence.

This series gives you enough foundation to begin a research project. Every module has three parts: a concept, a small experiment, and a written reflection.

## Create a lab repository

Make a repository with this structure:

```text
hpc-starter/
├── README.md
├── environment.md
├── results/
├── scripts/
└── src/
```

In `environment.md`, record:

- machine and cluster name;
- CPU and GPU model;
- compiler and version;
- important compiler flags;
- software modules or container image;
- scheduler parameters; and
- the Git commit used for each result.

Performance results without this context are difficult to interpret and often impossible to reproduce.

## Use a scientific loop

For every exercise:

1. **Question:** What do you want to understand?
2. **Hypothesis:** What do you expect, and why?
3. **Method:** What exactly will you run and measure?
4. **Result:** Report raw data, not only the best number.
5. **Interpretation:** Explain whether the evidence supports the hypothesis.

Change one important variable at a time. Run multiple trials. Check correctness before timing. Keep the input fixed when comparing implementations.

## Timing is measurement

A useful benchmark needs a warm-up, a well-defined timed region, multiple samples, and a summary such as median runtime. Do not include compilation, input generation, or file I/O unless those operations are part of the question.

Report a rate that connects time to useful work. Depending on the kernel, that may be elements per second, bytes per second, or floating-point operations per second.

## First exercise

Write down one system you can access and answer:

- How many CPU cores does it have?
- What memory capacity and memory channels does it have?
- Is there a GPU? Which one?
- Which compilers are installed?
- Is work launched directly or through a scheduler?

Add the answers to `environment.md`. You now have the first artifact in a reproducible HPC workflow.

**Next:** [Linux and cluster workflow](/hpc-starter/linux-cluster-workflow/)

