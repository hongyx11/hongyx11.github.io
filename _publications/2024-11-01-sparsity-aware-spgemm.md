---
title: "A Sparsity-Aware Distributed-Memory Algorithm for Sparse-Sparse Matrix Multiplication"
collection: publications
category: conferences
permalink: /publication/sparsity-aware-spgemm
excerpt: "A sparsity-aware 1D SpGEMM algorithm using MPI RDMA and block fetching to reduce unnecessary communication."
date: 2024-11-01
venue: "SC '24: International Conference for High Performance Computing, Networking, Storage and Analysis"
paperurl: "https://doi.org/10.1109/SC41406.2024.00053"
citation: "<strong>Y. Hong</strong> and A. Buluç. (2024). &quot;A Sparsity-Aware Distributed-Memory Algorithm for Sparse-Sparse Matrix Multiplication.&quot; <i>SC '24</i>."
---

This work uses matrix sparsity to avoid fetching nonzeros that cannot contribute to the product, combining a 1D distributed algorithm with MPI RDMA and block fetching.

