---
title: "Teaching Students to Read One Protein Deeply"
date: 2026-08-22
tags: ["Structural Bioinformatics", "Teaching", "Python"]
series: ["Teaching"]
description: "The idea behind the structural bioinformatics course materials I write for the Bio Data Science program at FHWN: fewer tools, one protein, real depth."
---

I'm part of the teaching team for the Bio Data Science program's structural bioinformatics course at FHWN, split across the Wiener Neustadt and Tulln campuses. The materials I write for it live at [structural-bioinformatics-exercises](https://github.com/yerkoescalona/structural-bioinformatics-exercises), and this post isn't really about the repository — it's about the idea that shaped it.

## The problem with tool-by-tool teaching

The obvious way to teach structural bioinformatics is a tour: a week on the PDB, a week on modeling, a week on dynamics, a week on docking, each with its own toy dataset chosen to make that week's tool look good. Students leave knowing how to run four tools on four unrelated inputs. What they don't leave with is the thing that actually matters in research: the ability to hold one protein in their head from every angle at once, and know which angle answers which question.

That gap is what I built the course materials to close. Every notebook isn't a tutorial on a tool in isolation — it's a lens for looking at a protein, and all the lenses are meant to be pointed at the same subject over the course of the semester.

## One protein, several lenses

The structure of the materials follows how a researcher actually approaches an unfamiliar protein, not how a software package happens to be organized. First you ask what's already known about it — pulling it from the database, reading its metadata, understanding what its resolution and quality metrics are actually telling you. Then you ask what its structure means — evaluating a model rather than just admiring it. Then you ask how it behaves — because a static structure is a single frame of something that moves, and the physics of that motion is where a lot of biological function actually lives. And finally you ask how it interacts — what fits into it, and why.

None of those questions is more "advanced" than the others; they're just different instruments pointed at the same thing. The point of sequencing them is that each one sharpens what the next one means. Once you've had to justify why a structure is trustworthy, dynamics stops being an abstract simulation and starts being a claim about a specific, particular molecule you already have opinions about.

## Why the whole is the point

The materials are deliberately built so a student can carry a single protein of their own choosing across all of it — the same PDB entry gets queried, modeled, simulated, and docked into, by the same person, across the same semester. That continuity is the actual pedagogical bet: a student who has spent months with one protein, looked at it from every angle available, and had to defend judgments about it at each stage, is no longer doing an exercise. They're doing what a researcher does with a new structure on their desk — building a case, layer by layer, for what it is and how it works.

That's the outcome I care about more than any individual notebook: not that a student can run a docking script, but that by the end they can stand behind a protein the way a researcher would, because they've earned that understanding one lens at a time. The materials are shared under CC BY-NC-SA 4.0, so other instructors building the same kind of depth-over-breadth course are welcome to it.
