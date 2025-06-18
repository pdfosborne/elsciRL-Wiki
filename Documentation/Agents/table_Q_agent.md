<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Agents/table_Q_agent.md -->

# Table Q-Learning Agent

The Table Q-Learning Agent implements a classic tabular Q-learning algorithm for discrete state and action spaces. It inherits from `QLearningAgent` and is suitable for environments where the state and action spaces are small enough to store a Q-table in memory.

## Key Features
- Maintains a Q-table mapping state-action pairs to Q-values.
- Uses an epsilon-greedy policy for exploration vs. exploitation.
- Supports saving and loading Q-tables.
- Tracks statistics such as total Q-value, number of known state-action pairs, and zero-valued entries.

## Main Methods
- `policy(state: Tensor, legal_actions: list) -> str`: Selects an action using an epsilon-greedy strategy based on the current Q-table.
- `learn(state: Tensor, next_state: Tensor, r_p: float, action_code: str) -> float`: Updates the Q-table using the Q-learning update rule.
- `save() -> List[dict]`: Saves the Q-table and related statistics.
- `load(saved_agent: List[dict])`: Loads a saved Q-table.
- `exploration_parameter_reset()`: Resets epsilon to its initial value.
- `clone()`: Returns a deep copy of the agent.
- `q_result()`: Summarizes Q-table statistics.

## Usage
This agent is ideal for small, discrete environments such as grid worlds, simple games, or educational tasks where the state and action spaces are not prohibitively large.

---