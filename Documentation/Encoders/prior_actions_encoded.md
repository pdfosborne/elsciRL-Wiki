<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Encoders/prior_actions_encoded.md -->

# Prior Actions Encoder

This encoder represents the sequence of actions taken so far in an episode as a vector or tensor. It is useful for agents that need to reason about action history (e.g., in partially observable environments).

## Class: `PriorActionsEncoder`
- Maps all possible actions to indices.
- Encodes the action history as a vector, preserving order.
- Supports both indexed and one-hot (flattened) representations.

### Example Usage
```python
from elsciRL.encoders.prior_actions_encoded import PriorActionsEncoder

all_actions = ['left', 'right', 'up', 'down']
encoder = PriorActionsEncoder(all_actions)

episode_action_history = ['left', 'up', 'right']
encoded = encoder.encode(episode_action_history=episode_action_history)
print(encoded.shape)  # Output: (output_dim,)
```

---
