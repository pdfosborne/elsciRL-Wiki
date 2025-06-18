<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Interaction_Loops/standard.md -->

# Standard Interaction Loop (elsciRL)

This module provides the `StandardInteractionLoop` class, which implements the core episode loop for running RL agents in elsciRL environments. It is responsible for managing agent-environment interactions, tracking results, handling sub-goals, and supporting rendering for visualization.

## Main Class: `StandardInteractionLoop`

### Features
- Handles agent-environment interaction for each episode
- Supports both training and testing phases
- Integrates with adapters for state representation (numeric, language, LLM, etc.)
- Tracks rewards, actions, and timing for each episode
- Supports sub-goal and multi-goal reward structures
- Can render episodes as GIFs for qualitative analysis

### Key Methods
- `__init__(Engine, Adapters, local_setup_info)`: Initializes the environment, agent, adapters, and configuration for the loop
- `episode_loop(render=False, render_save_dir=None)`: Runs the main episode loop, collects results, and optionally renders the episode

## Usage Example

The `StandardInteractionLoop` is used internally by the `Experiment` class in elsciRL. A typical workflow is:

```python
from elsciRL.experiments.standard import Experiment

# ... (set up Config, ProblemConfig, Engine, Adapters, etc.) ...

exp = Experiment(Config, ProblemConfig, Engine, Adapters, save_dir, show_figures, window_size)
exp.train()   # This will use StandardInteractionLoop for agent-environment interaction
exp.test()
```

If you want to use the interaction loop directly:

```python
from elsciRL.interaction_loops.standard import StandardInteractionLoop

loop = StandardInteractionLoop(Engine, Adapters, local_setup_info)
results = loop.episode_loop(render=True, render_save_dir='output/renders')
```

## Output
- Returns a results table with per-episode statistics (reward, actions, timing, etc.)
- Optionally saves a GIF of the rendered episode if `render=True`

---
