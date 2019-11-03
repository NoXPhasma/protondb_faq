![](https://github.com/NoXPhasma/protondb_faq/raw/master/logo.png)

## Languages
-  [English](#table-of-content) (Written by [NoXPhasma](https://github.com/NoXPhasma) & [Alexander](https://github.com/Alexander88207))
-  [German](README_DE.md) (Translated by [Alexander](https://github.com/Alexander88207))
-  [Spanish](README_ESP.md) (Translated by [Willdrick](https://github.com/Willdrick))
-  [French](README_FR.md) (Translated by [Askannz](https://github.com/Askannz))
-  [Italian](README_IT.md) (Translated by [Bloodis](https://github.com/bloodis))
-  [Norwegian](README_NO.md) (Translated by [MagZu](https://github.com/magzu))

Чтобы увидеть, кто еще помогал, посмотрите наш график! [contributors](https://github.com/NoXPhasma/protondb_faq/graphs/contributors)

## Введение
В этом FAQ мы хотим осветить наиболее важные вопросы, связанные с использованием ProtonDB, и, конечно же, технические вопросы, которые очень часто возникают из-за разногласий. Если вы хотите принять участие или у вас есть предложения, не стесняйтесь обращаться к нам в [Discord](https://discord.gg/uuwK9EV) или отправьте нам вопросы и вытяните запросы.


## Содержание
  - [[ProtonDB] Кнопки "Run" и "Install", похоже, не работают в Firefox.](#protondb-the-run-and-install-buttons-dont-seem-to-work-on-firefox)
  - [Why do my games crash on start, run very slow or have rendering issues?](#why-do-my-games-crash-on-start-run-very-slow-or-have-rendering-issues)
  - [My game crashes after a while but works fine without esync](#my-game-crashes-after-a-while-but-works-fine-without-esync)
  - [The game doesn't show any text](#the-game-doesnt-show-any-text)
  - [Some games like Witcher 3 have missing textures/enemies](#some-games-like-witcher-3-have-missing-texturesenemies)
  - [Why do some games stutter at the beginning?](#Why-do-some-games-stutter-at-the-beginning)
  - [I have sound problems like crackle for example](#i-have-sound-problems-like-crackle-for-example)
  - [My graphic card donsn’t support vulkan what can i do now?](#my-graphic-card-donsnt-support-vulkan-what-can-i-do-now)
  - [How do I create logs of a game I run with Proton?](#how-do-i-create-logs-of-a-game-i-run-with-proton)
  - [Some reports say they made the game running by installing some software, how do I do that?](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that)
  - [How do I run Windows games I don't own on Steam?](#how-do-i-run-windows-games-i-dont-own-on-steam)
  - [I have issues with my controller!](#i-have-issues-with-my-controller)
  - [Games stored on my Windows partition (NTFS) won't start](#games-stored-on-my-windows-partition-ntfs-wont-start)
  - [Punkbuster, Rockstar Social Club etc... fail during initial installation.](#punkbuster-rockstar-social-club-etc-fail-during-initial-installation)
  - [My Game won't save anything or crash while creating/loading a save.](#my-game-wont-save-anything-or-crash-while-creatingloading-a-save)
  - [My entire computer hangs up at some point in the game](#my-entire-computer-hangs-up-at-some-point-in-the-game)
  - [My Steam-Controller is not recognized even with native games, only the mouse functions.](#my-steam-controller-is-not-recognized-even-with-native-games-only-the-mouse-functions)
## [ProtonDB] кнопки "Run "Установить", похоже, не работают в Firefox.
Если Firefox не спрашивает вас, как он должен работать с URL-адресами " steam://", вам нужно заставить Firefox сделать это. Для этого откройте `about:config` в Firefox, щелкните правой кнопкой мыши в любом месте списка и выберите `New` » Boolean". Введите `network.protocol-handler.expose.steam` в качестве имени для новой записи и `false` в качестве значения. Теперь, если вы нажмете на URL `steam://`, Firefox должен спросить вас, как продолжить.
## Почему мои игры падают при запуске, работают очень медленно или есть проблемы рендеринга?

#### Убедитесь, что ваша система обновлена и что вы используете новейшие драйверы, доступные для вашей видеокарты. Подробную информацию об обновлении графических драйверов вы найдете в нашей [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

#### Взгляните на сайте вашу игру [WineHQ](http://appdb.winehq.org), вы можете найти обходные пути, чтобы заставить её работать. Если сайт сообщает, что он работает с Wine, это может быть специфическая проблема Proton или, возможно, сторонний DRM, такой как "Denuvo", создает проблемы здесь.

#### Убедитесь, что вы запускаете Steam со Steam Runtime библиотеками:

- Arch: Use Steam (Runtime)

- Solus: Disable the native-runtime in their "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"

## Моя игра вылетает через некоторое время, но отлично работает без синхронизации

Большинство проблем с sync связаны с ограниченным количеством открытых файлов. Прежде чем сообщать о проблемах с синхронизацией, проверьте, сообщает ли команда `ulimit -Hn` намного больше, чем 4096. Если нет, вы можете следуя [этим инструкциям](https://github.com/zfigura/wine/blob/async/README.esync) увеличить лимит.

## Игра не показывает текст

Некоторые игры требуют установки шрифтов Windows. Начиная с версии Proton [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) это будет сделано автоматически. Если вы используете Proton 3.7, проверьте, исправляет ли переход на версию 3.16-4 или выше, вашу проблему.

Чтобы изменить версию Proton, перейдите в настройки Steam, а затем во вкладку Steam Play. Вам необходимо активировать опцию "Enable Steam Play for all other titles". После этого вы можете выбрать версию Proton в выпадающем меню. 

## В некоторых играх, таких как Ведьмак 3, отсутствуют текстуры/враги

Это исправлено с DXVK версии [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) и Vulkan 1.1.88. К сожалению, на момент написания этой статьи вам нужны бета-драйверы для Nvidia (396.54.09), а пользователям AMD - как минимум Mesa версии 18.3

## Почему некоторые игры заикаются в начале?

Это вполне нормально. Потому что в начале шейдеры должны быть загружены первыми. Чтобы они не заикались в следующий раз, они записываются непосредственно в так называемый кэш шейдеров.

## У меня есть проблемы со звуком, как треск, например

В большинстве случаев, эту проблему решает установка xaudio2 (xact), но в таких случаях, как Skyrim, например, он также может решить некоторые проблемы, но также может вызвать новую проблему звука, но это всегда стоит попробовать.

Начиная с версии Proton [3.16-5](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-5) вам не нужно ничего делать, если вы не используете старую версию Proton, а затем читайте здесь:

достаточно установить "xaudio2_7.dll" в родной, или установить встроенный, xact, в winecfg с помощью winetricks.

[Здесь](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that) вы найдете более подробную информацию о том, как установить дополнительные программы в вашем gameprefix.

## Моя графическая карта не поддерживает Vulkan что я могу сделать сейчас?

Если вы действительно хотите попробовать сыграть в свою игру, попробуйте запустить игру со следующим [параметром запуска](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947)
``
PROTON_USE_WINED3D11=1 %command%
``
Примечание: Вы возможно будете иметь графические ошибки или низкую производительность, в зависимости от игры.

Если игра не запускается или аварийно завершается, ее нельзя запустить с помощью wine3d11

## Как создать логи игры, которую я запускаю с Proton?

Протон создаст файл журнала для конкретной игры, если вы [установите параметр запуска](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947):
```
PROTON_LOG=1 %command%
```
Файл журнала будет создан в вашей домашней папке со схемой имен `steam-$STEAMID.log`. Например:
```
$HOME/steam-379720.log
```

## Некоторые отчеты говорят, что они сделали игру работающей, установив некоторое программное обеспечение, как я могу это сделать?

Есть два способа установки дополнительного программного обеспечения в gameprefix:

#### Использование Winetricks
Убедитесь, что в вашей системе установлен winetricks. Этот пакет должен находиться в репозитории дистрибутивов.

Откройте терминал и используйте
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) необходимо заменить, к примеру для Garrys Mod game id 4000. Можно использовать [SteamDB](https://steamdb.info), чтобы узнать, какой id у вашей игры.

(Steam-папка) должна быть заменена на вашу .Steam папку.

Вот пример

```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```
##
#### Использование инстурментов

Два наиболее популярных в настоящее время являются [Protontricks](https://github.com/Matoking/protontricks) и [ProtonFixes](https://github.com/simons-public/protonfixes).

Пожалуйста, ознакомьтесь с инструкциями об этих инструментах на соответствующих сайтах.

## Как запустить Windows игры не мз Steam?

Для запуска игр, которых нет в Steam, вы можете использовать [Lutris](https://lutris.net/) запуская их с Wine. Lutris игровой менеджер, который поддерживает больше разных совместимых прослоек/эмуляторов, включая Wine/Proton.

## У меня проблемы с контроллером!

Случай №1: Мой контроллер распознается как игрок 1 и игрок 2 в играх Lego.

- Fix #1: Откройте настройки контроллера от gameprefix с командной например:`WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000pfx/ wine control  и  отключите контроллер "js" & "event" после этого перезапустите сессию, чтобы подтвердить, что Wine полностью закрыт, дабы гарантировать, что новые изменения загрузятся.

## Игры, сохраненные в разделе Windows (NTFS), не запускаются

По умолчанию Linux монтирует разделы NTFS только с правами Root. Необходимо подключить этот раздел с правами пользователя. Вы найдете простой turorial о том, как подключить диск NTFS с правами пользователя на [Proton Wiki](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows).

## Punkbuster, Rockstar Social Club и др... фейл в процессе начальной установки.

Может так случиться, что такие вещи неправильно установлены  [первый раз](https://github.com/NoXPhasma/protondb_faq/raw/master/Initial%20installation%20example.png) и тогда Steam больше не пытается их установить.

Каждая игра имеет в папке с игрой одну папку, она называется например: "Installers" "Redist" и так далее... Затем она содержит программу установки для PB или RGSC, они должны быть просто запущены в соответствующем gameprefix с Wine, вот пример:

`WINEPREFIX='/home/alexander/.steam/steam/steamapps/compatdata/271590/pfx' wine '/home/alexander/.steam/steam/steamapps/common/Grand Theft Auto V/Installers/Social-Club-Setup.exe'`

## Моя игра ничего не сохраняет или падает при создании/загрузке сохранения.

Вы можете попробовать начать игру с этого [параметра запуска](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947): `unset LC_ALL && %command%`

## Весь мой компьютер зависает в какой-то момент игры.

Это может GPU висеть, но чтобы быть уверенным, что это не ошибка Proton, проверьте игру с последней версией Wine в первую очередь.

Если это также происходит с последней версией Wine, только разработчики вашего графического драйвера ([nvidia](http://nvidia.custhelp.com/app/answers/detail/a_id/44) или [mesa](https://www.mesa3d.org/bugs.html)) или редко [dxvk](https://github.com/doitsujin/dxvk/issues) могут помочь вам. К примеру Radeon в игре Ведьмак 3, тогда вам следует переключиться на драйвер AMDVLK. (http://uploaded.net/file/tvzorp36/from/x65rhk)


## Мой Steam-контроллер не распознается даже в нативных играх, работает только мышь.

Это пока что замечено только самим [@Alexander](https://github.com/Alexander88207) на gento и дистрибутивах на его основе.

Если вы играете на Linux с помощью Steam и у вас есть Steam контроллер, вы, возможно, заметили что-то интересное. Контроллер Steam работает, но не работает в играх.
```
sudo groupadd steam
sudo /etc/udev/rules.d/99-steam-controller-perms.rules
```
и добавить
```
# Valve USB devices
SUBSYSTEM=="usb", ATTRS{idVendor}=="28de", MODE="0666"
# Steam Controller udev write access
KERNEL=="uinput", SUBSYSTEM=="misc", TAG+="uaccess", TAG+="udev-acl"
# This rule is necessary for gamepad emulation; make sure your user is in the 'steam' group
KERNEL=="uinput", MODE="0660", GROUP="steam", OPTIONS+="static_node=uinput"
# HTC Vive HID Sensor naming and permissions (VR GAMING)
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", ATTRS{idVendor}=="0bb4", ATTRS{idProduct}=="2c87", MODE="0666"
```
Затем обязательно добавьте себя в группу Steam с помощью usermod -a -G steam $USER

