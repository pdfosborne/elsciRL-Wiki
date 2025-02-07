%\subsection{Grounding Natural Language in Reinforcement Learning}

%A special note needs to be made to (ref)[https://www.cs.princeton.edu/~karthikn/assets/pdf/thesis.pdf] which introduce a novel approach to "integrate Reinforcement Learning with language understanding to induce grounded representations of semantics". The authors found that "by learning to ground the meaning of the text to dynamics of the environment such as transitions and rewards, an agent can effectively bootstrap policy learning on a new domain.".

% Specifically, the author submits three main contributions:

% \begin{itemize}
% 	\item Learning representations for language to navigate text-based games: Given access to an interactive environment such as a text adventure game, we demonstrate how to effectively learn task-optimised representations for natural language without requiring any manual annotations. With unstructured feedback from the environment, we also simultaneously learn a control policy that can utilise this representation to navigate the domain.
% 	\item Leveraging language to enable policy transfer: We explore the utility of language as a compact representation of knowledge that enables cross-domain transfer for Reinforcement Learning. As we demonstrate empirically, access to even a small amount of textual descriptions results in substantially improved learning for new domains.
% 	\item Autonomous exploration and aggregation of evidence to improve information extraction: We propose a novel framework for improving information extraction by autonomously querying, retrieving and aggregating external evidence from the world wide web. Leveraging the redundant information present across articles on the same event, we demonstrate more accurate and reliable extraction, especially in low-resource scenarios. This technique can also be adapted to other related NLP tasks like question answering or automated dialogue agents.
% \end{itemize}

%The first contribution is interesting but is not used directly within our methodology as the approach relies on an environment that is built in natural language descriptions. Therefore, the agent is, by design of the environment, built to learn language as the state space. However, the authors found that "by learning to ground the meaning of the text to dynamics of the environment such as transitions and rewards, an agent can effectively bootstrap policy learning on a new domain.". An important result which suggests promise for our approach to improve generalisability with natural language. 
