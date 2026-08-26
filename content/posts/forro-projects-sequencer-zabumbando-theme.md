---
title: "Three Ways Into Forró: Sequencer, Practice Log, and a VS Code Theme"
date: 2026-08-15
tags: ["Forró", "Music", "Web Audio", "Design Systems", "VS Code"]
series: ["Projects"]
description: "How a shared obsession with forró turned into three very different side projects: a rhythm sequencer, a bilingual percussion practice log, and VS Code theme."
---

Forró isn't just something I listen to — over the last while it's become the connective thread across a handful of unrelated side projects. None of them started as a coordinated plan; each came from a different itch, and only in hindsight do they read as three angles on the same thing: playing it, learning it, and coding to it.

## Forró Sequencer: making the rhythm playable

[Forró Sequencer](https://yerkoescalona.github.io/forro-sequencer/) started from a simple frustration — most rhythm tools are built around genres that aren't forró, so the pulse always feels slightly wrong. Forró's rhythmic backbone comes from the zabumba and triangle interlocking in a specific way, and generic drum-machine grids don't make that relationship visible.

The sequencer is a small, focused web app: adjustable BPM (100 by default, with a tap-tempo input for musicians who'd rather feel out the pace than type a number), an instrument picker, and a library of pre-built ritmos to start from instead of a blank grid. Measures can be added or removed on the fly, patterns save and load, and there's a dark mode for late-night arranging sessions. It's aimed squarely at "músicos de forró" — not a general-purpose sequencer with a Brazilian skin, but one where the defaults already assume you know what a baião feels like.

## Zabumbando: a practice log for hands still learning the pattern

[Zabumbando](https://yerkoescalona.github.io/zabumbando/) is less a project than a register — a bilingual (PT-BR/EN) place to write down what I'm learning as I work through the zabumba and other forró percussion. Posts, tags, an about page: the structure of a content site, used for the much smaller purpose of keeping track of my own progress and sharing it with the others going through the same thing.

Percussion knowledge in forró is mostly oral — passed hand to hand at a roda, not written down — so there isn't a lot to point beginners to. Writing it down bilingually was less a statement about accessibility and more a practical choice: some of the people I'm learning alongside read Portuguese, some read English, and I didn't want to pick one and lose the other.

## Forró theme: needed one, so I built one

The [Forró VS Code theme](https://yerkoescalona.github.io/forro-theme/) started from something much less deliberate than the other two: I was coding, staring at whatever theme I had installed, and realized what I actually wanted open in front of me all day was something that felt like forró instead of something generic. So I built it. Five variants ended up in it — Roots, Íntimo, Nordeste Vivo, Pé de Serra, and PD — each pulling from a different atmosphere within the music, from a quiet study session to full dance-floor energy, with code samples that feature real forró artists, regional cities, and musical traditions instead of `foo`/`bar` placeholders.

## Why keep them separate

It would be tidy to bundle all three into one "forró platform," but they solve different problems for me, and forcing them together would make each one worse at its actual job. The sequencer needs to be fast and disposable — open it, sketch a rhythm, close it. Zabumbando needs to be a running log I can add to without ceremony. The theme needs to disappear into the background of an editor for eight hours a day. Keeping them separate, single-purpose, is what's let each one stay simple.

- [Forró Sequencer](https://yerkoescalona.github.io/forro-sequencer/)
- [Zabumbando](https://yerkoescalona.github.io/zabumbando/)
- [Forró VS Code theme](https://yerkoescalona.github.io/forro-theme/)
