<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Analysis/combined_variance_visual.md -->

# Combined Variance Visual Analysis

This module provides a function for visualizing and comparing the variance in results across multiple reinforcement learning experiments. It is designed to help users analyze the performance and stability of different agents or experiment configurations by plotting reward statistics, cumulative reward, and timing information.

## Function: `combined_variance_analysis_graph`

**Location:** `elsciRL/elsciRL/analysis/combined_variance_visual.py`

### Description

The `combined_variance_analysis_graph` function loads experiment results from a specified directory, aggregates statistics, and generates a set of plots to visualize the mean and variance of rewards, cumulative rewards, and episode timing. It supports both training and testing analysis, and can compare multiple agents or experiment runs.

### Parameters
- `results_dir` (str): Path to the directory containing experiment results. **(Required)**
- `analysis_type` (str): Either `'training'` or `'testing'` (default: `'training'`). Determines which results to analyze.
- `show_figures` (str): `'Y'` to display figures interactively, `'N'` to only save them (default: `'N'`).
- `results_to_show` (str): `'all'` for full set of plots, `'simple'` for a single reward plot (default: `'all'`).
- `experiment_names` (list): Optional list of experiment names for labeling plots.

### Output
- Saves plots as PNG files in the results directory.
- Optionally displays the plots interactively.

## Usage Example

```python
from elsciRL.analysis.combined_variance_visual import combined_variance_analysis_graph

# Example usage: analyze training results and show all plots
results_dir = '/path/to/your/experiment/output'
combined_variance_analysis_graph(
    results_dir=results_dir,
    analysis_type='training',   # or 'testing'
    show_figures='Y',           # 'Y' to display, 'N' to only save
    results_to_show='all'       # 'all' for full set, 'simple' for single plot
)
```

This will generate and save a set of plots in the specified directory, including:
- Mean reward per episode (with standard error)
- Cumulative reward
- CDF of rolling average reward
- Distribution of time per episode

## Notes
- The function expects a specific directory structure and CSV result files as output by elsciRL experiments.
- If `show_figures='Y'`, the plots will be displayed for 5 seconds before closing.
- The function is useful for comparing the performance and stability of different agents or experiment settings.

---

