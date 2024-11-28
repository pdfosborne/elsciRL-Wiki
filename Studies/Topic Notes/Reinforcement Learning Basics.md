![[../Research and Definitions/RL Basics/Reinforcement Learning#Definition]]

## Tabular vs Neural Agent Architectures

The agent must include a method for language understanding. An agent which stores every state-action value in a large lookup table is known as a *tabular* agent and has the limitation that every state is considered unique. A tabular agent has no intrinsic methodology for leveraging the contextual information of language. Therefore, *neural* (a.k.a deep) agents \cite{Mnih:2013} are introduced as they can transfer knowledge between similar states. To achieve this, a Deep-RL agent's architecture (see Figure \ref{fig:AgentArchi}) consists of two core components: 1) an *encoder* for transforming a state into a numeric form (typically vector) and, 2) an *action selection* method which enacts the agent's policy.

A set of example agent implementations for numeric and language-based problems is shown in figures \ref{fig:agent_types_flat} and \ref{fig:agent_types_language}. In numeric solutions, the encoder is typically defined given the context of the problem specification. For example, a deck of cards can be defined as a binary vector of 52 items. A tabular agent has no inherent approach for generalising knowledge across similar states but typically requires less hardware and time to train than a neural agent if the problem is small. Language solutions typically use a pre-trained encoder (such as word2vec) that map observed information to a linguistic vector space. Text Games are notably defined by a generator approach rather than annotating language after a state has been observed using human labelling methods.

\begin{figure}[h!]
    \centering
    \includegraphics[scale=0.45]{figures/3-Text Games/TextGameArchi.png}
    \caption{Overview of the neural architecture structure of agents applied to a simple Text Game example.}
    \label{fig:AgentArchi}
\end{figure}

\begin{figure}[h!]
    \centering
    \includegraphics[width=\textwidth]{figures/2-Background/agent_types_flat.png}
    \caption{Examples of the application of agent architectures to traditional Reinforcement Learning problems.}
    \label{fig:agent_types_flat}
\end{figure}

\begin{figure}[h!]
    \centering
    \includegraphics[width=\textwidth]{figures/2-Background/agent_types_language.png}
    \caption{Examples of the application of agent architectures to a language based problems.}
    \label{fig:agent_types_language}
\end{figure}
