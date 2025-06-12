---
cite: "LLMpath"
title: "Can LLM be a Good Path Planner based on Prompt Engineering? Mitigating the Hallucination for Path Planning"
url: "https://arxiv.org/abs/2408.13184"
authors:
  - "Deng"
  - "Hourui"
  - "Zhang"
  - "Hongjie"
  - "Ou"
  - "Jie"
  - "Feng"
  - "Chaosheng"
publisher: "arxiv"
site: "arxiv"
published: 23/08/2024
year: 2024
created: 2025-06-11
description: "S2RCQL model improves LLM path-planning by addressing spatial hallucination."
tags:
  - "LLM"
  - "PathPlanning"
  - "Hallucination"
  - "S2RCQL"
  - "SpatialReasoning"
type: "ArXiv"
BibTeX (AI Generated): "@article{LLMpath, author = {Deng, Hourui and Zhang, Hongjie and Ou, Jie and Feng, Chaosheng}, title = {Can LLM be a Good Path Planner based on Prompt Engineering? Mitigating the Hallucination for Path Planning}, year = {2024}, journal = {arXiv preprint arXiv:2408.13184}}"
citations:
---
# Summary

LLMs face challenges in long-term path-planning due to spatial hallucination. S2RCQL model is proposed to address this, improving success and optimality rates.

----
# Article

Can LLM be a Good Path Planner based on Prompt Engineering? Mitigating the Hallucination for Path Planning

Abstract page for arXiv paper 2408.13184: Can LLM be a Good Path Planner based on Prompt Engineering? Mitigating the Hallucination for Path Planning

Spatial reasoning in Large Language Models (LLMs) is the foundation for embodied intelligence. However, even in simple maze environments, LLMs still encounter challenges in long-term path-planning, primarily influenced by their spatial hallucination and context inconsistency hallucination by long-term reasoning. To address this challenge, this study proposes an innovative model, Spatial-to-Relational Transformation and Curriculum Q-Learning (S2RCQL). To address the spatial hallucination of LLMs, we propose the Spatial-to-Relational approach, which transforms spatial prompts into entity relations and paths representing entity relation chains. This approach fully taps the potential of LLMs in terms of sequential thinking. As a result, we design a path-planning algorithm based on Q-learning to mitigate the context inconsistency hallucination, which enhances the reasoning ability of LLMs. Using the Q-value of state-action as auxiliary information for prompts, we correct the hallucinations of LLMs, thereby guiding LLMs to learn the optimal path. Finally, we propose a reverse curriculum learning technique based on LLMs to further mitigate the context inconsistency hallucination. LLMs can rapidly accumulate successful experiences by reducing task difficulty and leveraging them to tackle more complex tasks. We performed comprehensive experiments based on Baidu's self-developed LLM: ERNIE-Bot 4.0. The results showed that our S2RCQL achieved a 23%--40% improvement in both success and optimality rates compared with advanced prompt engineering.
