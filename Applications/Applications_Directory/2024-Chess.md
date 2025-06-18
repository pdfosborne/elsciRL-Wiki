---
cite: 2024-chess-simulation
title: Chess Simulation for RL
authors: Philip Osborne
authors_github: pdfosborne
year: 2024
publisher: elsciRL
url: https://github.com/pdfosborne/elsciRL-App-Chess
stars: 1
type: Game Simulation
tags:
  - AppliedReinforcementLearning
  - Chess
  - BoardGames
  - Language
  - EvaluationProtocol
complexity: intermediate
---

# Chess Simulation

## Summary
This application provides a Chess environment for RL agents, supporting both numeric and language-based state representations. Agents can learn to play chess using various adapters and configurations, with support for LLM-based state descriptions.

## Data Source
The Chess environment and adapters are based on open-source implementations and extended for use with elsciRL.

## elsciRL App Options

### Local Config

| Config Name | Config Code | Description |
|:-----------:|:-----------:|:-----------|
| Default     | default     | Standard chess configuration with all pieces and standard rules. |

### Adapters

| Adapter Name      | Adapter Code | Description                                                                 | Output type |
|:-----------------:|:------------:|:---------------------------------------------------------------------------:|:-----------:|
| Numeric Board     | numeric      | Encodes the board as a tensor of piece indices.                             | $tensor$    |
| Language Active   | language     | Describes the board in natural language, focusing on active pieces.         | $tensor$    |
| LLM Adapter       | llm          | Uses an LLM to generate a language description of the board state.          | $tensor$    |

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