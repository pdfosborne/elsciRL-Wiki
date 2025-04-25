---
cite: "bbycroftLLMVis"
title: "LLM Visualization"
url: "https://bbycroft.net/llm"
authors:
publisher: "bbycroft"
site: "bbycroft"
published:
year:
created: 2025-04-06
description: "Walkthrough of nano-gpt, explaining token sorting, embeddings, and next token prediction."
tags:
  - "LLM"
  - "GPT"
  - "Visualization"
  - "nano-gpt"
  - "AI"
type: "WebArticle"
BibTeX (AI Generated): "@misc{bbycroftLLMVis,  title={LLM Visualization},  url={https://bbycroft.net/},  note={Accessed}}"
citations:
---
# Summary

This page provides a walkthrough of the nano-gpt large language model, which has 85,000 parameters. It explains how the model sorts a sequence of letters into alphabetical order, using token indexes and embeddings. The model predicts the next token in the sequence and feeds it back into the model.

----
# Article

Welcome to the walkthrough of the GPT large language model! Here we'll explore the model *nano-gpt*, with a mere 85,000 parameters.

Its goal is a simple one: take a sequence of six letters:

C B A B B C

and sort them in alphabetical order, i.e. to \\"ABBBCC\\".

We call each of these letters a *token*, and the set of the model's different tokens make up its *vocabulary*:

| token | A | B | C |
|---|---|---|---|
| index | 0 | 1 | 2 |

From this table, each token is assigned a number, its *token index*. And now we can enter this sequence of numbers into the model:

2 1 0 1 1 2

In the 3d view, each green cell represents a number being processed, and each blue cell is a weight.

being processed

weights

Each number in the sequence first gets turned into a 48 element vector (a size chosen for this particular model). This is called an *embedding*.

The embedding is then passed through the model, going through a series of layers, called transformers, before reaching the bottom.

So what's the output? A prediction of the next token in the sequence. So at the 6th entry, we get probabilities that the next token is going to be 'A', 'B', or 'C'.

In this case, the model is pretty sure it's going to be 'A'. Now, we can feed this prediction back into the top of the model, and repeat the entire process.
