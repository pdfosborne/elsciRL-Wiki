---
cite: "zhang2023reward"
title: "alexzhang13/reward-shaping-rl"
url: "https://github.com/alexzhang13/reward-shaping-rl"
authors:
  - "alexzhang13"
publisher: "github"
site: "github"
published: Unavailable
year: 2023
created: 2025-06-11
description: "Reward shaping with LLM feedback for RL using gym environments. Includes training and evaluation scripts."
tags:
  - "rewardshaping"
  - "reinforcementlearning"
  - "LLM"
  - "gym"
  - "python"
  - "DQN"
  - "PPO"
type: "WebArticle"
BibTeX (AI Generated): "@misc{zhang2023reward,  author = {alexzhang13},  title = {reward-shaping-rl},  url = {https://github.com/alexzhang13/reward-shaping-rl},  year = {2023}}"
citations: 0
---
# Summary

This repository explores simple reward shaping with LLM feedback for RL, using gym environments like MountainCarv0 and Pokemon Showdown. It uses OpenAI APIs to generate shaped reward functions. Models include tabular Q-learning, PPO, and DQN. Training scripts and evaluation methods are provided.

----
# Article

# Simple Reward Shaping with LLM Feedback for RL

This repository provides a framework for using LLMs in generic RL (gym) environments, like MountainCarv0 and Pokemon Showdown (poke-env).

## Setup

1.  Set up the Pokemon Showdown server:

    ```bash
    git clone https://github.com/smogon/pokemon-showdown.git
    cd pokemon-showdown
    npm install
    cp config/config-example.js config/config.js
    node pokemon-showdown start --no-security
    ```

2.  Set up poke\_env and related libraries:

    ```bash
    conda create -n \\"reward_shaping\\" python=3.8
    pip install -e .
    ```

## The General Method

Reward shaping introduces an extra intrinsic reward, independent of the environment API, to the model. This reward is a function of (state, action, next state).

### Reward Shaping + Reward Shaping w/ LLMs

This project uses OpenAI APIs to generate a shaped reward function. An example:

```python
def reward(prev_battle_state, next_battle_state):
    prev_fainted = [mon for mon in prev_battle_state.opponent_team.values() if mon.fainted]
    next_fainted = [mon for mon in next_battle_state.opponent_team.values() if mon.fainted]
    
    prev_total_hp = sum([mon.current_hp for mon in prev_battle_state.opponent_team.values()])
    next_total_hp = sum([mon.current_hp for mon in next_battle_state.opponent_team.values()])
    
    reward_defeat = len(next_fainted) - len(prev_fainted)
    reward_damage = (prev_total_hp - next_total_hp) / 1000.0
    
    return reward_defeat + reward_damage
```

### Models

*   Tabular Q-learning (for MountainCarv0)
*   PPO (stable\_baselines implementation)
*   DQN/double DQN (custom implementation)

### Training and Evaluation

Training scripts:

```bash
bash scripts/run_{model}_m{k}.sh
```

where model is either {dqn,ppo} and k is in {1,2,3}.

Evaluation scripts:

```bash
python cross_evaluate.py
python self_play.py
```
