Table of Contents

- [Configuration Options](<#configuration-options>)
	- [Experiment Configuration](<#experiment-configuration>)
	- [Experiment Configuration](<#experiment-configuration>)
	- [Changing Parameters](<#changing-parameters>)
		- [Agents and Adapters](<#agents-and-adapters>)

---
# Configuration Options

Two forms of configuration are used by the elsciRL library:
- Experiment information such as agent parameters
- Problem information such as difficulty settings

In the FrozenLake application, these are defined by the *config.json* and *config_local.json* respectively.

## Experiment Configuration

The experiment config is to define:
- The application name and problem type
- The use of experience sampling (see REF)
- The number of training episodes, repeats/seeds
- The testing agent procedure, episodes and repeats
- Selection of agents to run and parameters

![Experiment Config](<./_images/Experiment Config.png>)

## Local Problem Configuration

The problem config is to define:
- Selection of adapters
- The action limits of the engine for training and testing
- The reward signal where reward is given using the form $[goal,\ per\_action,\ action\_limit]$
- Flag to include supervised sug-goals (if defined by engine)


In this example, there are two additional inputs for the problem:
 - The distance the sailing boat is required to travel
 - The precision (i.e. number of decimal places) for the observations

These are specific the to the Sailing setup and increase the difficulty of the problem. 

The first can be used to increase the number of actions needed to complete an episode and therefore increases the delay to obtain the reward for reaching the objective.

The second varies the precision of the observations and can therefore be used to increase the size of the state space by a factor of 10. In other words, 1 decimal place equates to 10 values between discrete points, 2 equates to 100, 3 equates to 1,000 and so on.

These additional parameters can be called inside the Engine for the problem and any number of settings can be added to give more control to the experiment. 

![Problem Config](<./_images/Problem Config.png>)

## Agents and Adapters

There are two options for defining how you wish Agents to be matched against Adapters.

### 1. One-to-Many Match

**ALL agents get applied to ALL adapters**

If we don't want to manually specify which agent gets applied to which adapter we can simply say which agents and which adapters we want to use.

In the example given in the previous configs this means that the 'Qlearntab' agent would then be applied to both the adapters 'default' and 'language'.

*experiment_config.py*
```json
agent_select: ["Qlearntab"]
```
*local_config.py*
```json
adapter_select: ["Default", "Language"]
```

**This results in the combinations:**

```json
agent_adapter: ["Qlearntab_Default", "Qlearntab_Language"]

```

If we added another agent then this would also be applied to both adapters and so on. 

For example, if we added a 'DQN' agent to the selection without changing the adapter selection: 

*experiment_config.py*
```json
agent_select: ["Qlearntab", "DQN"]
```
*local_config.py*
```json
adapter_select: ["Default", "Language"]
```

**Results in:**
```json
agent_adapter: ["Qlearntab_Default", "Qlearntab_Language", "DQN_Default", "DQN_Language"]

```

This makes it easy to setup but can slow down the runtime of experiments if too many combinations are added.

### 2. One-to-One Match

**The list of adapters directly matches the list of agents**

In the example above, there is only one agent defined but in order to use an exact match for both adapters we must align these. 

If we wanted to apply the *Language adapter* then the experiment config would need to be updated to the following:

*experiment_config.py*
```json
agent_select: ["Qlearntab", "Qlearntab"]
```
Thereby matching the local config adapters.

*local_config.py*
```json
adapter_select: ["Default", "Language"]
```
**Results in:**
```json
agent_adapter: ["Qlearntab_Default", "Qlearntab_Language"]

```

To add another agent we would then need to add more adapters to specify exactly which one should be used.

*experiment_config.py*
```json
agent_select: ["Qlearntab", "Qlearntab", "DQN"]
```

*local_config.py*
```json
adapter_select: ["Default", "Language", "Language"]
```
**Results in:**
```json
agent_adapter: ["Qlearntab_Default", "Qlearntab_Language", "DQN_Language"]

```