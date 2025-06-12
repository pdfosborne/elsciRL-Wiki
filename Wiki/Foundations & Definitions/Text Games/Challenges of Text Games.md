Environments built from the TextWorld generative system are bounded by the complexity of the set of objects available. For example, \cite{Cote:2018} introduced 10 objects including the logic rules for doors, containers and keys, where complexity can be increased by introducing more objects and rules into the generation process. The most challenging environments are defined in Jericho as these contain 57 real Interactive Fiction games which have been designed by humans, for humans. Specifically, these environments contain more complexity in forms of stochasticity, unnatural interactions, unknown objectives - difficulties originally created to trick and hamper players.

The design and partially observed representation of text games creates a set of natural challenges related to Reinforcement Learning. Furthermore, a set of challenges specific to language understanding and noted by both \cite{Cote:2018} and \cite{Hausknecht:2019jericho} are specified in detail in the following sections.

\textbf{Partial Observability} 

The main challenge for agents solving Textual Games is the environment's partial observability; when observed information is only representative of a small part of the underlying truth. The connection between the two is often unknown and can require extensive exploration and failures for an agent to learn from observations and how this relates to its actions.

A related additional challenge is that of causality which is when an agent moves away from a state to the next without completing pre-requisites of future states. For example, an agent is required to use a lantern necessary to light its way but may have to backtrack to previous states if this has not been obtained yet; an operation which becomes more complex as the length of the agent's trajectory increases further into the game from which \textcolor{red}{\st{have}} \textcolor{blue}{the agent has} to backtrack.

Handcrafted reward functions have been proved to work for easier settings, like CoinCollector \cite{Yuan:2018}, but real-world text games can require more nuanced approaches. Go-Explore has been used to find high-reward trajectories and discover under-explored states \cite{Madotto:2020,Ammanabrolu:2020grue} where more advanced states are given higher priority over states seen earlier on in the game using a weighted random exploration strategy.

The work in \cite{Ammanabrolu:2020grue} have expanded on this with a modular policy approach aimed at noticing bottleneck states with a combination of a patience parameter and intrinsic motivation for new knowledge. The agent would learn a chain of policies and backtrack to previous states upon getting stuck.

Heuristic-based approaches have been used by \cite{Hausknecht:2019nail} to restrict navigational commands to only after all other interactive commands have been exhausted.

Leveraging past information has been proven to improve model performance as it limits the partial observability aspect of the games. The work in \cite{Ammanabrolu:2020graph} propose using a dynamically learned Knowledge Graph (KG) with a novel graph mask to only fill out templates with entities already in the learned KG. 


\textbf{Large State Space} 
\label{sec:TG-large-state-space}

Whilst Textual Games, like all Reinforcement Learning problems, require some form of exploration to find better solutions, some papers focus specifically on countering that natural overfitting of Reinforcement Learning by actively encouraging exploration to unobserved states in new environments. For example, \cite{Yuan:2018} achieved this by setting a reward signal with a bonus for encountering a new state for the first time. This removes the agent's ability for high-level contextual knowledge of the environment in favor of simply searching for unseen states. 

Subsequent work by \cite{Cote:2018} - Treasure Hunter - has expanded on this by increasing the complexity of the environment with additional obstacles such as locked doors that need colour matching keys requiring basic object affordance and generalisation ability.

In a similar vein to Treasure Hunter, where in the worst case agents have to traverse all states to achieve the objective, the \textit{location} and \textit{existence} settings of QAit \cite{Yuan:2019} also require the same with the addition of stating the location or existence of an object in the generated game. 

These solutions are also related to the challenge of \textit{Exploration vs Exploitation} that is commonly referenced in all Reinforcement Learning literature \cite{Sutton:1998}.

\textbf{Large, Combinatorial and Sparse Action Spaces} 

Without any restrictions on length or semantics, Reinforcement Learning agents aiming to solve games in this domain face the problem of an unbounded action space. Early works limited the action phrases to two words sentences for a verb-object, more recently combinatory action spaces are considered that include action phrases with multiple verbs and objects. A commonly used method for handling combinatory action spaces has been to limit the agent to picking a template $T$ and then filling in the blanks with entity extraction \cite{Hausknecht:2019jericho,Ammanabrolu:2020grue,Guo:2020}. 

Two other approaches have been used: (i) action elimination \cite{Zahavy:2018,Jain:2020}, and (ii) generative models \cite{Tao:2018,Yao:2020}. The first aims to use Deep Reinforcement Learning with an Action Elimination Network for approximation of the admissibility function: whether the action taken changes the underlying game state or not. The second has been used in limited scope with pointer softmax models generating commands over a fixed vocabulary and the recent textual observation. The CALM generative model, leveraging a fine-tuned GPT-2 for textual games, has proved to be competitive against models using valid action handicaps.


