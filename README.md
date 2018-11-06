## Languages
-  [English](https://github.com/NoXPhasma/protondb_faq#table-of-content)
-  [German](https://github.com/NoXPhasma/protondb_faq#German)
-  French (Still looking for someone who can translate it)
-  Spanish (Still looking for someone who can translate it)
-  Italian (Soon)

## Table of content
  - [Why do my games crash on start, run very slow or have rendering issues?](#why-do-my-games-crash-on-start-run-very-slow-or-have-rendering-issues)
  - [My game crashes after a while but works fine without esync](#my-game-crashes-after-a-while-but-works-fine-without-esync)
  - [The game doesn't show any text](#the-game-doesnt-show-any-text)
  - [Some games like Witcher 3 have missing textures/enemies](#some-games-like-witcher-3-have-missing-texturesenemies)
  - [Some reports say they made the game running by installing some software, how do I do that?](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that)
  - [How do I run Windows games I don't own on Steam?](#how-do-i-run-windows-games-i-dont-own-on-steam)
  - [Games stored on my Windows partition (NTFS) won't start](#games-stored-on-my-windows-partition-ntfs-wont-start)
## Why do my games crash on start, run very slow or have rendering issues?

#### Be sure that your system is up-to-date and that you are using the latest drivers available for your graphics card.

#### Take a look at the site for your game on [WineHQ](https://appdb.winehq.org), you might find workarounds to make it run. If the site reports that it runs with Wine it could be a Proton specific issue or maybe a 3rd party DRM like "Denuvo" is making trouble here.

#### Be sure that you run Steam with Steam Runtime libraries:

- Arch: Use Steam (Runtime)

- Solus: Disable the native-runtime in their "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"

Note:

- These are stable drivers if you want to use newer beta/devel drivers do it on your own!

- LLVM 7 or newer is requiered to fix the most graphic/rendering issues. If your distro still use LLVM 6 like Solus for example then tell them to update!



##
### Graphics driver installation
#### AMD

Arch/Manjaro/Antergos:
```
sudo pacman -S vulkan-radeon lib32-vulkan-radeon lib32-mesa lib32-vulkan-icd-loader vulkan-tools
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
sudo apt update
sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```
Ubuntu 18.10

```
sudo apt install mesa-utils
sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
```
##
#### Nvidia

Arch/Manjaro/Antergos:
```
sudo pacman -S lib32-nvidia-utils lib32-opencl lib32-nvidia nvidia nvidia-utils
```

Ubuntu 18.10:
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-396
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-driver-396
```
##
#### Intel

Arch/Manjaro/Antergos:
```
sudo pacman -S lib32-vulkan-intel vulkan-intel lib32-mesa lib32-vulkan-icd-loader vulkan-tools
```

Ubuntu 18.10:
```
sudo apt install mesa-utils
sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
sudo apt update
sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```
##
To check if vulkan is working execute the command: `vulkaninfo`

Here is an example how it should look.

If you get: Cannot create Vulkan instance. Try to restart your PC. If the error still occur and you are really sure that all packages are installed, ask in our [Discord](https://discord.gg/uuwK9EV) for more help.

## My game crashes after a while but works fine without esync

Most issues with esync are related to the limited amount of opened files. Before reporting issues with esync, check if the command `ulimit -Hn` reports much more than 4096. If not, you can follow [these instructions](https://github.com/zfigura/wine/blob/esync/README.esync) to raise the limit.

## The game doesn't show any text

Some games need Windows fonts to be installed. Since Proton version [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) this will be done for you automatically. If you are using Proton 3.7, try if switching to version 3.16-4 or higher fixes your problem.

To change the Proton version, go to the Steam settings and there to the tab Steam Play. You need to activate the option "Use this tool instead of game-specific selections from Steam". Then you can chose the Proton version in the drop down menu.

## Some games like Witcher 3 have missing textures/enemies

This is fixed since DXVK Version [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) and Vulkan 1.1.88. Unfortunately at time of this writing, you need beta drivers for Nvidia (396.54.09) and AMD users need at least Mesa version 18.3.

## Some reports say they made the game running by installing some software, how do I do that?

There are two ways to install additional software into the games prefix:

#### Use of Winetricks
Make sure you have winetricks installed on your system. This package should be in your distributions repository.

Open a Terminal and use
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) must be replaced with the game id for example 4000 for Garry´s Mod, you can use [SteamDB](https://steamdb.info) to find out what id your game have.

(Steam-folder) must be replaced with your .steam folder loaction.

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

By default Linux mounts NFTS partitions only writable by Root. [WIP]

## German
## Inhaltsverzeichnis

- Warum läuft mein Spiel so langsam, hat Grafische fehler oder startet erst gar nicht?
- Mein Spiel stürzt nach einiger zeit ab. Dies passiert aber nicht ohne Esyc!
- Mein Spiel zeigt gar keinen Text an
- Einige Spiele wie Witcher 3 haben fehlende Texturen oder unsichtbare Feinde
- Einige Berichte sagen, dass sie das Spiel mit der Installation von zusätzlicher Software zum laufen gebracht haben, wie kann ich das tun?
- Wie führe ich Windows-Spiele aus, die ich nicht auf Steam besitze?

## Warum läuft mein Spiel so langsam, hat Grafische fehler oder startet erst gar nicht?

#### Überprüfen sie ihre Grafikkartentreiber ob sie auf den aktuellsten stand sind.

#### Werfen Sie auf jeden fall einen Blick auf die Website WineHQ von ihren Spiel, um Workarounds zu finden, damit ihr spiel läuft. Wenn die Seite meldet, dass es mit Wine läuft, könnte es sich um ein Proton-spezifisches Problem handeln, oder vielleicht macht ein Drittanbieter-DRM wie zum Beispiel  "Denuvo "  Probleme.

#### Seien sie sich sicher das sie Steam mit den Steam eigenen Laufzeitbibliotheken verwenden.

- Arch: Steam (Runtime)
- Solus: Hier muss im Solus eigenen "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)" die Option "native-runtime" ausgeschaltet werden.

Hinweiße:

- Bei den vorgegeben Grafikktreiber installationen handelt es sich um Stabile Treiber, wenn sie Beta- oder Entwicklungsversionen nutzen möchten tun sie dies auf ihre eigene Faust.

- LLVM 7 oder neuer wird benötigt um die meisten Grafikkfehler beim spielen zu vermeiden. Sollte ihre Distro immer noch LLVM 6 verwenden wie zum Beispiel : Solus dann fragen sie die entwickler ob sie LLVM aktualisieren.

## Installation der Grafikktreiber

#### AMD

Arch/Manjaro/Antergos:
```
sudo pacman -S vulkan-radeon lib32-vulkan-radeon lib32-mesa lib32-vulkan-icd-loader vulkan-tools
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
sudo apt update
sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```
Ubuntu 18.10

```
sudo apt install mesa-utils
sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
```
##
#### Nvidia

Arch/Manjaro/Antergos:
```
sudo pacman -S lib32-nvidia-utils lib32-opencl lib32-nvidia nvidia nvidia-utils
```

Ubuntu 18.10:
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-396
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-driver-396
```
##
#### Intel

Arch/Manjaro/Antergos:
```
sudo pacman -S lib32-vulkan-intel vulkan-intel lib32-mesa lib32-vulkan-icd-loader vulkan-tools
```

Ubuntu 18.10:
```
sudo apt install mesa-utils
sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
```

Ubuntu 18.04:
```
sudo add-apt-repository ppa:paulo-miguel-dias/pkppa
sudo apt update
sudo apt install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```
##
Um zu überprüfen ob Vulkan funktioniert führen sie folgenden Befehl aus : `vulkaninfo`

Hier ist ein Beispiel wie es aussehen sollte.

Wenn sie die Fehlermeldung: "Cannot create Vulkan instance" erhalten starten sie ihren Computer neu. Sollte der Fehler immer noch auftauchen obwohl die richtigen Packete installiert wurden, fragen sie im unseren [Discord](https://discord.gg/uuwK9EV) nach für weitere Hilfe.

## Mein Spiel stürzt nach einiger zeit ab. Dies passiert aber nicht ohne Esync!

Die meisten Probleme mit esync beziehen sich auf die begrenzte Anzahl geöffneter Dateien. Bevor Sie Probleme mit esync melden, prüfen Sie, ob der Befehl "ulimit-Hn" viel mehr als 4096 meldet. Wenn nicht dann folgen sie diesen [Anweisungen](https://github.com/zfigura/wine/blob/esync/README.esync) um das Limit zu erhöhen

## Mein Spiel zeigt gar keinen Text an

Einige Spiele benötigen Windows-Schriftarten, die installiert werden müssen. Aber seit der Proton Version [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) sind diese Schriftarten von Haus aus dabei. Wenn Sie Proton 3.7 verwenden, versuchen Sie auf Version 3.16-4 oder höher umzusteigen, um Ihr Problem zu beheben.

Um die Proton-Version zu ändern, gehen Sie zu den Steam-Einstellungen und dort zum Tab Steam Play. Nun müssen Sie die Option "Use this tool instead of game-specific selections from Steam" aktivieren. Dann können Sie die Proton-Version im Drop-Down-Menü auswählen.

## Einige Spiele wie Witcher 3 haben fehlende Texturen oder unsichtbare Feinde

Das ist seit der DXVK-Version [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) und Vulkan 1.1.88 behoben worden. Leider zum Zeitpunkt dieses Schreibens, brauchen Sie die Beta-Treiber für Nvidia (396.54.09) und AMD-Nutzer brauchen mindestens Mesa Version 18.3.

## Einige Berichte sagen, dass sie das Spiel mit der Installation von zusätzlicher Software zum laufen gebracht haben, wie kann ich das tun?

Es gibt zwei Möglichkeiten um, zusätzliche Software in das game-prefix zu installieren:

#### Einsatz von Winetricks
Stellen Sie sicher, dass Sie Winetricks auf Ihrem System installiert haben. Dieses Paket sollte sich in Ihrem Offiziellen Distributions-Repository befinden.

Terminal öffnen und folgenden befehl eingeben :
```
WINEPREFIX = (Steam-Ordner)/Steamapps/compatdata/(GAME-ID)/pfx/winetricks
```
(GAME-ID) muss durch die Spiel-ID ersetzt werden, zum Beispiel 4000 für Garry ́s Mod, können Sie [SteamDB] (https:/steamdb.info) verwenden, um herauszufinden, welche ID Ihr Spiel hat.

(Steam-Ordner) muss durch den .steam Ordner Loaction ersetzt werden.

Hier ein Beispiel wie der Befehl am Ende auszusehen hat.

```
WINEPREFIX=/home/alexander/.steam/steamapps/compatdata/4000/pfx/winetricks
```
##
#### Einsatz von speziellen Tools

Die beiden beliebtesten sind derzeit [Protontricks](https://github.com/Sirmentio/protontricks) and [ProtonFixes](https://github.com/simons-public/protonfixes).

Bitte lesen Sie die Anweisungen zu diesen Tools auf ihren jeweiligen Seiten.

## Wie führe ich Windows-Spiele aus, die ich nicht auf Steam besitze?

Um Spiele auszuführen, die nicht auf Steam sind, können Sie [Lutris](https:/lutris.net/) verwenden, um sie mit Wine zu benutzen. Lutris ist ein Game-Manager, der Unterstützung für eine Menge von verschiedenen Kompatibilitätslayers/Emulatoren, einschließlich Wine/Proton bietet.

## Spiele, die auf meiner Windows-Partition (NTFS) gespeichert sind, starten nicht

Standardmäßig stellt Linux NFTS-Partitionen nur von Root beschreibbar bereit. [WIP]
