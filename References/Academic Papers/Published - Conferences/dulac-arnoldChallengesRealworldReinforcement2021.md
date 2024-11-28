---
cite: dulac-arnoldChallengesRealworldReinforcement2021 
title: Challenges of real-world reinforcement learning - definitions, benchmarks and analysis
year: 2021
tags: [RL, EvaluationProtocol, Survey, AppliedReinforcementLearning, RealWorld]
authors: Gabriel Dulac-Arnold, Nir Levine, Daniel J. Mankowitz, Jerry Li, Cosmin Paduraru, Sven Gowal, Todd Hester
citations: 271 citations (Semantic Scholar/DOI) [2024-04-23]
publisher: Machine Learning
url: https://doi.org/10.1007/s10994-021-05961-4
DOI: 10.1007/s10994-021-05961-4
type: journalArticle
---

## Abstract 
Reinforcement learning (RL) has proven its worth in a series of artificial domains, and is beginning to show some successes in real-world scenarios. However, much of the research advances in RL are hard to leverage in real-world systems due to a series of assumptions that are rarely satisfied in practice. In this work, we identify and formalize a series of independent challenges that embody the difficulties that must be addressed for RL to be commonly deployed in real-world systems. For each challenge, we define it formally in the context of a Markov Decision Process, analyze the effects of the challenge on state-of-the-art learning algorithms, and present some existing attempts at tackling it. We believe that an approach that addresses our set of proposed challenges would be readily deployable in a large number of real world problems. Our proposed challenges are implemented in a suite of continuous control environments called realworldrl-suite which we propose an as an open-source benchmark.


---
## Notes

<mark class="customZot-Blue ">At a high level these challenges are: 1. Being able to learn on live systems from limited samples.  2. Dealing with unknown and potentially large delays in the system actuators, sensors, or rewards.  3. Learning and acting in high-dimensional state and action spaces.  4. Reasoning about system constraints that should never or rarely be violated.  5. Interacting with systems that are partially observable, which can alternatively be viewed as systems that are non-stationary or stochastic.  6. Learning from multi-objective or poorly specified reward functions.  7. Being able to provide actions quickly, especially for systems requiring low latencies.  8. Training off-line from the fixed logs of an external behavior policy.  9. Providing system operators with explainable policies.</mark>
 >


---
## Bibliography

```bibtex
@article{Dulac-Arnold_Levine_Mankowitz_Li_Paduraru_Gowal_Hester_2021, title={Challenges of real-world reinforcement learning - definitions, benchmarks and analysis}, volume={110}, ISSN={1573-0565}, DOI={[10.1007/s10994-021-05961-4](https://doi.org/10.1007/s10994-021-05961-4)}, abstractNote={Reinforcement learning (RL) has proven its worth in a series of artificial domains, and is beginning to show some successes in real-world scenarios. However, much of the research advances in RL are hard to leverage in real-world systems due to a series of assumptions that are rarely satisfied in practice. In this work, we identify and formalize a series of independent challenges that embody the difficulties that must be addressed for RL to be commonly deployed in real-world systems. For each challenge, we define it formally in the context of a Markov Decision Process, analyze the effects of the challenge on state-of-the-art learning algorithms, and present some existing attempts at tackling it. We believe that an approach that addresses our set of proposed challenges would be readily deployable in a large number of real world problems. Our proposed challenges are implemented in a suite of continuous control environments called realworldrl-suite which we propose an as an open-source benchmark.}, note={271 citations (Semantic Scholar/DOI) [2024-04-23]}, number={9}, journal={Machine Learning}, author={Dulac-Arnold, Gabriel and Levine, Nir and Mankowitz, Daniel J. and Li, Jerry and Paduraru, Cosmin and Gowal, Sven and Hester, Todd}, year={2021}, month=sep, pages={2419–2468}, language={en} }
```
