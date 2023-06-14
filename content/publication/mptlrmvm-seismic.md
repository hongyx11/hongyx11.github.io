---
title: 'Large-scale Marchenko imaging with distance-aware matrix reordering, tile low-rank compression, and mixed-precision computations'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Matteo Ravasi
  - admin
  - Hatem Ltaief
  - David Keyes
  - David Vargas


date: '2022-08-15T00:00:00Z'
doi: 'https://doi.org/10.1190/image2022-3744978.1'


publishDate: '2022-08-15T00:00:00Z'
# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['1']

# Publication name and optional abbreviated publication name.
publication: In *Second International Meeting for Applied Geoscience & Energy*
publication_short: In *IMAGE 22*

abstract: A variety of wave-equation-based seismic processing algorithms rely on the repeated application of the Multi- Dimensional Convolution (MDC) operator. For large-scale 3D seismic surveys, this comes with severe computational challenges due to the sheer size of high-density, full-azimuth seismic datasets required by such algorithms. We present a three-fold solution that greatly alleviates the memory footprint and computational cost of 3D MDC by leveraging a combination of i) distance-aware matrix reordering, ii) Tile Low-Rank (TLR) matrix compression, and iii) computations in mixed floating-point precision. By applying our strategy to a 3D synthetic dataset, we show that the size of kernel matrices used in the Marchenko redatuming and Multi-Dimensional Deconvolution equations can be reduced by a factor of 34 and 6, respectively. We also introduce a TLR Matrix-Vector Multiplication (TLR-MVM) algorithm that, as a direct consequence of such compression capabilities, is consistently faster than its dense counterpart by a factor of 4.8 to 36.1 (depending on the selected hardware). As a result, the associated inverse problems can be solved at a fraction of cost in comparison to state-of- the-art implementations that require a pass through the entire data at each MDC operation. This is achieved with minimal impact on the quality of the processing outcome.


# Summary. An optional shortened abstract.
summary:  redatuming, large-scale processing, compression, high-performance computing, inverse problems

tags: []

# Display this page in the Featured widget?
featured: false


---
