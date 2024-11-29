Table of Contents

- [Installing the elsciRL Package](<#installing-the-elscirl-package>)
	- [1. Open the terminal (or Command Prompt) and run the following](<#1-open-the-terminal-or-command-prompt-and-run-the-following>)
	- [2. Once installed, activate the newly created environment](<#2-once-installed-activate-the-newly-created-environment>)
	- [3. Then, simply install the package through the PyPi interface](<#3-then-simply-install-the-package-through-the-pypi-interface>)
- [Test the installation](<#test-the-installation>)
	- [Test using the built-in example experiment](<#test-using-the-built-in-example-experiment>)
		- [Custom parameters: User Input](<#custom-parameters-user-input>)
		- [Custom parameters: Manually Defined](<#custom-parameters-manually-defined>)
		- [Combined analysis output](<#combined-analysis-output>)
		- [Running the examples as a complete script](<#running-the-examples-as-a-complete-script>)
	- [Test the installation  with a downloaded application](<#test-the-installation--with-a-downloaded-application>)
- [Notes](<#notes>)
---
TO-DO:
 - [ ] Update images to 'elsciRL'
---
# Installing the elsciRL Package
To get started using elsciRL, it is first suggested to setup a new Python environment. This can be completed easily with [Anaconda](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#) with a recent or newest Python version. 

## 1. Open the terminal (or Command Prompt) and run the following

```
conda create -n elsciRL_env python=3.11
```
	
![QuickStart Terminal](<./attachments/QuickStart Terminal.png>)

*You can change the name from elsciRL_env to anything you'd like and update the Python version if needed.*

## 2. Once installed, activate the newly created environment

```
conda activate elsciRL_env
```
	
## 3. Then, simply install the package through the PyPi interface

```
pip install elsciRL
```

*This will install the required libraries alongside the core elsciRL package.*

# Test the installation 

## Test using the built-in example experiment

Once the elsciRL package is installed, you can run a quick experiment on a small set of pre-configured problems. 

First, create a folder for saving the output then navigate to this directory in the command line. For example:

```
cd Documents/elsciRL-Tests
```
*Note - you will need to create the folder 'Examples' inside your documents for this to be accessible.*

In the command line, enter the following command to enter the Python mode:

```
python
```

You can now write and run Python code line by line. First, we need to import the example experiment from elsciRL:

```python
from elsciRL.examples.experiment import DemoExperiment
```

This imports the DemoExperiment module but it is not initialised yet, to do this we simply need to call it and we also assign it a name:

```python 
exp = DemoExperiment()
```

Now we can simply use its function to run the pre-set examples:

```python 
exp.run()
```

This will complete a training and testing phase for a small set of example problems using a tabular Q-learning agent.

![Demo Experiment](<./attachments/Demo Experiment.png>)

Once complete, files will be saved in a timestamped directory for each problem that was run.

![Demo Experiment Output](<./attachments/Demo Experiment Output.png>)


### Custom parameters: User Input

The *DemoExperiment* module includes two methods for providing your own parameters.

First, you can call the input function that allows you to select which problems you would like to test and provide the number of training episodes. This can be done as follows:

```python
exp.user_input()
```


![Demo Experiment User Input](<./attachments/Demo Experiment User Input.png>)

### Custom parameters: Manually Defined

Alternatively, you can manually specify more parameters and even hyper-parameters for the tabular Q-learning agent with the following function call:

```python
exp.manual_config_overwrite(
	selected_problems=['sailing','frozenlake'],
	num_train_episodes=1000, num_train_repeats=5,
	num_test_episodes=10, number_test_repeats=5,
	Qlearntab_params={
		'alpha':0.1, 'gamma':0.95, 'epsilon':0.2, 'epsilon_step':0.01
	}
)
```

For example, the following would set the number of training episodes and only run the sailing example:

```python
exp.manual_config_overwrite(selected_problems='sailing', num_train_episodes=25000)
```

*Note - you will need to run all changes in a single call of this function. You can reset to default parameters by simply using: 

```python
exp.manual_config_overwrite()
```

Once an updated set of parameters are defined by either method, you can simply re-call:

```python 
exp.run()
```

### Combined analysis output

By default, results are shown for each agent's training and testing procedure and the summarised for the problem type.

You can run an example visual analysis that elsciRL provides by simply calling the following function:

```python
exp.analyze()
```


This will return a combined analysis for both training and testing of all problems the were run. 

![variance\_comparison\_TRAINING](<./attachments/variance_comparison_TRAINING.png>)

Understanding these results are explained in more detail in [3 - Output Format](<./3 - Output Format.md>) but for now, the simple rule is more reward is better. 

This is highlighted best in the graphs on the left side where reward is shown on the y-axis. In other words, the red line for the Default adaptor on the Sailing problem returns the highest reward in training these parameters.

### Running the examples as a complete script

If you wish to test this demo out further, you can create a simple Python script file to run more results. An example of this could look like the following:

```python title:test.py
from elsciRL.examples.experiment import DemoExperiment

exp = DemoExperiment()

exp.manual_config_overwrite(
	num_train_episodes=10000, num_train_repeats=25,
	num_test_episodes=250, number_test_repeats=10,
	Qlearntab_params={
		'alpha':0.05, 'gamma':0.95, 'epsilon':0.4, 'epsilon_step':0.01
	}
)

exp.run()
exp.analyze()
```

This can be saved (e.g. as *test.py*) and ran like any other Python script in your IDE simply using the following in the terminal:

```
python test.py
```


# Notes
- You will need to have Python installed, ideally alongside Anaconda for defining the environment.
- You will need to have Git installed if you wish to clone the demo application, otherwise you can manually download an application from its GitHub repository.
- If you are interested in using the GPU instead of CPU to train agents, then you will need to setup [CUDA](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/) on your machine.

---

--- start-multi-column: ExampleRegion1  
```column-settings  
number of columns: 2  
largest column: none  
```

**Previous:** [FAQs](<../../FAQs.md>)

--- end-column ---

 **Next:** [2 - Basic Applications](<./2 - Basic Applications.md>)

--- end-multi-column