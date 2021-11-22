---
title: DOS and Windows
description: Emulation of DOS and Windows environments
date: 2021-08-23
---

# DOS emulation

[[toc]]

When considering various solutions for legacy software, it is helpful to compare the different ways of substituting for Microsoft platforms from over the past four decades: DOSBox and WINE projects.

## DOSBox

DOSBox is unusual as an emulator: DOSBox emulates a set of hardware configurations that most of its users would rather not think about -- mostly a set of common PC platform targets from the 80s and 90s which have only subtle differences from one another -- in order to provide an environment which is compatible with most DOS software. Although all of these DOS platforms were/are based on x86 PC architectures and could theoretically be virtualized on most modern computers rather than emulated, the increased portability (e.g. to ARM platforms) of a fully emulated architecture, as well as the relatively low needs of the slower, older hardware being emulated, lessens the need to maintain a virtualization solution.

DOSBox also provides the DOS environment itself. This is somewhat atypical, owing to the various DOS APIs being relatively easy to reimplement. 

Copyright played a role in the development of DOSBox. FreeDOS was the first to emulate DOS software in 1998, after Microsoft stopped supporting DOS, yet the Windows compatibility layer wasn't satisfactory. 

Another difficulty in using emulation is the management of hardware/software peripherals for audio, video, keyboard and other peripherals. Managing various audio and video plugins to control output was difficult in DOS and remains an issue. The preconfigured DOSBox target machine settings are helpful here, but emulating DOS still entails working with a DOS filesystem and an ancient command prompt. 

It has been said that where Apple platforms are a delight to use up until you attempt to run a game on them, Microsoft platforms are the opposite, and true to form, most popular uses of DOSBox do not involve spending much time in DOS itself. Many resellers of legacy PC games from the period actually ship their titles in prepackaged configurations of DOSBox designed to run easily in modern environments; as in so many emulation use cases, the game is the point, rather than the DOS platform itself.

## Wine

WINE is not an emulator -- that's what the acronym stands for. Rather, WINE is a runtime compatibility layer for running Windows software on non-Windows platforms that replaces various Windows API calls and low-level libraries with their equivalents on other platforms. It is exceptionally performant, generally able to translate DirectX rendering calls in real time to cross-platform alternatives (such as OpenGL or Vulkan) with about one CPU thread's worth of overhead. Its compatibility with decades of Windows software is tracked at winehq.org, and it can be a very convenient alternative to needing an entire Windows virtual machine (and associated licensing) to run specific legacy applications.

WINE can be quite fussy when running complex applications. Wine defaults to storing various environment settings and copies of Windows libraries in per-app sandboxes (similar to how pyenv works for Python programming). Juggling these requires some command line expertise. It also tends to run 5-10 years behind newer Windows frameworks.

If there is a reason that WINE has never become more popular in preservation circles, it is probably because it solves the wrong problem in the wrong contexts. Its relative instability and fussiness generally makes it better suited to one-off solutions and individual needs to use a single piece of software; however, its primary use case of running software in an environment where Windows is not an option typically describes only servers[1], where there is a preference for running software that is more hardened and more reliable. This is unfortunate, because the WINE project has generated an enormous amount of documentation and technically liberated an enormous amount of software from a platform controlled by a single commercial entity; the WINE wiki is often said to be a better resource for legacy Windows APIs than Microsoft's own extant documentation. But the conditions under which an user cannot or will not run Windows for reasons that are technical in nature rather than ideological or circumstantial are nevertheless rare. However robust WINE itself may be, the ever-expanding set of Windows software that it is obliged to add compatibility for will likely always add uncertainty in practice.

DOSBox and Wine both have the advantage of being fairly monolithic projects with many contributors and no real competition where faithfulness of emulation is concerned. As such, they are often used as the basis for derivative projects. For example, https://github.com/danoon2/Boxedwine is a project that emulates Windows by emulating x86 Linux and running Wine on the emulated Linux.

[1]: Windows servers of course exist and are popular in enterprise IT contexts; they may as well not exist for the purposes of software preservation and access, as licensing and deployment are dramatically more prohibitive than with virtually all other tools available to curators, and there is a justifiably absolute preference for open source tooling of digital preservation platforms themselves, even when the platforms being preserved are otherwise encumbered.
