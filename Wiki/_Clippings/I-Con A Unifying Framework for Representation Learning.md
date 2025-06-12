---
cite: "alshammari2025icon"
title: "I-Con: A Unifying Framework for Representation Learning"
url: "https://arxiv.org/abs/2504.16929"
authors:
  - "Alshammari, Shaden"
  - "Hershey, John"
  - "Feldmann, Axel
  - "Freeman, William T."
  - "Hamilton, Mark"
publisher: "arXiv"
site: "arxiv"
published: 23/04/2025
year: 2025
created: 2025-04-24
description: "I-Con unifies representation learning loss functions, improving image classification and debiasing."
tags:
  - "RepresentationLearning"
  - "InformationTheory"
  - "KLdivergence"
  - "UnsupervisedClassification"
  - "Debiasing"
type: "ArXiv"
BibTeX (AI Generated): "@misc{alshammari2025icon,  title={I-Con: A Unifying Framework for Representation Learning},  author={Shaden Alshammari and John Hershey and Axel Feldmann and William T. Freeman and Mark Hamilton},  year={2025},  eprint={2504.16929},  archivePrefix={arXiv},  primaryClass={cs.LG}}"
citations:
---
# Summary

I-Con: A Unifying Framework for Representation Learning introduces a single information-theoretic equation that generalizes loss functions in machine learning. It minimizes an integrated KL divergence between supervisory and learned representations, exposing a hidden information geometry underlying various methods. The framework enables new loss functions and improves unsupervised image classification and debiasing methods.

----
# Article

I-Con: A Unifying Framework for Representation Learning

Abstract:

As the field of representation learning grows, there has been a proliferation of different loss functions to solve different classes of problems. We introduce a single information-theoretic equation that generalizes a large collection of modern loss functions in machine learning. In particular, we introduce a framework that shows that several broad classes of machine learning methods are precisely minimizing an integrated KL divergence between two conditional distributions: the supervisory and learned representations. This viewpoint exposes a hidden information geometry underlying clustering, spectral methods, dimensionality reduction, contrastive learning, and supervised learning. This framework enables the development of new loss functions by combining successful techniques from across the literature. We not only present a wide array of proofs, connecting over 23 different approaches, but we also leverage these theoretical results to create state-of-the-art unsupervised image classifiers that achieve a +8% improvement over the prior state-of-the-art on unsupervised classification on ImageNet-1K. We also demonstrate that I-Con can be used to derive principled debiasing methods which improve contrastive representation learners.
