---
cite: "pokechamp2025"
title: "PokéChamp: an Expert-level Minimax Language Agent"
url: "https://arxiv.org/abs/2503.04094"
authors:
<<<<<<< HEAD
  - "Karten, Seth"
  - "Nguyen, Andy Luu"
  - "Jin, Chi"
=======
  - "Karten"
  - "Seth"
  - "Nguyen"
  - "Andy Luu"
  - "Jin"
  - "Chi"
>>>>>>> origin/main
publisher: "arXiv"
site: "arxiv"
published: 06/03/2025
year: 2025
created: 2025-03-09
description: "PokéChamp: LLM-powered Pokémon agent beats existing bots and rivals human players."
tags:
  - "LLM"
  - "Pokemon"
  - "AI"
  - "Minimax"
  - "Agent"
  - "GameTheory"
type: "ArXiv"
BibTeX (AI Generated): "@article{pokechamp2025,  author = {Karten, Seth and Nguyen, Andy Luu and Jin, Chi},  title = {Pok{\e}Champ: an Expert-level Minimax Language Agent},  year = {2025},  journal = {arXiv preprint arXiv:2503.04094},  url = {https://arxiv.org/abs/2503.04094v1}}"
citations:
---
# Summary

PokeChamp is a minimax agent powered by LLMs for Pokemon battles, achieving high win rates against existing bots and human players. It uses LLMs for action sampling, opponent modeling, and value function estimation without additional training. The work also includes a large Pokemon battle dataset and updated game engine.

----
# Article

# PokéChamp: An Expert-level Minimax Language Agent

We introduce PokéChamp, a minimax agent powered by Large Language Models (LLMs) for Pokémon battles. Built on a general framework for two-player competitive games, PokéChamp leverages the generalist capabilities of LLMs to enhance minimax tree search. Specifically, LLMs replace three key modules:

1.  Player action sampling
2.  Opponent modeling
3.  Value function estimation

enabling the agent to effectively utilize gameplay history and human knowledge to reduce the search space and address partial observability. Notably, our framework requires no additional LLM training.

We evaluate PokéChamp in the popular Gen 9 OU format. When powered by GPT-4o, it achieves a win rate of 76% against the best existing LLM-based bot and 84% against the strongest rule-based bot, demonstrating its superior performance. Even with an open-source 8-billion-parameter Llama 3.1 model, PokéChamp consistently outperforms the previous best LLM-based bot, Pokéllmon powered by GPT-4o, with a 64% win rate.

PokéChamp attains a projected Elo of 1300-1500 on the Pokémon Showdown online ladder, placing it among the top 30%-10% of human players. In addition, this work compiles the largest real-player Pokémon battle dataset, featuring over 3 million games, including more than 500k high-Elo matches. Based on this dataset, we establish a series of battle benchmarks and puzzles to evaluate specific battling skills. We further provide key updates to the local game engine.

We hope this work fosters further research that leverages Pokémon battle as benchmark to integrate LLM technologies with game-theoretic algorithms addressing general multiagent problems. Videos, code, and dataset available at https://sites.google.com/view/pokechamp-llm.
