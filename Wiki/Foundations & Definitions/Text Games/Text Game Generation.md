# Generating a Text Game

Thus far, there are two main generation tools for applying agents to interactive fiction games: TextWorld and Jericho.

\textbf{TextWorld} \cite{Cote:2018} is a logic engine to create new game worlds, populating them with objects and generating quests that define the goal states (and subsequent reward signals). It has since been used as the generation tool for Treasure Hunter \cite{Cote:2018}, Coin Collector \cite{Yuan:2018}, CookingWorld \cite{Trischler:2019}, and the QAit Dataset \cite{Yuan:2019}.


\textbf{Jericho} \cite{Hausknecht:2019jericho} was recently developed as a tool for supporting a set of human-made interactive fiction games that cover a range of genres. These include titles such as Zork and Hitchhiker's Guide to the Galaxy. Unsupported games can also be played through Jericho but will not have the point-based scoring system that defines the reward signals. Jericho has been used as the generator tool for CALM \cite{Yao:2020} and Jericho QA \cite{Ammanabrolu:2020grue}. 

\subsection{Environment Model}

Reinforcement Learning is a framework that enables agents to reason about sequential decision making problems as an optimization process \cite{Sutton:1998}. Reinforcement Learning requires a problem to be formulated as a Markov Decision Process (MDP) defined by a tuple $< S, A, T, R, \gamma >$ where $S$ is the set of states, $A$ is the set of actions, $T$ is the transition probability function, $R$ the reward signal and $\gamma$ the discount factor. 

%Given an environment defined by an MDP, the goal of an agent is to determine a policy $\pi(a|s)$ specifying the action to be taken in any state that maximizes the expected discounted cumulative return $\sum_{k=0}^{\infty}\gamma^k r_{k+1}$.


In text games however, the environment states are never directly observed but rather textual feedback is provided after entering a command. As specified by \cite{Cote:2018}, a text game is a discrete-time Partially Observed Markov Decision Process (POMDP) defined by $< S, T, A, \Omega, O, R, \gamma >$ where we now have the addition of the set of observations ($\Omega$) and a set of conditional observed probabilities $O$. Specifically, the function $O$ selects from the environment state what information to show to the agent given the command entered to produce each observation $o_t \in \Omega$.

