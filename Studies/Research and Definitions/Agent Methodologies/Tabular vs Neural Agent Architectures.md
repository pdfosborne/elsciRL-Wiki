# Summary

Any reinforcement learning agent must include a method for language understanding. 

An agent which stores every state-action value in a large lookup table is known as a *tabular* agent and has the limitation that every state is considered unique. A tabular agent has no intrinsic methodology for leveraging the contextual information of language.  ^1c5f81

Therefore, *neural* (a.k.a deep) agents {[[../../../References/Academic Papers/ArXiv/mnihPlayingAtariDeep2013|mnihPlayingAtariDeep2013]]} are introduced as they can transfer knowledge between similar states. 

To achieve this, a Deep-RL agent's architecture consists of two core components: 
1) **a state encoder** an encoder for transforming a state into a numeric form (typically vector)
2) **an action selection** method which enacts the agent's policy.
