## Traducciones
-  [Inglés](README.md) (versión original, creada por [NoXPhasma](https://github.com/NoXPhasma))
-  [Alemán](README_DE.md) (traducido por [Alexander](https://github.com/Alexander88207))
-  [Español](#Tabla-de-Contenidos) (traducido por [Willdrick](https://github.com/Willdrick))
-  [Francés](README_FR.md) (traducido por [Askannz](https://github.com/Askannz))
-  [Italiano](README_IT.md) (traducido por [Bloodis](https://github.com/bloodis))
-  [Noruego](README_NO.md) (traducido por [MagZu](https://github.com/magzu))

## Introducción

Esta guía de preguntas frecuentes intenta cubrir aquellos temas relacionados al uso de ProtonDB, así como también las cuestiones técnicas que se suelen tratar en el Discord de la comunidad. Si quieres participar o dejar tus sugerencias, no dudes en contactarnos en [Discord](https://discord.gg/uuwK9EV) o utilizar "issues" o "pull requests" en este Git.

## Tabla de Contenidos
  - [[ProtonDB] Los botones "Run" e "Install" no funcionan en FireFox.](#protondb-los-botones-run-e-install-no-funcionan-en-firefox)
  - [¿Por qué mi juego se cuelga al abrir, anda muy lento o tiene problemas de renderizado?](#por-que-mi-juego-se-cuelga-al-abrir-anda-muy-lento-o-tiene-problemas-de-renderizado)
  - [Mi juego se cuelga después de un rato pero anda bien con esync](#mi-juego-se-cuelga-despues-de-un-rato-pero-anda-bien-con-esync)
  - [No se ve el texto en el juego](#no-se-ve-el-texto-en-el-juego)
  - [En algunos juegos como Witcher 3 no se ven algunas texturas o enemigos](#en-algunos-juegos-como-witcher-3-no-se-ven-algunas-texturas-o-enemigos)
  - [Tengo problemas con el sonido, como por ejemplo estática](#tengo-problemas-con-el-sonido-como-por-ejemplo-est%C3%A1tica)
  - [Mi tarjeta gráfica no soporta Vulkan ¿Qué puedo hacer?](#mi-tarjeta-gráfica-no-soporta-vulkan-qué-puedo-hacer)
  - [¿Cómo creo registros de un juego que corro con Proton?](#c%C3%B3mo-creo-registros-de-un-juego-que-corro-con-proton)
  - [En algunos reportes aclaran que hicieron funcionar el juego con otro programa ¿Cómo hago eso?](#en-algunos-reportes-aclaran-que-hicieron-funcionar-el-juego-con-otro-programa-como-hago-eso)
  - [¿Cómo corro juegos de Windows que no tengo en Steam?](#como-corro-juegos-de-windows-que-no-tengo-en-steam)
  - [Los juegos en mi partición de Windows (NTFS) no arrancan](#los-juegos-en-mi-particion-de-windows-ntfs-no-arrancan)

## [ProtonDB] Los botones "Run" e "Install" no funcionan en FireFox.
Si Firefox no te ofrece la elección de cómo proceder con los enlaces `steam://` deberás forzarlo. Para ello ve a `about:config` en la barra de direcciones, haz click derecho en cualquier lado y selecciona `nuevo` » `Booleano`. En el nombre escribe `network.protocol-handler.expose.steam` y dale el valor `falso` (o `false`). La próxima vez que selecciones un enlace `steam://` el FireFox te mostrará el diálogo para seleccionar la aplicación deseada.

## ¿Por qué mi juego se cuelga al abrir, anda muy lento o tiene problemas de renderizado?

#### Asegúrate que tu sistema esté al día con las actualizaciones, y que estés usando la última versión del controlador para tu tarjeta de video.

#### Busca tu juego en [WineHQ](https://appdb.winehq.org) para más información acerca de soluciones. Si en el sitio se reporta que corre en Wine, probablemente sea un problema específico de Proton, o de un problema relacionado al DRM como "Denuvo".

#### Asegúrate de que estás corriendo Steam con las librerías de Steam Runtime:

- Arch: Usar Steam (Runtime)

- Solus: Desactivar Entorno Nativo en "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"


## Mi juego se cuelga después de un rato pero anda bien con esync

La mayoría de los problemas con esync están relacionados con la cantidad limitada de archivos abiertos. Antes de reportar cualquier problema con esync, corre el comando `ulimit -Hn`y fíjate que devuelva un valor mucho más alto que 4096. Si no es así, puedes seguir [estas instrucciones](https://github.com/zfigura/wine/blob/esync/README.esync) para aumentar el límite.


## No se ve el texto en el juego

Algunos juegos necesitan las fuentes de Windows instaladas. Ésto se resuelve automáticamente desde la versión [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) de Proton. Si estás usando Proton 3.7, trata de cambiar a 3.16-4 o superior para resolver el problema.

Para cambiar la versión de Proton utilizada, ve a Steam, Parámetros y en la sección Steamplay habrá una opción para "Usar esta herramienta en lugar de selecciones específicas de juegos de Steam". Elige la versión deseada desde el menú desplegable.


## En algunos juegos como Witcher 3 no se ven algunas texturas o enemigos

Ésto está solucionado desde la versión [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) de DXVK y desde Vulkan 1.1.88. Desafortunadamente, en este momento necesitas los controladores beta de nVidia (396.54.09) o la última versión de Mesa (18.3) para AMD.

## Tengo problemas con el sonido, como por ejemplo estática.

En la mayoría de los casos, la instalación de la libería xaudio2 (xact) soluciona problemas, como por ejemplo en Skyrim, aunque ésto puede producir un nuevo problema. De todas formas siempre es un buen punto de inicio para probar.

Utilizando winecfg se puede indicar la librería "xaudio2_7.dll" como "built in" o se puede instalar "xact" desde winetricks.

[Aquí](#en-algunos-reportes-aclaran-que-hicieron-funcionar-el-juego-con-otro-programa-como-hago-eso) puedes encontrar más información de cómo utilizar Winetricks.

## Mi tarjeta gráfica no soporta Vulkan ¿Qué puedo hacer?

Puedes intentar arrancar el juego con los siguientes [parámetros de lanzamiento](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947)

```
PROTON_USE_WINED3D11=1 %command%
```

NOTA: Dependiendo del juego, es probable que tengas errores gráficos o problemas de rendimiento.
Si tu juego no abre o se cuelga, significa que no puede ser utilizado con wine3d11

## ¿Cómo creo registros de un juego que corro con Proton?

Para crear un registro, debes [configurar los parámetros de lanzamiento](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947) de steam de la siguiente forma:

```
PROTON_LOG=1 %command%
```

El archivo de registro se creará como `steam-$STEAMID.log`. 

por ejemplo:

```
$HOME/steam-379720.log
```

## En algunos reportes aclaran que hicieron funcionar el juego con otro programa ¿Cómo hago eso?

Hay dos formas de instalar programas adicionales en un prefix:

#### Usando Winetricks
Asegúrate de que Winetricks esté instalado. Normalmente se encuentra en los repositorios de tu distro.


Abrir la terminal y escribir:
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) debe ser reemplazado por el número de identificación de tu juego, por ejemplo 4000 para Garry's Mod. Si necesitas saber el número, puedes usar [SteamDB](https://steamdb.info) para averiguarlo.
(Steam-folder) debe ser reemplazado por la ubicación de tu carpeta .steam

Por ejemplo:

```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```
##
#### Usando Herramientas específicas para Proton

En este momento las más populares son [Protontricks](https://github.com/Matoking/protontricks) y [ProtonFixes](https://github.com/simons-public/protonfixes).

Puedes obtener instrucciones e información de ellas, en sus respectivos sitios web.

## ¿Cómo corro juegos de Windows que no tengo en Steam?

Para ejecutar juegos que no se encueentran en tu biblioteca de Steam puedes utilizar [Lutris](https://lutris.net/) y correrlos con Wine. Lutris es una aplicación que administra tus juegos y ofrece una gran variedad de capas de compatibilidad y emuladores, incluyendo Wine/Proton

## Los juegos en mi partición de Windows (NTFS) no arrancan

Linux monta los sistemas de archivos NTFS como sólo lectura para todos los usuarios salvo root. Puedes encontrar un tutorial de cómo montar una partición NTFS con permisos de usuario en la [Wiki](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows)
