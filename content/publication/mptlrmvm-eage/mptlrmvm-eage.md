---
title: 'Tile-Low Rank Compressed Multi-Dimensional Convolution and Its Application to Seismic Redatuming Problems'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Matteo Ravasi
  - admin
  - Hatem Ltaief
  - David Keyes


date: '2022-06-15T00:00:00Z'
doi: 'https://doi.org/10.3997/2214-4609.202210253'
url_pdf: './publication/mptlrmvm-eage/EAGE_2022_MDCTLR.pdf'

publishDate: '2022-06-15T00:00:00Z'
# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['1']

# Publication name and optional abbreviated publication name.
publication: In *83rd EAGE Annual Conference & Exhibition*
publication_short: In *EAGE 22*

abstract: A variety of algorithms in seismic processing and imaging rely on the repeated evaluation of a multidimensional integral of convolution (or correlation) type. This operator is notoriously expensive due to the fact that it inherently requires accessing the entire seismic reflection response to perform a batched matrix-vector (or matrix-matrix) multiplication. In this work, we propose to alleviate this memory and computational burden by leveraging data sparsity in the frequency-domain and using Tile Low-Rank (TLR) matrix approximation. We also show that a geographically aware re-arrangement of the rows and columns of the kernel of the operator can further boost the compression capabilities of the TLR algorithm with minimal impact on the quality of the processing outcome. A synthetic example of 3D Marchenko redatuming is used to validate the proposed strategies.


# Summary. An optional shortened abstract.
summary:  redatuming, large-scale processing, compression, high-performance computing, inverse problems

tags: []

# Display this page in the Featured widget?
featured: false


---
