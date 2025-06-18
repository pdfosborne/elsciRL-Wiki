<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Evaluation/standard_report.md -->

# Standard Report (elsciRL Evaluation)

This module provides the `Evaluation` class, which generates standard analysis reports and visualizations for RL experiment results in elsciRL. It supports both training and testing phases, and produces summary statistics, plots, and tabular outputs for easy comparison and interpretation.

## Main Class: `Evaluation`

### Purpose
- Automates the generation of visual and tabular reports for RL training and testing results.
- Aggregates results across multiple runs or seeds for variance analysis.
- Saves plots and tables to the specified output directory.

### Key Methods

#### `__init__(self, window_size)`
- Initializes the evaluation object with a window size for rolling averages.

#### `train_report(training_results: pd.DataFrame, save_dir: str, show_figures: str)`
- Produces visual and tabular analysis of individual training results.
- Saves plots (reward, cumulative reward, action distributions, etc.) and summary tables.
- Returns the final cumulative reward.

#### `training_variance_report(save_dir: str, show_figures: str)`
- Aggregates and visualizes variance across multiple training runs (repeats or seeds).
- Produces combined plots (mean reward, CDF, cumulative reward, timing) and saves summary CSVs.

#### `test_report(test_results: pd.DataFrame, save_dir: str, show_figures: str)`
- Produces visual and tabular analysis of testing results (similar to `train_report`).
- Returns the final cumulative reward.

#### `testing_variance_report(save_dir: str, show_figures: str)`
- Aggregates and visualizes variance across multiple testing runs.
- Produces combined plots and saves summary CSVs.

#### `convergence_analysis(results_table_dir: str, save_dir: str, show_figures: str)`
- Generates convergence analysis plots for training results.

## Usage Example

```python
from elsciRL.evaluation.standard_report import Evaluation
import pandas as pd

# Load results
training_results = pd.read_csv('path/to/results.csv')

# Create evaluation object
evaluator = Evaluation(window_size=0.1)

# Generate training report
final_cum_reward = evaluator.train_report(training_results, save_dir='output/dir', show_figures='Y')

# Generate variance report across multiple runs
# evaluator.training_variance_report(save_dir='output/dir', show_figures='N')
```

## Output
- Plots (PNG) and tables (CSV) are saved in the specified output directory.
- Optionally displays figures interactively if `show_figures='Y'`.

---