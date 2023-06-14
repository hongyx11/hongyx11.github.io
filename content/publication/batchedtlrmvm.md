---
title: 'Accelerating Seismic Redatuming Using Tile Low-Rank Approximations on NEC SX-Aurora TSUBASA'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Hatem Ltaief
  - Matteo Ravasi
  - Laurent Gatineau 
  - David Keyes

date: '2021-09-30T00:00:00Z'
doi: 'https://doi.org/10.1145/3458817.3476225'


publishDate: '2021-09-30T00:00:00Z'
# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['2']

# Publication name and optional abbreviated publication name.
publication: In *SUPERCOMPUTING FRONTIERS AND INNOVATIONS*
publication_short: In *SFI Vol. 8 No. 2 (2021)*

abstract: With the aim of imaging subsurface discontinuities, seismic data recorded at the surface of the Earth must be numerically re-positioned inside the subsurface where reflections have originated, a process referred to as redatuming. The recently developed Marchenko method is able to handle full-wavefield data including multiple arrivals. A downside of this approach is that a multi-dimensional convolution operator must be repeatedly evaluated to solve an expensive inverse problem. As such an operator applies multiple dense matrix-vector multiplications (MVM), we identify and leverage the data sparsity structure for each frequency matrix and propose to accelerate the MVM step using tile low-rank (TLR) matrix approximations. We study the TLR impact on time-to-solution for the MVM using different accuracy thresholds whilst at the same time assessing the quality of the resulting subsurface seismic wavefields and show that TLR leads to a minimal degradation in terms of signal-to-noise ratio on a 3D synthetic dataset. We mitigate the load imbalance overhead and provide performance evaluation on two distributed-memory systems. Our MPI+OpenMP TLR-MVM implementation reaches up to 3X performance speedup against the dense MVM counterpart from NEC scientific library on 128 NEC SX-Aurora TSUBASA cards. Thanks to the second generation of high bandwidth memory technology, it further attains up to 67X performance speedup compared to the dense MVM from Intel MKL when running on 128 dual-socket 20-core Intel Cascade Lake nodes with DDR4 memory. This corresponds to 110 TB/s of aggregated sustained bandwidth for our TLR-MVM implementation, without suffering deterioration in the quality of the reconstructed seismic wavefields.

# Summary. An optional shortened abstract.
summary: NEC Vector Engine, Batched TLR-MVM, Load Balancing

tags: []

# Display this page in the Featured widget?
featured: false


---
