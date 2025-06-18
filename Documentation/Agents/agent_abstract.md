<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Agents/agent_abstract.md -->

# elsciRL Agent Abstract Classes

This document describes the abstract agent interfaces in elsciRL, which define the core API for all agent types.

## Abstract Base Class: `Agent`

All agents in elsciRL inherit from the `Agent` abstract base class. This class defines the essential methods that any agent must implement:

### Methods
- `policy(**kwargs) -> str`: Abstract method. Returns the agent's action given the current state and other parameters. Must be implemented by all subclasses.
- `learn(**kwargs) -> str`: Optional. Updates the agent's internal state based on experience. Can be overridden by subclasses.

## QLearningAgent

A specialization of `Agent` for Q-learning-based agents. It defines the following methods:

- `policy(state: Tensor, game_over: bool, legal_actions: list, **kwargs) -> Hashable`: Returns the action to take given the current state and legal actions.
- `learn(state: Tensor, action: Hashable, next_state: Iterable[Any], immediate_reward: float, **kwargs)`: Updates the agent's Q-values based on the transition.

## LLMAgentAbstract

A specialization of `Agent` for language-based agents (LLMs). It defines the following methods:

- `policy(state: str, legal_actions: list, **kwargs) -> str`: Returns the action as a string, given the current state and legal actions.
- `learn(state: str, action: str, next_state: str, reward: float, **kwargs) -> str`: Updates the agent's internal state based on the language-based transition.

---

All concrete agents in elsciRL (e.g., DQN, Table Q-Learning, RandomAgent, LLM-based agents) inherit from these abstract classes and implement their own logic for policy selection and learning.