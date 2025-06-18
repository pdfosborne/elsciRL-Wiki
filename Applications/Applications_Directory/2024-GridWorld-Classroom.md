---
cite: 2024-classroom-simulation
title: GridWorld Classroom Simulation
authors: Philip Osborne
authors_github: pdfosborne
year: 2024
publisher: elsciRL
url: https://github.com/pdfosborne/elsciRL-App-Classroom
stars: 1
type: GridWorld Simulation
tags:
  - AppliedReinforcementLearning
  - Education
  - GridWorld
  - Language
  - EvaluationProtocol
complexity: beginner
---

# GridWorld Classroom Simulation

## Summary
This application simulates a classroom environment as a grid world. The agent navigates the classroom, interacting with students, teachers, and objects, with both numeric and language-based state representations.

## Data Source
The environment is based on a custom classroom grid, with student and teacher features provided in CSV and Python data files.

## elsciRL App Options

### Local Config

| Config Name   | Config Code | Description                                                                 |
|:-------------:|:-----------:|:--------------------------------------------------------------------------:|
| Classroom_A   | classroom_A | Standard classroom layout with students, teachers, and objects.            |

### Adapters

| Adapter Name         | Adapter Code | Description                                                                 | Output type |
|:--------------------:|:------------:|:---------------------------------------------------------------------------:|:-----------:|
| Default Numeric      | default      | Encodes the agent's position and classroom state as a tensor.               | $tensor$    |
| Classroom Language   | language     | Describes the classroom state in natural language using student features.   | $tensor$    |
| LLM Adapter         | llm          | Uses an LLM to generate a language description of the classroom state.      | $tensor$    |

## Citation

```bibtex
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