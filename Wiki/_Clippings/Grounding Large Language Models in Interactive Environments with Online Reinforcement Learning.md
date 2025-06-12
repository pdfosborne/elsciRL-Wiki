---
cite: "glam2023"
title: "Grounding Large Language Models in Interactive Environments with Online Reinforcement Learning"
url: "https://arxiv.org/abs/2302.02662"
authors:
  - "Carta"
  - "Thomas"
  - "Romac"
  - "Clément"
  - "Wolf"
  - "Thomas"
  - "Lamprier"
  - "Sylvain"
  - "Sigaud"
  - "Olivier"
  - "Oudeyer"
  - "Pierre-Yves"
publisher: "arXiv"
site: "arxiv"
published: 06/02/2023
year: 2023
created: 2025-06-11
description: "GLAM aligns LLMs with interactive environments via online RL for improved performance."
tags:
  - "LLMs"
  - "ReinforcementLearning"
  - "InteractiveEnvironments"
  - "FunctionalGrounding"
type: "ArXiv"
BibTeX (AI Generated): "@article{glam2023, author = {Carta, Thomas and Romac, Clément and Wolf, Thomas and Lamprier, Sylvain and Sigaud, Olivier and Oudeyer, Pierre-Yves}, title = {Grounding Large Language Models in Interactive Environments with Online Reinforcement Learning}, journal = {arXiv preprint arXiv:2302.02662}, year = {2023}}"
citations:
---
# Summary

This paper introduces GLAM, an approach to align Large Language Models (LLMs) with interactive environments through functional grounding, using online Reinforcement Learning to improve performance on spatial and navigation tasks. It studies if LLMs boost sample efficiency, generalization, and the impact of online learning using FLAN-T5 variants.

----
# Article

Grounding Large Language Models in Interactive Environments with Online Reinforcement Learning

Abstract page for arXiv paper 2302.02662: Grounding Large Language Models in Interactive Environments with Online Reinforcement Learning

Recent works successfully leveraged Large Language Models' (LLM) abilities to capture abstract knowledge about world's physics to solve decision-making problems. Yet, the alignment between LLMs' knowledge and the environment can be wrong and limit functional competence due to lack of grounding. In this paper, we study an approach (named GLAM) to achieve this alignment through functional grounding: we consider an agent using an LLM as a policy that is progressively updated as the agent interacts with the environment, leveraging online Reinforcement Learning to improve its performance to solve goals. Using an interactive textual environment designed to study higher-level forms of functional grounding, and a set of spatial and navigation tasks, we study several scientific questions: 1) Can LLMs boost sample efficiency for online learning of various RL tasks? 2) How can it boost different forms of generalization? 3) What is the impact of online learning? We study these questions by functionally grounding several variants (size, architecture) of FLAN-T5.
