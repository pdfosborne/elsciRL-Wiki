---
cite: illusionofthinking2025
title: "The Illusion of Thinking: Understanding the Strengths and Limitations of Reasoning Models via the Lens of Problem Complexity"
url: https://machinelearning.apple.com/research/illusion-of-thinking
authors:
  - Parshin Shojaee
  - Iman Mirzadeh
  - Keivan Alizadeh
  - Maxwell Horton
  - Samy Bengio
  - Mehrdad Farajtabar
publisher: apple
site: apple
published: 2025-06-06
year: 2025
created: 2025-06-08
description: LRMs face accuracy collapse beyond certain complexities, revealing limitations in reasoning.
tags:
  - reasoningmodels
  - lrms
  - language
  - models
  - puzzleenvironments
  - complexity
  - thinking
type: WebArticle
BibTeX (AI Generated): "@misc{illusionofthinking2025,  author = {Parshin Shojaee and Iman Mirzadeh and Keivan Alizadeh and Maxwell Horton and Samy Bengio and Mehrdad Farajtabar},  title = {The Illusion of Thinking: Understanding the Strengths and Limitations of Reasoning Models via the Lens of Problem Complexity},  howpublished = {\\url{https://machinelearning.apple.com/research/illusion-of-thinking}},  year = {2025}}"
citations: "0"
---
# Summary

This paper investigates the strengths and limitations of Large Reasoning Models (LRMs) using controllable puzzle environments. It finds that LRMs face accuracy collapse beyond certain complexities and exhibit counter-intuitive scaling limits. The study compares LRMs with standard LLMs, identifying performance regimes and limitations in exact computation and consistent reasoning.

----
# Article

# The Illusion of Thinking: Understanding the Strengths and Limitations of Reasoning Models via the Lens of Problem Complexity

Authors: Parshin Shojaee, Iman Mirzadeh, Keivan Alizadeh, Maxwell Horton, Samy Bengio, Mehrdad Farajtabar

[View publication](https://ml-site.cdn-apple.com/papers/the-illusion-of-thinking.pdf)

Recent generations of frontier language models have introduced Large Reasoning Models (LRMs) that generate detailed thinking processes before providing answers. While these models demonstrate improved performance on reasoning benchmarks, their fundamental capabilities, scaling properties, and limitations remain insufficiently understood. Current evaluations primarily focus on established mathematical and coding benchmarks, emphasizing final answer accuracy. However, this evaluation paradigm often suffers from data contamination and does not provide insights into the reasoning traces’ structure and quality.

In this work, we systematically investigate these gaps with the help of controllable puzzle environments that allow precise manipulation of compositional complexity while maintaining consistent logical structures. This setup enables the analysis of not only final answers but also the internal reasoning traces, offering insights into how LRMs “think”. Through extensive experimentation across diverse puzzles, we show that frontier LRMs face a complete accuracy collapse beyond certain complexities. Moreover, they exhibit a counter-intuitive scaling limit: their reasoning effort increases with problem complexity up to a point, then declines despite having an adequate token budget.

By comparing LRMs with their standard LLM counterparts under equivalent inference compute, we identify three performance regimes: (1) low-complexity tasks where standard models surprisingly outperform LRMs, (2) medium-complexity tasks where additional thinking in LRMs demonstrates advantage, and (3) high-complexity tasks where both models experience complete collapse. We found that LRMs have limitations in exact computation: they fail to use explicit algorithms and reason inconsistently across puzzles. We also investigate the reasoning traces in more depth, studying the patterns of explored solutions and analyzing the models’ computational behavior, shedding light on their strengths, limitations, and ultimately raising crucial questions about their true reasoning capabilities.

*Equal contribution. 
†Work done during an internship at Apple.
