---
title: Classic Mac
description: Emulation of Classic Mac Environments
date: 2021-08-23
---

# Classic Mac emulation

[[toc]]

## Disk images

The simplest emulators do not require any additional metadata or archived code beyond the emulator itself and the title you want to emulate. This was true in 1997 when the iNES header format was developed for backups of 8-bit Nintendo titles, and it remains true today when emulating many early computers; there was only ever a single hardware target for these platforms, no middleware which was required to go from booting the machine to running end-user software, and no platform revisions that create meaningful compatibility differences.

As we move from here toward and into the 90s, this becomes less and less the case for computers and game consoles alike. True to form for Microsoft, DOS is famously backward compatible on into oblivion, and versioning of DOS distributions is almost never necessary for historical purposes, but Classic Macintosh OS versions have significant differences between releases, as well as different levels of emulator support, and you will always need to bring a bootable OS image to a Macintosh emulator along with whatever other software you want.

## Mac environments

Summarized briefly, Basilisk II is the most complete and full-featured Classic MacOS emulator up through System 7 (supporting 68k hardware architectures), and Sheepshaver is the most complete and full-featured emulator for MacOS 8 and 9 (supporting PowerPC hardware architectures). Generally, there is no need to emulate MacOS versions earlier than System 6 other than historical curiosity about the operating system itself, as they were fairly rudimentary refinements on the various OS-level features, and System 6 is almost completely backward compatible with earlier software, though there are always exceptions in these cases. There is another popular Classic Mac emulator called Mini vMac which works on most of the same older releases as Basilisk II, which is simpler and lighter weight but less configurable. This is the same distinction usually made between System 6 and System 7; the latter was patched over many years to add various system extensions and features that Classic Macs lacked (like color output!) and any working System 7 environment can be quite different from another, whereas System 6 is pretty much always System 6.

Both MacOS operating systems and MacOS software will generally be distributed on disk images. Operating systems, especially later versions, will nominally be on hard drive-sized images, whereas other software will be on floppy or CD-ROM images, but MacOS makes relatively few distinctions between these in practice other than their size. In some cases, you may need to begin with a blank hard drive image and a CD-ROM image of an operating system installer in order to create a fresh environment to work in, similar to the way that many modern Virtual Machine environments work with Linux install media; or else you may be able to manipulate an existing hard drive image containing the OS already installed using software like HFSExplorer (designed for the exact purpose of moving files between MacOS disk images in modern environments) to add all the software you want to run to a single boot disk.

Moving Classic MacOS files across modern filesystems is generally a bad idea due to their use of an abandoned concept called *resource forks*. Any data contained in a file on a legacy HFS filesystem which is not meant to be user-editable -- e.g., binary executable data or other metadata properties -- is typically hidden in a file's resource fork, which required special tooling to view on legacy MacOS, and copying these files onto an NTFS or an ext4 filesystem will typically result in the resource fork being dropped entirely. The repercussions of this range from confusing (Classic MacOS did not use file extensions in filenames, instead keeping file associations stored in the resource fork) to unacceptable (some files basically do not exist outside of their resource fork). There are several solutions to this, most of which include always packaging these files into archives first, using either the StuffIt format (a popular zip alternative on MacOS) or the disk images themselves.

## Community Repositories

The Macintosh Garden is an excellent, community-maintained repository of many such .dsk images, including a large variety of commercial software. It is not visibly supported by any memory institutions within the preservation community, probably for complicated reasons of trust and funding. The risk posed by the unexpected loss of such an organization should not be underestimated.

Non-Macintosh platforms have similarly nuanced approaches to distribution of userspace software and operating system software or firmware, but the Mac is somewhat unique in that you can think of most such disk images interchangeably. Newer game consoles sometimes also require BIOS files in order to run the emulated hardware's boot sequence before loading a ROM image, and because these BIOS files are typically copyrighted as well, redistribution can be challenging, leading some emulators to attempt to reimplement an open source BIOS, similar to DOSBox, waiving this requirement. However, this is sometimes thought to be less faithful than the alternative, and you will find emulators that are biased toward one approach or the other.
