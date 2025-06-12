---
cite: Timmermann2024Lyft
title: Lyft’s Reinforcement Learning Platform
url: https://eng.lyft.com/lyfts-reinforcement-learning-platform-670f77ff46ec
authors: Jonas Timmermann
publisher: Lyft Engineering
site: lyft
published: 2024-03-12
year: 2024
created: 2025-02-07
description: Lyft's RL platform tackles decision-making using Contextual Bandits and Off-Policy Evaluation.
tags:
  - ReinforcementLearning
  - ContextualBandit
  - Mlops
  - MachineLearning
  - MlPlatform
type: WebArticle
BibTeX (AI Generated): "@misc{Timmermann2024Lyft, author = {Jonas Timmermann}, title = {Lyft's Reinforcement Learning Platform}, journal = {Lyft Engineering}, year = {2024}, url = {https://eng.lyft.com/lyfts-reinforcement-learning-platform-670f77ff46ec}}"
citations: "0"
---
# Lyft’s Reinforcement Learning Platform

## Summary

Lyft built a platform for Reinforcement Learning models, focusing on Contextual Bandits, for decision-making problems. They extended their ML ecosystem, used Off-Policy Evaluation, and shared lessons learned.

----
# Article

# Lyft’s Reinforcement Learning Platform

By Jonas Timmermann

## Summary

Lyft has built a platform for developing, training, and serving Reinforcement Learning models, focusing on Contextual Bandits. These models address decision-making problems where supervised learning or optimization models struggle. The article describes how Lyft extended its existing machine learning ecosystem to support Reinforcement Learning models, develop models using Off-Policy Evaluation, and the lessons learned along the way.

## Introduction

Reinforcement Learning (RL) has shown promise in research on challenging problems. This article shares how to apply RL to typical business applications such as dynamic pricing or recommendations.

### Reinforcement Learning

RL tests out different actions and observes feedback from the environment. It chooses the better performing actions for a state while exploring to detect changes over time.

Applied RL can be divided into three stages:

*   **Multi-Arm Bandits** (MAB): Identifies the variant that performs best globally without considering features.
*   **Contextual Bandits** (CB): Takes context features into consideration for finding the best performing variant.
*   **Full-RL:** Reasons over multiple steps of sequential decision making.

Lyft uses MABs for A/B tests and simpler applications. The main focus is on Contextual Bandits.

### Motivation

Reinforcement Learning is powerful for decision-making problems. Compared to supervised learning, RL doesn't require a fully labeled dataset. Instead, it optimizes for a reward metric. The reward function supports business priorities, including growth, profits, competitive pricing, and driver pay.

RL's online learning nature allows models to incrementally update. This keeps models fresh and allows for tracking non-stationary distributions.

Promising RL use-cases are applications where no ground truth is available, where efficient exploration is part of the task, or tricky problems that can't be captured with a mathematical optimization model.

However, there are also downsides:

*   Most Contextual Bandit libraries use simplistic linear models.
*   Solving a problem without fully labeled ground truth data is more difficult.
*   Few mature libraries and little guidance on best practices are available.

## Demo

To validate the Contextual Bandit model and infrastructure, a simple recommendation model was created, inspired by a Vowpal Wabbit use-case. It recommends different news article categories to a user based on the time of day and changing preferences over time.

### Model

The model's action space covers four news article categories: *[\\"politics\
