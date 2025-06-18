# Online Demo Details

<div align="center">
	<a href="https://osbornep.pythonanywhere.com/" class="button-63">Try the Online Demo!</a>
</div>

This version is pre-rendered so that it can be hosted without incurring hosting costs and is simply to show how the user input can impact the agent's performance.

The problem is a simple sailing simulation where the boat's forward movement is calculated based on its angle against the wind. 

The agent can turn left or right thereby allowing it to navigate to the goal line where the episode ends (i.e. a complete run of the problem). However, if the sailboat hits the walls then the episode also ends but it will be given a negative reward instead of a positive one that it gets for reaching the goal line. 

When you provide an input instruction the agent will match this against how it 'sees' the problem as best it can. This best match is shown in the image and in the output log. If it was unable to correctly match your intent the first time you can adjust your phrasing of what you want to achieve to match the problem. 

Once you validate the best match is correct to your input, the agent will train with this factored into its learning how to complete the problem and results are shown on the next tab.

This problem can be solved using the standard numeric representation of the state space and this is what we used to train the 'Standard_Experiment' shown in the results.

Our results show that even a small amount of guidance can improve the agent's training. 

Furthermore, the input allows you to do this in an intuitive language form. This is in contrast to prior works in Reinforcement Learning that require a supervised input to reach a numeric position (e.g. if 0<x<0.5, 0<angle<0.5 then reward=+0.1) which then is hard-coded into the agent's training.
