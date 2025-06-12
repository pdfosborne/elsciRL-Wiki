# MDP
## Definition

Reinforcement Learning is a framework that enables agents to solve sequential decision making problems as an optimisation process \cite{Sutton:1998}. Reinforcement Learning requires a problem to be formulated as a Markov Decision Process (MDP) defined by a tuple $< S, A, T, R, \gamma >$ where $S$ is the set of states, $A$ is the set of actions, $T$ is the transition probability function, $R$ the reward signal and $\gamma$ the discount factor. 

The following Figure \ref{fig:MDP-example} illustrates this for a simple example. States are shown as blocks with their associated reward for reaching and possible actions are depicted by the arrows. For example, this student cannot go from the bar to work because there is no link and if they decide to watch YouTube at work that returns a negative reward.

| ![MDP-Model](<./_images/MDP-model.png>) | 
|:--:| 
| *MDP model diagram as defined by {[[sutton2018ReinforcementLearningIntroduction]]}.* |

```
\begin{figure}[h!]
    \centering
    \includegraphics[scale=0.75]{MDP-model.png}
    \caption{MDP model diagram as defined by \citep{sutton2018ReinforcementLearningIntroduction}.}
    \label{fig:MDP-model}
\end{figure}
```
