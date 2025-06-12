# POMDP
## Definition

In problems such as Text Games, the environment states are never directly observed but rather textual feedback is provided after entering a command. As specified by \cite{Cote:2018}, a Text Game is a discrete-time Partially Observed Markov Decision Process (POMDP) defined by $< S, A, T, \Omega, O, R, \gamma >$ where we now have the addition of the set of observations ($\Omega$) and a set of conditional observed probabilities $O$. Specifically, the function $O$ selects from the environment state the information to be shown to the agent given the command entered to produce each observation $o_t \in \Omega$. 

The following figures \ref{fig:POMDP-example-1} and \ref{fig:POMDP-example-2} illustrate examples of the complexity of the language used to describe positions in Text Game environments. The latter shows *"sample gameplay for the classic dungeon game Zork1. The objective is to solve various puzzles and collect the 19 treasures to install the trophy case. The player receives textual observations describing the current game state and additional reward scalars encoding the game designers’ objective of game progress. The player sends textual action commands to control the protagonist."* \cite{Guo:2020}. These demonstrate the two primary challenges of text based environments that are considered in the following sections; 1) the observable information is a limited view of the position (i.e. partially observable) and, 2) language understanding is required to connect actions to objects. The challenge of partial observability is highlighted in Figure \ref{fig:POMDP-example-2} where each observation only contains a limited view of the player's position. A thorough analysis of all the challenges of Text Games is provided later in Section \ref{sec:TG-challenges}.

\begin{figure}[h!]
    \centering
    \includegraphics[scale=0.5]{figures/2-Background/text_game_example_1.jpg}
    \caption{Example of a partially observed state from a Text Game \cite{POMDP-example}.}
    \label{fig:POMDP-example-1}
\end{figure}


\begin{figure}[h!]
    \centering
    \includegraphics[scale=0.85]{figures/2-Background/text_game_example_3.jpg}
    \caption{Sample gameplay for the classic dungeon game Zork1.}
    \label{fig:POMDP-example-2}
\end{figure}
