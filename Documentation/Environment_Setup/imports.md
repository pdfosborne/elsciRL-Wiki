<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Environment_Setup/imports.md -->

# ImportHelper Utility (elsciRL)

This module provides the `ImportHelper` class, which is used to extract and organize agent, adapter, and environment configuration details from a setup dictionary. It is a key utility for initializing the agent-environment loop in elsciRL.

## Main Class: `ImportHelper`

### Features
- Extracts agent, agent type, agent name, and state adapter from setup info
- Retrieves training/testing episode counts, action caps, and reward signals
- Determines training/testing mode and live environment flags
- Handles flexible configuration keys for compatibility

### Key Methods
- `agent_info(STATE_ADAPTER_TYPES)`: Returns agent, agent type, agent name, and state adapter
- `parameter_info()`: Returns training/testing episode counts, action caps, and reward signals
- `training_flag()`: Returns whether the loop is in training mode
- `live_env_flag()`: Returns live environment and observed states flags

## Usage Example

The `ImportHelper` class is used internally by the `StandardInteractionLoop` to initialize the agent, adapters, and environment parameters. Example:

```python
from elsciRL.environment_setup.imports import ImportHelper

imports = ImportHelper(local_setup_info)
agent, agent_type, agent_name, agent_state_adapter = imports.agent_info(Adapters)
num_train_episodes, num_test_episodes, training_action_cap, testing_action_cap, reward_signal = imports.parameter_info()
train = imports.training_flag()
live_env, observed_states = imports.live_env_flag()
```

---
