<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Encoders/poss_state_encoded.md -->

# Possible State Encoder

This encoder provides a mapping from discrete environment states to unique vector or tensor representations. It is suitable for environments with a finite set of possible states.

## Class: `StateEncoder`
- Assigns a unique index to each observed state.
- Supports both index-based and one-hot encoding.
- Efficient for small to moderate state spaces.

### Example Usage
```python
from elsciRL.encoders.poss_state_encoded import StateEncoder

num_states = 100
encoder = StateEncoder(num_states)

state = '2_3'  # Example state string
encoded = encoder.encode(state, indexed=True)
print(encoded.shape)  # Output: (num_states,)
```

---
