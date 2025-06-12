---
author:
  - Philip Osborne
published: 2025-01-28
last edited: 2025-02-05
tags:
  - Instructions
  - Human
  - Foundation
type: Foundation
---

---

# Learning from Human Feedback

The work in \cite{Christiano:RLHuman-Prefences} scale up human feedback for deep Reinforcement Learning building upon prior works in RL from human ratings or rankings. Their work focused on the case where the environment did not provide a reward signal. Instead, human feedback was used to infer a preference for trajectories (sequence of observations and actions) to infer the goal. The qualitative evaluation of the trajectories was used: \textit{ ``we start from a goal expressed in natural language, ask a human to evaluate the agent’s behavior based on how well it fulfills that goal, and then present videos of agents attempting to fulfill that goal."}

Following this, \cite{Ibarz:RLHuman-Prefences} addressed two notable issues by incorporating imitation learning from expert demonstrations, these achieved this by:

 1. It is hard to obtain a good state space coverage with just random exploration guided by preferences. If the state space distribution is bad, then the diversity of the trajectory that we request preferences for is low and thus the human in the loop cannot convey meaningful information to the agent.
 2. Preferences are an inefficient way of soliciting information from humans, providing only a few hundred bits per hour per human.

Most recently \cite{ouyang:InstructGPT} used human feedback in their InstructGPT algorithm to enable fine-tuning of a large language model to individual human intent. 

---
