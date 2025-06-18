# elsciRL Adapters: Abstract Form Documentation

## Overview

Adapters in `elsciRL` provide a standardized interface for transforming raw environment states into a form suitable for reinforcement learning (RL) agents. This abstraction allows for flexible integration of various state representations, including numeric, symbolic, or language-based forms (e.g., via LLMs).

## Abstract Base Class: `StateAdapter`

All adapters inherit from the abstract base class `StateAdapter`, which defines the core interface and expected methods for any state adapter implementation.

### Key Methods

- **`__init__(self, raw_state)`**  
  Initializes the adapter with a raw state and processes it using the `_read` method.

- **`_read(raw_state) -> list`**  
  Abstract method. Reads and processes the raw state, returning a list of features.  
  *Must be implemented by subclasses.*

- **`adapter(self, state, legal_moves=None, episode_action_history=None, encode=True, indexed=False)`**  
  Returns the adapted state. May include options for encoded or non-encoded output, and for indexed representations.  
  *Should be overridden by subclasses.*

- **`sample(self)`**  
  Returns a sample adapted state, typically representing an initial environment state.  
  *Should be overridden by subclasses.*

### Example Abstract Adapter

```python
from abc import ABC, abstractmethod

class Adapter(ABC):
    def __init__(self, raw_state):
        super().__init__()
        self.state: list = self._read(raw_state)

    @abstractmethod
    def _read(raw_state) -> list:
        raise NotImplementedError

    def adapter(self, state, legal_moves=None, episode_action_history=None, encode=True, indexed=False):
        # Return the adapted state (to be implemented in subclass)
        pass

    def sample(self):
        # Return a sample adapted state (to be implemented in subclass)
        pass
```

---

## Practical Adapter Implementations

Below are examples of how the abstract adapter interface is implemented for different environments in elsciRL.

### 1. Tabular State Adapter (TextWorldExpress Example)

```python
from elsciRL.encoders.poss_state_encoded import StateEncoder
import torch

class Adapter:
    _cached_state_idx = dict()

    def __init__(self, setup_info={}):
        all_possible_states = [i for i in range(4*4)]
        self.encoder = StateEncoder(all_possible_states)

    def adapter(self, state, legal_moves=None, episode_action_history=None, encode=True, indexed=False):
        if encode:
            state_encoded = self.encoder.encode(state=state)
        else:
            state_encoded = state

        if indexed:
            state_indexed = []
            for sent in state:
                if sent not in Adapter._cached_state_idx:
                    Adapter._cached_state_idx[sent] = len(Adapter._cached_state_idx)
                state_indexed.append(Adapter._cached_state_idx[sent])
            state_encoded = torch.tensor(state_indexed)

        return state_encoded
```

### 2. Grid State Adapter (Classroom Example)

```python
from elsciRL.encoders.poss_state_encoded import StateEncoder
from gymnasium.spaces import Discrete
import torch

class Adapter:
    _cached_state_idx = dict()

    def __init__(self, setup_info={}):
        self.x_range = [0,1,2,3,4,5]
        self.y_range = [0,1,2,3,4,5]
        possible_states = [str(x)+'_'+str(y) for x in self.x_range for y in self.y_range]
        self.encoder = StateEncoder(len(possible_states))
        self.observation_space = Discrete(len(possible_states))

    def adapter(self, state, legal_moves=None, episode_action_history=None, encode=True, indexed=False):
        if encode:
            state_encoded = self.encoder.encode(state=state)
        else:
            state_encoded = state

        if indexed:
            state_indexed = []
            for sent in state:
                if sent not in Adapter._cached_state_idx:
                    Adapter._cached_state_idx[sent] = len(Adapter._cached_state_idx)
                state_indexed.append(Adapter._cached_state_idx[sent])
            state_encoded = torch.tensor(state_indexed)

        return state_encoded
```

### 3. Continuous/Discretized State Adapter (Sailing Example)

```python
from elsciRL.encoders.poss_state_encoded import StateEncoder
from gymnasium.spaces import Discrete
import numpy as np
import torch

class Adapter:
    @staticmethod
    def angle_to_state(angle):
        return int(30 * ((angle + np.pi) / (2 * np.pi) % 1))

    @staticmethod
    def x_to_state(x):
        return int(40 * ((x + -10) / 20))

    @staticmethod
    def state_discretizer(state):
        x = float(state.split('_')[0])
        x_state = Adapter.x_to_state(x)
        angle = float(state.split('_')[1])
        angle_state = Adapter.angle_to_state(angle)
        return str(x_state)+'_'+str(angle_state)

    _cached_state_idx = dict()

    def __init__(self, setup_info={}):
        num_x_states = 10*2
        num_angle_states = 30
        self.num_states = num_x_states*(10**setup_info['obs_precision']) * num_angle_states
        self.observation_space = Discrete(2000*30)
        self.one_hot_encoder = StateEncoder(self.num_states)
        self.index_encoder = {}
        self.encoder_idx = 0

    def adapter(self, state, legal_moves=None, episode_action_history=None, encode=True, indexed=False):
        #state = Adapter.state_discretizer(state)
        if encode:
            if indexed:
                state_encoded = self.one_hot_encoder.encode(state=state, legal_actions=legal_moves, episode_action_history=episode_action_history, indexed=indexed)
            else:
                if state not in self.index_encoder:
                    state_encoded = torch.tensor([self.encoder_idx]).float()
                    self.index_encoder[state] = state_encoded
                    self.encoder_idx += 1
                else:
                    state_encoded = self.index_encoder[state]
        else:
            state_encoded = state
        return state_encoded
```

---

## Summary

- **Adapters** in elsciRL provide a consistent interface for transforming environment states for RL agents.
- The **abstract base class** defines the required methods and structure.
- **Concrete implementations** adapt the interface for specific environments, handling encoding, indexing, and feature extraction as needed.
- This design supports both simple tabular and complex, high-dimensional or language-based state representations.