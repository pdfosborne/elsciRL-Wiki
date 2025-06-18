<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Experiments/standard.md -->

# Standard Experiment (elsciRL)

This module provides the `Experiment` class, which implements the standard workflow for running reinforcement learning (RL) experiments in elsciRL. It supports modular configuration, agent and adapter selection, training, testing, and result visualization.

## Main Class: `Experiment`

### Purpose
- Sets up and manages the full RL experiment lifecycle: environment, agent, adapter, training, testing, and reporting.
- Supports multiple engines, agent types, and adapters.
- Integrates with elsciRL's modular analysis and reporting tools.

### Key Methods

- `__init__(Config, ProblemConfig, Engine, Adapters, save_dir, show_figures, window_size, ...)`
  - Initializes the experiment with configuration dictionaries, environment engine, adapters, and output settings.
- `add_agent(agent_name, agent)`
  - Registers a new agent with the experiment.
- `train()`
  - Runs the training loop for all configured agents and adapters, saving results and generating variance reports.
- `test(training_setups=None)`
  - Runs the testing loop using trained agents, saving and visualizing results.
- `render_results(training_setups=None)`
  - Renders and visualizes the policy of trained agents for qualitative analysis.

## Usage Example

Below is a real usage example from a Maze application, showing how to set up and run a standard experiment:

```python
from elsciRL.experiments.standard import Experiment
from environment.engine import Engine
from adapters.language import Adapter as LanguageAdapter
import json
import os

def load_config(config_file):
    with open(config_file, 'r') as f:
        return json.load(f)

def main():
    # Load configurations
    experiment_config = load_config('configs/config.json')
    problem_config = load_config('configs/config_local.json')
    
    # Create experiment directory
    save_dir = "output"
    os.makedirs(save_dir, exist_ok=True)
    
    # Initialize experiment
    experiment = Experiment(
        Config=experiment_config,
        ProblemConfig=problem_config,
        Engine=Engine,
        Adapters={"language": LanguageAdapter},
        save_dir=save_dir,
        show_figures='Y',
        window_size=10.0,
        training_render=True,
        training_render_save_dir=os.path.join(save_dir, "renders")
    )
    
    # Run experiment
    experiment.train()
    experiment.test()

if __name__ == "__main__":
    main()
```

## Output
- Results, plots, and reports are saved in the specified output directory.
- Figures can be displayed interactively or saved, depending on the `show_figures` parameter.

---
