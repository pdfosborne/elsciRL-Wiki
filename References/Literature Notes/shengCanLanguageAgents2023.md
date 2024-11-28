---
zotero-key: HJ4ZMEXU
zt-attachments:
  - "10"
title: Can language agents be alternatives to PPO? A Preliminary Empirical Study On OpenAI Gym
citekey: shengCanLanguageAgents2023
---
# Can language agents be alternatives to PPO? A Preliminary Empirical Study On OpenAI Gym

[Zotero](zotero://select/library/items/HJ4ZMEXU) [attachment](<file:///home/philiposborne/Zotero/storage/XLWFVWZV/Sheng%20et%20al.%20-%202023%20-%20Can%20language%20agents%20be%20alternatives%20to%20PPO%20A%20Prel.pdf>)

> [!note] Page 3
> 
> Nonetheless, evaluating language agents’ decision-making capabilities (to decide which agents to use) in TextGym, which contains a set of classic sequence decision problems, with efficiency and fairness is challenging due to two factors.
> ^NIF2CYE6aXLWFVWZVp3

> [!note] Page 6
> 
> 
> 
> ---
> Definition - TextGym
> ^7BSG24UZaXLWFVWZVp6

> [!note] Page 6
> 
> 4.1 TextGym: A Friendly Gym for Language Agents We select OpenAI Gym (Brockman et al., 2016b) as our benchmark environment, owing to its extensive utilization in the assessment of PPO and other RL agents. In order to render Gym compatible with language agents, it is necessary to transform the environments into text-based representations, i.e., TextGym. It should be noted that we presuppose language agents possess access to the fundamental documentation of the environments. Concretely, we use the environment description, including the observation space, action space, reward function, and episode terminate conditions, for benchmarked environments in the official
> ^6QSWFXRHaXLWFVWZVp6

> [!note] Page 7
> 
> documentation1 for the transformation. We construct TextGym by adding a translation wrapper for OpenAI Gym. Specifically, the wrapper wraps each observation in a mixture of “game description”, “goal description”, “action space description”, and “observation description”.  To speed up the translation, we take GPT-4 (OpenAI, 2023) to make the translation, and the details are presented in Appendix A.1.
> ^49BX3XKLaXLWFVWZVp7

> [!note] Page 7
> 
> 
> 
> ---
> How this may be applied in the real world
> ^UZH5XL9SaXLWFVWZVp7

> [!note] Page 7
> 
> Remark 2: The assumption regarding the acquisition of documentation is justifiable, as documents are typically accessible in real-world applications (Harbour et al., 2001; Brockman et al., 2016a). By providing language agents with fundamental documentation, we emulate a pragmatic situation in which the agent possesses an elementary comprehension of the environment. This establishes the foundation for assessing language agents. In contrast to the prevailing handcrafted few-shot examples and heuristic prompting techniques, our assumption exhibits a higher degree of realism.
> ^T6CCXXK7aXLWFVWZVp7

> [!note] Page 21
> 
> 
> 
> ---
> Specification of TextGym language
> ^SQZASM9WaXLWFVWZVp21

> [!note] Page 21
> 
> A.1 Environments Details We summarize the environments of TextGym. We take the environments collected by OpenAI Gym as our backbone environments and employ GPT-4 (OpenAI, 2023) for the grounding procedure. OpenAI Gym provides exhaustive documentation elucidating the essential concepts of each environment. Initially, we develop a code template (Appendix A.1) predicated on the CartPole-v0 environment. This template encompasses three classes: ObsTranslator, GameDescriber, and TransitionTranslator. The ObsTranslator is responsible for converting each observation into a textual description, while the GameDescriber offers an introduction and delineates the objectives of the game. The TransitionTranslator grounds the observation, action, reward, and consecutive observation in a textual format. Upon completion of the code template, we adhere to the generation process illustrated in Figure 7 to ground additional environments. For each environment, we supply GPT-4 with the pertinent documentation and instruct it to generate the translation code in Python format. Utilizing our manually crafted code example, GPT-4 generates the remaining environments in a consistent manner. This grounding ensures that our environments obviate the need for GPT-4 queries during sampling, substantially reducing temporal and financial expenditures. In essence, we manually craft one environment and execute a single query for each environment translation, rendering our grounding process both efficacious and economical. To ground each environment, we first devise an example translation code as follows. Then we adopt GPT-4 to verify the code does not introduce additional information compared to the original document. After that, GPT-4 is further taken to ground all other environments as Figure 7.
> ^JA2DPQ43aXLWFVWZVp21

> [!note] Page 22
> 
> ![[./ImgExtracts/4QU43CYV.png]]
> 
> ---
> Overview diagram of language grounding method using GPT-4
> ^4QU43CYVaXLWFVWZVp22

> [!note] Page 22
> 
> ![[./ImgExtracts/375XLTAR.png]]
> 
> ---
> Adapter option for CartPole
> ^375XLTARaXLWFVWZVp22

> [!note] Page 23
> 
> ![[./ImgExtracts/HGH4BNPX.png]]
> ^HGH4BNPXaXLWFVWZVp23
