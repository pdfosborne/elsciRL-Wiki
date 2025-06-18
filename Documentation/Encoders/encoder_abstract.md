<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Encoders/encoder_abstract.md -->

# Encoder Abstract (elsciRL)

This module defines the abstract base class for all encoders in elsciRL. Encoders are responsible for transforming environment states, actions, or objects into vector or tensor representations suitable for RL agents.

## Abstract Base Class: `Encoder`

- All encoders inherit from `Encoder`, which requires the implementation of the `encode` method.
- The `encode` method should return a PyTorch `Tensor` representation of the input.

### Example Usage
```python
from elsciRL.encoders.encoder_abstract import Encoder

class MyEncoder(Encoder):
    def encode(self, state, **kwargs):
        # Custom encoding logic
        return my_tensor
```

## StateEncoder
- A concrete implementation for encoding discrete states, with optional caching for efficiency.

---
