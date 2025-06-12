---
cite: sung-park2023GenerativeAgents
title: "Generative Agents: Interactive Simulacra of Human Behavior"
url: https://dl.acm.org/doi/10.1145/3586183.3606763
authors: Joon Sung Park, Joseph O'Brien, Carrie Jun Cai, Meredith Ringel Morris, Percy Liang, Michael S. Bernstein
publisher: Association for Computing Machinery
site: acm
published: 2023-10-20
year: 2023
created: 2025-06-12
description: Generative agents simulate believable human behavior using large language models in an interactive environment.
tags:
  - GenerativeAgents
  - InteractiveSimulacra
  - HumanBehavior
  - Languagemodels
  - AISimulation
type: conferencePaper
BibTeX (AI Generated): "@inproceedings{generativeagents2023, author = {Joon Sung Park, Joseph O'Brien, Carrie Jun Cai, Meredith Ringel Morris, Percy Liang, Michael S. Bernstein}, title = {Generative Agents: Interactive Simulacra of Human Behavior}, year = {2023}, publisher = {Association for Computing Machinery}, booktitle = {UIST '23: Proceedings of the 36th Annual ACM Symposium on User Interface Software and Technology}, doi = {10.1145/3586183.3606763},}"
citations: 503
arxiv: https://arxiv.org/abs/2304.03442
code: https://github.com/joonspk-research/generative_agents
DOI: "3586183.3606763"
---
# Summary

This paper introduces generative agents, computational software agents that simulate believable human behavior. They use a large language model to store experiences, synthesize memories, and plan behavior in an interactive sandbox environment. Evaluation shows believable individual and emergent social behaviors.

----

# Generative Agents: Interactive Simulacra of Human Behavior

Believable proxies of human behavior can empower interactive applications ranging from immersive environments to rehearsal spaces for interpersonal communication to prototyping tools. In this paper, we introduce generative agents: computational software agents that simulate believable human behavior. Generative agents wake up, cook breakfast, and head to work; artists paint, while authors write; they form opinions, notice each other, and initiate conversations; they remember and reflect on days past as they plan the next day. To enable generative agents, we describe an architecture that extends a large language model to store a complete record of the agent’s experiences using natural language, synthesize those memories over time into higher-level reflections, and retrieve them dynamically to plan behavior. We instantiate generative agents to populate an interactive sandbox environment inspired by The Sims, where end users can interact with a small town of twenty-five agents using natural language. In an evaluation, these generative agents produce believable individual and emergent social behaviors. For example, starting with only a single user-specified notion that one agent wants to throw a Valentine’s Day party, the agents autonomously spread invitations to the party over the next two days, make new acquaintances, ask each other out on dates to the party, and coordinate to show up for the party together at the right time. We demonstrate through ablation that the components of our agent architecture—observation, planning, and reflection—each contribute critically to the believability of agent behavior. By fusing large language models with computational interactive agents, this work introduces architectural and interaction patterns for enabling believable simulations of human behavior.