---
author: Philip Osborne
published: 2025-01-28
last edited: 2025-02-05
tags:
  - RL-Agents
  - Foundation
---

# Introduction

In order to make good decisions the agent must include a mechanism for choosing actions. This entails two components: 1) storage of knowledge (i.e. within a table or neural network weights) and, 2) sampling an optimal action.

The simplest approach for choosing actions based on the current knowledge is the *epsilon-greedy* method. Specifically, an action is selected randomly with probability epsilon and greedy otherwise. Greedy in this case means taking the action with the highest value in the current calculations. The reason random actions are included is to enable the agent to continue to explore and find a better path to the goal.

An analysis of action selection methods used in recent Text Game methodologies is specified later in Section \ref{sec:TG-agent_archi}, Table \ref{tab:Models}.
