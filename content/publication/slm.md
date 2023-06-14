---
title: 'Outsmarting the Atmospheric Turbulence for Ground-Based Telescopes Using the Stochastic Levenberg-Marquardt Method'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - El Houcine Bergou
  - Nicolas Doucet
  - Hao Zhang
  - Jesse Cranney
  - Hatem Ltaief
  - Damien Gratadour
  - Francois Rigaut
  - David Keyes

# Author notes (optional)
# author_notes:
#   - 'Equal contribution'
#   - 'Equal contribution'

date: '2021-09-30T00:00:00Z'
doi: 'https://doi.org/10.1007/978-3-030-85665-6_35'


publishDate: '2021-09-30T00:00:00Z'
# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['1']

# Publication name and optional abbreviated publication name.
publication: In *27th International Conference on Parallel and Distributed Computing*
publication_short: In *Euro-Par 2021*

abstract: One of the main challenges for ground-based optical astronomy is to compensate for atmospheric turbulence in near real-time. The goal is to obtain images as close as possible to the diffraction limit of the telescope. This challenge is addressed on the latest generation of giant optical telescopes by deploying multi-conjugate adaptive optics (MCAO) systems performing predictive tomography of the turbulence and multi-layer compensation. Such complex systems require a high fidelity estimate of the turbulence profile above the telescope, to be updated regularly during operations as turbulence conditions evolve. In this paper, we modify the traditional Levenberg-Marquardt (LM) algorithm by considering stochastically chosen subsystems of the full problem to identify the required parameters efficiently, while coping with the real-time challenge. While LM operates on the full set data samples, the resulting Stochastic LM (SLM) method randomly selects subsamples to compute corresponding approximate gradients and Hessians. Hence, SLM reduces the algorithmic complexity per iteration and shortens the overall time to solution, while maintaining LM’s numerical robustness. We present a new convergence analysis for SLM, implement the algorithm with optimized GPU kernels, and deploy it on shared-memory systems with multiple GPU accelerators. We assess SLM in the adaptive optics system configurations in the context of the MCAO-Assisted Visible Imager & Spectrograph (MAVIS) instrument for the Very Large Telescope (VLT). We demonstrate performance superiority of SLM over the traditional LM algorithm and the classical stochastic first-order methods. At the scale of VLT AO, SLM finishes the optimization process and accurately retrieves the parameters (e.g., turbulence strength and wind speed profiles) in less than a second using up to eight NVIDIA A100 GPUs, which permits high acuity real-time throughput over a night of observations.

# - {{< staticref "uploads/yuxicv.pdf" "newtab" >}}Curriculum Vitae{{< /staticref >}}

# Summary. An optional shortened abstract.
summary: Optimization, GPU Programming

tags: []

# Display this page in the Featured widget?
featured: false


---