\textbf{Long-Term Credit Assignment} 

Assigning rewards to actions can be difficult in situations when the reward signals are sparse. Specifically, positive rewards might only be obtained at the successful completion of the game. However, environments where an agent is unlikely to finish the game through random exploration provide rewards for specific subtasks such as in \cite{Murugesan:2020env,Trischler:2019,Hausknecht:2019jericho}. The reward signal structured in this way also aligns with hierarchical approaches such as in \cite{Adolphs:2020}. Lastly, to overcome the challenges presented with reward-sparsity, various hand-crafted reward signals have been experimented with \cite{Yuan:2018,Ammanabrolu:2020grue}. 


\textbf{Understanding Parser Feedback and Language Acquisition} 

LIGHT \cite{Urbanek:2019} is a crowdsourced platform for the experimentation of grounded dialogue in fantasy settings. It differs from the previous action-oriented environments by requiring dialogue with humans, embodied agents and the world itself as part of the quest completion. The authors designed LIGHT to investigate how \textit{`a model can both speak and act grounded in perception of its environment and dialogue from other speakers'}.

The work in \cite{Ammanabrolu:2020light} extended this by providing a system that incorporates: `1) large-scale language modelling based commonsense reasoning pre-training to imbue the agent with relevant priors and 2) a factorized action space of commands and dialogue'. Furthermore, evaluation can be performed against a dataset collected of held-out human demonstrations. 

\textbf{Commonsense Reasoning and Affordance Extraction} 

As part of their semantic interpretation, in order solve Textual Games commonsense knowledge is required. For example, modelling the association between actions and associated objects (\textit{opening} doors instead of \textit{cutting} them, or the fact that \textit{taking} items allows the agent to use them later on in the game). Various environments have been proposed for testing procedural knowledge in more distinct domains and to asses the agent's generalisation abilities.

For example, \cite{Trischler:2019} proposed the `First TextWorld Problems' competition with the intention of setting a challenge requiring more planning and memory than previous benchmarks. To achieve this, the competition featured `thousands of unique game instances generated using the TextWorld framework to share the same overarching theme - an agent is hungry in a house and has a goal of cooking a meal from gathered ingredients'. The agents therefore face a task that is more hierarchical in nature as cooking requires abstract instructions that entail a sequence of high-level actions on objects that are solved as sub-problems.

Furthermore, TW-Commonsense \cite{Murugesan:2020env} is explicitly built around agents leveraging prior commonsense knowledge for object-affordance and detection of out of place objects.

Two pre-training datasets have been proposed that form the evaluation goal for specialised modules of Reinforcement Learning agents. The ClubFloyd dataset\footnote{\url{http://www.allthingsjacq.com/interactive_fiction.html\#clubfloyd}} provides human playthroughs of 590 different text based games, allowing priors to be built and to pre-train generative action generators. Likewise, the Jericho-QA \cite{Ammanabrolu:2020grue} dataset provides context at a specific timestep in various classic IF games supported by Jericho, and a list of questions, enabling pre-training of QA systems in the domain of Text Games. They also used the dataset for fine-tuning a pre-trained language model for building a question-answering-based Knowledge Graph.


Lastly, ALFWorld \cite{Shridhar:2020} offers a new dimension by enabling the learning of a general policy in a textual environment and then tests and enhances it in an embodied environment with a common latent structure. The general tasks also require commonsense reasoning for the agent to make connections between items and attributes, e.g. (sink, ``clean"), (lamp, ``light"). Likewise, the \textit{attribute} setting of QAit \cite{Yuan:2019} environment demands agents to understand attribute affordances (cuttable, edible, cookable) to find and alter (cut, eat, cook) objects in the environment.


\textbf{Knowledge Representation} 

It can be specified that at any given time step, the game's state can be represented as a graph that captures observation entities (player, objects, locations, etc.) as vertices and the relationship between them as edges. As Text Games are partially observable, an agent can track its belief of the environment into a knowledge graph as it discovers it, eventually converging to an accurate representation of the entire game state \cite{Ammanabrolu:2018dqn}.

In contrast to methods which encode their entire Knowledge Graph into a single vector (as shown in \cite{Ammanabrolu:2020graph,Ammanabrolu:2020grue}), \cite{Xu:2020sha} suggests an intuitive approach of using multiple sub-graphs with different semantical meanings for multi-step reasoning. Previous approaches have relied on predefined rules and Stanford's Open Information Extraction \cite{Angeli:2015} for deriving information from observations for Knowledge Graph construction. The work in \cite{Adhikari:2020} have instead built an agent which is capable of designing and updating its belief graph without supervision.

%\cite{Guo:2020} reframes the Text Game problem by considering observations as passages in a multi-passage RC task. They use an object-centric past-observation retrieval to enhance current state representations with relevant past information and then apply attention to draw focus on correlations for action-value prediction.
