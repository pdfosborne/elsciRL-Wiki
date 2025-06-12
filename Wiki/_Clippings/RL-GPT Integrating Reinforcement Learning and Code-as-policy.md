---
cite: "RLGPT2024"
title: "RL-GPT: Integrating Reinforcement Learning and Code-as-policy"
url: "https://arxiv.org/abs/2402.19299"
authors:
  - "Liu"
  - "Shaoteng"
  - "Yuan"
  - "Haoqi"
  - "Hu"
  - "Minda"
  - "Li"
  - "Yanwei"
  - "Chen"
  - "Yukang"
  - "Liu"
  - "Shu"
  - "Lu"
  - "Zongqing"
  - "Jia"
  - "Jiaya"
publisher: "arXiv"
site: "arxiv"
published: 29/02/2024
year: 2024
created: 2025-06-11
description: "RL-GPT integrates RL and code, outperforming existing methods in Minecraft and MineDojo tasks."
tags:
  - "ReinforcementLearning"
  - "CodeAsPolicy"
  - "LLM"
  - "Minecraft"
  - "MineDojo"
type: "ArXiv"
BibTeX (AI Generated): "@article{RLGPT2024, author = {Liu, Shaoteng and Yuan, Haoqi and Hu, Minda and Li, Yanwei and Chen, Yukang and Liu, Shu and Lu, Zongqing and Jia, Jiaya}, title = {RL-GPT: Integrating Reinforcement Learning and Code-as-policy}, year = {2024}, journal = {arXiv preprint arXiv:2402.19299}, url = {https://arxiv.org/abs/2402.19299v1}}"
citations:
---
# Summary

RL-GPT integrates Reinforcement Learning and Code-as-policy, using a two-level hierarchical framework with slow and fast agents. It outperforms traditional RL and GPT agents, achieving rapid diamond acquisition in Minecraft and SOTA performance on MineDojo tasks.

----
# Article

## RL-GPT: Integrating Reinforcement Learning and Code-as-policy

Large Language Models (LLMs) have demonstrated proficiency in utilizing various tools by coding, yet they face limitations in handling intricate logic and precise control. In embodied tasks, high-level planning is amenable to direct coding, while low-level actions often necessitate task-specific refinement, such as Reinforcement Learning (RL). To seamlessly integrate both modalities, we introduce a two-level hierarchical framework, RL-GPT, comprising a slow agent and a fast agent. The slow agent analyzes actions suitable for coding, while the fast agent executes coding tasks. This decomposition effectively focuses each agent on specific tasks, proving highly efficient within our pipeline. Our approach outperforms traditional RL methods and existing GPT agents, demonstrating superior efficiency. In the Minecraft game, it rapidly obtains diamonds within a single day on an RTX3090. Additionally, it achieves SOTA performance across all designated MineDojo tasks.
