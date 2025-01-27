# How to Use the App Interface
<div align="center">

<a href="https://github.com/pdfosborne/elsciRL">![elsciRL GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)</a> <a href="https://github.com/pdfosborne/elsciRL-Wiki">![Wiki GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)</a> <a href="https://discord.gg/GgaqcrYCxt">![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)</a>

</div>

**Quicklinks:** [FAQs](<./FAQs.md>) | [Getting Started](<./Documentation/I - Introduction/1 - Getting Started.md>)  | [Contributing Guide](<./Become a Contributor.md>)

## Run the App

You will need to install the elsciRL python package to get started - use the [elsciRL install guide](https://github.com/pdfosborne/elsciRL?tab=readme-ov-file#install-guide) if you are a first time user.

Once the required packages are installed, run the following code in a Python script.

```python
from elsciRL import App
App.run()
```

This will give you a localhost link to open in a browser. 

The App will looks similar to the [public demo](https://osbornep.pythonanywhere.com/) except now the algorithm will directly compare your instruction against known environment positions to find the best match. Furthermore, if validated as a correct match, will use your computer resources to train the agent with this factored in.

By default the instruction agent will be run for 1,000 episodes to save time but you can increase or decrease this if you wish to change the training time.

Once you've finished a test you can see the results will show on the App and also save the full output in your local file directory.

<div align="center">
	<iframe width="600" height="425"  
		src="https://www.youtube.com/embed/JbPtl7Sk49Y">  
	</iframe>
</div>

## Input

The interface allows you to select the application you wish to apply agents to. You can learn how to add your own application or methods by following the [getting started guide](<./Documentation/I - Introduction/1 - Getting Started.md>).

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


### Example 1: 'Go to the beach side'
In this first example, the instruction guides the agent's training noticeably to the beach side. However, none of the training attempts managed to go from that guidance to the goal line and therefore in the final chart performs considerably worse than the agent without instructions.

![](<./Documentation/0 - Prerequisites/attachments/demo_output_example_1.png>)

### Example 2: 'Go to the beach side' --> 'Turn back from the beach so the wind is on the starboard side of the boat'
We therefore add a second instruction to guide the boat to turn back towards the middle after it has reached the beach side and it now performed considerably better.

Interestingly, not all the instruction agent's attempts follow the input guidance. This is dependent on how strict we are with requiring it to follow the instruction but if the agent will always try to reach the end goal so it can sometimes find a path that works on its own.

Similarly, the agent without instructions can reach the end goal but less often and its paths are more random than those guided by our input.

![](<./Documentation/0 - Prerequisites/attachments/demo_output_example_2.png>)

# Online Demo
<a href="https://osbornep.pythonanywhere.com/" class="button-63">Try the Online Demo!</a>

This version is pre-rendered so that it can be hosted without incurring hosting costs and is simply to show how the user input can impact the agent's performance.

The problem is a simple sailing simulation where the boat's forward movement is calculated based on its angle against the wind. 

The agent can turn left or right thereby allowing it to navigate to the goal line where the episode ends (i.e. a complete run of the problem). However, if the sailboat hits the walls then the episode also ends but it will be given a negative reward instead of a positive one that it gets for reaching the goal line. 

When you provide an input instruction the agent will match this against how it 'sees' the problem as best it can. This best match is shown in the image and in the output log. If it was unable to correctly match your intent the first time you can adjust your phrasing of what you want to achieve to match the problem. 

Once you validate the best match is correct to your input, the agent will train with this factored into its learning how to complete the problem and results are shown on the next tab.

This problem can be solved using the standard numeric representation of the state space and this is what we used to train the 'Standard_Experiment' shown in the results.

Our results show that even a small amount of guidance can improve the agent's training. 

Furthermore, the input allows you to do this in an intuitive language form. This is in contrast to prior works in Reinforcement Learning that require a supervised input to reach a numeric position (e.g. if 0<x<0.5, 0<angle<0.5 then reward=+0.1) which then is hard-coded into the agent's training.


--- 
────────────────────────────────────────|**Next Steps:** [Getting Started](<./Documentation/I - Introduction/1 - Getting Started.md>) </div>
