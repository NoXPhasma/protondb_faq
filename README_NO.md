## Språk
-  [Engelsk](#table-of-content)
-  [Tysk](README_DE.md) (Oversatt av [CrackedCrafterz](https://github.com/CrackedCrafterz))
-  [Spanish](README_ESP.md) (Oversatt av [Willdrick](https://github.com/Willdrick))
-  French (Ser fremdeles etter noen som kan oversette.)
-  Italian (Snart)
-  [Norsk](README_NO.md) (Oversatt av [MagZu](https://github.com/magzu))

## Innholdsfortegnelse
  - [Hvorfor krasjer spillet mitt, er treg eller har grafikk problemer?](#hvorfor-krasjer-spillet-mitt-er-treg-eller-har-grafikk-problemer)
  - [Spillet mitt crasher etter en stund men fungerer fint uten esync](#spillet-mitt-crasher-etter-en-stund-men-fungerer-fint-uten-esync)
  - [Spillet viser ingen tekst](#spillet-viser-ingen-tekst)
  - [Noen spill som Witcher 3 mangler fiender eller tekstur](#noen-spill-som-witcher-3-mangler-fiender-eller-tekstur)
  - [Noen rapporter sier de fikk spillet til å kjøre, ved å installere ekstra programvare. Hvordan?](#noen-rapporter-sier-de-fikk-spillet-til-å-kjøre-ved-å-installere-ekstra-programvare-hvordan)
  - [Hvordan kjører jeg Windows spill som ikke er på Steam?](#hvordan-kjører-jeg-windows-spill-som-ikke-er-på-steam)
  - [Spill lagret på min Windows partisjon (NTFS) vill ikke starte](#spill-lagret-på-min-windows-partisjon-ntfs-vill-ikke-starte)
## Hvorfor krasjer spillet mitt, er treg eller har grafikk problemer?

#### Sørg for at maskinen er oppdatert og at du har installert siste grafikk kort driver.

#### Sjekk ut denne nettsiden for spillet ditt [WineHQ](https://appdb.winehq.org), Så kan du finne metoder for å få spillet til å kjøre. Hvis det står på WineHQ at spillet kjører fint i Wine, så kan det hende det er proton eller treddeparts DRM som "Denuvo" som foresaker at spillet ikke kjører.

#### Sørg for at du bruker steam sitt bibliotek (Steam Runtime):

- Arch: Bruk Steam (Runtime)

- Solus: Her må du skru av Solus sin egene "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"

Merk:

- Dette er Stabile drivere, Hvis du vil kjøre nyere drivere som Beta eller Utvikler drivere. Så må du gjøre det på egenhånd.

- LLVM 7 eller nyere er påkrevd for å løse mange grafikk problemer. Hvis din distro fortsatt bruker LLVM 6, som Solus for eksempel så må du si ifra til Distro eierene at de må oppdatere.



##
### Installasjon av Grafikk driver
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
For å se om Vulkan fungerer, kjør følgende kommando: `vulkaninfo`

Her er et [Eksempel](https://raw.githubusercontent.com/NoXPhasma/protondb_faq/master/VulkaninfoExample.png) På hvordan det skal se ut.

Hvis du får: "Cannot create Vulkan instance." Prøv å restart din PC. Hvis du fremdeles får feilmeldingen og du er sikker på at alle pakker er installert. Spør etter hjelp på [Discord](https://discord.gg/uuwK9EV).

## Spillet mitt crasher etter en stund men fungerer fint uten esync

Fleste esync problemer er relatert til en begrensning av hvor mange filer som kan være åpene. Før du rapporterer problemer med esync sørg for at kommando 'ulimit -Hn' viser mer enn 4096. Hvis den ikke gjør dette så må du følge instruksene her: these instructions](https://github.com/zfigura/wine/blob/esync/README.esync) for å skru opp fil begrensningene.

## Spillet viser ingen tekst

Noen spill er avhengig av at Windows fonter er installert. Etter Proton versjon [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) er dette installert automatisk. Hvis du bruker Proton 3.7, prøv å bytt til versjon 3.16-4 eller høyere å se om dette løser problemet.

For å bytte Proton versjon, Gå til Steam instillinger. Der vil du ha et valg som heter Steam Play gå til denne. Huk av på valget "Bruk dette verktøyet i stedet for spillspesifikke valg fra Steam". Velg så Proton versjon fra menyen under, Sørg for å velge versjon 3.16-4 eller høyere.

## Noen spill som Witcher 3 mangler fiender eller tekstur

Dette er løst i DXVK versjon [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) og Vulkan 1.1.88.
Men pr nå krever dette at du har Nvidia Beta drivere (396.54.09) og AMD brukere trenger Mesa versjon 18.3.

## Noen rapporter sier de fikk spillet til å kjøre, ved å installere ekstra programvare. Hvordan?

Det er 2 måter å installere ekstra programvare på i spill prefiksen:

#### Ved bruk av Winetricks
Sørg for at du har winetricks installert på din maskin. Dette burde være i pakkebehandler brønnen til din distro.

Åpne en terminal og skriv:
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) Må byttes ut med iden til spillet.  For eksempel id 4000 for spillet Garry's Mod. Du kan bruke [SteamDB](https://steamdb.info) for å finne ut hvilke id spillet ditt har.

(Steam-folder) Må byttes ut med din .steam mappe lokasjon

Her er et eksempel:

```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```
##
#### Ved bruk av verktøy

The two most popular currently are [Protontricks](https://github.com/Sirmentio/protontricks) and [ProtonFixes](https://github.com/simons-public/protonfixes).

Vær vennlig og les instruksene til verktøyene på deres nettsider.

## Hvordan kjører jeg Windows spill som ikke er på Steam?

For å kjøre spill som ikke er på steam, da kan du bruke [Lutris](https://lutris.net/) for å kjøre de med Wine. Lutris er en spill behandler som tilbyd støtte for mange ulike kompatibilitets lag og emulatorer, Inkludert Wine/proton

## Spill lagret på min Windows partisjon (NTFS) vill ikke starte

Som standard monterer Linux ntfs partisjoner som kun skrivbar av Rot bruker (Root). [WIP]
