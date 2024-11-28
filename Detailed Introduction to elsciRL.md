![elsciRL_logo|150x150](<./Resources/images/elsciRL_logo.png>)
# elsciRL (pronounced L-SEE)

*Every problem can be automated with Language and Self-Completing Instructions.*

![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-TextWorldExpress?style=for-the-badge&logo=github&label=Followers&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-TextWorldExpress) ![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-TextWorldExpress?style=for-the-badge&logo=github&label=Followers&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-TextWorldExpress) ![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-TextWorldExpress?style=for-the-badge&logo=github&label=Followers&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-TextWorldExpress)  ![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)  

**Quicklinks:** [Homepage](<./README.md>) | [New Developers](<./New Developers.md>)  | [Getting Started](<./elsciRL Core/I - Introduction/1 - Getting Started.md>) | [Introduction to Language RL](<./elsciRL Core/III - Language RL/1 - Introduction to Language RL.md>)

# What is the elsciRL framework?

The elsciRL approach is a generally applicable instruction following method whereby a two-layer hierarchy is formed: 1) a high level instruction plan and 2) the low level environment interaction. Uniquely, this work does not assume that instructions (or sub-goals) need to be supervised. Instead, we assume the environment contains some language such that this can be completed unsupervised. Furthermore, the unsupervised completion of each instruction is presented back to the user and their feedback strengthens the quality of the matching between observed environment positions and expected outcomes.

Instructions help greatly in mitigating the issue of long-term objectives never being reached and enable transfer of knowledge through the re-use of sub-instructions to new tasks.

To make this work possible, we built this software solution such that it could enable the application of this work to any Reinforcement Learning problem. Unlike other Reinforcement Learning packages that are only designed to enable the importing a pre-built agent we go much further.

First, we standardize the interaction loop setup such that setting up new problems is significantly easier and faster.

Second, instead of simply importing pre-built agents into a custom system we reverse this process so the interaction loop can be imported into far more complex hierarchical solutions without needing to be purpose built to each problems.

Lastly, analysis formatting and structure is generated such that the individual user only needs to interpret them to adjust parameters accordingly.

Provided a user can setup their problem using the template structure provided they can then leverage the most advanced Reinforcement Learning approaches with a simple parameter input. This also ensures the system is future-proof as new agents or encoders will be added as modules in later updates.

# Python Library

elsciRL includes an open-source Python library designed to make it easier to apply Reinforcement Learning to language problems.

This is achieved with the following novel features:
- Language problems are collected into centralized hub
- Encoders are separated into their own module, especially useful for language problems to test different transformer methods
- Simplified method for defining problems with language that are otherwise restricted to numeric features
- Interaction Loops, Analysis and Evaluation protocols are pre-built and ready to use
- Hierarchy methodologies are generally applicable so they can be more easily applied to new problems

### Suggested Prerequisites 
- Python experience
- Understand the basics of Reinforcement Learning
- Applied a Reinforcement Learning agent example with code