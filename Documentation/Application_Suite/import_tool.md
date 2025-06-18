<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/Application_Suite/import_tool.md -->

# elsciRL Application Suite: Import Tool

This module provides the `PullApplications` class, which is responsible for dynamically loading and managing RL application environments, adapters, configurations, and related resources from local or remote repositories (e.g., GitHub). It is a core utility for setting up and running experiments in the elsciRL framework.

## Main Class: `PullApplications`

### Purpose
- Dynamically fetches engines, adapters, configs, and analysis modules for selected problems.
- Supports pulling from specific commits or the latest main branch of remote repositories.
- Handles local and remote resource management, including pre-rendered data and images.
- Provides methods for adding and removing applications at runtime.

### Key Methods

#### `pull(problem_selection: list = []) -> dict`
- Loads all resources for the specified problems (or all available if none specified).
- Downloads engines, adapters, configs, and analysis modules from the configured repositories.
- Returns a dictionary with all loaded resources for each problem.

#### `setup(agent_config: dict = {}) -> dict`
- Loads or sets up the experiment configuration for an agent.
- Returns the experiment configuration dictionary.

#### `add_applicaiton(problem: str, application_data: dict) -> dict`
- Adds a new application to the list of available problems.
- Loads configs and data from local files if provided as paths.
- Updates the internal registry and returns the updated applications dictionary.

#### `remove_application(problem: str) -> dict`
- Removes an application from the list of available problems.
- Updates the internal registry and returns the updated applications dictionary.

### Usage Example

```python
from elsciRL.application_suite.import_tool import PullApplications

# Initialize the tool
app_importer = PullApplications()

# Pull data for selected problems
problems = ['Sailing', 'Classroom']
app_data = app_importer.pull(problem_selection=problems)

# Access engine, adapters, configs, etc.
engine = app_data['Sailing']['engine']
adapter = app_data['Sailing']['adapters']['default']
experiment_config = app_data['Sailing']['experiment_configs']['default']

# Add a new application
app_importer.add_applicaiton('NewProblem', application_data)

# Remove an application
app_importer.remove_application('Sailing')
```

### Notes
- The import tool expects a specific structure in the remote repositories (engine, adapters, configs, etc.).
- It uses `httpimport` to dynamically load Python modules from URLs.
- Pre-rendered data and images are also fetched and made available for analysis or visualization.
- The tool is designed for extensibility and can be used to add or remove applications at runtime.

---