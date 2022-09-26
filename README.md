# ScummVM + libretro core backend For Miyoo Mini


This repo is based on [StupidHoroscope/ScummVM-MiyooMini](https://github.com/StupidHoroscope/ScummVM-MiyooMini) which is a fork of the official ScummVM repo.

Coupled with  [schmurtzm/libretro-scummvm-miyoo-backend](https://github.com/schmurtzm/libretro-scummvm-miyoo-backend)  which is a fork of [diablodiab/libretro-scummvm-backend](https://github.com/diablodiab/libretro-scummvm-backend) it allows to generate an up to date Retroarch core from current version of ScummVM (v2.6 stable or v2.7 dev).

[libretro-scummvm-miyoo-backend](https://github.com/schmurtzm/libretro-scummvm-miyoo-backend) has been included as a submodule of this project.
This ScummVM core is more up to date than the current official libretro core so it supports more games including 2.5D games like Grim Fandango (About 385 in v2.7 vs 298 games for the v2.1.1).


Comparing the official ScummVM, this repo contains very few differences : 
- Disabled SVG rendering in themes 
- Added libretro-scummvm-miyoo-backend as submodule (the differences for the Miyoo Mini are more in this part)


## Compiling

To compile the core, run the following:

```
git submodule init 
git submodule update
cd backends/platform/libretro/build
make platform=miyoomini -j$(nproc)
```

When updating ScummVM, it's important to rebuild [scummvm.zip](aux-data/scummvm.zip) so that any auxiliary data is bundled in. The compile the new scummvm.zip, run the following command:

```
cd backends/platform/libretro/aux-data
./bundle_aux_data.bash
```
These extra files can be unziped in BIOS folder of the Miyoo Mini. 
This archive contains themes and files required to make some engines work (like kyra.dat for westwood games).

---


# [ScummVM README](https://www.scummvm.org/) · [![CI](https://github.com/scummvm/scummvm/actions/workflows/ci.yml/badge.svg)](https://github.com/scummvm/scummvm/actions/workflows/ci.yml) [![Translation status](https://translations.scummvm.org/widgets/scummvm/-/scummvm/svg-badge.svg)](https://translations.scummvm.org/engage/scummvm/?utm_source=widget) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md#pull-requests) [![Codacy Badge](https://app.codacy.com/project/badge/Grade/e06e5b18f8464fef859b5a7f78d10357)](https://www.codacy.com/gh/scummvm/scummvm/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=scummvm/scummvm&amp;utm_campaign=Badge_Grade)

## About ScummVM

ScummVM allows you to play classic graphic point-and-click adventure games, text adventure games, and RPGs, as long as you already have the game data files. ScummVM replaces the executable files shipped with the games, which means you can now play your favorite games on all your favorite devices.

So how did ScummVM get its name? Many of the famous LucasArts adventure games, such as Maniac Mansion and the Monkey Island series, were created using a utility called SCUMM (Script Creation Utility for Maniac Mansion). The ‘VM’ in ScummVM stands for Virtual Machine.

While ScummVM was originally designed to run LucasArts’ SCUMM games, over time support has been added for many other games: see the full list [on our wiki](https://wiki.scummvm.org/index.php?title=Category:Supported_Games). Noteworthy titles include Broken Sword, Myst and Blade Runner, although there are countless other hidden gems to explore.

For more information, compatibility lists, details on donating, the
latest release, progress reports and more, please visit the ScummVM [home
page](https://www.scummvm.org/).

## Quickstart

For the impatient among you, here is how to get ScummVM running in five simple steps.

1. Download ScummVM from [our website](https://www.scummvm.org/downloads/) and install it.

2. Create a directory on your hard drive and copy the game datafiles from the original media to this directory. Repeat this for every game you want to play.

3. Start ScummVM, choose 'Add game', select the directory containing the game datafiles (do not try to select the datafiles themselves!) and press Choose.

4. The Game Options dialog opens to allow configuration of various settings for the game. These can be reconfigured at any time, but for now everything should be OK at the default settings.

5. Select the game you want to play in the list, and press Start. To play a game next time, skip to step 5, unless you want to add more games.

>
> Hint:
>
> To add multiple games in one go, press and hold the shift key, then click 'Add game' -- the label will change to 'Mass Add' and if you press it, you are again asked to select a directory, only this time ScummVM will search through all subdirectories for supported games.



## Reporting a bug

To report a bug, go to the ScummVM [Issue Tracker](https://bugs.scummvm.org/) and log in with your GitHub account.

Please make sure the bug is reproducible, and still occurs in the latest git/Daily build version. Also check the [compatibility list](https://www.scummvm.org/compatibility/) for that game, to ensure the issue is not already known. Please do not report bugs for games that are not listed as completable on the [Supported Games](https://wiki.scummvm.org/index.php?title=Category:Supported_Games) wiki page, or on the compatibility list. We already know those games have bugs!

Please include the following information in the bug report:

- ScummVM version (test the latest git/Daily build)
- Bug details, including instructions for how to reproduce the bug. If possible, include log files, screenshots, and any other relevant information.
- Game language
- Game version (for example, talkie or floppy)
- Platform and Compiler (for example, Win32, Linux or FreeBSD)
- An attached saved game, if possible.
- If this bug only occurred recently, include the last version without the bug, and the first version with the bug. That way we can fix it quicker by looking at the changes made.

Finally, please report each issue separately; do not file multiple issues on the same ticket. It is difficult to track the status of each individual bug when they aren't on their own tickets.

## Documentation

### User documentation

For everything you need to know about how to use ScummVM, see our [user documentation](https://docs.scummvm.org/).

### The ScummVM Wiki

[The wiki](https://wiki.scummvm.org/) is the place to go for information about every game supported by ScummVM. If you're a developer, there's also some very handy information in the Developer section.

### Changelog

Our extensive change log is available [here](NEWS.md).

## Credits

A massive thank you to the entire team for making the ScummVM project possible. See the credits [here](AUTHORS)!

-----

> Good Luck and Happy Adventuring\!
> The ScummVM team.
> <https://www.scummvm.org/>
