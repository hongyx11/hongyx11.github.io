---
title: 'LSDDL: Layer-Wise Sparsification for Distributed Deep Learning'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Peng Han


date: '2021-11-15T00:00:00Z'
doi: 'https://doi.org/10.1016/j.bdr.2021.100272'


publishDate: '2021-11-15T00:00:00Z'
# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['2']

# Publication name and optional abbreviated publication name.
publication: In *Big Data Research*
publication_short: In *Big Data Research*

abstract: With an escalating arms race to adopt machine learning (ML) into diverse application domains, there is an urgent need to efficiently support distributed machine learning (ML) algorithms. As Stochastic Gradient Descent (SGD) is widely adopted in training ML models, the performance bottleneck of distributed ML would be the communication cost to transmit gradients through the network. While a lot of existing studies aim at compressing the gradient so as to reduce the overhead of network communication, they ignore the model structure in the process of compression. As a result, while they could reduce the communication time, they would result in serious computation discontinuity for deep neural networks, which will lower the prediction accuracy.In this paper, we propose LSDDL, a scalable and light-weighted method to boost the training process of deep learning models in shared-nothing environment. The cornerstone of LSDDL lies on the observation that different layers in a neural network have different importance in the process of decompression. To exploit this insight, we devise a sparsification strategy to compress the gradient of deep neural networks which can preserve the structural information of the model. In addition, we provide a series of compression techniques to further reduce the communication overhead and optimize the overall performance. We implement our LSDDL framework in the PyTorch system and encapsulate it as a user friendly API. We validate our proposed techniques by training several real models on a large cluster. Experimental results show that the communication time of LSDDL is up to 5.43 times less than the original SGD without losing much accuracy.

# Summary. An optional shortened abstract.
summary:   distributed deep learning training GPU 

tags: []

# Display this page in the Featured widget?
featured: false


---
