# Reinforcement Learning Basics
## Definition

A **policy** decides the agent's actions in any given state, denoted as $\pi(s)$.

The **value function** specifies the quality of each state. This can be defined either by state only, $V(s)$, or by state-action pairs $Q(s,a)$.

The final step of the path is known as the **terminal state**. After reaching a terminal state, the environment is reset, returning the agent to one of the **initial states**.

An **episode** is defined by a single path, from an initial state to a terminal state. When the terminal state is reached, the environment is reset to its initial position.

The **return** is calculated as the discounted sum of rewards in the episode:

$$ 
	R_t = \sum_{t=1}^{T}\gamma r_{t} 
$$

Where $0 \leq \gamma \leq 1$. If $\gamma = 1$, future rewards are equally as important as immediate rewards. Conversely, if $\gamma = 0$ only the most immediate reward is important (i.e. $r_1$). 

The **optimal policy** is the best possible choice of actions and denoted by $\pi^{\star}(s)$. There will always be at least one policy that is currently the best. In order to find the optimal policy, we continually compare our current policy against a new one, and if the new one is better, we use that instead. Once we can no longer find a policy that is better, we then deduce that it is the optimal policy. Formally, a policy, $\pi(s)$, is better than another policy, $\pi'(s)$, if and only if:

$$
    V_{\pi(s)}(s) \geq V_{\pi'(s)}(s), \forall s\in S 
$$

In summary, given an environment defined by an Markov Decision Process, the goal of an agent is to determine the optimal policy $\pi^{\star}(a|s)$ specifying the best action to be taken in any state. The best action is defined such that it maximizes the expected reward starting in any state:

$$
    V_{\pi}(s) = E[R_t|s] = E\left[\sum^{\infty}_{t=0}\gamma r_{t}|s\right]
$$

This is trained through continuous interaction with the environment as shown in Figure \ref{fig:setup_overview} where the interaction continues until the results have converged (i.e. stops changing significantly). The most notable challenge in RL is therefore the amount of *exploration* needed to find a good path against *exploiting* current knowledge to maximise reward.