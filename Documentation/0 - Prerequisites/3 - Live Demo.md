# Online Version

<a href="https://osbornep.pythonanywhere.com/" class="button">Try the Online Demo!</a>

This version is pre-rendered so that it can be hosted without incurring hosting costs and is simply to show how the user input can impact the agent's performance.

The problem is a simple sailing simulation where the boat's forward movement is calculated based on its angle against the wind. 

The agent can turn left or right thereby allowing it to navigate to the goal line where the episode ends (i.e. a complete run of the problem). However, if the sailboat hits the walls then the episode also ends but it will be given a negative reward instead of a positive one that it gets for reaching the goal line. 

When you provide an input instruction the agent will match this against how it 'sees' the problem as best it can. This best match is shown in the image and in the output log. If it was unable to correctly match your intent the first time you can adjust your phrasing of what you want to achieve to match the problem. 

Once you validate the best match is correct to your input, the agent will train with this factored into its learning how to complete the problem and results are shown on the next tab.

This problem can be solved using the standard numeric representation of the state space and this is what we used to train the 'Standard_Experiment' shown in the results.

Our results show that even a small amount of guidance can improve the agent's training. 

Furthermore, the input allows you to do this in an intuitive language form. This is in contrast to prior works in Reinforcement Learning that require a supervised input to reach a numeric position (e.g. if 0<x<0.5, 0<angle<0.5 then reward=+0.1) which then is hard-coded into the agent's training.

# Local Version
To run the full demo that can train an agent using your local machine, first ensure you have installed $elsciRL\geq0.1.7$ and $Flask$:

```
pip install elscirl
pip install flask
```

Once the required packages are installed, run the following code in a Python script.

```python
from elsciRL import Demo
Demo.run()
```

![](<./attachments/demo_local.png>)

This will give you a localhost link to open in a browser. The WebApp will look identical to the public demo but the back-end will compare your instruction against known environment positions to find the best match and then, if validated as a correct match, train the agent with this factored in.

By default the instruction agent will be run for 1,000 episodes to save time but you can increase or decrease this if you wish to change the training time.

When you use the 'Rerun the Demo' button it will track this as a new input id.

Once you've finished a test you can see the results will show on the WebApp and also save the full output in your local file directory.

## Understanding results

The results includes three charts, the first two show the route of the trained agent's best attempts. The first chart shows the route of the agent factoring in your instruction whereby the second is without.

The final and the last shows the average reward obtained per episode. The Standard Experiment is without your instruction and has been pre-trained with 10,000 episodes to compare against. 


### Example 1: 'Go to the beach side'
In this first example, the instruction guides the agent's training noticeably to the beach side. However, none of the training attempts managed to go from that guidance to the goal line and therefore in the final chart performs considerably worse than the agent without instructions.

![](<./attachments/demo_output_example_1.png>)

### Example 2: 'Go to the beach side' --> 'Turn back from the beach so the wind is on the starboard side of the boat'
We therefore add a second instruction to guide the boat to turn back towards the middle after it has reached the beach side and it now performed considerably better.

Interestingly, not all the instruction agent's attempts follow the input guidance. This is dependent on how strict we are with requiring it to follow the instruction but if the agent will always try to reach the end goal so it can sometimes find a path that works on its own.

Similarly, the agent without instructions can reach the end goal but less often and its paths are more random than those guided by our input.

![](<./attachments/demo_output_example_2.png>)

--- 
────────────────────────────────────────|**Next Steps:** [Getting Started](</Documentation/I - Introduction/1 - Getting Started.md>) </div>
