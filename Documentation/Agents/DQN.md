<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Agents/DQN.md -->

# DQN Agent

The DQN (Deep Q-Network) Agent implements a neural network-based Q-learning algorithm for environments with large or continuous state spaces. It inherits from `QLearningAgent` and uses deep learning to approximate the Q-value function.

## Key Features
- Utilizes a neural network to estimate Q-values for each action.
- Employs experience replay (memory buffer) for stable training.
- Maintains separate policy and target networks for improved learning stability.
- Supports epsilon-greedy exploration with decay.
- Can save and load model weights and optimizer state.

## Main Methods
- `policy(state: torch.Tensor, legal_actions: list, **kwargs) -> Hashable`: Selects an action using an epsilon-greedy strategy based on the Q-network's output.
- `learn(state: torch.Tensor, next_state: torch.Tensor, immediate_reward: float, action: Hashable, **kwargs)`: Stores experience and trains the network using mini-batch updates.
- `save() -> List[Dict]`: Saves the model and optimizer state.
- `load(saved_agent: List[Dict])`: Loads the model and optimizer state.
- `exploration_parameter_reset()`: Resets epsilon to its initial value.
- `clone()`: Returns a deep copy of the agent.

## Usage
The DQN agent is suitable for complex environments where tabular methods are infeasible, such as video games, robotics, or any domain with high-dimensional observations.

---