Table of Contents

- [Running an Experiment](<#running-an-experiment>)
	- [Configuration Control and Agent Selection](<#configuration-control-and-agent-selection>)
	- [Experiment Selection](<#experiment-selection>)
		- [Results from a Tabular Agent Experiment](<#results-from-a-tabular-agent-experiment>)
- [Things to Try](<#things-to-try>)

---
# Running an Experiment

Experiments are pre-defined protocol for how the agent should be trained. Furthermore, they can be used to specify more complex architectures such as hierarchies that would normally need to be custom built.

Without any other changes we can run the  *[main.py](http://main.py)*  script which will first train a tabular agent for this problem before failing to train a neural agent. 

This is intentional and important to understand that other parameters will need to be updated to align as, in this case, the default neural agent parameters do not match the size of the vector created by the state’s encoder. 

![Running a New Experiment](<./attachments/Running a New Experiment.png>)

## Configuration Control and Agent Selection

For now, we will remove the neural agent as a choice in the config. To do this, we remove both the second item from the agent choice in  *config.json*  and in the adapter selection in  *config_local.json*.

![Configuration Options](<./attachments/Configuration Options.png>)

The following is a Git difference view where the deletion of ‘Neural_Q’ and the second ‘Default’ adapter selection are shown with the new files on the right.

![Configuration Removing Neural Agent](<./attachments/Configuration Removing Neural Agent.png>)


## Experiment Selection

Lastly, we simplify the experiment call in *main.py* and only run a standard flat agent architecture instead of the instruction following specified by the template (can simply comment this out).

![Experiment Selection](<./attachments/Experiment Selection.png>)

### Results from a Tabular Agent Experiment

Running the experiment now will train a tabular agent for this problem and return the summary results in the output directory. 

![Experiment Output](<./attachments/Experiment Output.png>)

In this case with default parameters, two agents are ***trained*** for 100 episodes completely independently. Repeats are used to confirm that the results are statistically significant and not due to chance as exploration is a significant component of the success or failure of a Reinforcement Learning agent. 

The measurement used is the reward and it appears that with very few episodes the best our agents can do is to reach the environment’s timeout limit (net 0 reward).

![Results Example Training](<./attachments/Results Example Training.png>)

In ***testing***, the policy (decision making) of each trained agent is fixed and applied for a further 100 episodes. We do this to better analyse the output policy of the training and if this would produce stable outcomes.

![Results Example Testing](<./attachments/Results Example Testing.png>)

All of the previous steps can be replicated from the public GitHub repository and specifically the commit: [elsciRL-GymFrozenLake-OutputExample](https://github.com/pdfosborne/elsciRL-GymFrozenLake/commit/e5b123d7dc8a6ceb2b7b542fbff7f5e58824506b)

# Things to Try

At this stage I would suggest trying some basic customization options. 

To get started: 

1. Increase the number of training episodes to 1,000
2. Increase the number of training and testing repeats to 5 or more
3. Change the tabular agent parameters
4. **Advanced:** Update the engine to use an 8x8 Frozen Lake problem AND update the default.py adapter to match this change