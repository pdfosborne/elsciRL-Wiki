# Handicaps for Evaluation Control

Before introducing the challenges of the environments, it is important to understand the possible limitations that can be imposed by the generation tools to reduce the complexity of each problem. These handicaps are typically used to limit the scope of the challenges being faced at any one time for more rigorous comparisons and for simplicity. 

It has been noted that TextWorld's \cite{Cote:2018} generative functionality explicit advantage is that it can be used to focus on a desired subset of challenges. For example, the \textbf{size of the state space} can be controlled and how many commands are required in order to reach the goal. Evaluation of specific generalisability measures can also be improved by controlling the training \textcolor{red}{\st{vs}} \textcolor{blue}{versus} testing variations. 

The \textbf{partial observability} of the state can also be controlled by augmenting the agent's observations. It is possible for the environment to provide all information about the current game state and therefore reduce the amount an agent must explore to determine the world, relationships, and objects contained within.  

Furthermore, the \textbf{complexity of the language} itself can be reduced by restricting the agent's vocabulary to in-game words only or the verbs to only those understood by the parser. The grammar can be further simplified by replacing object names with symbolic tokens. It is even possible for the language generation to be avoided completely by converting every generated game into a \textit{choice-based} game where actions at each timestep are defined by a list of pre-defined commands to choose from. 

\textbf{Rewards} can \textcolor{blue}{be} simplified with more immediate rewards during training based on the environment state transitions and the known ground truth winning policy rather than simply a sparse reward at the end of a quest as normally provided.

\textbf{Actions} are defined by text commands of at least one word. The interpreter can accept any sequence of characters but will only recognize a tiny subset and moreso only a fraction of these will change the state of the world. The action space is therefore enormous and \textcolor{red}{\st{therefore}} \textcolor{blue}{hence} two simplifying assumptions are made:

	- \textit{Word-level Commands} are sequences of at most L words taken from a fixed vocabulary V.
	- \textit{Syntax Commands} have the following structure - verb[noun phrase [adverb phrase]] where [...] indicates that the sub-string is optional. 			
	
Jericho \cite{Hausknecht:2019jericho} similarly has a set of possible simplifying steps to reduce the environment's complexity. Most notably, each environment provides agents with the set of valid actions in each game's state. It achieves this by executing a candidate action and looking for the resulting changes to the world-object-tree. To further reduce the difficulty of the games, optional handicaps can be used:

\begin{itemize}
    \item Fixed random seed to enforce determinism.
    \item Use of load, save functionality.
    \item Use of game-specific templates and vocabulary.
    \item Use of world object tree as an auxiliary state representation or method for detection player location and objects.
    \item Use of world-change-detection to identify valid actions.
\end{itemize}

Jericho also introduces a set of possible restrictions to the action-space:

\begin{itemize}
    \item \textit{Template-based} action spaces separate the problem of picking actions into two: (i) picking a template (e.g. ``take \_\_\_ from \_\_\_"); (ii) filling the template with objects (e.g. ``apple", ``fridge"). Essentially this reduces the issue to verb selection and contextualised entity extraction.
    \item \textit{Parser-Based} action spaces require the agent to generate a command word-per-word, sometimes following pre-specified structures such as ($\text{verb}, \text{object}\_1, \text{modifier}, \text{object}\_2$).
    \item \textit{Choice-based} requires agents to rank a predefined set of actions without any option for ``creativity" from the model itself.

\end{itemize}


Lastly, the observation space may be enhanced with the outputs of bonus commands such as ``look" and ``inventory". These are commands that the agent can issue on its own but are not considered an actual step in the exploration process that could be costly and produce risks in the real-world when asked for. 
