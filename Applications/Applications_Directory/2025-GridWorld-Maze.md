---
cite: 2025-maze-simulation
title: GridWorld Maze Simulation
authors: Philip Osborne
authors_github: pdfosborne
year: 2025
publisher: elsciRL
url: https://github.com/pdfosborne/elsciRL-App-Maze
stars: 1
type: GridWorld Simulation
tags:
  - AppliedReinforcementLearning
  - Maze
  - GridWorld
  - Language
  - EvaluationProtocol
complexity: intermediate
---

# Maze Simulation

## Summary
This application recreates the maze problems from "[Natural Language Reinforcement Learning](https://arxiv.org/abs/2402.07157)" (2023), adapted for the elsciRL framework. Agents must navigate mazes using both numeric and language-based state representations.

## Data Source
Based on code from [waterhorse1/Natural-language-RL](https://github.com/waterhorse1/Natural-language-RL), adapted for elsciRL.

## elsciRL App Options

### Local Config

| Config Name | Config Code | Description                                                                 |
|:-----------:|:-----------:|:--------------------------------------------------------------------------:|
| umaze       | umaze      | U-shaped maze configuration.                                                |
| double_t    | double_t   | Double T-shaped maze configuration.                                         |
| medium      | medium     | Medium-sized maze.                                                          |
| large       | large      | Large maze configuration.                                                   |
| random      | random     | Randomly generated maze.                                                    |

### Adapters

| Adapter Name      | Adapter Code | Description                                                                 | Output type |
|:-----------------:|:------------:|:---------------------------------------------------------------------------:|:-----------:|
| Language          | language     | Describes the maze state in natural language.                               | $tensor$    |
| LLM Adapter       | llm          | Uses an LLM to generate a language description of the maze state.           | $tensor$    |

## Citation

```bibtex
  @misc{nlrl,
    title={Natural Language Reinforcement Learning},
    author={Xidong Feng and Ziyu Wan and Haotian Fu and Bo Liu and Mengyue Yang and Girish A. Koushik and Zhiyuan Hu and Ying Wen and Jun Wang},
    year={2024},
    eprint={2411.14251},
    archivePrefix={arXiv},
    primaryClass={cs.LG},
    url={https://arxiv.org/abs/2411.14251},
    }
```