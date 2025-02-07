\section{Challenges in Real-World RL}
 
 \cite(Dulac-Arnold, Mankowitz \& Hester, 2019) provide a more detailed description of the challenges of applying RL to real-life tasks. In summary, they outline 9 key challenges:

\begin{enumerate}
     \item Training off-line from the fixed logs of an external behaviour policy, 
     \item Learning on the real system from limited samples,
     \item High-dimensional continuous state and action spaces, 
     \item Safety constraints that should never or at least rarely be violated, 
     \item Tasks that may be partially observable, alternatively viewed as non-stationary or stochastic, 
     \item Reward functions that are unspecified, multi-objective, or risk-sensitive, 
     \item System operators who desire explainable policies and actions,
     \item Inference that must happen in real-time at the control frequency of the system, and, 
     \item Large and/or unknown delays in the system actuators, sensors, or rewards.    
 \end{enumerate}

Where points 1 and 2 match the need for considering generalisability and efficiency respectively and points 4, 7 \& 8 align with our final aim of interpretability.
