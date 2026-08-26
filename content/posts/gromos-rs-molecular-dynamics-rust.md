---
title: "gromos-rs: A Rust Molecular Dynamics Engine, Built to Teach"
date: 2026-08-16
tags: ["Molecular Dynamics", "Rust", "Structural Bioinformatics", "Computing"]
series: "Science"
description: "Building a Rust-based MD simulator with Python bindings."
---

Every structural biology course eventually hits the same wall: students can look at a folded protein in PyMOL, they can dock a ligand with AutoDock Vina, but they never actually see the physics doing the work. PyMOL doesn't visualize forces. Vina's scoring function is a black box unless you go digging through source code most students will never open. The intuition that molecular dynamics is just Newton's second law, applied a few million times in a row, gets lost somewhere between the lecture slides and the exercise sheet.

`gromos-rs` is my attempt to fix that gap — a molecular dynamics simulator written in Rust, with Python bindings, designed from day one to be a teaching tool first and a research-grade engine second.

## Two Goals, One Codebase

The project has a dual mandate. First, pedagogy: it should serve as the connective thread through a structural bioinformatics course I'm designing, covering protein modeling, molecular dynamics, and docking, where students can watch forces act on a toy system before they ever touch a real protein. Second, performance: in the long run it should match or outperform the original C++ GROMOS/GromosXX implementation, because a teaching tool that's slow teaches the wrong lesson about what MD actually costs.

Rust is the obvious language for this — memory safety without a garbage collector, genuine speed, and a Python bridge that lets the same core engine power both a fast native binary and a friendly notebook import.

## Architecture

The workspace is split along the natural boundaries of an MD engine: a core module for topology, configuration and math; a forces module for bonded and nonbonded terms, electrostatics, and QM/MM; an integrators module for leap-frog dynamics, constraints, thermostats and barostats; an I/O module for the various file formats; analysis and tooling modules; and a binding layer that turns all of it into a Python package.

The design stays deliberately conservative. Splitting a codebase into too many small pieces at this scale mostly adds overhead without real build-time wins, so `gromos-rs` stays close to a layered structure rather than fragmenting further. It's heavily inspired by GROMOS itself, but rebuilt with a newer architecture whose modules are ready for extension from day one — QM/MM and neural-network potentials plug into the same forces interface rather than needing their own code paths.

That composability carries over into Python, which is where the project takes its other cue: the same kind of ergonomic, buildable-block interface that makes libraries like OpenMM pleasant to script against. You load a topology, a starting configuration and a set of run parameters, build a simulation object from them, and step it forward. The forces and positions come back as plain arrays you can plot directly, and the same call that advances the simulation can sample an energy trajectory as it goes, laid out the same way GROMOS's own energy files are.

Code is on GitHub: [yerkoescalona/gromos-rs](https://github.com/yerkoescalona/gromos-rs).
