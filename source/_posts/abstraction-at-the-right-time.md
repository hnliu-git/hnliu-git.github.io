---
title: Abstraction at the right time
tags: 
- "Software Engineering" 
- "Short Note"
date: 2023-07-13 21:11:07
---

# TL:DR

Two software abstrction principles learned from a recent task are:
- Abstract components that have complicate interaction process.
- Abstract components that have various features but have the same input and output.

## Problem

We have mulitple use cases for retreving and processing data from a data source and we ended up developing a tool for each case. To reuse the same component and avoid reinventing wheels, I worked a task to develop a generic data tool.

## Implementation

### Abstract complicated components

Retrieval and processing data from the source requires three components. Interact with them have complicated steps so you need to learn how to do that. That motivates me to abstract these three components so that the call function is the only thing you need to know for interaction.

### Abstract actions with various possibility

Amonght the use cases, there are demands for filtering and exporting data. However, demands are vary case by case but the action is fixed (i.e, you do nothing special than excluding data or write data to some file formats). Thus, abstract the action as the base class and all demands can be special action inherited from the base. That makes the project flexible and use to maintain.

### Connect abstractions into a pipeline

You can define the recipe for your use case and send it to the pipeline. The pipeline connects all abstractions and run based on the recipe. 

