---
cite: "LLMPOET"
title: "LLM-POET: Evolving Complex Environments using Large Language Models | Proceedings of the Genetic and Evolutionary Computation Conference Companion"
url: "https://dl.acm.org/doi/10.1145/3638530.3654115"
authors:
publisher: "Association for Computing Machinery"
site: "acm"
published: 01/08/2024
year: 2024
created: 2025-06-11
description: "LLM-POET uses LLMs to create complex, diverse environments, improving co-evolution performance."
tags:
  - "LLMPOET"
  - "OpenEndedEvolution"
  - "LargeLanguageModels"
  - "POETAlgorithm"
  - "EvolutionGym"
type: "Conference Paper"
BibTeX (AI Generated): "@inproceedings{LLMPOET,  title={LLM-POET: Evolving Complex Environments using Large Language Models},  year={2024},  publisher={Association for Computing Machinery}}"
citations: 1
---
# Summary

The paper introduces LLM-POET, a modification of the POET algorithm using Large Language Models (LLM) for environment creation and mutation. It demonstrates that LLMs can generate complex and diverse environments, leading to improved performance in co-evolution compared to CPPNs.

----
# Article

# LLM-POET: Evolving Complex Environments using Large Language Models | Proceedings of the Genetic and Evolutionary Computation Conference Companion

## Abstract

Creating systems capable of generating virtually infinite variations of complex and novel behaviour without predetermined goals or limits is a major challenge in the field of AI. This challenge has been addressed through the development of several open-ended algorithms that can continuously generate new and diverse behaviours, such as the POET and Enhanced-POET algorithms for co-evolving environments and agent behaviour. One of the challenges with existing methods however, is that they struggle to continuously generate complex environments. In this work, we propose LLM-POET, a modification of the POET algorithm where the environment is both created and mutated using a Large Language Model (LLM). By fine-tuning a LLM with text representations of Evolution Gym environments and captions that describe the environment, we were able to generate complex and diverse environments using natural language. We found that not only could the LLM produce a diverse range of environments, but compared to the CPPNs used in Enhanced-POET for environment generation, the LLM allowed for a 34% increase in the performance gain of co-evolution. This increased performance suggests that the agents were able to learn a more diverse set of skills by training on more complex environments.

## References

[1] Bowen Baker, Ingmar Kanitscheider, Todor Markov, Yi Wu, Glenn Powell, Bob McGrew, and Igor Mordatch. 2019. Emergent tool use from multi-agent autocurricula. *arXiv preprint arXiv:1909.07528* (2019).

[2] Jagdeep Bhatia, Holly Jackson, Yunsheng Tian, Jie Xu, and Wojciech Matusik. 2021. Evolution Gym: A Large-Scale Benchmark for Evolving Soft Robots. *Advances in Neural Information Processing Systems* 34 (2021), 2201--2214.

[3] Herbie Bradley, Andrew Dai, Hannah Teufel, Jenny Zhang, Koen Oostermeijer, Marco Bellagente, Jeff Clune, Kenneth Stanley, Grégory Schott, and Joel Lehman. 2023. Quality-Diversity through AI Feedback. *arXiv preprint arXiv:2310.13032* (2023).

[4] Jonathan C. Brant and Kenneth O. Stanley. 2017. Minimal Criterion Coevolution: A New Approach to Open-Ended Search. In *Proceedings of the Genetic and Evolutionary Computation Conference (GECCO '17).*

[5] Jonathan C. Brant and Kenneth O. Stanley. 2020. Diversity Preservation in Minimal Criterion Coevolution through Resource Limitation. In *Proceedings of the 2020 Genetic and Evolutionary Computation Conference (GECCO '20).*

[6] Joel Lehman and Kenneth O. Stanley. 2011. Abandoning Objectives: Evolution Through the Search for Novelty Alone. *Evolutionary Computation* 19, 2 (06 2011), 189--223.

[7] Joel Lehman and Kenneth O. Stanley. 2021. Evolving a diversity of virtual creatures through novelty search and local competition. In *Proc. of the 13th Annual Conference on Genetic and Evolutionary Computation (GECCO '11).*

[8] Jean-Baptiste Mouret and Jeff Clune. 2015. Illuminating search spaces by mapping elites. *arXiv preprint arXiv:1504.04909* (2015).

[9] Mizuki Oka, Takumi Saito, and Takeshi Shimada. 2023. *Open-ended Evolutionary Algorithms in Python.* O'Reilly.

[10] S Sudhakaran, M González-Duque, C Glanois, M Freiberger, E Najarro, and S Risi. 2023. MarioGPT: open-ended text2level generation through large language models. *arXiv preprint arxiv:2302.05981* (2023).

[11] Rui Wang, Joel Lehman, Jeff Clune, and Kenneth O Stanley. 2019. Paired open-ended trailblazer (poet): Endlessly generating increasingly complex and diverse learning environments and their solutions. *arXiv preprint arXiv:1901.01753* (2019).

[12] Rui Wang, Joel Lehman, Aditya Rawal, Jiale Zhi, Yulun Li, Jeffrey Clune, and Kenneth Stanley. 2020. Enhanced poet: Open-ended reinforcement learning through unbounded invention of learning challenges and their solutions. In *International Conference on Machine Learning.*
