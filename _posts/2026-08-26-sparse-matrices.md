---
title: "HPC Starter 07: Sparse matrix computation"
date: 2026-08-26
permalink: /hpc-starter/sparse-matrices/
tags: [HPC Starter, sparse matrices, SpMV]
excerpt: "Understand CSR storage, sparse matrix–vector multiplication, irregularity, and performance limits."
---

A matrix is sparse when storing and computing with every entry would waste significant work on zeros. Sparse formats store nonzeros and enough metadata to locate them.

## Compressed Sparse Row

CSR represents an $m \times n$ matrix using:

- `values`: the nonzero values;
- `column_indices`: the column of each value; and
- `row_offsets`: where each row begins in the first two arrays.

Row $i$ occupies positions `row_offsets[i]` through `row_offsets[i+1] - 1`.

Sparse matrix–vector multiplication computes $y=Ax$:

```cpp
for (std::size_t row = 0; row < rows; ++row) {
  double sum = 0.0;
  for (index_t p = row_offsets[row]; p < row_offsets[row + 1]; ++p) {
    sum += values[p] * x[column_indices[p]];
  }
  y[row] = sum;
}
```

The loop is short, but performance is subtle. `values` and `column_indices` stream predictably; accesses to `x` depend on the sparsity pattern; and rows may contain very different amounts of work.

## Why SpMV is usually bandwidth bound

Each nonzero performs roughly a multiply and an add but requires a value, a column index, and an element of `x`. Reuse of `x` depends on the matrix. This low arithmetic intensity means memory traffic often limits performance.

Report performance in both GFLOP/s and effective bandwidth. GFLOP/s alone can make a memory-bound implementation look misleadingly poor, while bandwidth connects the result to the hardware limit.

## Sparse matrix–matrix multiplication

SpGEMM computes $C=AB$ when both inputs are sparse. Unlike SpMV, the sparsity pattern and size of $C$ may not be known in advance. Implementations must discover candidate products, accumulate duplicates, allocate output, and balance highly irregular work.

This combination of symbolic structure, numerical computation, and data movement is a central topic in my research.

## Exercise

Using [IU Sparse](https://github.com/hongyx11/iusparse):

1. identify the sparse formats used;
2. trace how one input row is processed;
3. verify output against a small dense reference;
4. benchmark at least three matrices with different row-length distributions; and
5. explain the performance differences using structure, not only matrix dimensions.

**Next:** [Capstone: study a sparse kernel](/hpc-starter/capstone/)

