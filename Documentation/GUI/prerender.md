<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/GUI/prerender.md -->

# elsciRL Prerender Script

This script provides a command-line utility for generating and saving observed states for RL environments in the elsciRL framework. It is useful for precomputing state representations for analysis, visualization, or LLM-based instruction following.

## Main Class: `Prerender`

### Features
- Loads available applications and their configurations
- Allows interactive selection of application, configuration, and adapter
- Runs exploration episodes to collect observed states
- Saves observed states to disk in a structured directory

### Usage Example

To run the prerender script interactively:

```python
from elsciRL import get_prerender_data

get = get_prerender_data
get.run()
```

You will be prompted to:
1. Select an application (e.g., Chess, Classroom, Sailing, etc.)
2. Select a configuration and adapter
3. Enter the number of exploration episodes

The script will then run the exploration and save the observed states to a file in the `prerender-data/` directory.

### Example Output
- Observed states are saved as JSON files with descriptive filenames, organized by application and adapter.

---

## Adding Your Own Application

The prerender script uses the elsciRL import tool to dynamically load available applications. To add your own application to the available options:

1. **Prepare your application files** (engine, adapters, configs, etc.) in a structure similar to the provided example applications.
2. **Create an application data dictionary** describing your application, including paths to engine, configs, adapters, and any prerender data or images.
3. **Use the import tool to register your application** before running the prerender script. For example:

```python
from elsciRL.application_suite.import_tool import PullApplications

pull = PullApplications()
my_app_data = {
    'engine': 'path/to/engine.py',
    'experiment_configs': {'default': 'path/to/experiment_config.json'},
    'local_configs': {'default': 'path/to/local_config.json'},
    'adapters': {'default': 'path/to/adapter.py'},
    'local_analysis': {},
    'prerender_data': {},
    'prerender_images': {}
}
pull.add_applicaiton('MyCustomApp', my_app_data)
```

4. **Run the prerender script**. Your custom application will now appear in the list of selectable options.

---