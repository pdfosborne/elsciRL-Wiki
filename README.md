# elsci AI
## Solve Reinforcement Learning with Language

<a href="https://elsci.org"><img src="https://raw.githubusercontent.com/pdfosborne/elsciRL-Wiki/refs/heads/main/Resources/images/elsci-whale-logo.png" align="left" height="150" width="150" ></a>

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



## What is elsci?

**elsci (pronounced L-SEE)** is an abbreviation of our mission: 

<div align="center">
 <i>"Everything can be automated using Language and Self-Completing Instructions".</i>
</div>

To achieve this, **elsci** offers a novel framework and infrastructure for accelerating the development of language based Reinforcement Learning (RL) solutions.

This has also been known as *AI agents* but we notably do not require the problem to already contain language.

See the [[Documentation/I - Introduction/1 - Getting Started|Getting Started]] for a first time user guide to applying the Python library. 

<img src="https://github.com/pdfosborne/elsciRL-Wiki/blob/main/Resources/images/elsciRL-key-benefits-AI.png?raw=true" />

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

*It will also produce animations showing the how well the best agent is currently trying to solve the problem.*

See [[Documentation/I - Introduction/1 - Getting Started|Getting Started]] for more information on applying to Python library.

## Download the Wiki

The elsciRL Wiki is written using [Obsidian.md](https://obsidian.md/) and backed-up through GitHub as an open-source documentation site. 

If you wish to download the documentation for personal use: ^58a83d
	1. Download the [elsciRL-Wiki](https://github.com/pdfosborne/elsciRL-Wiki/tree/main) (click the *Code* button > *Download ZIP*)
	2. Unzip the Vault to a local directory (e.g. inside Documents)
	3. [Download Obsidian.md](https://obsidian.md/download)
	4. Open the Obsidian software
	5. Select the *Open folder as Vault* option and then the *elsciRL-Wiki* folder 

See [[Documentation/0 - Prerequisites/1 - New Contributors|New Contributors Guide]] for more information on contributing to the open-source development of this project.

### Obsidian Configuration

By default, not all formatting will work without the correct plugins but they can be setup by:
1. Overriding the configuration folder in *Obsidian>Files and Links settings* to this folder *.obsidian-git* (see image below)
2. Lastly, restart obsidian

We also use a set of custom css snippets that you can enable in settings > appearance > CSS snippets at the bottom.

![osbsidian\_settings](https://raw.githubusercontent.com/pdfosborne/elsciRL-Wiki/refs/heads/main/Documentation/0%20-%20Prerequisites/attachments/Obsidian%20settings.png)

--- 

**First Time Users:** [FAQs](<./FAQs.md>) |───────────────--──| **Next Steps:** [Getting Started](<./Documentation/I - Introduction/1 - Getting Started.md>)
