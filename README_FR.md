![](https://github.com/NoXPhasma/protondb_faq/raw/master/logo.png)

## Languages
-  [English](#table-of-content) (Écrit par by [NoXPhasma](https://github.com/NoXPhasma) & [Alexander](https://github.com/Alexander88207))
-  [German](README_DE.md) (Traduit par [Alexander](https://github.com/Alexander88207))
-  [Spanish](README_ESP.md) (Traduit par [Willdrick](https://github.com/Willdrick))
-  [French](README_FR.md) (Traduit par [Askannz](https://github.com/Askannz))
-  [Italian](README_IT.md) (Traduit par [Bloodis](https://github.com/bloodis))
-  [Norwegian](README_NO.md) (Traduit par [MagZu](https://github.com/magzu))

Vous pouvez voir qui d'autre a participé sur notre [pqge des contributeurs](https://github.com/NoXPhasma/protondb_faq/graphs/contributors) !

## Sommaire

  - [[ProtonDB] Les boutons "Run" et "Install" ne fonctionnent pas sur Firefox.](#protondb-les-boutons-run-et-install-ne-fonctionnent-pas-sur-firefox)
  - [[ProtonDB] Le site affiche me dit qu'un jeu est un jeu Windows alors qu'il possède une version Linux, ou vice-versa.](#protondb-at-the-site-my-game-is-displayed-as-a-windows-game-but-it-have-a-native-port-or-the-other-way-round)
  - [Pourquoi est-ce que mes jeux échouent à se lancer, ont des problèmes de performance ou des bugs d'affichage ?](#pourquoi-est-ce-que-mes-jeux-échouent-à-se-lancer-ont-des-problèmes-de-performance-ou-des-bugs-daffichage-)
  - [Mon jeu quitte subitement après un certain temps, mais fonctionne si esync est désactivé](#mon-jeu-quitte-subitement-après-un-certain-temps-mais-fonctionne-si-esync-est-désactivé)
  - [Les textes dans mon jeu ne s'affichent pas](#les-textes-dans-mon-jeu-ne-saffichent-pas)
  - [Il manque des textures/ennemis dans certains jeux (notamment The Witcher 3)](#il-manque-des-texturesennemis-dans-certains-jeux-notamment-the-witcher-3)
  - [Pourquoi est-ce que certains jeux "rament" quand j'y joue pour la première fois ?](#Why-do-some-games-stutter-at-the-beginning)
  - [J'ai des problèmes de son (craquements par exemple)](#i-have-sound-problems-like-crackle-for-example)
  - [Je veux lancer mes jeux sans DXVK.](#i-want-to-play-a-game-without-dxvk)
  - [Comment puis-je récupérer le journal d'erreur d'un jeu lancé avec Proton ?](#how-do-i-create-logs-of-a-game-i-run-with-proton)
  - [Certains reports mentionnent avoir fait fonctionner le jeu en installant un composant additionnel. Comment puis-je faire cela ?](#certains-reports-mentionnent-avoir-fait-fonctionner-le-jeu-en-installant-un-composant-additionnel-comment-puis-je-faire-cela-)
  - [Comment puis-je jouer à des jeux Windows que je ne possède pas sur Steam ?](#comment-puis-je-jouer-à-des-jeux-windows-que-je-ne-possède-pas-sur-steam-)
  - [Mon contrôleur de jeu ne fonctionne pas correctement](#i-have-issues-with-my-controller)
  - [Les jeux stockés sur ma partition Windows (NTFS) ne se lancent pas.](#les-jeux-stockés-sur-ma-partition-windows-ntfs-ne-se-lancent-pas)
  - [Punkbuster, Rockstar Social Club etc... échouent à s'installer.](#punkbuster-rockstar-social-club-etc-fail-during-initial-installation)
  - [Les sauvegardes de mon jeu ne fonctionne pas, ou bien le jeu plante lorsque je crée ou charge une sauvegarde.](#my-game-wont-save-anything-or-crash-while-creatingloading-a-save)
  - [Parfois, mon ordinateur se fige totalement lorsque je joue.](#my-entire-computer-hangs-up-at-some-point-in-the-game)

## [ProtonDB] Les boutons "Run" et "Install" ne fonctionnent pas sur Firefox.
Si Firefox ne vous a pas demandé comment gérer les URLs de type `steam://` URLS, vous devez le lui spécifier manuellement. Pour cela, ouvrez la page `about:config`, faites un clic droit n'importe où dans la liste et sélectionnez `New (Nouveau)` » `Boolean (Booléen)`. Entrez le nom `network.protocol-handler.expose.steam` et la valeur `false`. À présent, si vous cliquez sur une URL de type `steam://`, Firefox vous demandera l'action à effectuer.

## [ProtonDB] Le site affiche me dit qu'un jeu est un jeu Windows alors qu'il possède une version Linux, ou vice-versa.

ProtonDB obtient ces informations depuis le site SteamDB, qui lui-même ne fait que relayer les affirmations des développeurs. Donc si, par exemple, un jeu avait dans le passé une version native qui a été abandonnée (c'est le cas de Rust), le jeu apparaîtra comme un jeu Windows même si certains utilisateurs possèdent toujours la version native.

## Pourquoi est-ce que mes jeux échouent à se lancer, ont des problèmes de performance ou des bugs d'affichage ?

#### Vérifiez que votre système est à jour et que vous utilisez les derniers pilotes disponibles pour votre carte graphique. Vous trouverez des instructions détaillées dans notre [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

#### Consultez la page correspondant à votre jeu sur [WineHQ](https://appdb.winehq.org), vous y trouverez peut-être des instructions pour le faire fonctionner. Si WineHQ confirme que le jeu fonctionne with Wine, alors il est possible que le problème soit spécifique à Proton, ou causé par un système de DRM comme "Denuvo".

#### Vérifiez que vous lancez Steam en utilisant les bibliothèques du Steam Runtime:

- Arch: Utilisez `Steam (Runtime)`

- Solus: Désactivez native-runtime dans le "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"


## Mon jeu quitte subitement après un certain temps, mais fonctionne si esync est désactivé

La plupart des problèmes avec esync sont liés à la limite imposée par le système sur le nombre de fichiers ouverts. Avant de signaler un bug avec esync, vérifiez si la commande `ulimit -Hn` affiche un nombre très supérieur à 4096. Si ce n'est pas le cas, vous pouvez suivre [ces instructions](https://github.com/zfigura/wine/blob/esync/README.esync) pour augmenter la limite.

## Les textes dans mon jeu ne s'affichent pas

Certains jeux ont besoin que les polices de caractère de Windows soient installées. Depuis la version [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) de Proton, cela est fait pour vous automatiquement. Si vous utilisez encore Proton 3.7, essayez de passer à 3.16-4 ou une version supérieure.

Pour changer de version de Proton, allez dans les options de Steam puis dans l'onglet Steam Play. Vous devez activer l'option "Utilisez cet outil au lieu des sélections spécifiques au jeu de Steam". Choisissez ensuite la version de Proton que vous souhaitez dans le menu déroulant.

## Il manque des textures/ennemis dans certains jeux (notamment The Witcher 3)

Ce problème est résolu depuis la version [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) de DXVK et la version 1.1.88 de Vulkan. Malheureusement, à l'heure où ces lignes sont écrites, il vous faudra aussi les pilotes bêta de Nvidia (396.54.09), ou la version 18.3 (ou supérieure) de Mesa pour AMD.

## Pourquoi est-ce que certains jeux "rament" quand j'y joue pour la première fois ?

C'est tout à fait normal. Steam doit charger les shaders du jeu quand vous commencer à jouer. Ils sont ensuite sauvegardés dans un cache sur votre disque afin que le jeu ne rame plus à l'avenir.

À noter que ce mécanisme de "Shader Pre-Caching" n'a rien à voir avec le cache créé par DXVK.

## J'ai des problèmes de son (craquements par exemple)

Depuis Proton [3.16-5](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-5), ce problème est globalement résolu. Si vous utilisez une version de Proton plus ancienne, essayez de changer de version.

Sinon, vous pouvez aussi forcer "xaudio2_7.dll" en "native", ou utilliser le verbe winetricks "xact". Vous trouverez plus d'information sur ce type d'actions [ici](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that).

## Je veux lancer mes jeux sans DXVK.

Si vous voulez *vraiment* désactiver DXVK, [lancer votre jeu avec le paramètre suivant](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947) dans Steam :

```
PROTON_USE_WINED3D11=1 %command%
```
Notez que cela peut causer une réduction des performances ou des bugs graphiques. Certains jeux ne fonctionneront pas du tout avec WineD3D11.

## Comment puis-je récupérer le journal d'erreur d'un jeu lancé avec Proton ?

Proton créera le journal d'erreur d'un jeu si vous [spécifiez le paramètre](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947)
```
PROTON_LOG=1 %command%
```
The journal sera créé dans votre dossier personnel sous le nom `steam-$STEAMID.log`. Par exemple :
```
$HOME/steam-379720.log
```


## Certains reports mentionnent avoir fait fonctionner le jeu en installant un composant additionnel. Comment puis-je faire cela ?

Il y a deux façons d'installer un composant additionnel dans le préfixe d'un jeu:

#### En utilisant Winetricks
Vérifiez que `winetricks` est installé sur votre système. Ce paquet peut normalement être trouvé dans les dépôts de votre distribution.

Ouvrez un Terminal et exécutez
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) doit être remplacé par l'ID Steam du jeu. Par exemple, 4000 pour Garry´s Mod. Vous pouvez utiliser [SteamDB](https://steamdb.info) pour trouver l'ID de votre jeu.

(Steam-folder) doit être remplacé par l'emplacement de votre dossier `.steam`.

Exemple :

```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```

#### En utilisant des outils additionnels

Les deux outils les plus utilisés à l'heure actuelle sont [Protontricks](https://github.com/Sirmentio/protontricks) et [ProtonFixes](https://github.com/simons-public/protonfixes).

Vous pouvez trouver les instructions d'utilisation de ces outils sur leurs sites respectifs.

## Comment puis-je jouer à des jeux Windows que je ne possède pas sur Steam ?

Pour jouer à des jeux qui ne sont pas sur Steam, plutôt que d'utiliser Steam Play, nous recommendons l'utilisation de [Lutris](https://lutris.net/). Lutris est un gestionnaire de jeux intégrant de 

Si vous souhaitez tout de même utiliser Steam Play, suivez ces instructions :

Cliquez sur "Ajouter un jeu", "Ajouter un jeu non-Steam", "Parcourir", réglez sur "All files" dans le menu déroulant, et sélectionnez l'exécutable (.exe) de votre jeu.

Ensuite, clic droit sur votre jeu dans votre Bibliothèque, "Propriétés", cochez "Forcer l'utilisation d'un outil de compatibilité Steam Play en particulier".

Si il y a le moinde espace dans le chemin menant à l'exécutable du jeu, vous devrez aussi corriger le champ "Cible" dans cette fenêtre. Supprimez aussi tout ce qui se trouve dans "Définir les options de lancement".

## Mon contrôleur de jeu ne fonctionne pas correctement

Cas #1: Mon controlleur est reconnu en tant que "Joueur 1" et "Joueur 2" dans les jeux Lego.

Solution: Ouvrez la fenêtre des paramètres de contrôleur en étant dans le préfixe de votre jeu. Par exemple, `WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ wine control`. Dans cette fenêtre, désactivez le contrôleur "js" & "event", puis redémarrez votre session afin d'être sûr que le changement a été pris en compte.

Cas #2: Mon Steam-Controller n'est pas reconnu, même dans les jeux natifs. Seul le contrôle de la souris fonctionne.

(Note : ce bug semble n'affecter que Gentoo et ses distributions dérivées)

Solution : Utiliser [sc-controller)](https://github.com/kozec/sc-controller).

## Les jeux stockés sur ma partition Windows (NTFS) ne se lancent pas.

Par défaut, Linux monte les partitions NTFS en lecture seule (sauf pour l'utilisateur Root). Pour résoudre ce problème, vous devez monter votre partition avec des droits d'écriture pour votre compte utilisateur. Vous trouverez un tutorial basique à ce sujet sur le [Wiki Proton](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows).

## Punkbuster, Rockstar Social Club etc... échouent à s'installer.

Il arrive que ce genre de client ne s'installe pas correctement [la première fois](https://github.com/NoXPhasma/protondb_faq/raw/master/Initial%20installation%20example.png), et que Steam n'essaie pas de les installer à nouveau.

Solution : lancer l'installation manuellement depuis le dossier principal du jeu. Ce dossier contient généralement un sous-dossier nommé par exemple "Installers" ou "Redist", qui contient l'exécutable de Punkbuster, Social Club, etc. Vous devez lancer cet exécutable dans le préfixe Wine correspondant au jeu.

Par exemple :

`WINEPREFIX='/home/alexander/.steam/steam/steamapps/compatdata/271590/pfx' wine '/home/alexander/.steam/steam/steamapps/common/Grand Theft Auto V/Installers/Social-Club-Setup.exe'`

## Les sauvegardes de mon jeu ne fonctionne pas, ou bien le jeu plante lorsque je crée ou charge une sauvegarde.

Essayez de lancer le jeu avec [ce paramètre](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947): `unset LC_ALL && %command%`

## Parfois, mon ordinateur se fige totalement lorsque je joue.

Cela peut petre dû à un problème de carte graphique, mais pour être sûr que Proton n'est pas en cause, essayez lancer le jeu en utilisant la dernière version de Wine.

Si le problème survient toujours, dans ce cas vous devrez chercher une solution spéficique à votre pilote graphique : [nvidia](https://nvidia.custhelp.com/app/answers/detail/a_id/44) ou [Mesa](https://www.mesa3d.org/bugs.html). Le [bug tracker de DXVK](https://github.com/doitsujin/dxvk/issues) contient parfois des pistes.
