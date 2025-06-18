<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Agents/random_agent.md -->

# Random Agent

The Random Agent is a baseline agent that selects actions uniformly at random from the set of legal actions. It does not learn from experience and serves as a control or benchmark for evaluating other agents.

## Key Features
- Stateless: does not maintain or update any internal knowledge.
- Always selects a random action from the available legal actions.
- Provides a baseline for comparison with learning agents.

## Main Methods
- `policy(state: Tensor, legal_actions: list) -> str`: Returns a random action from the legal actions.
- `learn(state: Tensor, next_state: Tensor, r_p: float, action_code: str) -> float`: Does nothing (returns None).
- `q_result()`: Returns zero knowledge (total_q = 0, mean_q = 0).

## Usage
Use the Random Agent as a baseline to measure the performance of learning agents in any environment.

---