![](https://github.com/NoXPhasma/protondb_faq/raw/master/logo.png)

## Languages
-  [English](#table-of-content) (Written by [NoXPhasma](https://github.com/NoXPhasma) & [Alexander](https://github.com/Alexander88207))
-  [German](README_DE.md) (Translated by [Alexander](https://github.com/Alexander88207))
-  [Spanish](README_ESP.md) (Translated by [Willdrick](https://github.com/Willdrick))
-  [French](README_FR.md) (Translated by [Askannz](https://github.com/Askannz))
-  [Italian](README_IT.md) (Translated by [Bloodis](https://github.com/bloodis))
-  [Norwegian](README_NO.md) (Translated by [MagZu](https://github.com/magzu))
-  [Latvian](README_LV.md) (Translated by [HolimaX](https://github.com/HolimaX))
-  [Indonesian](README_ID.md) (Translated by [Ari-El-Uno](https://github.com/Ari-El-Uno))
-  [Swedish](README_SE.md) (Translated by [Kattus](https://github.com/Kattus))
-  [Russian](README_RU.md) (Still needs to be translated by someone)

To see who else was helping, see our [contributors](https://github.com/NoXPhasma/protondb_faq/graphs/contributors) graph!

## Introduction
With this FAQ, we want to cover the most important questions related to the usage of ProtonDB and of course technical questions which occur very often on the Discord. If you want to participate or have suggestions, don't hesitate to contact us on [Discord](https://discord.gg/uuwK9EV) or send us issues and pull requests.


## Table of content
  - [[ProtonDB] The "Run" and "Install" buttons doesn't seem to work on Firefox.](#protondb-the-run-and-install-buttons-dont-seem-to-work-on-firefox)
  - [[ProtonDB] At the site my game is displayed as a windows game but it have a native port or the other way round.
](#protondb-at-the-site-my-game-is-displayed-as-a-windows-game-but-it-have-a-native-port-or-the-other-way-round)
  - [Why do my games crash on start, run very slow or have rendering issues?](#why-do-my-games-crash-on-start-run-very-slow-or-have-rendering-issues)
  - [My game crashes after a while but works fine without esync](#my-game-crashes-after-a-while-but-works-fine-without-esync)
  - [The game doesn't show any text](#the-game-doesnt-show-any-text)
  - [Some games like Witcher 3 have missing textures/enemies](#some-games-like-witcher-3-have-missing-texturesenemies)
  - [Why do some games stutter at the beginning?](#Why-do-some-games-stutter-at-the-beginning)
  - [I have sound problems like crackle for example](#i-have-sound-problems-like-crackle-for-example)
  - [I want to play a game without DXVK](#i-want-to-play-a-game-without-dxvk)
  - [How do I create logs of a game I run with Proton?](#how-do-i-create-logs-of-a-game-i-run-with-proton)
  - [Some reports say they made the game running by installing some software, how do I do that?](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that)
  - [How do I run Windows games I don't own on Steam?](#how-do-i-run-windows-games-i-dont-own-on-steam)
  - [I have issues with my controller!](#i-have-issues-with-my-controller)
  - [Games stored on my Windows partition (NTFS) won't start](#games-stored-on-my-windows-partition-ntfs-wont-start)
  - [Punkbuster, Rockstar Social Club etc... fail during initial installation.](#punkbuster-rockstar-social-club-etc-fail-during-initial-installation)
  - [My Game won't save anything or crash while creating/loading a save.](#my-game-wont-save-anything-or-crash-while-creatingloading-a-save)
  - [My entire computer hangs up at some point in the game](#my-entire-computer-hangs-up-at-some-point-in-the-game)
  
## [ProtonDB] The "Run" and "Install" buttons doesn't seem to work on Firefox.
If Firefox doesn't ask you how it should proceed with `steam://` URLS, you need to force Firefox to do so. For that open `about:config` in your Firefox, right click anywhere in the list and select `New` » `Boolean`. Enter `network.protocol-handler.expose.steam` as the name for the new entry, and `false` as the value. Now if you click on a `steam://` URL, Firefox should ask you how to proceed.

## [ProtonDB] At the site my game is displayed as a windows game but it have a native port or the other way round.

ProtonDB obtains the data from SteamDB and these in turn from the developers of the respective game. So if the developers had a native port like for example at Rust and it was closed then the game will be shown as a Windows game but buyers at the time of the native port will keep the native port of course so there will be some users who write: "it have a native port!".

## Why do my games crash on start, run very slow or have rendering issues?

#### Be sure that your system is up-to-date and that you are using the latest drivers available your graphics card. You will find detailed informations about how to update your graphic drivers in our [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

#### Take a look at the site for your game on [WineHQ](https://appdb.winehq.org), you might find workarounds to make it run. If the site reports that it runs with Wine it could be a Proton specific issue or maybe a 3rd party DRM like "Denuvo" is making trouble here.

#### Be sure that you run Steam with Steam Runtime libraries:

- Arch: Use Steam (Runtime)

- Solus: Disable the native-runtime in their "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"

## My game crashes after a while but works fine without esync

Most issues with esync are related to the limited amount of opened files. Before reporting issues with esync, check if the command `ulimit -Hn` reports much more than 4096. If not, you can follow [these instructions](https://github.com/zfigura/wine/blob/esync/README.esync) to raise the limit.

## The game doesn't show any text

Some games need Windows fonts to be installed. Since Proton version [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) this will be done for you automatically. If you are using Proton 3.7, see if switching to version 3.16-4 or higher fixes your problem.

To change the Proton version, go to the Steam settings and then to the tab Steam Play. You need to activate the option "Use this tool instead of game-specific selections from Steam". Then you can chose the Proton version in the drop down menu.

## Some games like Witcher 3 have missing textures/enemies

This is fixed since DXVK Version [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) and Vulkan 1.1.88. Nvidia users need at least driver version 415.22, and AMD users need at least Mesa version 18.3.

## Why do some games stutter at the beginning?

This is quite normal. Because at the beginning the shaders have to be loaded first. So that it doesn't stutter next time, The are written directly into a so-called shader cache.

Note that the dxvk cache is not related to the "Shader Pre-Caching" by Steam.

## I have sound problems like crackle for example

In most cases, it helps to install xaudio2 (xact) but in cases such as Skyrim, for example, it can also solve a problem for some but can also cause a new sound problem, but it is always worth a try.

Since proton version [3.16-5](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-5) you don't have to do anything unless you're using an older version of proton then read on here:

it is sufficient to set "xaudio2_7.dll" to native, built-in in winecfg or installing xact with winetricks.

[Here](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that) you will find more information on how to install additional programs in your gameprefix.

## I want to play a game without DXVK.

If you really want to try to play your game without DXVK, then try to start the game with the following [launch parameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947)
```
PROTON_USE_WINED3D11=1 %command%
```
Note: You will have maybe graphical error's or poor performance depending on the game.

If your game doesn't start or crash then your game cannot be run with wine3d11
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

There are two ways to install additional software into the gameprefix:

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

Add a Non-Steam game to your library (set File Type to "All Files") and select the .exe

Right click the game in your Library and in Properties - Enable "Force the use of a specific Steam Play compatibility Tool"

If there are any spaces in the path to your .exe you will need to fix the "Target:" path in the game's Properties and clear the "Set Launch Options"

However, we do recommend [Lutris](https://lutris.net/) to run most non Steam games through Wine. Lutris is a game manager which offers support for many different compatibility layers/emulators, including Wine/Proton.

## I have issues with my controller!

Case #1: My controller gets recognized as player 1 & player 2 in lego games.

- Fix  #1: Open the controller settings from the gameprefix with the command for example:`WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ wine control` and deactivate the controller "js" & "event" after that restart your session to confirm that wine is completely closed to ensure that the new changes to be loaded.

Case #2: My Steam-Controller is not recognized even with native games, only the mouse functions.

- Fix #2: This happens on distros based on gentoo or gentoo itself. Noticed by [@Alexander](https://github.com/Alexander88207)

If you game on Linux using steam and have a steam controller you may have noticed something interesting. The steam controller appears to be working, but doesn't work in games or is not displayed under wine control.

We recommend to use the tool [sc-controller)](https://github.com/kozec/sc-controller) to workaround this issue.

## Games stored on my Windows partition (NTFS) won't start

By default Linux mounts NFTS partitions only writeable by Root. It is necessary to mount that partition with user rights. You will find a simple tutorial on how to mount a NTFS drive with user rights on the [Proton Wiki](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows).

## Punkbuster, Rockstar Social Club etc... fail during initial installation.

It can happen that such things are not installed correctly the [first time](https://github.com/NoXPhasma/protondb_faq/raw/master/Initial%20installation%20example.png) and then Steam does not try to install them anymore. 

Each game has a folder in the game folder which for example are called so: "Installers" "Redist" and so on...... These folders contain the installation program for PB or RGSC, these must be started in the corresponding game prefix with Wine, here an example: 

`WINEPREFIX='/home/alexander/.steam/steam/steamapps/compatdata/271590/pfx' wine '/home/alexander/.steam/steam/steamapps/common/Grand Theft Auto V/Installers/Social-Club-Setup.exe'`

## My Game won't save anything or crash while creating/loading a save.

You can try to start the game with this [launchparameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947): `unset LC_ALL && %command%`

## My entire computer hangs up at some point in the game.

This could be a GPU hang but to be sure that this is not Proton's fault test the game in the latest Wine version first.

if this also happens in the latest wine version, only the developers of your graphics driver ([nvidia](https://nvidia.custhelp.com/app/answers/detail/a_id/44) or [mesa](https://www.mesa3d.org/bugs.html)) or rarely [dxvk](https://github.com/doitsujin/dxvk/issues) can help you.
