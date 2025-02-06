# Definition

An agent must incorporate the long-term outcomes of actions into the calculations. A well known method for achieving this is Q-learning and defined by @suttonReinforcementLearningIntroduction2018 whereby calculations are updated based on the transitions from the current state-action pair to the next state.

Formally, the value of state-action pairs, $Q(s,a)$, are updated using the following calculation in equation @eq-Q_learn_update_rule after reaching every non-terminal state. If the next state is a terminal state, then this is fixed to $Q(s^\prime,a^\prime)=0$ and often a large reward is provided depending on the outcome. Over time, the numeric results of the long-term outcome propagates backwards to the earliest states in an episode such that the agent can make immediate actions that are not going to cause long-term issues. 

### Q-Learning Update Rule:


$$Q^{new}(s,a)\leftarrow Q(s,a) + \alpha {\bigg (} r + \gamma \max_{a'}Q(s',a') - Q(s,a) {\bigg )}$${#eq-Q_learn_update_rule}

where:
- $Q(s,a)$ is the value of state-action pair $s$,
- $\alpha$ is the learning rate parameter,
- $r$ is the immediate reward,
- $\gamma$ is the discount factor parameter and,
- $Q(s', a')$ is the value of action-pair in the next state taking the best known action.

The method is defined as *off-policy* as the calculation is based on the maximum possible value that could be obtained in the next state rather than one based on an action selection policy. 
