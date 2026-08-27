---
title: "HPC Starter 03: Performance foundations"
date: 2026-08-22
permalink: /hpc-starter/performance-foundations/
tags: [HPC Starter, performance, roofline, memory]
excerpt: "Reason about latency, bandwidth, locality, arithmetic intensity, and trustworthy benchmark results."
---

Optimization starts by identifying the limiting resource. A processor can execute arithmetic much faster than it can retrieve arbitrary data from memory, so many scientific kernels are limited by data movement rather than floating-point throughput.

## Latency, bandwidth, and locality

**Latency** is the delay before an operation completes. **Bandwidth** is the amount transferred per unit time. Caches reduce the effective latency and traffic when programs reuse recently accessed data.

- Temporal locality: reuse the same data soon.
- Spatial locality: access nearby addresses together.
- Sequential access: lets hardware prefetchers anticipate future data.

Sparse algorithms are challenging because indices can turn a compact loop into irregular memory access.

## Arithmetic intensity

Arithmetic intensity is approximately:

$$I = \frac{\text{floating-point operations}}{\text{bytes moved from main memory}}.$$

A kernel with low intensity tends to be memory-bandwidth bound. A kernel with high intensity may become compute bound. The roofline model summarizes this with:

$$P \le \min(P_{peak},\ I \times B_{memory}).$$

This is a bound, not a performance guarantee. It tells you which resource deserves attention.

## Measure carefully

In C++, use a monotonic clock around only the operation of interest:

```cpp
const auto start = std::chrono::steady_clock::now();
kernel(input, output);
const auto stop = std::chrono::steady_clock::now();
const double seconds =
    std::chrono::duration<double>(stop - start).count();
```

Warm up the code, run multiple trials, and report a distribution. Confirm CPU affinity and thread count. Avoid comparing two codes that use different inputs, precision, stopping criteria, or correctness requirements.

## A bandwidth experiment

Implement `c[i] = a[i] + scalar * b[i]` for large arrays. Estimate the useful bytes moved per element and compute achieved bandwidth. Sweep sizes from cache-resident to much larger than the last-level cache.

Plot size on the horizontal axis and bandwidth on the vertical axis. Mark approximate cache capacities. Explain the transitions you observe.

## Questions to ask before optimizing

1. Is the output correct?
2. Which region consumes the time?
3. Is it limited by arithmetic, memory, synchronization, or communication?
4. What model predicts the expected performance?
5. What profiler evidence supports that explanation?

**Next:** [Shared-memory parallelism with OpenMP](/hpc-starter/openmp/)

