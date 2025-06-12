---
cite: "Zhang2025"
title: "VideoGameBench: Can Vision-Language Models complete popular video games?"
url: "https://arxiv.org/abs/2505.18134"
authors:
  - "Zhang"
  - "Alex L."
  - "Griffiths"
  - "Thomas L."
  - "Narasimhan"
  - "Karthik R."
  - "Press"
  - "Ofir"
publisher: "arXiv"
site: "arxiv"
published: 23/05/2025
year: 2025
created: 2025-05-29
description: "VideoGameBench: VLMs struggle with 90s video games, showing limitations in perception and navigation."
tags:
  - "VisionLanguageModels"
  - "VideoGames"
  - "Benchmark"
  - "VLMs"
  - "AI"
  - "RealTime"
  - "Navigation"
type: "ArXiv"
BibTeX (AI Generated): "@article{Zhang2025,  author = {Zhang, Alex L. and Griffiths, Thomas L. and Narasimhan, Karthik R. and Press, Ofir},  title = {VideoGameBench: Can Vision-Language Models complete popular video games?},  year = {2025},  journal = {arXiv},  volume = {2505.18134}}"
citations: NaN
---
# Summary

VideoGameBench introduces a benchmark of 10 video games from the 1990s to evaluate vision-language models (VLMs). VLMs struggle to complete the games, highlighting limitations in perception, navigation, and memory. A paused version, VideoGameBench Lite, shows slight improvement.

----
# Article

VideoGameBench: Can Vision-Language Models complete popular video games?

Vision-language models (VLMs) have achieved strong results on coding and math benchmarks that are challenging for humans, yet their ability to perform tasks that come naturally to humans--such as perception, spatial navigation, and memory management--remains understudied. Real video games are crafted to be intuitive for humans to learn and master by leveraging innate inductive biases, making them an ideal testbed for evaluating such capabilities in VLMs. To this end, we introduce VideoGameBench, a benchmark consisting of 10 popular video games from the 1990s that VLMs directly interact with in real-time. VideoGameBench challenges models to complete entire games with access to only raw visual inputs and a high-level description of objectives and controls, a significant departure from existing setups that rely on game-specific scaffolding and auxiliary information. We keep three of the games secret to encourage solutions that generalize to unseen environments. Our experiments show that frontier vision-language models struggle to progress beyond the beginning of each game. We find inference latency to be a major limitation of frontier models in the real-time setting; therefore, we introduce VideoGameBench Lite, a setting where the game pauses while waiting for the LM's next action. The best performing model, Gemini 2.5 Pro, completes only 0.48% of VideoGameBench and 1.6% of VideoGameBench Lite. We hope that the formalization of the human skills mentioned above into this benchmark motivates progress in these research directions.
