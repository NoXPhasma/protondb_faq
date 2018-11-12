## Languages
-  [English](#table-of-content) (Written by [NoXPhasma](https://github.com/NoXPhasma) & [CrackedCrafterz](https://github.com/CrackedCrafterz))
-  [German](README_DE.md) (Translated by [CrackedCrafterz](https://github.com/CrackedCrafterz))
-  [Spanish](README_ESP.md) (Translated by [Willdrick](https://github.com/Willdrick))
-  [French](README_FR.md) (Translated by [Askannz](https://github.com/Askannz))
-  [Italian](README_IT.md) (Translated by [Bloodis](https://github.com/bloodis))
-  [Norwegian](README_NO.md) (Translated by [MagZu](https://github.com/magzu))

## Introduction
With this FAQ we want to cover the most important questions related to the usage of ProtonDB and of course technical questions which occur very often on the Discord. If you want to participate or have suggestions, don't hesitate to contact us on [Discord](https://discord.gg/uuwK9EV) or send us issues and pull requests.


## Table of content
  - [[ProtonDB] The "Run" and "Install" buttons don't seem to work on Firefox.](#protondb-the-run-and-install-buttons-dont-seem-to-work-on-firefox)
  - [Why do my games crash on start, run very slow or have rendering issues?](#why-do-my-games-crash-on-start-run-very-slow-or-have-rendering-issues)
  - [My game crashes after a while but works fine without esync](#my-game-crashes-after-a-while-but-works-fine-without-esync)
  - [The game doesn't show any text](#the-game-doesnt-show-any-text)
  - [Some games like Witcher 3 have missing textures/enemies](#some-games-like-witcher-3-have-missing-texturesenemies)
  - [How do I create logs of a game I run with Proton?](#how-do-i-create-logs-of-a-game-i-run-with-proton)
  - [Some reports say they made the game running by installing some software, how do I do that?](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that)
  - [How do I run Windows games I don't own on Steam?](#how-do-i-run-windows-games-i-dont-own-on-steam)
  - [Games stored on my Windows partition (NTFS) won't start](#games-stored-on-my-windows-partition-ntfs-wont-start)
## [ProtonDB] The "Run" and "Install" buttons don't seem to work on Firefox.
If Firefox don't ask you, how it should proceed with `steam://` URLS, you need to force Firefox to do so. For that open `about:config` in your Firefox, right click anywhere in the list and select `New` » `Bolean`. As name for the new entry you chose `network.protocol-handler.expose.steam` and as value `false`. Now if you click on a `steam://` URL, Firefox should ask you how to proceed.
## Why do my games crash on start, run very slow or have rendering issues?

#### Be sure that your system is up-to-date and that you are using the latest drivers available for your graphics card. You will find detailed informations about how to update your graphic drivers in our [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

Note:

- LLVM 7 or newer is required to fix the most graphic/rendering issues. If your distro still use LLVM 6 then tell them to update!

#### Take a look at the site for your game on [WineHQ](https://appdb.winehq.org), you might find workarounds to make it run. If the site reports that it runs with Wine it could be a Proton specific issue or maybe a 3rd party DRM like "Denuvo" is making trouble here.

#### Be sure that you run Steam with Steam Runtime libraries:

- Arch: Use Steam (Runtime)

- Solus: Disable the native-runtime in their "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"


## My game crashes after a while but works fine without esync

Most issues with esync are related to the limited amount of opened files. Before reporting issues with esync, check if the command `ulimit -Hn` reports much more than 4096. If not, you can follow [these instructions](https://github.com/zfigura/wine/blob/esync/README.esync) to raise the limit.

## The game doesn't show any text

Some games need Windows fonts to be installed. Since Proton version [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) this will be done for you automatically. If you are using Proton 3.7, try if switching to version 3.16-4 or higher fixes your problem.

To change the Proton version, go to the Steam settings and there to the tab Steam Play. You need to activate the option "Use this tool instead of game-specific selections from Steam". Then you can chose the Proton version in the drop down menu.

## Some games like Witcher 3 have missing textures/enemies

This is fixed since DXVK Version [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) and Vulkan 1.1.88. Unfortunately at time of this writing, you need beta drivers for Nvidia (396.54.09) and AMD users need at least Mesa version 18.3.

## How do I create logs of a game I run with Proton?

Proton will create a log file for a particular game, if you [set the launch parameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947) to:
```
PROTON_LOG=1 %command%
```
The log file will be created in your home folder with the name scheme `steam-$STEAMID.log`. For example:
```
$HOME/steam-379720.log
```

## Some reports say they made the game running by installing some software, how do I do that?

There are two ways to install additional software into the games prefix:

#### Use of Winetricks
Make sure you have winetricks installed on your system. This package should be in your distributions repository.

Open a Terminal and use
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) must be replaced with the game id for example 4000 for Garry´s Mod, you can use [SteamDB](https://steamdb.info) to find out what id your game have.

(Steam-folder) must be replaced with your .steam folder location.

Here is an example

```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```
##
#### Use of Tools

The two most popular currently are [Protontricks](https://github.com/Sirmentio/protontricks) and [ProtonFixes](https://github.com/simons-public/protonfixes).

Please read the instructions about those tools on their respective sites.

## How do I run Windows games I don't own on Steam?

To run games which are not on Steam, you can use [Lutris](https://lutris.net/) to run them with Wine. Lutris is a game manager which offers support for a lot of different compatibility layers/emulators, including Wine/Proton.

## Games stored on my Windows partition (NTFS) won't start

By default Linux mounts NFTS partitions only writeable by Root. [WIP]
