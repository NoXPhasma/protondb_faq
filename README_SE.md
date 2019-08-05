![](https://github.com/NoXPhasma/protondb_faq/raw/master/logo.png)

## Språk
- [Engelska](#table-of-content) (Skriven av [NoXPhasma](https://github.com/NoXPhasma) & [Alexander](https://github.com/Alexander88207))
- [Tyska](README_DE.md) (Översatt av [Alexander](https://github.com/Alexander88207))
- [Spanska](README_ESP.md) (Översatt av [Willdrick](https://github.com/Willdrick))
- [Franska](README_FR.md) (Översatt av [Askannz](https://github.com/Askannz))
- [Italienska](README_IT.md) (Översatt av [Bloodis](https://github.com/bloodis))
- [Norska](README_NO.md) (Översatt av [MagZu](https://github.com/magzu))
- [Lettiska](README_LV.md) (Översatt av [HolimaX](https://github.com/HolimaX))
- [Indonesiska](README_ID.md) (Översatt av [Ari-El-Uno](https://github.com/Ari-El-Uno))
- [Ryska](README_RU.md) (Behövs fortfarande översättas)
- [Svenska](README_SE.md) (Översatt av [Kattus](https://github.com/Kattus))

För att se vem mer som hjälper till, se vår [bidragsgraf](https://github.com/NoXPhasma/protondb_faq/graphs/contributors)!


## Introduktion
Med denna FAQ vill vi täcka de viktigaste frågorna relaterade till användandet av ProtonDB, och såklart tekniska frågor som ofta dyker på Discorden. Om du vill delta eller har frågor, tveka inte att kontakta oss på [Discord](https://discord.gg/uuwK9EV) eller skicka en issue eller pull request.


## Innehållsförteckning
- [[ProtonDB] "Spela" och "Installera" verkar inte fungera i Firefox.](#protondb-spela-och-installera-verkar-inte-fungera-i-firefox)
- [[ProtonDB] På sidan visas mitt spel som ett windowsspel men den har en native portning eller tvärtom.](#protondb-på-sidan-visas-mitt-spel-som-ett-windowsspel-men-den-har-en-native-portning-eller-tvärtom)
- [Varför kraschar mina spel vid start, körs långsamt eller har renderingsproblem?](#varför-kraschar-mina-spel-vid-start-körs-långsamt-eller-har-renderingsproblem)
- [Mitt spel kraschar efter ett tag men fungerar bra utan esync.](#mitt-spel-kraschar-efter-ett-tag-men-fungerar-bra-utan-esync)
- [Spelet visar ingen text.](#spelet-visar-ingen-text)
- [Vissa spel såsom Witcher 3 saknar texturer/fiender.](#vissa-spel-såsom-witcher-3-saknar-texturerfiender)
- [Varför hackar vissa spel i början?](#varför-hackar-vissa-spel-i-början)
- [Jag har ljudproblem såsom sprakande.](#jag-har-ljudproblem-såsom-sprakande)
- [Jag vill spela ett spel utan DXVK.](#jag-vill-spela-ett-spel-utan-dxvk)
- [Hur skapar jag en logg från ett spel jag kör med Proton?](#hur-skapar-jag-en-logg-från-ett-spel-jag-kör-med-proton)
- [Några rapporter säger att de får spelet att fungera genom att installera någon mjukvara, hur gör jag det?](#några-rapporter-säger-att-de-får-spelet-att-fungera-genom-att-installera-någon-mjukvara-hur-gör-jag-det)
- [Hur kör jag Windows-spel jag inte äger på Steam?](#hur-kör-jag-windows-spel-jag-inte-äger-på-steam)
- [Jag har problem med min kontroller!](#jag-har-problem-med-min-kontroller)
- [Spel lagrade på min Windows-partition (NTFS) startar inte.](#spel-lagrade-på-min-windows-partition-ntfs-startar-inte)
- [Punkbuster, Rockstar Social Club osv... misslyckas under förstagångsinstallationen utförs.](#punkbuster-rockstar-social-club-osv-misslyckas-under-förstagångsinstallationen-utförs)
- [Mitt spel sparar ingenting eller kraschar när jag skapar/laddar en sparning.](#mitt-spel-sparar-ingenting-eller-kraschar-när-jag-skaparladdar-en-sparning)
- [Hela min dator hänger sig någon gång under spelet.](#hela-min-dator-hänger-sig-någon-gång-under-spelet)


## [ProtonDB] "Spela" och "Installera" verkar inte fungera i Firefox.
Om Firefox inte frågar dig hur den skall hantera `steam://` URLs, behöver du tvinga Firefox att göra det. För att göra det öppna `about:config` i Firefox, högerklicka var som helst i listan och välj `Ny` » `Boolean`. Skriv in `network.protocol-handler.expose.steam` som namn för den nya posten, och `false` som värde. Nu när du klickar på en `steam://` URL, ska Firefox fråga dig hur du vill fortsätta.


## [ProtonDB] På sidan visas mitt spel som ett windowsspel men den har en native portning eller tvärtom.
ProtonDB erhåller data från SteamDB och dessa i sin tur från utvecklarna av respektive spel. Så om utvecklarna hade en native portning som till exempel Rust och det stängdes så kommer spelet att visas som ett Windows-spel men köpare av den nativa portningen kommer såklart att behålla den nativa portningen så det kommer att finnas några användare som skriver: "det har en native portning!".


## Varför kraschar mina spel vid start, körs långsamt eller har renderingsproblem?
**Var säker på att ditt system är uppdaterat och att du använder de senaste drivrutinerna till ditt grafikkort. Du kan hitta detaljerad information om hur du uppdaterar dina grafikdrivrutiner på vår [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)**

**Ta en titt på sidan för ditt spel på [WineHQ](https://appdb.winehq.org), du kan möjligtvis hitta lösningar för att få det att fungera. Om sidan rapporterar att det funkar med Wine kan det vara ett Proton-specifikt problem eller en tredjeparts-DRM såsom "Dunuvo" som ställer till det.**


**Var säker på att du kör Steam med Steam Runtime bibliotek:**

- Arch: Använd `Steam (Runtime)`

- Solus: Stäng av native-runtime i deras "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"


## Mitt spel kraschar efter ett tag men fungerar bra utan esync.
De flesta problem med esync är relaterade till de begränsade antalet öppnade filer. Innan du rapporterar problem med esync, kolla om kommandot `ulimit -Hn` rapporterar mycket mer än 4096. Om inte kan du följa [dessa instruktioner](https://github.com/zfigura/wine/blob/esync/README.esync) för att höja gränsen.


## Spelet visar ingen text.
Vissa spel behöver Windows-typsnitt installerade. Sedan Proton version [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) görs detta automatiskt åt dig. Om du använder Proton 3.7, se om ett byte till version 3.16-4 eller högre löser problemet.

För att byta Protonversion, gå till Steaminställningarna och sedan till fliken Steam Play. Du behöver aktivera alternativet "Aktivera Steam Play för alla andra produkter". Sedan kan du välja Protonversionen i menyn.


## Vissa spel såsom Witcher 3 saknar texturer/fiender.
Detta är fixat sedan DXVK version [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) och Vulkan 1.1.88. Nvidia-användare behöver minst drivrutinsversion 415.22, och AMD-användare behöver minst Mesa version 18.3.


## Varför hackar vissa spel i början?
Detta är helt normalt. I början måste shaderna laddas först så att det inte hackar nästa gång. De skrivs direkt in i ett så kallat shader cache.

Notera att dxvk cache inte är relaterat till "Shader Pre-Caching" från Steam.


## Jag har ljudproblem såsom sprakande.
I de flesta fall hjälper det att installera xaudio2 (xact), men i fall som Skyrim till exempel, kan det lösa problem för vissa men skapa nya ljudproblem, men det är värt ett försök.

Sedan Protonversion [3.16-5](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-5) behöver du inte göra någonting. Om du använder en äldre version av Protonkan du läsa här:

det räcker med att sätta "xaudio2_7.dll" till native, built-in i winecfg eller installera xact med winetricks.

[Här](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that) kan du hitta mer information om du kan installera fler program i din gameprefix.


## Jag vill spela ett spel utan DXVK.
Om du verkligen vill pröva att spela ditt spel utan DXVK, pröva starta spelet med följande [startalternativ](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947)

```
PROTON_USE_WINED3D11=1 %command%
```
Notera: Du kommer möjligtvis få grafiska fel eller dålig prestanda beroende på spelet.

Om spelet inte startar eller kraschar så kanske ditt spel inte kan köras med wine3d11


## Hur skapar jag en logg från ett spel jag kör med Proton?
Proton kommer att skapa en loggfil för ett specifikt spel om du [sätter startalternativna](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947) till:

```
PROTON_LOG=1 %command%
```
Loggfilen kommer att skapas i din hem-mapp med namnschemat `steam-$STEAMID.log`. Till exempel:
```
$HOME/steam-379720.log
```

## Några rapporter säger att de får spelet att fungera genom att installera någon mjukvara, hur gör jag det?
Det finns två sätt att installera yttligare mjukvara i gameprefixen:

#### Använd Winetricks
Var säker på att du har winetricks installerat på ditt system. Detta paket bör finnas i din distrubtions repository.

Öppna en terminal och använd
```
WINEPREFIX=(Steam-mapp)/steamapps/compatdata/(SPEL-ID)/pfx/ winetricks
```
(SPEL-ID) måste bytas ut mot spelets ID, till exempel 4000 för Garry's Mod. Du kan använda [SteamDB](https://steamdb.info) för att se vad för ID ditt spel har.

(Steam-mapp) måste bytas ut med din .steam mapps plats.

Här är ett exempel
```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```

#### Använd verktyg
De två mest populära just nu är [Protontricks](https://github.com/Sirmentio/protontricks) och [ProtonFixes](https://github.com/simons-public/protonfixes).

Var vänlig läs instruktionerna om dessa verktyg på deras respektive sidor.


## Hur kör jag Windows-spel jag inte äger på Steam?
Lägg till ett Icke-Steam-spel till ditt bibliotek (sätt Filtyp till "Alla Filer") och välj .exe'n

Högerklicka på spelet i ditt bibliotek och i Egenskaper - Aktivera "Tvinga användandet av ett specifikt Steam Play-kompatibilitetsverktyg"

Om det finns några mellanslag i din sökväg till .exe'n behöver du fixa "Mål:"'ets sökväg i spelets Egenskaper och ta rensa "Ange Startalternativ"

Men, vi rekommdenrar [Lutris](https://lutris.net) för att köra de flesta icke-steam-spelen genom Wine. Lutris är en spelhanterare som erbjuder stöd för många olika kompatibilitetslager/emulatorer, inkluderande Wine/Proton.


## Jag har problem med min kontroller!
Fall #1: Min kontroller upptäcks som spelare 1 & spelare 2 i legospel.

- Lösning #1: Öppna kontrollerinställningarna från gameprefixet med kommandot exempelvis: `WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ wine control` och avaktivera kontrollerns "js" & "event" och starta sedan om sessionen för att kontrollera att wine är helt stängt för att vara säker på att de nya ändringarna laddas.

Fall #2: Min Steam Controller upptäcks inte ens med native spel, bara musfunktionen.

- Lösning #2: Detta händer på distrubtioner baserade på Gentoo eller Gentoo själv. Upptäckt av [@Alexander](https://github.com/Alexander88207)

Om du spelar på Linux genom Steam och har en Steam Controller kan du ha upptäckt något intressant. Steam Controller'n ser ut att fungera, men fungerar inte i spel eller under wine control.

Vi rekommenderar att använda verktyget [sc-controller)](https://github.com/kozec/sc-controller) för att jobba runt problemet.


## Spel lagrade på min Windows-partition (NTFS) startar inte.
Som standard monterar Linux NTFS-partitioner endast skrivbara av root. Det är nödvändigt att montera partitionen med användar-rättigheter. Du kan hitta en enkel guide om hur du kan montera en NTFS-enhet med användar-rättigheter på [Proton Wiki'n](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows).


## Punkbuster, Rockstar Social Club osv... misslyckas under förstagångsinstallationen utförs.
Det kan hända att sådana saker inte är installerade korrekt den [första gången](https://github.com/NoXPhasma/protondb_faq/raw/master/Initial%20installation%20example.png) och att Steam inte försöker installera dem igen.

Varje spel har en mapp i spelets mapp vilket exempelvis är kallade som så: "Installers", "Redist" och så vidare... Dessa mappar innehåller installationsprogrammen för PB eller RGSC, dessa måste startar i den motsvaramde spelprefixen med wine, här är ett exempel:

`WINEPREFIX='/home/alexander/.steam/steam/steamapps/compatdata/271590/pfx' wine '/home/alexander/.steam/steam/steamapps/common/Grand Theft Auto V/Installers/Social-Club-Setup.exe'`


## Mitt spel sparar ingenting eller kraschar när jag skapar/laddar en sparning.
Du kan pröva att starta spelet med detta [startalternativ](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947): `unset LC_ALL && %command%`


## Hela min dator hänger sig någon gång under spelet.
Detta kan vara en GPU-hängning men för att vara säker på att det inte är Proton's fel pröva spelet med den senaste Wine-versionen först.

Om detta även händer med den senaste Wine-versionen, kan endast programmerarna av din grafikdrivrutin ([nvidia](https://nvidia.custhelp.com/app/answers/detail/a_id/44) eller [mesa](https://www.mesa3d.org/bugs.html)) eller sällan [dxvk](https://github.com/doitsujin/dxvk/issues) hjälpa dig.