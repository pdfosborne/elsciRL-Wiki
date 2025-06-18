<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Instruction_Following/elsciRL_instruction_following.md -->

# elsciRL Instruction Following

This module provides the `elsciRLOptimize` class, which enables instruction-based reinforcement learning in elsciRL. It supports training and evaluating agents using human or LLM-generated instructions, sub-goal chaining, and integration with standard RL workflows.

## Main Class: `elsciRLOptimize`

### Features
- Supports instruction-based RL with sub-goal chaining and flexible instruction episode ratios
- Integrates with elsciRL's agent, adapter, and environment modules
- Produces standard and instruction-specific analysis reports
- Can be used alongside standard RL experiments for comparison

### Key Methods
- `__init__(...)`: Initializes the instruction-following experiment with configs, environment, adapters, and instruction paths
- `train()`: Trains agents using instruction-based sub-goals and chaining
- `test(training_setups=None)`: Tests trained agents on instruction-based tasks
- `render_results(training_setups=None)`: Renders agent policies for qualitative analysis

## Usage Example

Below is an example usage from a Sailing application, showing how to use instruction search and instruction following:

```python
from elsciRL import STANDARD_RL, elsciRL_SEARCH, elsciRL_OPTIMIZE
from elsciRL.config import TestingSetupConfig
from elsciRL.config_local import ConfigSetup
from environment.engine import Engine
from adapters.default import DefaultAdapter
from adapters.language import LanguageAdapter
ADAPTERS = {"Default": DefaultAdapter, "Language": LanguageAdapter}

# Load configs
ExperimentConfig = TestingSetupConfig("./configs/config.json").state_configs
ProblemConfig = ConfigSetup("./configs/config_local.json").state_configs

# Specify save dir
save_dir = './output/test_01-01-2025_12-00'

# Instruction search (unsupervised sub-goal discovery)
search_agent = elsciRL_SEARCH(
    Config=ExperimentConfig, LocalConfig=ProblemConfig,
    Engine=Engine, Adapters=ADAPTERS,
    save_dir=save_dir+'/Reinforced_Instr_Experiment',
    num_plans=50, number_exploration_episodes=100000, sim_threshold=0.9,
    feedback_increment=0.1, feedback_repeats=1
)
results = search_agent.search(action_cap=100)
observed_states = results[0]
instruction_results = results[1]

# Instruction following (train to sub-goals)
reinforced_experiment = elsciRL_OPTIMIZE(
    Config=ExperimentConfig, LocalConfig=ProblemConfig,
    Engine=Engine, Adapters=ADAPTERS,
    save_dir=save_dir+'/Reinforced_Instr_Experiment', show_figures='No', window_size=0.1,
    instruction_path=instruction_results, predicted_path=None, instruction_episode_ratio=0.05,
    instruction_chain=True, instruction_chain_how='exact'
)
reinforced_experiment.train()
reinforced_experiment.test()

# (Optional) Run standard RL for comparison
flat = STANDARD_RL(
    Config=ExperimentConfig, LocalConfig=ProblemConfig,
    Engine=Engine, Adapters=ADAPTERS,
    save_dir=save_dir, show_figures='No', window_size=0.1
)
flat.train()
flat.test()
```

## Output
- Results, plots, and reports are saved in the specified output directory.
- Supports both instruction-based and standard RL workflows for comparison.

---
