---
title: 'Meeting the real-time challenges of ground-based telescopes using low-rank matrix computations'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Hatem Ltaief
  - Jesse Cranney
  - Damien Gratadour
  - admin
  - Laurent Gatineau 
  - David Keyes

date: '2021-11-14T00:00:00Z'
doi: 'https://doi.org/10.1145/3458817.3476225'


publishDate: '2021-11-14T00:00:00Z'
# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['1']

# Publication name and optional abbreviated publication name.
publication: In *Proceedings of the International Conference for High Performance Computing, Networking, Storage and Analysis*
publication_short: In *SC 21*

abstract: Adaptive Optics (AO) is a technology that permits to measure and mitigate the distortion effects of atmospheric turbulence on optical beams. AO must operate in real-time by controlling thousands of actuators to shape the surface of deformable mirrors deployed on ground-based telescopes to compensate for these distortions. The command vectors that trigger how each individual actuator should act to bend a portion of the mirror are obtained from Matrix-Vector Multiplications (MVM). We identify and leverage the data sparsity structure of these control matrices coming from the MAVIS instruments for the European Southern Observatory's Very Large Telescope. We provide performance evaluation on x86 and accelerator-based systems. We present the impact of tile low-rank (TLR) matrix approximations on time-to-solution for the MVM and assess the produced image quality. We achieve performance improvement up to two orders of magnitude for TLR-MVM compared to regular dense MVM, while maintaining the image quality.

# - {{< staticref "uploads/yuxicv.pdf" "newtab" >}}Curriculum Vitae{{< /staticref >}}

# Summary. An optional shortened abstract.
summary: Task

tags: []

# Display this page in the Featured widget?
featured: false


---
