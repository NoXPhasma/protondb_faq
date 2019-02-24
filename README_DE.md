![](https://github.com/NoXPhasma/protondb_faq/raw/master/logo.png)

## Sprachen
-  [Englisch](README.md) (Geschrieben von [NoXPhasma](https://github.com/NoXPhasma) & [Alexander](https://github.com/Alexander88207))
-  [Deutsch](#Inhaltsverzeichnis) (Übersetzt von [Alexander](https://github.com/Alexander88207))
-  [Spanisch](README_ESP.md) (Übersetzt von [Willdrick](https://github.com/Willdrick))
-  [Französisch](README_FR.md) (Übersetzt von [Askannz](https://github.com/Askannz))
-  [Italienisch](README_IT.md) (Übersetzt von [Bloodis](https://github.com/bloodis))
-  [Norwegisch](README_NO.md) (Übersetzt von [MagZu](https://github.com/magzu))

## Einführung

Mit dieser FAQ wollen wir die wichtigsten Fragen im Zusammenhang mit der Verwendung von ProtonDB und natürlich technische Fragen, die sehr häufig auf dem Discord gestellt werden, abdecken. Wenn Sie teilnehmen möchten oder Anregungen haben, zögern  Sie nicht uns im [Discord](https://discord.gg/uuwK9EV) zu kontaktieren oder Issues und Pull Requests zu erstellen.

## Inhaltsverzeichnis

- [[[ProtonDB] Die Buttons "Run " und "Install " scheinen nicht auf Firefox zu funktionieren](#protondb-die-buttons-run-und--install-scheinen-im-firefox-nicht-zu-funktionieren)
- [Warum läuft mein Spiel so langsam, hat grafische Fehler oder startet erst gar nicht?](#warum-läuft-mein-spiel-so-langsam-hat-grafische-fehler-oder-startet-erst-gar-nicht)
- [Mein Spiel stürzt nach einiger Zeit ab. Dies passiert aber nicht ohne Esyc!](#mein-spiel-stürzt-nach-einiger-zeit-ab-dies-passiert-aber-nicht-ohne-esync)
- [Mein Spiel zeigt gar keinen Text an](#mein-spiel-zeigt-gar-keinen-text-an)
- [Einige Spiele wie Witcher 3 haben fehlende Texturen oder unsichtbare Feinde](#einige-spiele-wie-witcher-3-haben-fehlende-texturen-oder-unsichtbare-feinde)
- [Warum ruckeln manche spiele schwer am anfang?](#warum-ruckeln-manche-spiele-schwer-am-anfang)
- [Mein Spiel hat Probleme mit den Ton zum Beispiel: fürchterliches Knacken, Knistern etc...](#mein-spiel-hat-probleme-mit-den-ton-zum-beispiel-fürchterliches-knacken-knistern-etc)
- [Wie erstelle ich Protokolle eines Spiels, das ich mit Proton ausführe?](#wie-erstelle-ich-protokolle-eines-spiels-das-ich-mit-proton-ausführe)
- [Einige Berichte sagen, dass sie das Spiel mit der Installation von zusätzlicher Software zum laufen gebracht haben, wie kann ich das tun?](#einige-berichte-sagen-dass-sie-das-spiel-mit-der-installation-von-zusätzlicher-software-zum-laufen-gebracht-haben-wie-kann-ich-das-tun)
- [Wie führe ich Windows-Spiele aus, die ich nicht auf Steam besitze?](#wie-führe-ich-windows-spiele-aus-die-ich-nicht-auf-steam-besitze)
- [Ich habe Probleme mit meinen Controller!](ich-habe-probleme-mit-meinen-controller)
- [Spiele, die auf meiner Windows-Partition (NTFS) gespeichert sind, starten nicht!](#spiele-die-auf-meiner-windows-partition-ntfs-gespeichert-sind-starten-nicht)
- [Punkbuster, Rockstar Social Club etc.... scheitern bei der Erstinstallation.](#punkbuster-rockstar-social-club-etc-scheitern-bei-der-erstinstallation)

## [ProtonDB] Die Buttons "Run" und  "Install" scheinen im Firefox nicht zu funktionieren
Falls Firefox Sie nicht fragt, wie es mit `steam://` URLs umgehen soll, können Sie Firefox dazu zwingen. Dafür öffnen Sie `about:config` im Firefox, rechtsklick in der Liste und im Menü wählen Sie `Neu` » `Bolean`. Als Name für den neuen Eintrag geben Sie `network.protocol-handler.expose.steam` an und als Wert `false`. Nun sollte Firefox beim nächsten Aufruf einer `steam://` URL fragen wie er damit umgehen soll.

## Warum läuft mein Spiel so langsam, hat Grafische Fehler oder startet erst gar nicht?

#### Überprüfen sie ihre Grafikkartentreiber ob sie auf den aktuellsten stand sind. Detaillierte Informationen dazu finden Sie in unserem [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

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

Das ist seit der DXVK-Version [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) und Vulkan 1.1.88 behoben worden. Leider zum Zeitpunkt dieses Schreibens, brauchen Sie die Beta-Treiber für Nvidia (396.54.09) und AMD-Nutzer brauchen mindestens Mesa Version 18.3

## Warum ruckeln manche spiele schwer am anfang?

Das ist ganz normal. Denn zu Beginn müssen die Shader zuerst geladen werden. Damit es das nächste Mal nicht ruckelt, werden die direkt in einen sogenannten Shader-Cache geschrieben und dann in zukunft von dort auch gelesen.

## Mein Spiel hat Probleme mit den Ton zum Beispiel: fürchterliches Knacken, Knistern etc...

In den meisten Fällen ist es ausreichend xaudio2 (xact) zu installieren. Es kann aber auch bei manchen passieren, dass damit ein ton problem gelöst wird, aber dafür ein anderes auftritt. Wie zum Beispiel in Skyrim. Aber es ist immer ein Versuch wert.

Es genügt, "xaudio2_7.dll " auf native, builtin in winecfg zu setzen oder die xact mit winetricks zu installieren.

Weitere Informationen zur Installation zusätzlicher Programme in das game-prefix finden sie [hier](#einige-berichte-sagen-dass-sie-das-spiel-mit-der-installation-von-zusätzlicher-software-zum-laufen-gebracht-haben-wie-kann-ich-das-tun)

## Wie erstelle ich Protokolle eines Spiels, das ich mit Proton ausführe?

Proton erstellt eine Protokolldatei, wenn Sie ihr Spiel mit den folgenden [Startparameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947&l=german) starten:

```
PROTON_LOG=1 %command%
```
Die Protokolldatei wird in Ihrem Home-Ordner mit dem Namensschema ' steam-$STEAMID .log ' erstellt. Zum Beispiel:

```
$HOME/steam-379720.log
```

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

## Ich habe Probleme mit meinen Controller!

Fall #1: Mein Controller wird bei Lego Spielen als Spieler 1 & Spieler 2 erkannt.
- Lösung #1: Öffnen sie die controller einstellungen von wine im gameprefix mit den Befehl `wine control` am ende. Hier ist ein Beispiel  : `WINEPREFIX =/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ wine control` und deaktivieren Sie die Controller "js" & "event ". Dannach starten Sie Ihre Sitzung neu, um sicherzustellen, dass alle Wine prozesse vollständig geschlossen sind und dass die neuen Änderungen geladen werden.

Fall #2: Der Steam-Controller funktioniert auf dem Desktop, wird aber im Spiel nicht erkannt.
- Lösung #2: Dies ist [Alexander](https://github.com/Alexander88207) bisher nur von gentoo selbst und darauf basierenden Distributionen bemerkt worden.

Das Problem kann mit dem Tool "[sc-controller](https://github.com/kozec/sc-controller)" umgangen werden.

## Spiele, die auf meiner Windows-Partition (NTFS) gespeichert sind, starten nicht!

Standardmäßig hängt Linux, NFTS-Partitionen nur von Root beschreibbar ein. Es ist notwendig, diese Partition mit Benutzerrechten einzuhängen. [Hier](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows) finden Sie ein einfaches Tutorial, wie Sie ein NTFS-Laufwerk mit Benutzerrechten einhängen können.

## Punkbuster, Rockstar Social Club etc.... scheitern bei der Erstinstallation.

Es kann vorkommen, dass solche Dinge beim ersten Mal nicht richtig installiert werden und dann versucht Steam nicht mehr, sie zu installieren.

Jedes Spiel hat im Spielordner einen Ordner, die z.b. : "Installer", "Redist" und so weiter..... heißen. Diese enthalten dann das Installationsprogramm für PB,RGSC usw...Und diese müssen dann einfach im jeweiligen Spielpräfix mit wine gestartet werden, hier ein Beispiel:

`WINEPREFIX='/home/alexander/.steam/steam/steamapps/compatdata/271590/pfx' wine '/home/alexander/.steam/steam/steamapps/common/Grand Theft Auto V/Installers/Social-Club-Setup.exe'`

## Mein Spiel speichert nichts oder stürzt beim laden eines Spielstandes ab.

Sie können versuchen das Spiel mit dem folgenden [Startparameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947&l=german) zu starten.

`unset LC_ALL && %command%`

## Mein ganzes System hängt sich am einer gewissen Stelle im Spiel auf.

Dies könnte ein sog. "GPU Hang" sein. Das beduetet das der Treiber der Grafikkarte abgestürzt ist, aber nicht wiederhergestellt werden konnte.

Wenn dies auch in der neuesten Wine version auch der Fall ist, können nur die Entwickler Ihres Grafiktreibers [nvidia](https://nvidia.custhelp.com/app/answers/detail/a_id/44) oder [mesa](https: / /www.mesa3d.org/bugs.html)) ihnen helfen das Problem zu lösen. Selten kann es auch etwas bringen das Problem trotzdem den [dxvk Entwickler](https://github.com/doitsujin/dxvk/issues) zu melden.

