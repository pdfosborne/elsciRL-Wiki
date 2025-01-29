# Quick-start

Install the Python library (see the [install guide](https://github.com/pdfosborne/elsciRL#install-guide) for more options)
```
pip install elsciRL
```

Run the App Interface with the following code in a Python script.  
```python
from elsciRL import App
App.run()
```

This will give you a localhost link to open the App in a browser. This enables you to select a problem, change parameters and then input instructions to guide the agent before training. 

Once you've finished a test you can see the results will show on the App and also save the full output in your local file directory.

*Click the image to watch the demo video*

[![YouTube](http://i.ytimg.com/vi/JbPtl7Sk49Y/hqdefault.jpg)](https://www.youtube.com/watch?v=JbPtl7Sk49Y)

# Guide for New Developers

If you wish to apply the elsciRL library to your own problems or design your own algorithms you will need to understand how to train agents without the App interface. 

To edit the core elsciRL library you will need to install it as an editable package, we suggest doing this in a [Python environment](https://github.com/pdfosborne/elsciRL#using-a-python-environment)).
```
git clone https://github.com/pdfosborne/elsciRL.git
cd elsciRL
pip install -e .
```

## Test the installation 

### Test using the built-in example experiment

Once the elsciRL package is installed, you can run a quick experiment on a small set of pre-configured problems. 

In the command line, enter the following command to enter the Python mode:

```
python
```

You can now write and run Python code line by line. First, we need to import the example experiment from elsciRL:

```python
from elsciRL import DemoExperiment
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

Once complete, files will be saved in a timestamped directory for each problem that was run.

![demo\_gif](<./attachments/elsciRL_demo_short.gif>)

#### Custom parameters: User Input

The *DemoExperiment* module includes two methods for providing your own parameters.

First, you can call the input function that allows you to select which problems you would like to test and provide the number of training episodes. This can be done as follows:

```python
exp.input()
```

#### Custom parameters: Manually Defined

Alternatively, you can manually specify more parameters and even hyper-parameters for the tabular Q-learning agent with the following function call:

```python
exp.config(
	num_train_episodes=1000, num_train_repeats=5,
	num_test_episodes=10, number_test_repeats=5,
	Qlearntab_params={
		'alpha':0.1, 'gamma':0.95, 'epsilon':0.2, 'epsilon_step':0.01
	}
)
```

For example, the following would set the number of training episodes and only run the sailing example:

```python
exp.config(num_train_episodes=25000)
```

*Note - you will need to run all changes in a single call of this function. You can reset to default parameters by simply using: 

```python
exp.config()
```

Once an updated set of parameters are defined by either method, you can simply re-call the run function and use this to specify which problems you want to try:

```python 
exp.run('sailing')
```

#### Combined analysis output

By default, results are shown for each agent's training and testing procedure and the summarised for the problem type.

You can run an example visual analysis that elsciRL provides by simply calling the following function:

```python
exp.evaluate()
```


This will return a combined analysis for both training and testing of all problems the were run. 

![variance\_comparison\_TRAINING](<./attachments/variance_comparison_TRAINING.png>)

Understanding these results are explained in more detail in [3 - Output Format](<./3 - Output Format.md>) but for now, the simple rule is more reward is better. 

This is highlighted best in the graphs on the left side where reward is shown on the y-axis. In other words, the red line for the Default adaptor on the Sailing problem returns the highest reward in training these parameters.

#### Running the examples as a complete script

If you wish to test this demo out further, you can create a simple Python script file to run more results. An example of this could look like the following:

```python title:test.py
from elsciRL import DemoExperiment

exp = DemoExperiment()

exp.config(
	num_train_episodes=10000, num_train_repeats=25,
	num_test_episodes=250, number_test_repeats=10,
	Qlearntab_params={
		'alpha':0.05, 'gamma':0.95, 'epsilon':0.4, 'epsilon_step':0.01
	}
)

exp.run()
exp.evaluate()
```

This can be saved (e.g. as *elsciRL_Demo.py*) and ran like any other Python script in your IDE simply using the following in the terminal:

```
python elsciRL_Demo.py
```


## Notes
- You will need to have Python installed, ideally alongside Anaconda for defining the environment.
- You will need to have Git installed if you wish to clone the demo application, otherwise you can manually download an application from its GitHub repository.
- If you are interested in using the GPU instead of CPU to train agents, then you will need to setup [CUDA](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/) on your machine.

---

**Previous:** [FAQs](<../../FAQs.md>)     <div style="text-align: right"> **Next:** [2 - Basic Applications](<./2 - Basic Applications.md>) </div>