# Pre-Configured Applications

The following applications are simple problems that allow us to try out some of the features of elsciRL. 

A more complete set of applications can be found in the elsciRL Applications directory (*REF - Needs to be GitHub link*).

| **Author**           | **Title** | **Source**       | **Description**                              |
|:-------------------- |:-------------------- |:------------- |:-------------------------------------------- |
| **elsciRL**           | Classroom            | *https://...* | *A GridWorld based problem.* |
|                      | Sailing              | *https://...* | *A simulation of Sailing.*                     |
| **OpenAI Gymnasium** | FrozenLake           | *https://...* | *Application of...*                          |
|                      | CartPole             | *https://...* | *Application of...*                          |



# Running your first Application

Applications are specifications of the Reinforcement Learning environment. 

This is composed of the data engine and encoder that defines the form of state and and actions.

The general approach is the following:
1. Find an application repository
2. Clone to a local directory
3. Activate the elsciRL Python environment:``conda activate elsciRL_env``
4. Run an experiment by executing the *main.py* script:```python main.py```

For example, we will use the FrozenLake problem from OpenAi's Gymnasium:

```
git clone https://github.com/pdfosborne/elsciRL-GymFrozenLake
```

*Then, run the pre-configured experiment:* 
```
python main.py
```
	
If there are no issues, the training procedure should start with results saved in the *output* folder (see [3 - Output Format](<./3 - Output Format.md>) for more information on these).

![Running an Experiment](<./_images/Running an Experiment.png>)

- [ ] TODO: UPDATE VIDEO TO MATCH GUIDE (➕ 2025-03-24)

![test\_image](<./_images/test_image.gif>)


## Running in an IDE

If you want to run the code from your IDE you will first need to select the environment we create before. 

For example, in VS Studio Code for example this can be done using the command ‘Python: Select Interpreter’ or clicking the current Python environment on the bottom right toolbar.

![VS Code Interpreter 1](<./_images/VS Code Interpreter 1.png>)
![VS Code Interpreter 2](<./_images/VS Code Interpreter 2.png>)

You can then open the *main.py* file and run this inside the IDE.

# Custom Parameters

Each application will have an experiment and problem configuration file. The former controls the agent and evaluation and the latter is to control the environment and data engine.

These are explained in more detail in [4 - Configuration](<./4 - Configuration.md>) but you can edit these to test how it effects the training and testing procedures.

