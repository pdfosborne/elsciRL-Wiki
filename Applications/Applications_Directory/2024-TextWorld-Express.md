---
cite: 2024-textworld-express
title: TextWorldExpress
authors: Philip Osborne
authors_github: pdfosborne
year: 2024
publisher: elsciRL
url: https://github.com/pdfosborne/elsciRL-App-TextWorldExpress
stars: 1
type: TextWorld Simulation
tags:
  - AppliedReinforcementLearning
  - TextWorld
  - Language
  - EvaluationProtocol
complexity: intermediate
---

# TextWorldExpress

## Summary
This application provides an interface to the TextWorldExpress environment, allowing RL agents to interact with text-based worlds and tasks. Supports both numeric and language-based adapters.

## Data Source
Based on the [TextWorldExpress](https://github.com/cognitiveailab/TextWorldExpress) environment.

## elsciRL App Options

### Local Config

| Config Name | Config Code | Description                                                                 |
|:-----------:|:-----------:|:--------------------------------------------------------------------------:|
| CoinCollector | coin      | Collect coins in a text-based world.                                       |
| CookingWorld | cooking    | Complete cooking tasks in a text-based world.                              |

### Adapters

| Adapter Name      | Adapter Code | Description                                                                 | Output type |
|:-----------------:|:------------:|:---------------------------------------------------------------------------:|:-----------:|
| Default Numeric   | default      | Encodes the text world state as a tensor of indices.                        | $tensor$    |
| Language          | language     | Describes the text world state in natural language.                         | $tensor$    |
| LLM Adapter       | llm          | Uses an LLM to generate a language description of the text world state.     | $tensor$    |

## Citation

```bibtex
    @article{jansen2022textworldexpress,
        url = {https://arxiv.org/abs/2208.01174},
        author = {Jansen, Peter A. and Côté, Marc-Alexandre},
        title = {TextWorldExpress: Simulating Text Games at One Million Steps Per Second},
        journal = {arXiv},
        year = {2022},
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