<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Environment_Setup/elsciRL_info.md -->

# elsciRLInfo Utility (elsciRL)

This module provides the `elsciRLInfo` class, which is used for tracking observed states and experience samples during RL agent-environment interaction. It is especially useful for unsupervised learning, experience replay, and analysis of state-action transitions.

## Main Class: `elsciRLInfo`

### Features
- Tracks observed states and their adapted (e.g., language) representations
- Stores and updates experience samples (state, action, next state, reward, termination)
- Provides methods to retrieve legal actions and sample transitions from experience
- Supports both tensor and array-like state representations

### Key Methods
- `observed_state_tracker(engine_observation, language_state)`: Records a new observed state and its adapted form
- `experience_sampling_add(engine_observation, action, next_observation, reward, terminated)`: Adds a transition to the experience buffer
- `experience_sampling_legal_actions(engine_observation)`: Returns known legal actions for a given state
- `experience_sampling_step(engine_observation, action)`: Samples the outcome of an action from experience

## Usage Example

The `elsciRLInfo` class is used internally by the `StandardInteractionLoop` for tracking and sampling experience. Example:

```python
from elsciRL.environment_setup.elsciRL_info import elsciRLInfo

info = elsciRLInfo()
info.observed_state_tracker(engine_observation, language_state)
info.experience_sampling_add(engine_observation, action, next_observation, reward, terminated)
legal_actions = info.experience_sampling_legal_actions(engine_observation)
next_obs, reward, terminated = info.experience_sampling_step(engine_observation, action)
```

---
