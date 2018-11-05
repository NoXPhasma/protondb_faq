##### My game crashes after a while but works fine without esync

Most issues with esync are related to the limited amount of opened files. Before reporting issues with esync, check if the command `ulimit -Hn` reports much more than 4096. If not, you can follow [these instructions](https://github.com/zfigura/wine/blob/esync/README.esync) to raise the limit.

##### The game doesn't show any text ==

Some games need Windows fonts to be installed. Since Proton version 3.16-4 this will be done for you automatically. If you are using Proton 3.7, try if switching to version 3.16-4 or higher fixes your problem.

To change the Proton version, go to the Steam settings and there to the tab Steam Play. You need to activate the option "Use this tool instead of game-specific selections from Steam". Then you can chose the Proton version in the drop down menu.

##### One or more of my games I try run very slow ==

Be sure that your system is up-to-date and that you use the latest drivers available for your graphics card. The [official Proton wiki](https://github.com/ValveSoftware/Proton/wiki/Requirements#graphics-drivers-quickstart---ubuntu-1804) has detailed informations on what driver Versions are needed.

##### Some games like Witcher 3 have missing textures/enemies ==

This is fixed since DXVK Version 0.90 and Vulkan 1.1.88. Unfortunately at time of this writing, you need beta drivers for Nvidia (396.54.09) and AMD users need at least Mesa version 18.3.

##### Some reports say they made the game running by installing some software, how do I do that? ==

There are some tools to fix issues with games, the two most popular currently are [Protontricks](https://github.com/Sirmentio/protontricks) and [ProtonFixes](https://github.com/simons-public/protonfixes).

Please read the instructions about those tools on their respective sites.

##### How do I run Windows games I don't own on Steam? ==

To run games which are not on Steam, you can use [Lutris](https://lutris.net/) to run them with Wine. Lutris is a game manager which offers support for a lot of different compatibility layers/emulators, including Wine/Proton.

##### Games stored on my Windows partition (NTFS) won't start ==

By default Linux mounts NFTS partitions only writable by Root. [WIP]
