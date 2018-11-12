## Lingue
-  [Inglese](README.md) (Scritto da [NoXPhasma](https://github.com/NoXPhasma))
-  [Tedesco](README_DE.md) (Tradotto da [CrackedCrafterz](https://github.com/CrackedCrafterz))
-  [Spagnolo](README_ESP.md) (Tradotto da [Willdrick](https://github.com/Willdrick))
-  [Francese](README_FR.md) (Tradotto da [Askannz](https://github.com/Askannz))
-  [Italiano](#tabella-dei-contenuti) (Tradotto da [bloodis](https://github.com/bloodis))
-  [Norvegese](README_NO.md) (Tradotto da [MagZu](https://github.com/magzu))

## Introduzione
Con queste FAQ vogliamo coprire le domande più importanti relative all'uso di ProtonDB e, ovviamente, le domande tecniche più ricorrenti sul canale Discord. Se vuoi partecipare, o hai dei suggerimenti, non esitare a contattarci su [Discord](https://discord.gg/uuwK9EV), oppure invia delle segnalazioni e delle richieste di pull su questa repository github.

## Tabella dei contenuti
  - [(ProtonDB) I bottoni "Run" e "Install" non sembrano funzionare su Firefox.](#protondb-i-bottoni-run-e-install-non-sembrano-funzionare-su-firefox)
  - [Perchè i miei giochi si bloccano all'avvio, sono molto lenti o hanno problemi di rendering?](#perchè-i-miei-giochi-si-bloccano-allavvio-sono-molto-lenti-o-hanno-problemi-di-rendering)
  - [I miei giochi si bloccano dopo un'pò, ma funzionano bene con l'esync disattivato](#i-miei-giochi-si-bloccano-dopo-unpò-ma-funzionano-bene-con-lesync-disattivato)
  - [In gioco non viene mostrato nessun testo](#in-gioco-non-viene-mostrato-nessun-testo)
  - [In alcuni giochi, come The Witcher 3, sono presenti texture/modelli/nemici mancanti](#in-alcuni-giochi-come-The-Witcher-3-sono-presenti-texturemodellinemici-mancanti)
  - [Come creo i logs di un gioco che viene avviato con Proton?](#come-creo-i-logs-di-un-gioco-che-viene-avviato-con-proton)
  - [Alcuni reporter dicono di essere riusciti ad avviare il gioco installando un software,come posso farlo anche io?](#alcuni-reporter-dicono-di-essere-riusciti-ad-avviare-il-gioco-installando-un-softwarecome-posso-farlo-anche-io)
  - [Come eseguo giochi Windows che non possiedo su steam?](#come-eseguo-giochi-Windows-che-non-possiedo-su-steam)
  - [I giochi memorizzati sulla mia partizione Windows (NTFS) non si avviano](#i-giochi-memorizzati-sulla-mia-partizione-windows-ntfs-non-si-avviano)

## (ProtonDB) I bottoni "Run" e "Install" non sembrano funzionare su Firefox.
  Se Firefox non ti chiede come gestire gli URL `steam://` , devi forzarlo a farlo. per farlo, apri `about:config` scrivendolo come indirizzo nella barra degli indirizzi, premi il tasto destro del mouse in un punto qualsiasi della lista e seleziona `Nuovo` » `Booleano`. Come nome del nuovo elemento inserisci `network.protocol-handler.expose.steam` e, come valore, `false`. Ora se cliccherai su un qualsiasi URL `steam://` Firefox dovrebbe chiederti come procedere.

## Perchè i miei giochi si bloccano all'avvio, sono molto lenti o hanno problemi di rendering?

#### Assicurati che il tuo sistema sia aggiornato e che vi siano installati i drivers più recenti per la tua scheda grafica. Troverai informazioni più dettagliate su come aggiornare i drivers nella nostra [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation).

Note:
- È necessario LLVM 7 o le versioni più recenti per risolvere la maggior parte dei problemi grafici e/o di rendering. Se la tua [distribuzione](https://repology.org/metapackage/llvm/versions) usa ancora LLVM 6 allora chiedi che venga aggiornata!

#### Dai uno sguardo alla pagina dedicata al tuo gioco su [WineHQ](https://appdb.winehq.org), potresti trovarci dei workarounds per farlo funzionare. Se la pagina riporta che il gioco funziona bene su Wine potrebbe essere un problema specifico di Proton, oppure dei DRM di terze parti come "Denuvo" potrebbero star creando dei problemi.

#### Assicurati di eseguire Steam con le librerie Steam Runtime:

- Arch: Usa Steam (Runtime)

- Solus: Disattiva native-runtime nel tool: "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"


## I miei giochi si bloccano dopo un'pò, ma funzionano bene con l'esync disattivato

La maggior parte dei problemi con esync sono relativi al limite di files aperti contemporaneamente. Prima di segnalare un problema con esync, Controlla se il comando `ulimit -Hn` restituisce un valore molto più alto di 4096. Se non è così puoi seguire [queste istruzioni](https://github.com/zfigura/wine/blob/esync/README.esync) per alzare il limite.

## In gioco non viene mostrato nessun testo

Alcuni giochi hanno bisogno che i fonts Windows siano installati. Dalla versione [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) di Proton questo viene fatto per te in automatico. Se stai usando la versione 3.7 di Proton, prova a spostarti sulla versione 3.16-4 o successive e controlla se il tuo problema viene risolto.

Per cambiare la versione di Proton, vai nelle impostazioni di Steam, dovrebbe essere presente una tab chiamata Steam Play. Al suo interno devi attivare l'opzione "Usa questo strumento invece delle selezioni specifiche per i giochi di Steam". A quel punto potrai scegliere la versione di Proton dal menù a tendina.

## In alcuni giochi, come The Witcher 3, sono presenti texture/modelli/nemici mancanti

Questo problema è stato risolto dalla versione [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) di DXVK e dalla versione 1.1.88 di Vulkan. Sfortunatamente, al momento di questa stesura, È necessario utilizzare i drivers beta per le schede Nvidia (396.54.09) mentre gli utenti AMD hanno bisogno almeno della versione 18.3 dei drivers Mesa.

## Come creo i logs di un gioco che viene avviato con Proton?

Per far creare automaticamente un log a Proton devi [impostare i parametri di avvio](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947) con:
```
PROTON_LOG=1 %command%
```
Il log verrà creato nella cartella home seguendo lo schema del nome `steam-$STEAMID.log`. Per esempio:
```
$HOME/steam-379720.log
```

## Alcuni reporter dicono di essere riusciti ad avviare il gioco installando un software,come posso farlo anche io?

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
