---
cite: a035f089-d10c-4fde-b75c-0b50c351bf77
title: |
  Lyft’s Reinforcement Learning Platform | by Jonas Timmermann | Lyft Engineering
year: 
date_published: 12-03-2024
tags:
  - RL-Applications
  - RL-Software
  - obsidian
  - RW-RL
authors: |
  Jonas Timmermann
citations: 
publisher: 
date_saved: 09-09-2024
url: https://eng.lyft.com/lyfts-reinforcement-learning-platform-670f77ff46ec
DOI: 
type: WebArticle
id: a035f089-d10c-4fde-b75c-0b50c351bf77
---

# Lyft’s Reinforcement Learning Platform | by Jonas Timmermann | Lyft Engineering
*Highlighted in Omnivore* [Read Original](https://eng.lyft.com/lyfts-reinforcement-learning-platform-670f77ff46ec)

## Highlights

> ## Summary
> 
> At Lyft we have built a platform for developing, training and serving Reinforcement Learning models for typical internet industry applications with a focus on Contextual Bandits. Those models have been critical for decision making problems that other techniques such as supervised learning or optimization models struggled with. In this article we describe how we extended our existing machine learning ecosystem to support Reinforcement Learning models, develop models using Off-Policy Evaluation, and the lessons learned along the way.  ^531a0b9f

> Instead, we only need to define a reward metric that the model optimizes for. The metric can be fairly high level, for example conversion or revenue.
> 
> This highlights another strength of RL models — they optimize for the whole decision making process towards a target metric in potentially changing environments. Supervised models, on the other hand, only make predictions which need to be further processed for making a decision  ^1935bd61

> Another benefit is RL’s online learning nature that allows models to incrementally update rather than having to train on the whole history.  ^acdd0610

> However, there are also downsides to the RL-based approach.
> 
> * Most Contextual Bandit libraries use fairly simplistic linear models that lack the expressiveness of tree or neural network models.
> * Solving a problem without fully labeled ground truth data is inherently more difficult. More data is necessary to learn the problem and it is more challenging to gauge a model’s performance. Off-Policy Evaluation (OPE) that we discuss in a later section is an approach to address this but it comes with its own challenges.
> * Finally, there are few mature libraries and little guidance on best practices available, which requires a lot of trial and error exploration.  ^de68d807

> ## Library
> 
> We leverage open-source libraries like Vowpal Wabbit and RLlib for modeling. In addition, we created our own internal RL library with model definitions, data processing, and bandit algorithm implementations to integrate with our infrastructure and make it easy for model creators to get started.  ^8e4be5b1

> In order to integrate the VW Contextual Bandits and other RL models into our ML ecosystem, we created a library with the following components.
> 
> ![Model class hierarchy showing how the RL base model extends the general model class and different RL implementations like Vowpal Wabbit extend the base RL model](https://proxy-prod.omnivore-image-cache.app/700x564,ssHn-36JIn7FyFIEV75aEOGN7q4XILrV-fz7IS-XwhRM/https://miro.medium.com/v2/resize:fit:700/0*bZy_-18LyqSF5lGX)
> 
> Model Class Inheritance Tree  ^ff188f17

> [Coba](https://github.com/VowpalWabbit/coba) is an open-source Contextual Bandit benchmark framework that we contribute to and which has been instrumental for analyzing the performance of our models. While VW natively supports learning from logs, its evaluation and visualization capabilities are fairly limited.  ^4ae28121

> ## Lessons Learned
> 
> Supporting RL models on a machine learning platform that’s extensible is actually fairly straightforward but getting the models to perform well is hard.
> 
> * The evaluation of RL models is inherently more difficult due to the lack of labeled ground truth data but the tooling is also nowhere as mature as that for supervised learning. Therefore, it requires a lot of trial and error to build an intuition of how things work. A great way to do this is by working with data for which the underlying distribution is known. This can either be a classification dataset or a simulation where the reward distribution is controllable. Both are supported in Coba.
> * When moving to a real-world application, it’s important to normalize the reward as well as to evaluate different hyperparameters such as learning rate and interaction terms.
> * For evaluating a candidate model, relying solely on the total accumulated reward is risky as the measure is sensitive to estimator errors. Other metrics like context-specific convergence provide additional insights. Overlaying the candidate model’s arm selection frequencies with the average arm rewards in the log data is also helpful to get a sense of how well the model adapts to changes in the environment.
> * Running multiple evaluation passes over slightly shuffled versions of the data (just jiggling the order of the rows a bit to avoid scrambling longer term patterns) is helpful to gain confidence intervals.  ^9f5da974

