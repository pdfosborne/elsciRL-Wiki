# Automate Anything, Automate Everything.

[![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)](https://github.com/pdfosborne/elsciRL) [![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)](https://github.com/pdfosborne/elsciRL-Wiki)  [![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)](https://discord.gg/A2dRVrhB)

**Quicklinks:**  [FAQs](<./FAQs.md>) | [Getting Started](<./Documentation/I - Introduction/1 - Getting Started.md>) | [Contributing Guide](<./Documentation/0 - Prerequisites/0 - New Developers.md>) | [Introduction to Language RL](<./Documentation/III - Language RL/1 - Introduction to Language RL.md>)


## What is elsciRL?

**elsciRL (pronounced L-SEE)** is an abbreviation of our mission: *"Everything can be automated using Language and Self-Completing Instructions in Reinforcement Learning"*.

To achieve this, **elsciRL** offers a novel framework and infrastructure for accelerating the development of language based Reinforcement Learning solutions.

## Quick-start

1. Install the Python library
```
pip install elsciRL
```
2. Run the demo experiment in a Python shell
```python
from elsciRL.examples.experiment import DemoExperiment
exp = DemoExperiment()
exp.run()
exp.analyze()
``` 
*This will run a Reinforcement Learning experiment on two simple problems (OpenAI Gym's FrozenLake and a Sailing Simulation).*

*The analyze function will return a combined chart for the experiments you just ran!*

![variance\_comparison\_TRAINING](<./attachments/variance_comparison_TRAINING.png>)


## What does elsciRL provide?

A principle challenge of Reinforcement Learning is that there is currently no standard approach to designing a language based Reinforcement Learning solution. Instead, individual applications are purpose built, requiring both extensive Reinforcement Learning and software experience and rarely can be applied to another problem without significant remodelling effort. **elsciRL’s** mission is to solve this.

The **elsciRL** framework separates the responsibilities of a Reinforcement Learning solution so that as much as possible can be applied by domain experts that may even be non-technical. 

To achieve this, we provide:

1. An open-source software to apply our framework with 'off the shelf' solutions
2. A centralized repository of applications and examples
3. A benchmarking suite to evaluate new methods 
4. Documentation for all experience levels
5. An open-source Wiki for the acceleration of language based reinforcement learning research
6. A public Discord server for the community to connect and collaborate



