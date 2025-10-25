---
title: "Current Technical Focus Areas"
date: 2025-10-25
draft: false
series: "Science"
tags: ["Data Science", "Computing"]
---

## DataFrame Operations: A Framework-Agnostic Library

Dataframe operations form the foundation of modern data science workflows, yet researchers often face vendor lock-in when choosing between different dataframe frameworks. My work addresses this by developing a unified operations library that abstracts away framework-specific implementations. The challenge lies in handling the fundamental differences between these systems—some pandas-like dataframes use row-by-row operations, others employ lazy evaluation with native expressions, some require distributed execution patterns, while others focus on parallelization.

I've implemented operations like merge, reduce, replace, forward-fill, and mathematical transformations that work identically across all frameworks. Extensive benchmarking infrastructure—with synthetic datasets at small, medium, and large scales—ensures performance optimization while maintaining consistent behavior.

![DataFrames](/images/dataframes.png)
<!--more-->

## Bioprocess Modeling and Simulation

Bioprocess engineering requires mathematical modeling of complex unit operations. My work focuses on developing simulation engines ranging from reactors, chromatography and filtration. These models use iterative step-by-step calculations and mass balance equations to predict system behavior for bioprocess optimization.


![Process Engine](/images/process_engine.png)
