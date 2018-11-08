## Sprachen
-  [Englisch](README.md)
-  [Deutsch](#Inhaltsverzeichnis) (Übersetzt von [CrackedCrafterz](https://github.com/CrackedCrafterz))
-  [Spanisch](README_ESP.md) (Übersetzt von [Willdrick](https://github.com/Willdrick))
-  Französisch (Wir suchen immer noch jemanden der Lust hat die französische Übersetzung zu schreiben.)
-  [Italienisch](README_IT.md) (Übersetzt von [Bloodis](https://github.com/bloodis))
-  [Norwegisch](README_NO.md) (Übersetzt von [MagZu](https://github.com/magzu))

## Inhaltsverzeichnis

- [Warum läuft mein Spiel so langsam, hat grafische Fehler oder startet erst gar nicht?](#warum-läuft-mein-spiel-so-langsam-hat-grafische-fehler-oder-startet-erst-gar-nicht)
- [Mein Spiel stürzt nach einiger Zeit ab. Dies passiert aber nicht ohne Esyc!](#mein-spiel-stürzt-nach-einiger-zeit-ab-dies-passiert-aber-nicht-ohne-esync)
- [Mein Spiel zeigt gar keinen Text an](#mein-spiel-zeigt-gar-keinen-text-an)
- [Einige Spiele wie Witcher 3 haben fehlende Texturen oder unsichtbare Feinde](#einige-spiele-wie-witcher-3-haben-fehlende-texturen-oder-unsichtbare-feinde)
- [Einige Berichte sagen, dass sie das Spiel mit der Installation von zusätzlicher Software zum laufen gebracht haben, wie kann ich das tun?](#einige-berichte-sagen-dass-sie-das-spiel-mit-der-installation-von-zusätzlicher-software-zum-laufen-gebracht-haben-wie-kann-ich-das-tun)
- [Wie führe ich Windows-Spiele aus, die ich nicht auf Steam besitze?](#wie-führe-ich-windows-spiele-aus-die-ich-nicht-auf-steam-besitze)
- [Spiele, die auf meiner Windows-Partition (NTFS) gespeichert sind, starten nicht!](#spiele-die-auf-meiner-windows-partition-ntfs-gespeichert-sind-starten-nicht)

## Warum läuft mein Spiel so langsam, hat Grafische Fehler oder startet erst gar nicht?

#### Überprüfen sie ihre Grafikkartentreiber ob sie auf den aktuellsten stand sind. Detaillierte Informationen dazu finden Sie in unserem [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

Hinweise:

- Bei den vorgegeben Grafiktreiber Installationen handelt es sich um Stabile Treiber, wenn sie Beta- oder Entwicklungsversionen nutzen möchten tun sie dies auf ihre eigene Faust.

- LLVM 7 oder neuer wird benötigt um die meisten Grafikfehler beim spielen zu vermeiden. Sollte ihre Distro immer noch LLVM 6 verwenden wie zum Beispiel : Solus dann fragen sie die Entwickler ob sie LLVM aktualisieren.

#### Werfen Sie auf jeden Fall einen Blick auf die Website WineHQ von ihren Spiel, um Workarounds zu finden, damit ihr spiel läuft. Wenn die Seite meldet, dass es mit Wine läuft, könnte es sich um ein Proton-spezifisches Problem handeln, oder vielleicht macht ein Drittanbieter-DRM wie zum Beispiel  "Denuvo "  Probleme.

#### Seien sie sich sicher das sie Steam mit den Steam eigenen Laufzeitbibliotheken verwenden.

- Arch: Steam (Runtime)
- Solus: Hier muss im Solus eigenen "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)" die Option "native-runtime" ausgeschaltet werden.



## Mein Spiel stürzt nach einiger Zeit ab. Dies passiert aber nicht ohne Esync!

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

Terminal öffnen und folgenden Befehl eingeben :
```
WINEPREFIX = (Steam-Ordner)/Steamapps/compatdata/(GAME-ID)/pfx/winetricks
```
(GAME-ID) muss durch die Spiel-ID ersetzt werden, zum Beispiel 4000 für Garry ́s Mod, können Sie [SteamDB] (https:/steamdb.info) verwenden, um herauszufinden, welche ID Ihr Spiel hat.

(Steam-Ordner) muss durch den .steam Ordner Location ersetzt werden.

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

## Spiele, die auf meiner Windows-Partition (NTFS) gespeichert sind, starten nicht!

Standardmäßig stellt Linux NFTS-Partitionen nur von Root beschreibbar bereit. [WIP]
