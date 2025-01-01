# Solving Reinforcement Learning with Language

<a href="https://elsci.org"><img src="https://github.com/pdfosborne/elsciRL-Wiki/blob/main/Resources/images/elsci-whale-logo.png" align="left" height="160" width="160" ></a>

<div align="center">

<b>Automate Anything, Automate Everything!</b>
<br>
Visit our <a href="https://elsci.org">website</a> to get started, explore our <a href="https://github.com/pdfosborne/elsciRL-Wiki">open-source Wiki</a> to learn more or join our <a href="https://discord.gg/GgaqcrYCxt">Discord server</a> to connect with the community.
<br>
<i>In early Alpha Development.</i>
</div>

<div align="center">

<a href="https://github.com/pdfosborne/elsciRL">![elsciRL GitHub](https://img.shields.io/github/watchers/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)</a> <a href="https://github.com/pdfosborne/elsciRL-Wiki">![Wiki GitHub](https://img.shields.io/github/watchers/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)</a> <a href="https://discord.gg/GgaqcrYCxt">![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)</a>

</div>

**Quicklinks:**  [FAQs](<./FAQs.md>) | [Getting Started](<./Documentation/I - Introduction/1 - Getting Started.md>) | [Contributing Guide](<./Documentation/0 - Prerequisites/1 - New Contributors.md>) | [Intro to Language RL](<./Documentation/III - Language RL/1 - Introduction to Language RL.md>)


## What is elsciRL?

**elsciRL (pronounced L-SEE)** is an abbreviation of our mission: 

<div align="center">
 <i>"Everything can be automated using Language and Self-Completing Instructions in Reinforcement Learning".</i>
</div>

To achieve this, **elsciRL** offers a novel framework and infrastructure for accelerating the development of language based Reinforcement Learning solutions.

This is also known as *AI agents* in relation to Large Language Model development (e.g. ChatGPT).

## Quick-start

1. Install the Python library
```
pip install elsciRL
```
2. Run the demo experiment in a Python shell
```python
from elsciRL import DemoExperiment
exp = DemoExperiment()
exp.run()
exp.evaluate()
``` 
*This will run a Reinforcement Learning experiment on two simple problems (OpenAI Gym's FrozenLake and a Sailing Simulation)*.* 

*The 'evaluate' function will produce animations showing the how well the best agent is currently trying to solve the problem. It will also return a combined chart for the experiments you just ran, examples of this are shown below!*

**First Time Users:** [FAQs](<../../FAQs.md>) |────────────────────────────| **Next Steps:** [Getting Started](<./Documentation/I - Introduction/1 - Getting Started.md>) </div>


<div align="center">
  <img src="https://github.com/pdfosborne/elsciRL-Wiki/blob/main/Documentation/I%20-%20Introduction/attachments/sailing_setup.png?raw=true" width="240" />
  <img src="https://raw.githubusercontent.com/pdfosborne/elsciRL-Wiki/refs/heads/main/Documentation/I%20-%20Introduction/attachments/sailboat_render_animation.gif" width="300" /> 
</div>

![variance\_comparison\_TRAINING](<./Documentation/I - Introduction/attachments/variance_comparison_TRAINING.png>)

