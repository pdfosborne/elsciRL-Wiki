---
cite: "@misc{SWE-RL,  title={SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution},  author={Wei, Yuxiang and Duchenne, Olivier and Copet, Jade and Carbonneaux, Quentin and Zhang, Lingming and Fried, Daniel and Synnaeve, Gabriel and Singh, Rishabh and Wang, Sida I.},  year={2025}}"
title: "SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution"
url: https://arxiv.org/abs/2502.18449
authors:
  - Wei
  - Yuxiang
  - Duchenne
  - Olivier
  - Copet
  - Jade
  - Carbonneaux
  - Quentin
  - Zhang
  - Lingming
  - Fried
  - Daniel
  - Synnaeve
  - Gabriel
  - Singh
  - Rishabh
  - Wang
  - Sida I.
publisher: arXiv
site: arxiv
published: 2025-02-25
year: 2025
created: 2025-02-27
description: "SWE-RL: RL enhances LLM reasoning for software engineering. Llama3 achieves 41% on SWE-bench."
tags:
  - ReinforcementLearning
  - LLM
  - SoftwareEngineering
  - OpenSource
  - Llama3
type: ArXiv
BibTeX (AI Generated): "@misc{SWERL,  title={SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution},  author={Wei, Yuxiang and Duchenne, Olivier and Copet, Jade and Carbonneaux, Quentin and Zhang, Lingming and Fried, Daniel and Synnaeve, Gabriel and Singh, Rishabh and Wang, Sida I.},  year={2025},  url={https://arxiv.org/abs/2502.18449v1}}"
citations: "0"
---
# Summary

SWE-RL enhances LLM reasoning for software engineering using reinforcement learning on open-source software evolution data. Llama3-SWE-RL-70B achieves 41.0% solve rate on SWE-bench Verified.

----
# Article

SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution

The recent DeepSeek-R1 release has demonstrated the immense potential of reinforcement learning (RL) in enhancing the general reasoning capabilities of large language models (LLMs). While DeepSeek-R1 and other follow-up work primarily focus on applying RL to competitive coding and math problems, this paper introduces SWE-RL, the first approach to scale RL-based LLM reasoning for real-world software engineering. Leveraging a lightweight rule-based reward (e.g., the similarity score between ground-truth and LLM-generated solutions), SWE-RL enables LLMs to autonomously recover a developer's reasoning processes and solutions by learning from extensive open-source software evolution data -- the record of a software's entire lifecycle, including its code snapshots, code changes, and events such as issues and pull requests. Trained on top of Llama 3, our resulting reasoning model, Llama3-SWE-RL-70B, achieves a 41.0% solve rate on SWE-bench Verified -- a human-verified collection of real-world GitHub issues. To our knowledge, this is the best performance reported for medium-sized (
