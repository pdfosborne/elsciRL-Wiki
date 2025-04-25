---
cite: OpenAI-PromptGuide2025
title: GPT-4.1 Prompting Guide | OpenAI Cookbook
url: https://cookbook.openai.com/examples/gpt4-1_prompting_guide
authors: OpenAI
publisher: OpenAI
site: OpenAI
published: 
year: 2025
created: 2025-04-16
description: 
tags:
  - LLM
  - Prompting
  - Guide
  - Tutorial
type: Tutorial
BibTeX (AI Generated): 
citations:
---
# Summary

A prompting guide for GPT-4.1, highlighting best practices for agentic workflows, long context usage, chain of thought prompting, and instruction following. Includes examples and tips for maximizing model performance.

----
# Article

Full content cleaned up for better Markdown reading:

# GPT-4.1 Prompting Guide

The GPT-4.1 family of models represents a significant step forward from GPT-4o in capabilities across coding, instruction following, and long context. In this prompting guide, we collate a series of important prompting tips derived from extensive internal testing to help developers fully leverage the improved abilities of this new model family.

Many typical best practices still apply to GPT-4.1, such as providing context examples, making instructions as specific and clear as possible, and inducing planning via prompting to maximize model intelligence. However, we expect that getting the most out of this model will require some prompt migration. GPT-4.1 is trained to follow instructions more closely and more literally than its predecessors, which tended to more liberally infer intent from user and system prompts. This also means, however, that GPT-4.1 is highly steerable and responsive to well-specified prompts - if model behavior is different from what you expect, a single sentence firmly and unequivocally clarifying your desired behavior is almost always sufficient to steer the model on course.

Please read on for prompt examples you can use as a reference, and remember that while this guidance is widely applicable, no advice is one-size-fits-all. AI engineering is inherently an empirical discipline, and large language models inherently nondeterministic; in addition to following this guide, we advise building informative evals and iterating often to ensure your prompt engineering changes are yielding benefits for your use case.

# 1. Agentic Workflows

GPT-4.1 is a great place to build agentic workflows. In model training we emphasized providing a diverse range of agentic problem-solving trajectories, and our agentic harness for the model achieves state-of-the-art performance for non-reasoning models on SWE-bench Verified, solving 55% of problems.

## System Prompt Reminders

In order to fully utilize the agentic capabilities of GPT-4.1, we recommend including three key types of reminders in all agent prompts. The following prompts are optimized specifically for the agentic coding workflow, but can be easily modified for general agentic use cases.

1. Persistence: this ensures the model understands it is entering a multi-message turn, and prevents it from prematurely yielding control back to the user. Our example is the following:

   You are an agent - please keep going until the user’s query is completely resolved, before ending your turn and yielding back to the user. Only terminate your turn when you are sure that the problem is solved.

2. Tool-calling: this encourages the model to make full use of its tools, and reduces its likelihood of hallucinating or guessing an answer. Our example is the following:

   If you are not sure about file content or codebase structure pertaining to the user’s request, use your tools to read files and gather the relevant information: do NOT guess or make up an answer.

3. Planning [optional]: if desired, this ensures the model explicitly plans and reflects upon each tool call in text, instead of completing the task by chaining together a series of only tool calls. Our example is the following:

   You MUST plan extensively before each function call, and reflect extensively on the outcomes of the previous function calls. DO NOT do this entire process by making function calls only, as this can impair your ability to solve the problem and think insightfully.

GPT-4.1 is trained to respond very closely to both user instructions and system prompts in the agentic setting. The model adhered closely to these three simple instructions and increased our internal SWE-bench Verified score by close to 20% - so we highly encourage starting any agent prompt with clear reminders covering the three categories listed above. As a whole, we find that these three instructions transform the model from a chatbot-like state into a much more “eager” agent, driving the interaction forward autonomously and independently.

## Tool Calls

Compared to previous models, GPT-4.1 has undergone more training on effectively utilizing tools passed as arguments in an OpenAI API request. We encourage developers to exclusively use the tools field to pass tools, rather than manually injecting tool descriptions into your prompt and writing a separate parser for tool calls, as some have reported doing in the past. This is the best way to minimize errors and ensure the model remains in distribution during tool-calling trajectories - in our own experiments, we observed a 2% increase in SWE-bench Verified pass rate when using API-parsed tool descriptions versus manually injecting the schemas into the system prompt.

Developers should name tools clearly to indicate their purpose and add a clear, detailed description in the \\"description\\" field of the tool. Similarly, for each tool param, lean on good naming and descriptions to ensure appropriate usage. If your tool is particularly complicated and you'd like to provide examples of tool usage, we recommend that you create an # Examples section in your system prompt and place the examples there, rather than adding them into the \\"description' field, which should remain thorough but relatively concise. Providing examples can be helpful to indicate when to use tools, whether to include user text alongside tool calls, and what parameters are appropriate for different inputs. Remember that you can use “Generate Anything” in the Prompt Playground to get a good starting point for your new tool definitions.

## Prompting-Induced Planning & Chain-of-Thought

As mentioned already, developers can optionally prompt agents built with GPT-4.1 to plan and reflect between tool calls, instead of silently calling tools in an unbroken sequence. GPT-4.1 is not a reasoning model - meaning that it does not produce an internal chain of thought before answering - but in the prompt, a developer can induce the model to produce an explicit, step-by-step plan by using any variant of the Planning prompt component shown above. This can be thought of as the model “thinking out loud.” In our experimentation with the SWE-bench Verified agentic task, inducing explicit planning increased the pass rate by 4%.

## Sample Prompt: SWE-bench Verified

Below, we share the agentic prompt that we used to achieve our highest score on SWE-bench Verified, which features detailed instructions about workflow and problem-solving strategy. This general pattern can be used for any agentic task.

```python
from openai import OpenAI
import os

client = OpenAI(
    api_key=os.environ.get(
        \\"OPENAI_API_KEY\
