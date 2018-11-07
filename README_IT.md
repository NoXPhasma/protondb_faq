## Lingue
-  [Inglese](README.md) (Scritto da [NoXPhasma](https://github.com/NoXPhasma))
-  [Tedesco](README_DE.md) (Tradotto da [CrackedCrafterz](https://github.com/CrackedCrafterz))
-  [Spagnolo](README_ESP.md) (Tradotto da [Willdrick](https://github.com/Willdrick))
-  Francese (Ancora alla ricerca di qualcuno in grado di tradurlo)
-  [Italiano](README_IT.md) (Tradotto da [bloodis](https://github.com/bloodis))
-  [Norvegese](README_NO.md) (Tradotto da [MagZu](https://github.com/magzu))

## Tabella dei contenuti
  - [Perchè i miei giochi si bloccano all'avvio, sono molto lenti o hanno problemi di rendering?](#perche-i-miei-giochi-si-bloccano-all-avvio-sono-molto-lenti-o-hanno-problemi-di-rendering)
  - [I miei giochi si bloccano dopo un'pò, ma funzionano bene con l'esync disattivato](#i-miei-giochi-si-bloccano-dopo-un-po-ma-funzionano-bene-con-lesync-disattivato)
  - [In gioco non viene mostrato nessun testo](#in-gioco-non-viene-mostrato-nessun-testo)
  - [In alcuni giochi, come The Witcher 3, sono presenti texture/modelli/nemici mancanti](#in-alcuni-giochi-come-The-Witcher-3-sono-presenti-texturemodellinemici-mancanti)
  - [Alcuni report dicono di essere riusciti ad avviare il gioco installando qualche software,come si fà?](#alcuni-report-dicono-di-essere-riusciti-ad-avviare-il-gioco-installando-qualche-software-come-si-fa)
  - [Come eseguo giochi Windows che non possiedo su steam?](#come-eseguo-giochi-Windows-che-non-possiedo-su-steam)
  - [I giochi memorizzati sulla mia partizione Windows (NTFS) non si avviano](#i-giochi-memorizzati-sulla-mia-partizione-windows-ntfs-non-si-avviano)
## Perchè i miei giochi si bloccano all'avvio, sono molto lenti o hanno proglemi di rendering?

#### Assicurati che il tuo sistema sia aggiornato e che vi siano installati i drivers più recenti per la tua scheda grafica.

#### Dai uno sguardo alla pagina dedicata al tuo gioco su [WineHQ](https://appdb.winehq.org), potresti trovarci dei workarounds per farlo funzionare. Se la pagina riporta che il gioco funziona bene su Wine potrebbe essere un problema specifico di Proton, oppure dei DRM di terze parti come "Denuvo" potrebbero star creando dei problemi.

#### Assicurati di eseguire Steam con le librerie Steam Runtime:

- Arch: Usa Steam (Runtime)

- Solus: Disattiva native-runtime nel tool: "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"

Note:

- Questi sono i drivers stabili, se desideri i drivers Beta/Devel devi cercarli da solo!

- È necessario LLVM 7 o le versioni più recenti per risolvere la maggior parte dei problemi grafici e/o di rendering. Se la tua distribuzione usa ancora LLVM 6 come, ad esempio, Solus allora chiedi che venga aggiornata!



##
### Installazione drivers grafici
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
Per controllare che vulkan funzioni usa il comando: `vulkaninfo`

Questo è un'[Esempio](https://raw.githubusercontent.com/NoXPhasma/protondb_faq/master/VulkaninfoExample.png) di cosa dovresti vedere.

Se ottieni: ```Cannot create Vulkan instance```. Prova a riavviare il tuo PC. Se l'errore si presenta ancora, e tu sei veramente sicuro di aver installato tutti i packages, chiedi pure aiuto nel nostro [Discord](https://discord.gg/uuwK9EV) per ricevere supporto.

## I miei giochi si bloccano dopo un'pò, ma funzionano bene con l'esync disattivato

La maggior parte dei problemi con esync sono relativi al limite di files aperti contemporaneamente. Prima di segnalare un problema con esync, Controlla se il comando `ulimit -Hn` restituisce un valore molto più alto di 4096. Se non è così puoi seguire [queste istruzioni](https://github.com/zfigura/wine/blob/esync/README.esync) per alzare il limite.

## In gioco non viene mostrato nessun testo

Alcuni giochi hanno bisogno che i fonts Windows siano installati. Dalla versione [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) di Proton questo viene fatto per te in automatico. Se stai usando la versione 3.7 di Proton, prova a spostarti sulla versione 3.16-4 o successive e controlla se il tuo problema viene risolto.

Per cambiare la versione di Proton, vai nelle impostazioni di Steam, dovrebbe essere presente una tab chiamata Steam Play. Al suo interno devi attivare l'opzione "Usa questo strumento invece delle selezioni specifiche per i giochi di Steam". A quel punto potrai scegliere la versione di Proton dal menù a tendina.

## In alcuni giochi, come The Witcher 3, sono presenti texture/modelli/nemici mancanti

Questo problema è stato risolto dalla versione [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) di DXVK e dalla versione 1.1.88 di Vulkan. Sfortunatamente, al momento di questa stesura, È necessario utilizzare i drivers beta per le schede Nvidia (396.54.09) mentre gli utenti AMD hanno bisogno almeno della versione 18.3 dei drivers Mesa.

## Alcuni report dicono di essere riusciti ad avviare il gioco installando qualche software,come si fà?

Ci sono due modi di installare software addizionali nel prefisso dei giochi:

#### Utilizzo di Winetricks
Assicurati di avere winetricks installato nel tuo sistema. Questo package dovrebbe trovarsi nella repository della tua distribuzione.

Apri un terminale e lancia
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) deve essere rimpiazzato con l'ID del gioco,ad esempio 4000 per Garry´s Mod, puoi usare [SteamDB](https://steamdb.info) per trovare quello del tuo gioco.

(Steam-folder) deve essere rimpiazzato con il percorso in cui si trova la cartella .steam.

Ecco un'esempio
```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```
##
#### Utilizzo dei Tools

Attualmente i due tools più popolari sono [Protontricks](https://github.com/Sirmentio/protontricks) e [ProtonFixes](https://github.com/simons-public/protonfixes).

Per favore leggi la documentazione relativa a questi due tools sui loro rispettivi siti.

## Come eseguo giochi Windows che non possiedo su steam?

Per eseguire giochi che non sono su Steam puoi usare [Lutris](https://lutris.net/) per eseguirli con Wine. Lutris è un game manager che offre supporto per molti differenti compatibility layers/emulatori, incluso Wine/Proton.

## I giochi memorizzati sulla mia partizione Windows (NTFS) non si avviano

Per impostazione predefinita le partizioni NTFS vengono montate come scrivibili solo da Root. [WIP]
