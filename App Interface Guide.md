# First Time Setup
<div align="center">

<a href="https://github.com/pdfosborne/elsciRL">![elsciRL GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)</a> <a href="https://github.com/pdfosborne/elsciRL-Wiki">![Wiki GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)</a> <a href="https://discord.gg/GgaqcrYCxt">![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)</a>

</div>

**Quicklinks:** [Homepage](https://elsci.org) | [About Us](https://elsci.org/About+us) | [FAQs](https://elsci.org/FAQs) | [New Developers](https://elsci.org/New+Developers)  | [Contributing Guide](https://elsci.org/Become+a+Contributor)

## Quick-Start

Install the Python library from the PyPi package library:

```bash
pip install elsciRL
```

*See the [elsciRL install guide](https://github.com/pdfosborne/elsciRL?tab=readme-ov-file#install-guide) for more install options.*

Once the required packages are installed, run the following code in a Python script.

```python
from elsciRL import App
App.run()
```

This will give you a localhost link to open in a browser. 

The App will looks similar to the [public demo](https://osbornep.pythonanywhere.com/) except now the algorithm will directly compare your instruction against known environment positions to find the best match. Furthermore, if validated as a correct match it will use your computer resources to train the agent with this factored in.

By default the instruction agent will be run for 1,000 episodes to save time but you can increase or decrease this if you wish to change the training time.

Once you've finished a test you can see the results will show on the App and also save the full output in your local file directory.

<div align="center">
	<iframe width="700" height="400"  
		src="https://www.youtube.com/embed/JbPtl7Sk49Y">  
	</iframe>
</div>

## Configuration

The interface allows you to select the application you wish to apply agents to. You can learn how to add your own application or methods by following the [New Developers Guide](https://elsci.org/New+Developers).

For now, you can simply select one of the applications already set up such as the sailing simulation. 

You can then choose the local configuration and analysis reporting to use, these allow you to compare you method on the exact specification and challenges used in prior works without needing to set it up yourself.

You can then choose a set of experiment parameters such as number of training episodes and repeats.

Lastly, you can select the agents to train for this experiment and their parameters. 

## Instruction Input

This is a unique feature of elsciRL that lets you input language based instructions on any reinforcement learning problem. 

The objective is to help the agent reach the goal more often with fewer samples. 

You can input any number of instructions separated by a line break (i.e. pressing enter after each). Once you submit your set of instructions the agent will do its best attempt to match these against how it understands the problem setting. 

If the agent doesn't match what was intended you can submit a new set of instructions with more detail or more aligned to the agents's knowledge of the problem.

When you are happy with the predicted positions you can submit these as correct and the agent will then train to reach the end goal with your input instructions and their confirmed sub-goal positions in the environment factored in.

## Results

The results include charts specific to the problem type and a set of summary reward figures based on the analysis selected in the configuration tab.

For example, the sailing problem shows travel paths the agent has taken during training. 

One chart shows the route of the agent factoring in your instruction (denoted with '*Instruction*' in the title label) whereby the other is without (denotes as '*Standard Experiment'*).

The final and the last shows the average reward obtained per episode with standard deviation calculated across the repeated training samples.


### Example 1
***'Go to the beach side'***
In this first example, the instruction guides the agent's training noticeably to the beach side. However, none of the training attempts managed to go from that guidance to the goal line and therefore in the final chart performs considerably worse than the agent without instructions.

![](<./Documentation/0 - Prerequisites/attachments/demo_output_example_1.png>)

### Example 2
***'Go to the beach side' --> 'Turn back from the beach so the wind is on the starboard side of the boat'***
We therefore add a second instruction to guide the boat to turn back towards the middle after it has reached the beach side and it now performed considerably better.

Interestingly, not all the instruction agent's attempts follow the input guidance. This is dependent on how strict we are with requiring it to follow the instruction but if the agent will always try to reach the end goal so it can sometimes find a path that works on its own.

Similarly, the agent without instructions can reach the end goal but less often and its paths are more random than those guided by our input.

![](<./Documentation/0 - Prerequisites/attachments/demo_output_example_2.png>)


<div id="sticky-button">
  <a href="https://discord.gg/GgaqcrYCxt"><img src="https://raw.githubusercontent.com/pdfosborne/elsciRL-Wiki/refs/heads/main/Resources/images/discord_icon.png" width="50"></a>
</div>