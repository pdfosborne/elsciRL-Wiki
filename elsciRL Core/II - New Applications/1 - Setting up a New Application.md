Table of Contents

- [Setting up a New Application](<#setting-up-a-new-application>)
	- [Option 1: Fork the Application Template](<#option-1-fork-the-application-template>)
	- [Option 2: Clone the Application Template Directly](<#option-2-clone-the-application-template-directly>)
	- [Option 3: Download the Application Template Manually](<#option-3-download-the-application-template-manually>)
- [Understanding Data Engines](<#understanding-data-engines>)
	- [1. Initialization function](<#1-initialization-function>)
	- [2. Reset function](<#2-reset-function>)
	- [3. Step function](<#3-step-function>)
	- [4. Legal move generator](<#4-legal-move-generator>)
- [Creating a New Engine](<#creating-a-new-engine>)

---
# Setting up a New Application

A new application is defined when an environment has not been setup before. The easiest method for achieving this is to fork the elsciRL application template. 

In this demonstration we create a new application from the public GitHub repository and you should adapt this depending on your situation. Using a fork means that any future feature additions to the template can be pulled into your application.

If the application is complete then it can be published - for more information see [4 - Publishing an Application](<./4 - Publishing an Application.md>).

## Option 1: Fork the Application Template

To start this process, simply create a fork of the template repository: https://github.com/pdfosborne/elsciRL-TEMPLATE.

This will create a new repository in your personal account which you can then clone to your local computer to edit.

The advantage of using a fork of the template is that updates to the template can be incorporated into your application.

![elsciRL Template](<./attachments/elsciRL Template.png>)

![elsciRL Template Fork](<./attachments/elsciRL Template Fork.png>)

## Option 2: Clone the Application Template Directly

Alternatively, you can clone the template repository https://github.com/pdfosborne/elsciRL-TEMPLATE.

You can then manually configure the link to the cloned template and a GitHub repository on your profile (see [4 - Publishing an Application](<./4 - Publishing an Application.md>) for more detail)

```bash
git clone https://github.com/pdfosborne/elsciRL-TEMPLATE.git elsciRL-YourApp
```

## Option 3: Download the Application Template Manually

Lastly, you can simply download the complete template ZIP by the *Code > Download ZIP* link on the template repository https://github.com/pdfosborne/elsciRL-TEMPLATE.

---

# Understanding Data Engines

The interaction process is defined within  *environment/engine.py .* This captures the Markov Decision Process model required to enable the Reinforcement Learning agent make actions in the environment. It is defined the match the standard [**OpenAI Gym format**](https://gymnasium.farama.org/api/env/).

### 1. Initialization function

The  *__init__()*  function is called when the environment is first called. In short, any data loading or per-requisite steps that will not change are to be defined here. 

Variables that track the agent’s performance across episodes can be initialized here. 

### 2. Reset function

The  *reset()*  function is used to restart the agent’s position for each episode and is commonly fixed. 

The output should be the initial observation used to begin the episode. 

Variables that need to be reset between episodes can be initialized here. For example, a stock trading problem would set the initial balance.

### 3. Step function

The   step*(state, action)*  function is the defining interaction method that is used by the agents to obtain the next state. 

The output should be a tuple with the outcome observation and reward given the current state and action. Also, a boolean flag is used to specify whether reaching this outcome should terminate the episode.

### 4. Legal move generator

The   legal_move_generator*(state)*  function returns the list of possible moves given the current position.

In some problems this may be fixed and consistent for all states (e.g. *[up, down, left, right]*), in others a lookup may be required given the current position.

![elsciRL Template Engine](<./attachments/elsciRL Template Engine.png>)

---

# Creating a New Engine

Specifying how the agent interacts with the environment is the most important and challenging components of Reinforcement Learning. In some cases the Markov Decision Process model may already be well defined elsewhere and so we may adapt it from it. 

Otherwise, defining the probabilistic outcomes of actions given states can be achieved with sampled statistics, simulation or live experience.

For now, we will be using a simple pre-defined example from OpenAI’s Gymnasium - specifically the Frozen Lake problem.

[Frozen Lake - Gym Documentation](https://www.gymlibrary.dev/environments/toy_text/frozen_lake/)

[OpenAI’s Gymnasium](https://github.com/Farama-Foundation/Gymnasium) can be installed using the following:

```bash
pip install gymnsium
```

In this example, all we need to do is call the FrozenLake generation from Gym and specify the list of possible actions.

![Creating a New Engine](<./attachments/Creating a New Engine.png>)

**Next we need to setup the encoder methodology through adapters outlined in the following page: [Adapters](<./2 - Adapters.md>).**
