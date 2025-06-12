---
cite: "yang2025"
title: "LLM-Guided Reinforcement Learning for Interactive Environments"
url: "https://www.mdpi.com/2227-7390/13/12/1932"
authors:
  - "Fuxue Yang"
  - "Jiawen Liu"
  - "Kan Li"
publisher: "mdpi"
site: "mdpi"
published: 10/06/2025
year: 2025
created: 2025-06-11
description: "LGRL uses LLMs to decompose tasks for RL agents, improving efficiency and convergence in interactive environments."
tags:
  - "reinforcementlearning"
  - "largelanguagemodels"
  - "chainofthought"
type: "Journal Paper"
BibTeX (AI Generated): "@article{Yang2025,  author    = {Fuxue Yang and Jiawen Liu and Kan Li},  title     = {LLM-Guided Reinforcement Learning for Interactive Environments},  journal   = {Mathematics},  volume    = {13},  number    = {12},  pages     = {1932},  year      = {2025},  doi       = {10.3390/math13121932},  publisher = {MDPI}}"
citations: 0
---
# Summary

LLM-Guided Reinforcement Learning (LGRL) decomposes high-level objectives into subgoals in interactive environments, improving efficiency and convergence.

----
# Article

# LLM-Guided Reinforcement Learning for Interactive Environments

This article proposes LLM-Guided Reinforcement Learning (LGRL), a framework using large language models (LLMs) to break down complex objectives into manageable subgoals in interactive environments.

LGRL decouples high-level planning from low-level action execution by generating context-aware subgoals that guide a reinforcement learning (RL) agent. During training, intermediate subgoals, associated with partial rewards, are created based on the agent's progress. This approach facilitates structured exploration and accelerates convergence.

At inference, a chain-of-thought strategy is used, allowing the LLM to adapt subgoals in response to evolving environmental states. The method is demonstrated in an interactive setting and is generalizable to various complex, goal-oriented tasks.

Experimental results show that LGRL achieves higher success rates, improved efficiency, and faster convergence compared to baseline approaches.

## Key Contributions:

*   Hierarchical Task Decomposition: LLM planner generates subgoals, and a modular RL executor translates these into actions.
*   Zero-Shot LLM Utilization: Operates via generic prompts.
*   Progress-Aware Rewards: Reward mechanism for each LLM-generated subgoal upon completion.
*   LGRL is validated on interactive tasks derived from the Minigrid environment.

## Methods

The framework uses LLMs (like DeepSeek V3) to decompose high-level missions into subgoals. This is evaluated in Minigrid, a 2D grid-based environment where the agent operates with a discrete action space and receives visual observations and a textual mission.

## Experiments

LGRL was evaluated on Minigrid environments with a multi-step curriculum. Results show that LGRL achieves higher success rates, improved efficiency, and faster convergence compared to baseline approaches.
