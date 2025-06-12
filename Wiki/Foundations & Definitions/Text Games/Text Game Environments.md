Thus far, the majority of researchers have independently generated their own environments with TextWorld \cite{Cote:2018}. As the field moves towards more uniformity in evaluation, a clear overview of which environments are already generated, their design goals and the benchmark approach is needed.

Table \ref{tasks2} shows the publicly available environments and datasets. Much of the research in text games has been published in recent years (2018-2020). Jericho's Suite of Games (SoG) \cite{Hausknecht:2019jericho} is a collection of 52 games and therefore has its results averaged across all games included in evaluation.

We find that many of the environments focus on exploring increasingly complex environments to \textit{`collect'} an item of some kind ranging from a simple coin to household objects. This is due to the TextWorld generator's well defined logic rules for such objects but this can also be a limitation on the possible scope of the environment.
% Most environments focus on one type of evaluation setting, either single or zero-shot, with only Coin Collector being used for all three types (single, joint and zero-shot) so far. 


When evaluating an agent's performance, three types of evaluation settings are typically considered:

\begin{itemize}
    \item \textbf{Single Game} evaluates agents in the same game under the same conditions,
    \item \textbf{Joint} settings evaluate agents trained on the same \textit{set} of games that typically share some similarities in the states seen,
    \item \textbf{Zero-Shot} settings evaluate agents on games completely unseen in training.
\end{itemize}

The difficulty settings of the environments are defined by the complexity of the challenges that the agents are required to overcome. In most cases, these have been limited to just a few levels. However, CookingWorld defines the challenge by a set of key variables that can be changed separately or in combination and therefore does not offer clear discrete difficulty settings.

The maximum number of rooms and objects depends heavily on the type of task. Coin Collector for example has only one object to find as the complexity comes from traversing a number of rooms. Alternatively, CookingWorld has a limited number of rooms and instead focuses on a large number of objects to consider. Zork is naturally the most complex in this regard as an adaptation of a game designed for human players. Likewise, the complexity of the vocabulary depends heavily on the task but it is clear to see that the environments limit the number of Action-Verbs for simplicity.

TODO ADD TABLE IMAGE