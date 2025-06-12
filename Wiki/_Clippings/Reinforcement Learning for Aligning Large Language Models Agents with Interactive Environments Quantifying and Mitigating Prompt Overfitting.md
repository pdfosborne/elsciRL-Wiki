---
cite: "aissi2024reinforcement"
title: "Reinforcement Learning for Aligning Large Language Models Agents with Interactive Environments: Quantifying and Mitigating Prompt Overfitting"
url: "https://arxiv.org/abs/2410.19920"
authors:
  - "Aissi"
  - "Mohamed Salim"
  - "Romac"
  - "Clement"
  - "Carta"
  - "Thomas"
  - "Lamprier"
  - "Sylvain"
  - "Oudeyer"
  - "Pierre-Yves"
  - "Sigaud"
  - "Olivier"
  - "Soulier"
  - "Laure"
  - "Thome"
  - "Nicolas"
publisher: "arxiv"
site: "arxiv"
published: 25/10/2024
year: 2024
created: 2025-06-11
description: "LLMs' sensitivity to prompt variations after RL training is analyzed. Contrastive loss mitigates this."
tags:
  - "ReinforcementLearning"
  - "LLMs"
  - "PromptOverfitting"
  - "ContrastiveLoss"
type: "ArXiv"
BibTeX (AI Generated): "@article{aissi2024reinforcement, author = {Mohamed Salim Aissi and Clement Romac and Thomas Carta and Sylvain Lamprier and Pierre-Yves Oudeyer and Olivier Sigaud and Laure Soulier and Nicolas Thome}, title = {Reinforcement Learning for Aligning Large Language Models Agents with Interactive Environments: Quantifying and Mitigating Prompt Overfitting}, journal = {arXiv preprint arXiv:2410.19920}, year = {2024}}"
citations:
---
# Summary

This paper analyzes the sensitivity of LLMs to prompt formulations after RL training in a textual environment and proposes a contrastive loss to mitigate this sensitivity.

----
# Article

Reinforcement Learning for Aligning Large Language Models Agents with Interactive Environments: Quantifying and Mitigating Prompt Overfitting

Abstract page for arXiv paper 2410.19920: Reinforcement Learning for Aligning Large Language Models Agents with Interactive Environments: Quantifying and Mitigating Prompt Overfitting

Reinforcement learning (RL) is a promising approach for aligning large language models (LLMs) knowledge with sequential decision-making tasks. However, few studies have thoroughly investigated the impact on LLM agents capabilities of fine-tuning them with RL in a specific environment. In this paper, we propose a novel framework to analyze the sensitivity of LLMs to prompt formulations following RL training in a textual environment. Our findings reveal that the performance of LLMs degrades when faced with prompt formulations different from those used during the RL training phase. Besides, we analyze the source of this sensitivity by examining the model's internal representations and salient tokens. Finally, we propose to use a contrastive loss to mitigate this sensitivity and improve the robustness and generalization capabilities of LLMs.
