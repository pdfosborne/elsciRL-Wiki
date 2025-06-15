---
author:
  - Philip Osborne
published: 2025-04-15
last edited: 2025-04-15
tags:
  - Application
  - First-time
  - Guide
  - Tutorial
  - Foundation
type: Tutorial
---
---
# New Application Setup

Each application can be added to the elsciRL library to be used within the GUI interface app.

## Add Application to elsciRL 

Once the following functions are specified, you can add the application to the elsciRL library by first publishing it to GitHub and then referencing this in the application suite.

> elsciRL > application_suite > import_data.py

![import_data](<./_images/import_data_small.png>)

## Core Requirements

### Environment
Each application is defined by a unique engine that generates the data. Variations of the same problem specified by different data engines are considered different applications.

Define the MDP data engine with the following functions.

```python
class Engine:
  def __init__(self, local_setup_info:dict):
    # Store optional setup info
    # Initialize ledger of required & optional data
    # Prepare any internal environment data structures
    # Initialize histories (e.g., action_history, obs_history)

  def reset(self, start_obs = None):
    # Reset environment state
    # Optionally accept a specified start_obs
    return start_state

  def step(self, state, action):
    # Apply the chosen action
    # Update state and compute reward
    # Determine if episode is terminated
    return next_state, reward, terminated, info

  def legal_move_generator(self, state = None):
    # Return a list of valid actions given the current observation
    return legal_moves

  def render(self, state = None):
    # Generate and optionally display a visual representation of the environment
    # Return a figure object
    return fig

  def close(self):
    # Close active processes/handles related to the environment
```


### Configs
There are two type of configuration files. Note that only agent parameters can be adjusted in the GUI app interface.

Environment configurations can be varied and saved as separate inputs to change in the interface.

- *agent config* is used specify agent parameters
	- fixed by agent methodology and hierarchy architecture
- *env config* is used to specify problems specific parameters
	- Any parameters that are used by the environment
	- Specify the action limit
	- Specify manual sub_goal positions (exact state matching)
	- Specify the reward signal
		- [*sub_goal_reached, per_action, incomplete*]
		- *sub_goal_reached* is used for instruction completion
		- *per_action* and *incomplete* are optional if not specified by environment already

```json
// agent config (agent_config.json)
"name": "env_name"
"problem_type" = "category"
"experience_sample_batch_ratio": 0

"number_training_episodes": 1000
"number_training_repeats":  20
"number_training_seeds": 1

"test_agent_type":"all",
"number_test_episodes": 100,
"number_test_repeats": 5,

"agent_select": ["Qlearntab"]
"agent_parameters" = {
    "Qlearntab": {
        "alpha": 0.1,
        "gamma": 0.9,
        "epsilon": 0.2,
        "epsilon_step": 0
    }
}
```

```json
// environment config (env_config.json)
"environment_size": "4x4"
"adapter_select": ["default", "language"]
"action_limit": 100
"reward_signal": [1, 0, -0.05]
"sub_goal": "None"
```
### Adapters

![[Wiki/Applications/Adapters#Adapters|Adapters]]

## Analysis Scripts

You can add a script file that produces problem specific analysis for the results tab.

The form of this is the following, note the class function must be call *Analysis* and it must return a dict of matplotlib figures.

```python
class Analysis:
	def __init__(self, save_dir):
		self.save_dir = save_dir

	def plot_1(self):
		"""
		Extract the results data from the save_dir and create problem
		specific evaluation.
		Return a dict of the form:
			{
			 'plot_name_1':matplotlib.figure,
			 'plot_name_2':matplotlib.figure
			}
		"""
		plot_dict = {}
		n = 1
		for data in self.save_dir:
			...
			figure = plt.figure()
			ax = figure.add_subplot(1, 1, 1)
			ax.scatter(data['x'],data['y'])
			...
			
			plot_dict['plot'+str(n)] = figure
			n+=1
	return plot_dict

	def plot_2(self)
		"""Any number of plot functions will be used."""
		...
		return plot_dict
```



## Prerender Data
Prerender data can be used to add and image to describe the problem.

Observed states are required to complete the unsupervised instruction following method. 

Once you have added the application to the *import_data.py* library you can use the elsciRL *get_prerender_data* tool to extract the observed states data.

 Run the following code and it will guide you through a prompt to select your application, the language adapter to use in instruction following and number of exploration episodes.

```python
from elsciRL import get_prerender_data
get = get_prerender_data()
get.run()
```

A fully random search agent is used to find as many states as possible. *observed_states.txt* will be saved in the directory you run the code and you can then add this to the prerender data.