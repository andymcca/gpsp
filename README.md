
lr-gpsp-amcc (forked from gpSP for libretro)
============================================

This is a fork-of-a-fork of gpsp for libretro frontends (like Retroarch).

I'm adding features here and also raising PRs for visibilty on the main
libretro gpsp repo.  

The current maintainer/main contributor of https://github.com/libretro/gpsp/ 
is davidgfnet (check out the repo at https://github.com/davidgfnet/gpsp). 
His version has a bunch of fixes and features, and my fork here just builds on
that with a few of my experimental bits which are unlikely to be committed to
the main repo in their present form!  These currently include -

 - Partial support for OAM Order Hijacking (fixes display issues in Golden Sun 1/2,
   Zelda Minish Cap and others)
 - Checking for DMA/IRQ more frequently during scanline render (fixes display issues
   in Sims 2, Monster House and Teen Titans)
 - Smaller blocks/exits for ARM in the Dynarec (this gives a general speed up in
   Camelot games such as Mario Tennis and Mario Golf)
 - Dynamic Translation Gates (auto-detected and added whilst games are running)
 - STR instruction value check before write in the ARM dynarec (saves a few SMC
   flushes here and there)
 - Green Swap support (not used in commercial games, but in some homebrew/demos)
 - Fix for the audio in CT Special Forces 3 by partially reverting an earlier
   commit (not sure if this breaks anything else)

Other things I hope/want to do here -

 - Choose between old/new video renderer - David rewrote the entire renderer last
   year and did a fantastic job in also implementing other features like Mosaic
   which were previously unsupported.  In some instances the old renderer can be
   a bit quicker so I'd like to implement a core option to switch between the two.

Main gpsp Feature list
======================

gpSP features a dynamic recompiler that makes it quite fast (compared to other
emulators at least). It supports x86/x64, ARMv6/7 and ARMv8 and MIPS (32 and 64
bits), for other platforms an interpreter is available (albeit slower). Both
little and big endian systems are supported. Some supported platforms are PSP,
PS2, GameCube/Wii, Nintendo 3DS and Switch, Dingux/OpenDingux and of course
PC and Android.

At the moment this emulator lacks a native UI and must be played using some
libretro frontend (we recommend Retroarch). A list of available frontends can
be found at https://docs.libretro.com/development/frontends/

Many new features (compared to the original release) are:

 - Wireless Adapter networked multiplayer!
 - Rumble support (including Gameboy Player emulation)
 - New video renderer, fixes many graphical bugs & adds many effects (mosaic).
 - Many long standing issues have been fixed.
 - Slightly better performance (for some games at least!)
 - Better audio (fixed many audio related bugs).
 - Ships an opensource BIOS replacement,we recommend using the original though.



