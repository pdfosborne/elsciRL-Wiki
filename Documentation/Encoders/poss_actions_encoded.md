<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Encoders/poss_actions_encoded.md -->

# Possible Actions Encoder

This encoder transforms the set of possible actions into a vector or tensor representation, indicating which actions are currently legal or available.

## Class: `PossibleActionsEncoder`
- Maps all possible actions to indices.
- Encodes the set of legal actions as a binary or one-hot vector.
- Useful for environments with a fixed action set.

### Example Usage
```python
from elsciRL.encoders.poss_actions_encoded import PossibleActionsEncoder

all_actions = ['left', 'right', 'up', 'down']
encoder = PossibleActionsEncoder(all_actions)

legal_actions = ['left', 'up']
encoded = encoder.encode(legal_actions=legal_actions)
print(encoded.shape)  # Output: (output_dim,)
```

---
