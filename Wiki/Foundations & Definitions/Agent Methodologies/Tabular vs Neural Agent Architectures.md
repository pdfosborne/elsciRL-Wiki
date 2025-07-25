---
author: Philip Osborne
published: 2025-01-28
last edited: 2025-02-05
tags:
  - RL-Agents
  - Foundation
type: Foundation
---

# Tabular vs Neural Agent Architectures

Any reinforcement learning agent must include a method for language understanding. 

An agent which stores every state-action value in a large lookup table is known as a *tabular* agent and has the limitation that every state is considered unique. A tabular agent has no intrinsic methodology for leveraging the contextual information of language.  ^1c5f81

Therefore, *neural* (a.k.a deep) agents @mnih2013PlayingAtariDeep are introduced as they can transfer knowledge between similar states. 

To achieve this, a Deep-RL agent's architecture consists of two core components: 
1) **a state encoder** an encoder for transforming a state into a numeric form (typically vector)
2) **an action selection** method which enacts the agent's policy.

---
1: [[Wiki/References/Academic Papers/ArXiv/mnih2013PlayingAtariDeep|@mnih2013PlayingAtariDeep]]
