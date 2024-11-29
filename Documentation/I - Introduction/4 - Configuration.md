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

![Experiment Config](<./attachments/Experiment Config.png>)

## Experiment Configuration

The problem config is to define:
- Selection of adapters
- The action limits of the engine for training and testing
- The reward signal
- Flag to include supervised sug-goals (if defined by engine)
- **Any additional problem specific control (not shown in example)**

![Problem Config](<./attachments/Problem Config.png>)

## Changing Parameters

Editing parameters is as simple as updating to values given within their required ranges. 

For now, agent parameters are limited to one input.

![[./attachments/Changing Parameters.png]]

### Agents and Adapters

The list of adapters must match the list of agents. 

In the example above, there is only one for each so the Tabular Q-learning agent will use the *Default* adapter. 

If we wanted to apply the *Language adapter* then these would need to be updated to the following:

```json title:config.json
agent_select: ["Qlearntab", "Qlearntab"]
```

```json title:config_local.json
adapter_select: ["Default", "Language"]
```

