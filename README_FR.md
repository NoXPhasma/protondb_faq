## Languages
-  [Anglais](README.md)
-  [Allemand](README_DE.md) (Traduit par [CrackedCrafterz](https://github.com/CrackedCrafterz))
-  [Espagnol](README_ESP.md) (Traduit par [Willdrick](https://github.com/Willdrick))
-  [Français](#sommaire) (Traduit par [Askannz](https://github.com/Askannz))
-  [Italien](README_IT.md) (Traduit par [Bloodis](https://github.com/bloodis))
-  [Norvégien](README_NO.md) (Traduit par [MagZu](https://github.com/magzu))

## Sommaire
 - [[ProtonDB] Les boutons "Run" et "Install" ne fonctionnent pas sur Firefox.](#protondb-les-boutons-run-et-install-ne-fonctionnent-pas-sur-firefox)
  - [Pourquoi est-ce que mes jeux échouent à se lancer, ont des problèmes de performance ou des bugs d'affichage ?](#pourquoi-est-ce-que-mes-jeux-échouent-à-se-lancer-ont-des-problèmes-de-performance-ou-des-bugs-daffichage-)
  - [Mon jeu quitte subitement après un certain temps, mais fonctionne si esync est désactivé](#mon-jeu-quitte-subitement-après-un-certain-temps-mais-fonctionne-si-esync-est-désactivé)
  - [Les textes dans mon jeu ne s'affichent pas](#les-textes-dans-mon-jeu-ne-saffichent-pas)
  - [Il manque des textures/ennemis dans certains jeux (notamment The Witcher 3)](#il-manque-des-texturesennemis-dans-certains-jeux-notamment-the-witcher-3)
  - [Certains reports mentionnent avoir fait fonctionner le jeu en installant un composant additionnel. Comment puis-je faire cela ?](#certains-reports-mentionnent-avoir-fait-fonctionner-le-jeu-en-installant-un-composant-additionnel-comment-puis-je-faire-cela-)
  - [Comment puis-je jouer à des jeux Windows que je ne possède pas sur Steam ?](#comment-puis-je-jouer-à-des-jeux-windows-que-je-ne-possède-pas-sur-steam-)
  - [Les jeux stockés sur ma partition Windows (NTFS) ne se lancent pas.](#les-jeux-stockés-sur-ma-partition-windows-ntfs-ne-se-lancent-pas)
## [ProtonDB] Les boutons "Run" et "Install" ne fonctionnent pas sur Firefox.
Si Firefox ne vous a pas demandé comment gérer les URLs de type `steam://` URLS, vous devez le lui spécifier manuellement. Pour cela, ouvrez la page `about:config`, faites un clic droit n'importe où dans la liste et sélectionnez `New (Nouveau)` » `Boolean (Booléen)`. Entrez le nom `network.protocol-handler.expose.steam` et la valeur `false`. À présent, si vous cliquez sur une URL de type `steam://`, Firefox vous demandera l'action à effectuer.
## Pourquoi est-ce que mes jeux échouent à se lancer, ont des problèmes de performance ou des bugs d'affichage ?

#### Vérifiez que votre système est à jour et que vous utilisez les derniers pilotes disponibles pour votre carte graphique. Vous trouverez des instructions détaillées dans notre [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

Notes:

- À l'heure actuelle ce guide ne couvre que les pilotes stables. Si vous avez besoin des versions bêta, consultez les instructions spécifiques à votre distribution.

- Pour éviter de nombreux bugs et problèmes d'affichage sur AMD/Intel, vous avez besoin de LLVM en version 7 ou supérieure. Si votre distribution utilise toujours LLVM 6 (comme Solus), faites-vous entendre et demandez à ce que ce paquet soit mis à jour !

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
##
#### En utilisant des outils additionnels

Les deux outils les plus utilisés à l'heure actuelle sont [Protontricks](https://github.com/Sirmentio/protontricks) et [ProtonFixes](https://github.com/simons-public/protonfixes).

Vous pouvez trouver les instructions d'utilisation de ces outils sur leurs sites respectifs.

## Comment puis-je jouer à des jeux Windows que je ne possède pas sur Steam ?

Pour jouer à des jeux qui ne sont pas sur Steam, vous pouvez utiliser [Lutris](https://lutris.net/) pour les faire fonctionner avec Wine. Lutris est un gestionnaire de jeux intégrant de nombreux émulateurs et outils de compatibilité, dont Wine et Proton.

## Les jeux stockés sur ma partition Windows (NTFS) ne se lancent pas.

Par défaut, Linux monte les partitions NTFS en lecture seule (sauf pour l'utilisateur Root). [WIP]
