<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Encoders/observable_objects_encoded.md -->

# Observable Objects Encoder

This encoder transforms a list of observable objects in the environment into a vector or tensor representation. It is useful for environments where the state is described by the presence or type of objects (e.g., pieces on a chessboard).

## Class: `ObjectEncoder`
- Maps each object to a unique index.
- Encodes the state as a tensor, where each entry represents the occurrence of an object type.
- Supports both indexed and one-hot (flattened) representations.

### Example Usage
```python
from elsciRL.encoders.observable_objects_encoded import ObjectEncoder

local_objects = ['pawn', 'knight', 'bishop', 'rook', 'queen', 'king']
encoder = ObjectEncoder(local_objects)

state = ['pawn', 'pawn', 'knight', 'empty', 'king']
encoded = encoder.encode(state)
print(encoded.shape)  # Output: (output_dim,)
```

---
