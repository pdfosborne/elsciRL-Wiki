# elsciRL LLM State Generator Adapter

## Summary

- **LLM adapters** in elsciRL enable RL agents to leverage language models for state representation and reasoning.
- The **abstract base class** defines the required interface.
- **OllamaAdapter** provides a practical implementation for local LLMs, supporting both raw and encoded outputs.
- Environment-specific adapters can translate numeric or symbolic states into rich language prompts for the LLM.
- This approach is ideal for environments where state information is complex, ambiguous, or best described in natural language.

## Overview

The LLM (Large Language Model) state generator adapters in `elsciRL` provide a flexible interface for transforming raw environment states and context into natural language descriptions using local LLMs (such as those served by Ollama). These adapters enable RL agents to interact with environments where state information is best represented or augmented by language, supporting both text-based and hybrid RL workflows.

## Abstract Base Class: `LLMAdapter`

The `LLMAdapter` is an abstract base class that defines the interface for all LLM-based adapters. It is responsible for:

- Managing the base prompt for the LLM.
- Defining the `_read` method for processing raw states.
- Providing a structure for concrete LLM adapters (such as `OllamaAdapter`).

### Key Methods

- **`__init__(self, base_prompt: str = None)`**  
  Initializes the adapter with a base prompt, which is prepended to all LLM queries.

- **`_read(raw_state) -> list`**  
  Abstract method. Reads and processes the raw state, returning a list of features.  
  *Must be implemented by subclasses.*

---

## Practical LLM Adapter Implementations

Below are examples of how the LLM adapter interface is implemented for different environments in elsciRL.

### 1. LLM Adapter for Sailing

This adapter translates numeric state variables (such as position and angle) into a descriptive language prompt, which is then passed to the LLM for further processing and encoding.

```python
from torch import Tensor
import numpy as np
from gymnasium.spaces import Box
from elsciRL.adapters.LLM_state_generators.text_ollama import OllamaAdapter

class Adapter:
    def __init__(self, setup_info:dict={}):
        self.observation_space = Box(low=-1, high=1, shape=(1,384), dtype=np.float32)
        self.LLM_adapter = OllamaAdapter(
            model_name=setup_info.get('model_name', 'llama3.2'),
            base_prompt=setup_info.get('system_prompt', 'You are sailing a boat.'),
            context_length=2000,
            action_history_length=setup_info.get('action_history_length', 5),
            encoder=setup_info.get('encoder', 'MiniLM_L6v2')
        )

    def adapter(self, state: str, legal_moves:list = None, episode_action_history:list = None, encode:bool=True, indexed: bool = False) -> Tensor:
        # Translate numeric state to language
        x = float(state.split('_')[0])
        angle = float(state.split('_')[1])
        # ... (logic to describe x and angle in language) ...
        L_state = "The boat is near the center, cutting the wind, on the port side."
        if episode_action_history and len(episode_action_history) > 0:
            last_action = episode_action_history[-1]
            # ... (logic to describe last action) ...
            L_state += " The last action was to turn towards the beach."
        # Use the LLM adapter to encode
        state_encoded = self.LLM_adapter.adapter(
            state=L_state,
            legal_moves=legal_moves,
            episode_action_history=episode_action_history,
            encode=encode,
            indexed=indexed
        )
        return state_encoded
```

### 2. LLM Adapter for Maze

This adapter generates a natural language description of the agent's position, the goal, and nearby walls, then uses the LLM to encode this description.

```python
from elsciRL.adapters.LLM_state_generators.text_ollama import OllamaAdapter
import numpy as np

class Adapter:
    def __init__(self, setup_info):
        self.LLM_adapter = OllamaAdapter(
            model_name=setup_info.get('model_name', 'llama3.2'),
            base_prompt=setup_info.get('system_prompt', 'You are navigating a maze.'),
            context_length=2000,
            action_history_length=setup_info.get('action_history_length', 5),
            encoder=setup_info.get('encoder', 'MiniLM_L6v2')
        )
        self.describe_mode = setup_info.get("describe_mode", "give_position")
        # ... (maze initialization logic) ...

    def describe_observation(self, maze, position, goal_position, move_history=None):
        # ... (logic to describe position, goal, and walls in language) ...
        return "The goal is at position 3, 3. Your current position is at position 1, 1. There is a wall to your right."

    def adapter(self, state, legal_moves=[], episode_action_history=[], encode=True, indexed=False):
        text_description = self.describe_observation(
            maze=self.maze,
            position=state,
            goal_position=self.goal,
            move_history=episode_action_history
        )
        state_encoded = self.LLM_adapter.adapter(
            state=text_description,
            legal_moves=legal_moves,
            episode_action_history=episode_action_history,
            encode=encode,
            indexed=indexed
        )
        return state_encoded
```

---

## OllamaAdapter: Example Implementation

The `OllamaAdapter` is a concrete implementation of `LLMAdapter` that interacts with a local Ollama LLM server. It supports:

- Building context-rich prompts including state, legal moves, and action history.
- Calling the Ollama API to generate a natural language description of the state.
- Encoding the LLM's response using a language encoder (e.g., MiniLM_L6v2).
- Returning either the raw or encoded state for agent consumption.

### Key Methods

- **`adapter(self, state, legal_moves=None, episode_action_history=None, encode=True, indexed=False)`**  
  - Builds a prompt from the current state, legal moves, and action history.
  - Calls the LLM to generate a description.
  - Optionally encodes the response for use with neural agents.

- **`sample(self, state=None)`**  
  - Generates and prints a sample adapted state, demonstrating both the raw and encoded outputs.

### Example Usage

```python
adapter = OllamaAdapter(base_prompt="Describe the environment state for an RL agent.")
state = "player at (2,3), goal at (5,5)"
legal_moves = ["up", "down", "left", "right"]
action_history = ["up", "right"]

# Get encoded state representation
encoded_state = adapter.adapter(state, legal_moves, action_history, encode=True)

# Get raw language description
raw_description = adapter.adapter(state, legal_moves, action_history, encode=False)
```

---
