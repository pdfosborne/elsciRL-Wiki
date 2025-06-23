# DemoExperiment

## Source

```python
from elsciRL.examples.DemoExperiment import DemoExperiment as Demo
```

This file provides a demonstration script for running reinforcement learning (RL) experiments using the `elsciRL` framework. The main class, `DemoExperiment`, guides users through configuring, running, and evaluating RL experiments on selected problems from the elsciRL application suite.

## Usage Example

- Initialise the Demo Experiment
```python
from elsciRL import Demo
demo = Demo()
```

- Run an experiment with the CLI selection tool
```python
demo.run()
```

- Use the help function to learn more
```python
demo.help()
```

### Supported Applications

- Classroom
- Gym-FrozenLake
- Sailing

### Output

- Results are saved in a timestamped directory under `elsciRL-EXAMPLE-output`.
- Evaluation produces visual analysis of training and testing variance.


# Components

### Imports
- Standard libraries: `datetime`, `os`
- elsciRL modules for experiments and analysis

### DemoExperiment Class

#### Initialization
- Sets up an output directory for experiment results.

#### help()
- Prints usage instructions and an example workflow for the demo experiment.

#### input()
- Prompts the user for the number of training episodes (with a default value).
- Stores this value for experiment configuration.

#### results_save_dir()
- Creates a timestamped directory for saving experiment results.

#### experiment(problem, exp_save_dir, num_train_epi)
- Guides the user through selecting:
  - Local configuration
  - Experiment configuration
  - Adapter (excluding LLM adapters)
- Updates experiment configuration based on user input.
- Instantiates and returns a `STANDARD_RL` experiment object.

#### run()
- Loads available applications using `PullApplications`.
- Displays available problems, engines, adapters, and configurations.
- Prompts the user to select a problem and number of training episodes.
- Sets up directories and runs the selected experiment (training and testing).

#### evaluate()
- Runs combined variance analysis on the training and testing results, displaying figures.

