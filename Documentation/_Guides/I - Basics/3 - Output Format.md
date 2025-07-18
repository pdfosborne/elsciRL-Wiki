# Understanding Results

When the agent is run, it will automatically save the results in the output folder as shown in the following image.

The structure of these will depend on the experiment. Within the experiment, each selected agent is run with its corresponding adapter and repeated depending on the number of repeats/seeds chosen in the configuration. 

Testing procedures take the trained output agent and fix the policy before re-applying it for a limited number of episodes when it can no longer learn. In other words, it provides evaluation on what the agent thinks is best at this time. 

![Output Folder](<./_images/Output Folder.png>)

## Comparison between Agents

Results for each agent type are summarised into a single comparison chart. 

In the following example image:
- The same tabular Q-learning agent is applied with two different adapters (default and language)
- Three formats of reward per episode
- A distribution of time taken per episode

![Training Variance Comparison](<./_images/Training Variance Comparison.png>)

## Evaluating a Single Agent

Each of the training and testing results return a set of analysis charts. These can include:
- Average reward per episode
- Rolling average reward per episode *(top-left in example above)*
- Cumulative reward per episode *(bottom-left in example above)*
- Cumulative Distribution Frequency (CDF) of the rolling average reward per episode *(top-left in example above)* 
- Distribution of reward per episode
- Number of actions per episode
- Distribution of the number of actions per episode
- Time per episode
- Distribution of time per episode *(bottom-right in example above)*

Furthermore, all results are logged into a *results.csv* file that can be explored to find discrepancies in the learning procedure.

Reward is used as a consistent measurement between problems. However, some problems may benefit from analysing specific measurements such as win percentage.
