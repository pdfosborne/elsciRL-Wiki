[![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)](https://github.com/pdfosborne/elsciRL) [![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)](https://github.com/pdfosborne/elsciRL-Wiki)  [![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)](https://discord.gg/A2dRVrhB)

**Quicklinks:** [Homepage](<./README.md>)  | [Getting Started](<./Documentation/I - Introduction/1 - Getting Started.md>) | [Contributing Guide](<./Documentation/0 - Prerequisites/0 - New Developers.md>) | [Introduction to Language RL](<./Documentation/III - Language RL/1 - Introduction to Language RL.md>)

# What is the elsciRL framework?

The elsciRL approach is a generally applicable instruction following method whereby a two-layer hierarchy is formed: 1) a high level instruction plan and 2) the low level environment interaction. Uniquely, this work does not assume that instructions (or sub-goals) need to be supervised. Instead, we assume the environment contains some language such that this can be completed unsupervised. Furthermore, the unsupervised completion of each instruction is presented back to the user and their feedback strengthens the quality of the matching between observed environment positions and expected outcomes.

Instructions help greatly in mitigating the issue of long-term objectives never being reached and enable transfer of knowledge through the re-use of sub-instructions to new tasks.

To make this work possible, we built this software solution such that it could enable the application of this work to any Reinforcement Learning problem. Unlike other Reinforcement Learning packages that are only designed to enable the importing a pre-built agent we go much further.

First, we standardize the interaction loop setup such that setting up new problems is significantly easier and faster.

Second, instead of simply importing pre-built agents into a custom system we reverse this process so the interaction loop can be imported into far more complex hierarchical solutions without needing to be purpose built to each problems.

Lastly, analysis formatting and structure is generated such that the individual user only needs to interpret them to adjust parameters accordingly.

Provided a user can setup their problem using the template structure provided they can then leverage the most advanced Reinforcement Learning approaches with a simple parameter input. This also ensures the system is future-proof as new agents or encoders will be added as modules in later updates.

# What does elsciRL provide?

A principle challenge of Reinforcement Learning is that there is currently no standard approach to designing a language based Reinforcement Learning solution. Instead, individual applications are purpose built, requiring both extensive Reinforcement Learning and software experience and rarely can be applied to another problem without significant remodelling effort. **elsciRL’s** mission is to solve this.

The **elsciRL** framework separates the responsibilities of a Reinforcement Learning solution so that as much as possible can be applied by domain experts that may even be non-technical. 

To achieve this, we provide:

1. An open-source software to apply our framework with 'off the shelf' solutions
2. A centralized repository of applications and examples
3. A benchmarking suite to evaluate new methods 
4. Documentation for all experience levels
5. An open-source Wiki for the acceleration of language based reinforcement learning research
6. A public Discord server for the community to connect and collaborate




# What is included in the Python Library?

elsciRL includes an open-source Python library designed to make it easier to apply Reinforcement Learning to language problems.

This is achieved with the following novel features:
- Language problems are collected into centralized hub
- Encoders are separated into their own module, especially useful for language problems to test different transformer methods
- Simplified method for defining problems with language that are otherwise restricted to numeric features
- Interaction Loops, Analysis and Evaluation protocols are pre-built and ready to use
- Hierarchy methodologies are generally applicable so they can be more easily applied to new problems

# What are the suggested prerequisites? 
- Python experience
- Understand the basics of Reinforcement Learning
- Applied a Reinforcement Learning agent example with code