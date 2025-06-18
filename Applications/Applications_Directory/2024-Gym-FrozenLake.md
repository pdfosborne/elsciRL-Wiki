---
cite: 2024-gym-frozenlake
title: Gym FrozenLake
authors: Philip Osborne
authors_github: pdfosborne
year: 2024
publisher: elsciRL
url: https://github.com/pdfosborne/elsciRL-App-GymFrozenLake
stars: 1
type: ToyText Simulation
tags:
  - AppliedReinforcementLearning
  - Gymnasium
  - FrozenLake
  - GridWorld
  - EvaluationProtocol
complexity: beginner
---

# Gym: FrozenLake

## Summary
This application provides an interface to the classic FrozenLake environment from Gymnasium. The agent must navigate a slippery grid to reach the goal, avoiding holes.

## Data Source
Based on the [FrozenLake](https://gymnasium.farama.org/environments/toy_text/frozen_lake/) environment from Gymnasium.

## elsciRL App Options

### Local Config

| Config Name | Config Code | Description                                                                 |
|:-----------:|:-----------:|:--------------------------------------------------------------------------:|
| 4x4         | 4x4         | Standard 4x4 FrozenLake grid.                                              |

### Adapters

| Adapter Name      | Adapter Code | Description                                                                 | Output type |
|:-----------------:|:------------:|:---------------------------------------------------------------------------:|:-----------:|
| Numeric           | numeric      | Encodes the grid state as a tensor of indices.                              | $tensor$    |
| Language          | language     | Describes the grid state in natural language.                               | $tensor$    |
| LLM Adapter       | llm          | Uses an LLM to generate a language description of the grid state.           | $tensor$    |

## Citation

```bibtex
    @article{towers2024gymnasium,
        title={Gymnasium: A Standard Interface for Reinforcement Learning Environments},
        author={Towers, Mark and Kwiatkowski, Ariel and Terry, Jordan and Balis, John U and De Cola, Gianluca and Deleu, Tristan and Goul{\~a}o, Manuel and Kallinteris, Andreas and Krimmel, Markus and KG, Arjun and others},
        journal={arXiv preprint arXiv:2407.17032},
        year={2024}
    }

    @phdthesis{Osborne2024,
        title        = {Improving Real-World Reinforcement Learning by Self Completing Human Instructions on Rule Defined Language},  
        author       = {Philip Osborne},  
        year         = 2024,  
        month        = {August},  
        address      = {Manchester, UK},  
        note         = {Available at \url{https://research.manchester.ac.uk/en/studentTheses/improving-real-world-reinforcement-learning-by-self-completing-hu}},  
        school       = {The University of Manchester},  
        type         = {PhD thesis}
    }
```