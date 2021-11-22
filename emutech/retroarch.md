---
title: Retroarch and Frameworks
description: The Retroarch Emulation Framework in context
date: 2021-08-23
---

# Retroarch

[[toc]]

The dominance of retro videogame emulation in the collective imagination of *all* emulation is certainly somewhat responsible for the lack of academic or even general audience writing in this area until the last decade. The tendency until recently for videogame emulators to be obsoleted by competing projects at intervals of a few years, requiring hobbyists to keep track of the various advantages of *ZSNES* vs *SNES9x* vs *bsnes* meanwhile made summarizing the state of the art as we are doing here a near-pointless exercise. And the determination of rights holders to confuse the issues around intellectual property and preservation, especially as long as "emulation" was most commonly associated with running Super Nintendo games on a Windows computer -- as was once depicted on *The Big Bang Theory* of all places, having achieved network television levels of intelligibility -- also did not help.

However, it is now widely accepted in practitioner-focused digital preservation circles, like the audiovisual community's *No Time to Wait* conference, that our best format solutions almost always come from hobbyists. The open source Matroska (.mkv) video container format, which is universally regarded as the most versatile for archival usage and has begun to gain commercial uptake, was famously created by English and French-speaking software developers who wanted a more reliable way of managing their anime subtitles; and the most comprehensive guide to imaging video from optical discs was authored by a indefatigable movie pirate with a determinedly [unfortunate screen name](https://www.dropbox.com/s/4oba7llxgmi3ti7/354211217-The-HANDJOB-Guide-pdf.pdf?dl=0). Even if you were take the position that videogame emulation is functionally a distraction from software preservation, we wouldn't have the same well-documented or well-optimized Motorola 68000 interpreters for use in Macintosh emulation if not for the desirability of playing expensive Neo Geo titles on Pentium II vintage computers in 1998.

...

## Output Filtering

Another of Retroarch's innovations in this space (maybe not original to them, but popularized by their unified community) is the recent standardization of postprocessing shaders, most commonly used to simulate the effects of a CRT monitor when running software that predates modern displays. For the first decade-plus of videogame emulation, it was popular to upscale native output resolutions from 240x192 or so up to XGA displays with the goal of making older games look more modern. This had the downside of often ignoring original authors' intent around colour temperature and aspect ratio correction, and gave rise to a peculiarly artificial aesthetic of clean, hard-edged pixels which didn't quite belong to any era. It also, of course, poses interesting questions around authenticity, and faithfulness of emulation -- hobbyists had by then comprehensively preserved entire legacy platforms' release catalogues, but their typical modes of *access* to this software were pretty far from where they started.

Recently, development has proceeded in the opposite direction, of developing output filters using features of modern GPUs (commonly referred to as *shader programming*) to get as close as possible to the visual artifacts of CRT monitors on LCD displays. This means simulating colour bleed and other artifacts to an extent that is typically unwanted on *capture* of older video signals, but can lend a great deal to their recreation.
