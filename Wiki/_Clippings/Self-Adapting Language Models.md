---
cite: "seal2025"
title: "Self-Adapting Language Models"
url: "https://arxiv.org/abs/2506.10943"
authors:
  - "Zweiger"
  - "Adam"
  - "Pari"
  - "Jyothish"
  - "Guo"
  - "Han"
  - "Akyürek"
  - "Ekin"
  - "Kim"
  - "Yoon"
  - "Agrawal"
  - "Pulkit"
publisher: "arXiv"
site: "arxiv"
published: 12/06/2025
year: 2025
created: 2025-06-15
description: "SEAL enables LLMs to adapt by generating finetuning data and update directives using reinforcement learning."
tags:
  - "LLMs"
  - "SelfAdapting"
  - "Finetuning"
  - "ReinforcementLearning"
type: "ArXiv"
BibTeX (AI Generated): "@article{seal2025,  title={Self-Adapting Language Models},  author={Zweiger, Adam and Pari, Jyothish and Guo, Han and Akyurek, Ekin and Kim, Yoon and Agrawal, Pulkit},  year={2025},  journal={arXiv preprint arXiv:2506.10943}}"
citations:
---
# Summary

Self-Adapting LLMs (SEAL) enable LLMs to self-adapt by generating finetuning data and update directives. Uses reinforcement learning to train effective self-edits, resulting in lasting adaptation.

----
# Article

Self-Adapting Language Models

Abstract page for arXiv paper 2506.10943: Self-Adapting Language Models

Large language models (LLMs) are powerful but static; they lack mechanisms to adapt their weights in response to new tasks, knowledge, or examples. We introduce Self-Adapting LLMs (SEAL), a framework that enables LLMs to self-adapt by generating their own finetuning data and update directives. Given a new input, the model produces a self-edit-a generation that may restructure the information in different ways, specify optimization hyperparameters, or invoke tools for data augmentation and gradient-based updates. Through supervised finetuning (SFT), these self-edits result in persistent weight updates, enabling lasting adaptation. To train the model to produce effective self-edits, we use a reinforcement learning loop with the downstream performance of the updated model as the reward signal. Unlike prior approaches that rely on separate adaptation modules or auxiliary networks, SEAL directly uses the model's own generation to control its adaptation process. Experiments on knowledge incorporation and few-shot generalization show that SEAL is a promising step toward language models capable of self-directed adaptation. Our website and code is available at https://jyopari.github.io/posts/seal.
