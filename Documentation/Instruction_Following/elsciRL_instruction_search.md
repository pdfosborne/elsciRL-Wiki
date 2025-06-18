<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Instruction_Following/elsciRL_instruction_search.md -->

# elsciRL Instruction Search

This module provides the `elsciRLSearch` class, which enables unsupervised discovery of sub-goals and instruction mapping in RL environments. It is used to generate instruction paths and observed states for instruction-based RL experiments.

## Main Class: `elsciRLSearch`

### Features
- Unsupervised exploration to discover sub-goals and instruction mappings
- Supports multiple agent types and adapters
- Produces observed states and instruction results for downstream instruction following
- Integrates with elsciRL's environment and agent modules

### Key Methods
- `__init__(...)`: Initializes the search with configs, environment, adapters, and exploration parameters
- `search(action_cap=5, ...)`: Runs the exploration and instruction mapping process

## Usage Example

See the example in the [Instruction Following documentation](./elsciRL_instruction_following.md) for a full workflow combining instruction search and instruction following.

---
