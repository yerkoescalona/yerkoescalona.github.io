---
title: "newen-md: A Rust Molecular Dynamics Engine for Teaching"
date: 2026-08-16
tags: ["Molecular Dynamics", "Rust", "Structural Bioinformatics", "Computing"]
series: ["Science"]
description: "Building a Rust-based MD simulator with Python bindings."
---

In a structural bioinformatics course, students look at proteins in PyMOL and dock ligands with AutoDock Vina, but neither tool shows them the forces involved. PyMOL doesn't display forces, and Vina's scoring function is hard to inspect without reading its source code. The idea that molecular dynamics is Newton's second law applied many times in a row is easy to state in a lecture and hard to see in practice.

`newen-md`, or newen for short, is a molecular dynamics simulator written in Rust, with Python bindings, that I'm writing mainly for teaching. It is an independent reimplementation based on the GROMOS C++ programs gromosXX and gromos++, not an official GROMOS release, and it is not ready for production research.

## The name

*Newen* means force in Mapudungun: strength, energy, the power that sets things in motion. In the Mapuche worldview it isn't only something people have. The land, the water, the wind and the mountains each carry their own newen.

Computing forces is most of what an MD engine does, so the name fits.

## Goals

The first goal is teaching. I'm designing a structural bioinformatics course that covers protein modeling, molecular dynamics and docking, and `newen` is meant to be used throughout it, so students can watch forces act on a small toy system before they work with a real protein.

The second goal is performance. In the long run I want it to match the speed of the C++ GROMOS implementation, because a slow teaching code gives students the wrong idea of what MD costs.

I chose Rust because it gives memory safety without a garbage collector, compiles to fast native code, and has good support for Python bindings, so the same core can run as a standalone binary or be imported in a notebook.

## Architecture

The workspace is split into modules that follow the usual parts of an MD engine:

- core: topology, configuration and math
- forces: bonded and nonbonded terms, electrostatics and QM/MM
- integrators: leap-frog dynamics, constraints, thermostats and barostats
- I/O: the various file formats
- analysis and tooling
- a binding layer that builds the Python package

I've kept the number of modules small. At this size, splitting the code into many more pieces adds overhead without making builds noticeably faster. The design follows GROMOS closely, but QM/MM and neural-network potentials go through the same forces interface as the classical terms instead of having their own code paths.

The Python interface follows the style of libraries like OpenMM. You load a topology, a starting configuration and a set of run parameters, build a simulation object from them, and step it forward. Forces and positions come back as plain arrays you can plot directly, and the call that advances the simulation can also record an energy trajectory, in the same layout as GROMOS energy files.

## Checking the code with Lean

Comparing newen against gromosXX shows that it reproduces gromosXX, not that either follows the equations. I've recently started using the [Lean](https://lean-lang.org) theorem prover, together with [Aeneas](https://github.com/AeneasVerif/aeneas), to check parts of the Rust code against a written specification. So far it covers a single function.

The code is on GitHub: [yerkoescalona/newen-md](https://github.com/yerkoescalona/newen-md).

[![The newen-md repository on GitHub](/images/newen-md-repo.webp)](https://github.com/yerkoescalona/newen-md)
