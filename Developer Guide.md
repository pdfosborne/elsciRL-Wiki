# New Developers

<div align="center">

<a href="https://github.com/pdfosborne/elsciRL">![elsciRL GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)</a> <a href="https://github.com/pdfosborne/elsciRL-Wiki">![Wiki GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)</a> <a href="https://discord.gg/GgaqcrYCxt">![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)</a>

</div>

**Quicklinks:** [Homepage](https://elsci.org) | [About Us](https://elsci.org/About+us) | [FAQs](https://elsci.org/FAQs) | [Contributing Guide](https://elsci.org/Become+a+Contributor) | [App Interface Guide](https://elsci.org/App+Interface+Guide) | [Using the Wiki](https://elsci.org/Docs+&+Wiki+Guide)


## Quick-start

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

<div align="center">
	<iframe width="700" height="400"  
		src="https://www.youtube.com/embed/JbPtl7Sk49Y">  
	</iframe>
</div>

## First time Development Setup

If you wish to apply the elsciRL library to your own problems or design your own algorithms you will need to understand how to train agents without the App interface. 

To edit the core elsciRL library you will need to install it as an editable package, we suggest doing this in a [Python environment](https://github.com/pdfosborne/elsciRL#using-a-python-environment)).
```bash
git clone https://github.com/pdfosborne/elsciRL.git
cd elsciRL
pip install -e .
```

## Test the installation 

### Test using the built-in example experiment

You can check the install has worked by running a quick CLI demo from a selection of applications:

```python
from elsciRL import Demo
test = Demo()
test.run()
```

This will run a tabular Q learning agent on your selected problem and save results to:

> '*CURRENT_DIRECTORY*/elsciRL-EXAMPLE-output/...'

A help function is included in demo: *test.help()*

This will complete a training and testing phase for a small set of example problems using a tabular Q-learning agent.

Once complete, files will be saved in a timestamped directory for each problem that was run.

#### Combined analysis output

By default, results are shown for each agent's training and testing procedure and the summarised for the problem type.

You can run an example visual analysis that elsciRL provides by simply calling the following function:

```python
exp.evaluate()
```


This will return a combined analysis for both training and testing of all problems the were run. 

![variance\_comparison\_TRAINING](<./Documentation/I - Introduction/_images/variance_comparison_TRAINING.png>)

Understanding these results are explained in more detail in [3 - Output Format](<./Documentation/I - Introduction/3 - Output Format.md>) but for now, the simple rule is more reward is better. 

This is highlighted best in the graphs on the left side where reward is shown on the y-axis. In other words, the red line for the Default adaptor on the Sailing problem returns the highest reward in training these parameters.

#### Running the examples as a complete script

If you wish to test this demo out further, you can create a simple Python script file to run more results. An example of this could look like the following:

```python
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

<div id="sticky-button">
  <a href="https://discord.gg/GgaqcrYCxt"><img src="https://raw.githubusercontent.com/pdfosborne/elsciRL-Wiki/refs/heads/main/Resources/images/discord_icon.png" width="50"></a>
</div>