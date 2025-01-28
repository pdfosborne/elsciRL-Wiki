---
cite: 2023-sailing-simulation
title: Sailing Simulation for a River with Fixed Wind Direction
authors: Philip Osborne
authors_github: pdfosborne
year: 2024
publisher: elsciRL
url: https://github.com/pdfosborne/elsciRL-App-Sailing
stars: 1
type: Robotics Simulation
tags:
  - AppliedReinforcementLearning
  - EvaluationProtocol
  - RealWorld
  - Sailing
  - Robotics
complexity: beginner
---

# Sailing Simulation

## Summary
The application allows the agent to control a sailboat by turning left or right to navigate obstacles. ^d3afa9

Distance moved after every action is calculated based on the direction the boat is facing against the wind. 

## Data Source
The data is adapted from a Sailing Simulation by https://github.com/PPierzc/ai-learns-to-sail. ^a7fb61

The sailboat distance is calculated based on the direction against the wind. The reward for reaching the objective is +1 and conversely -1 for failing.   

# elsciRL App  Options

## Local Config

The following table summarises the adapters available in the current application.


| Config Name | Config Code |                                                                                             Description                                                                                              |
|:------------:|:------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|  Easy River  |     easy     | The simplest setting; fixed wind direction and a 25m distance to the goal line without hitting the walls. Observation precise to 2 decimal places, reward = 0.5 for sub-goal, -0.1 if the action limit of 100 is reached. |
|              |              |                                                                                                                                                                                                      |


## Adapters

The following table summarises the adapters available in the current application.


|  Adapter Name   | Adapter Code |                                                                                            Description                                                                                            | Output type |
|:---------------:|:------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------:|
| Default Numeric |   default    |              States "x_angle" that denotes the horizontal position and angle against the wind are indexed based on the list of all possible states and then transformed to a tensor.              |  $tensor$   |
| Simple Language |   language   | States "x_angle" are transformed to a description based on: 1) horizontal position, 2) side of river (beach or harbor side), 3) angle against the wind and 4) direction of previous action taken. |  $tensor$   |


# Citation

```bibtex
  title        = {Improving Real-World Reinforcement Learning by Self Completing Human Instructions on Rule Defined Language},  
  author       = {Philip Osborne},  
  year         = 2024,  
  month        = {August},  
  address      = {Manchester, UK},  
  note         = {Available at \url{https://research.manchester.ac.uk/en/studentTheses/improving-real-world-reinforcement-learning-by-self-completing-hu}},  
  school       = {Department of Computer Science},  
  type         = {PhD thesis}
```
