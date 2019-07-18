![](https://github.com/NoXPhasma/protondb_faq/raw/master/logo.png)

## Bahasa
-  [Bahasa Inggris](#table-of-content) (Ditulis oleh [NoXPhasma](https://github.com/NoXPhasma) & [Alexander](https://github.com/Alexander88207))
-  [Bahasa Jerman](README_DE.md) (Diterjemahkan oleh [Alexander](https://github.com/Alexander88207))
-  [Bahasa Spanyol](README_ESP.md) (Diterjemahkan oleh [Willdrick](https://github.com/Willdrick))
-  [Bahasa Perancis](README_FR.md) (Diterjemahkan oleh [Askannz](https://github.com/Askannz))
-  [Bahasa Italia](README_IT.md) (Diterjemahkan oleh [Bloodis](https://github.com/bloodis))
-  [Bahasa Norwegia](README_NO.md) (Diterjemahkan oleh [MagZu](https://github.com/magzu))
-  [Bahasa Indonesia](README_ID.md) (Diterjemahkan oleh [Ari](https://github.com/Ari-El-Uno))

Untuk melihat siapa saja yang membantu, silakan lihat ke grafik [kontributor](https://github.com/NoXPhasma/protondb_faq/graphs/contributors) kami!

## Pengenalan
Dengan FAQ ini, kami ingin menampung pertanyaan-pertanyaan penting terkait dengan penggunaan ProtonDB dan tentu saja pertanyaan teknis yang mana sering ditanyakan di Discord kami. Jika Anda ingin berpartisipasi atau memiliki saran, jangan ragu untuk menghubungi [Discord](https://discord.gg/uuwK9EV) kami atau kirim issues dan pull requests.


## Daftar Isi
  - [[ProtonDB] Tombol "Run" dan "Install" tidak dapat bekerja di Firefox.](#protondb-tombol-run-dan-install-tidak-dapat-bekerja-di-firefox)
  - [[ProtonDB] Di dalam website game saya ditampilkan sebagai game Windows tetapi ia punya native port, atau sebaliknya.
](#protondb-di-dalam-website-game-saya-ditampilkan-sebagai-game-windows-tetapi-ia-punya-native-port-atau-sebaliknya)
  - [Mengapa game saya crash saat dijalankan, berjalan sangat lambat atau memiliki masalah rendering?](#mengapa-game-saya-crash-saat-dijalankan-berjalan-sangat-lambat-atau-memiliki-masalah-rendering)
  - [Game saya crash setelah beberapa saat tetapi berjalan baik tanpa esync.](#game-saya-crash-setelah-beberapa-saat-tetapi-berjalan-baik-tanpa-esync)
  - [Game saya tidak menampilkan teks apapun.](#game-saya-tidak-menampilkan-teks-apapun)
  - [Beberapa game seperti Witcher 3 mengalami missing textures/enemies.](#beberapa-game-seperti-witcher-3-mengalami-missing-texturesenemies)
  - [Mengapa beberapa game stutter pada saat dimulai?](#mengapa-beberapa-game-stutter-pada-saat-dimulai)
  - [Saya memiliki masalah suara seperti gemericik/berisik misalnya.](#saya-memiliki-masalah-suara-seperti-gemericikberisik-misalnya)
  - [Saya ingin memainkan game tanpa DXVK.](#saya-ingin-memainkan-game-tanpa-dxvk)
  - [Bagaimana saya membuat logs dari sebuah game yang saya jalankan dengan Proton?](#bagaimana-saya-membuat-logs-dari-sebuah-game-yang-saya-jalankan-dengan-proton)
  - [Beberapa laporan mengatakan mereka membuat game bisa dijalankan dengan memasang beberapa software, bagaimana saya melakukannya?](#beberapa-laporan-mengatakan-mereka-membuat-game-bisa-dijalankan-dengan-memasang-beberapa-software-bagaimana-saya-melakukannya)
  - [Bagaimana saya menjalankan game Windows yang tidak saya miliki di Steam?](#bagaimana-saya-menjalankan-game-windows-yang-tidak-saya-miliki-di-steam)
  - [Saya memiliki masalah pada controller saya!](#saya-memiliki-masalah-pada-controller-saya)
  - [Game yang disimpan di partisi Windows saya (NTFS) tidak mau dijalankan.](#game-yang-disimpan-di-partisi-windows-saya-ntfs-tidak-mau-dijalankan)
  - [Punkbuster, Rockstar Social Club, dan sebagainya... gagal saat instalasi awal.](#punkbuster-rockstar-social-club-dan-sebagainya-gagal-saat-instalasi-awal)
  - [Game saya tidak mau menyimpan apapun atau crash saat membuat/memuat simpanan.](#game-saya-tidak-mau-menyimpan-apapun-atau-crash-saat-membuatmemuat-simpanan)
  - [Komputer saya hang total saat berada dalam game.](#komputer-saya-hang-total-saat-berada-dalam-game)
  
## [ProtonDB] Tombol "Run" dan "Install" tidak dapat bekerja di Firefox.
Jika Firefox tidak meminta Anda bagaimana seharusnya berproses dengan `steam://` URLS, Anda perlu memaksa Firefox untuk melakukannya. Untuk itu bukalah `about:config` di Firefox, klik kanan dimanapun lalu klik `New` » `Boolean`. Masukkan `network.protocol-handler.expose.steam` sebagai nama entry yang baru, dan `false` sebagai nilainya. Sekarang jika Anda klik pada `steam://` URL, Firefox akan meminta Anda bagaimana berproses selanjutnya.

## [ProtonDB] Di dalam website game saya ditampilkan sebagai game Windows tetapi ia punya native port, atau sebaliknya.

ProtonDB mendapatkan data dari SteamDB dan ini langsung dari developer game yang bersangkutan. Jadi apabila developer memiliki native port seperti misalnya Rust lalu ditutup kembali, maka game tersebut akan ditampilkan sebagai game Windows, tetapi pembeli pada saat ada native port akan tetap memiliki native port tentu saja, sehingga akan ada pengguna yang menuliskan: "itu punya native port!".

## Mengapa game saya crash saat dijalankan, berjalan sangat lambat atau memiliki masalah rendering?

#### Pastikan sistem Anda terupdate dan Anda menggunakan driver terbaru untuk kartu grafis. Anda akan menemukan informasi detail tentang bagaimana mengupdate driver kartu grafis pada [Wiki](https://github.com/NoXPhasma/protondb_faq/wiki/Graphics-driver-installation)

#### Lihat juga halaman website tentang game Anda di [WineHQ](https://appdb.winehq.org), Anda mungkin akan menemukan workarounds untuk membuatnya berjalan. Apabila website tersebut melaporkan bahwa game tersebut berjalan dengan Wine, kemungkinan itu adalah masalah spesifik pada Proton atau mungkin ada 3rd party DRM seperti "Denuvo" membuat masalah disini.

#### Pastikan Anda menjalankan Steam dengan Steam Runtime libraries:

- Arch: Gunakan Steam (Runtime)

- Solus: Matikan native-runtime dalam "[linux-steam-integration-tool](https://raw.githubusercontent.com/solus-project/linux-steam-integration/master/.github/LSI_Settings.png)"

## Game saya crash setelah beberapa saat tetapi berjalan baik tanpa esync.

Kebanyakan masalah dengan esync adalah tentang batasan jumlah file yang terbuka. Sebelum melaporkan masalah tentang esync, cek apakah perintah `ulimit -Hn` melaporkan lebih dari 4096. Jika tidak, Anda dapat mengikuti [instruksi ini](https://github.com/zfigura/wine/blob/esync/README.esync) untuk menambah batasan.

## Game saya tidak menampilkan teks apapun.

Beberapa game butuh font Windows terpasang. Sejak Proton versi [3.16-4](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-4) ini sudah ada otomatis. Jika Anda menggunakan Proton 3.7, lihat apakah mengganti versi ke 3.16-4 ke atas bisa menyelesaikan masalah.

Untuk mengganti versi Proton, pergi ke Steam settings lalu ke tab Steam Play. Anda perlu mengaktifkan opsi "Use this tool instead of game-specific selections from Steam". Lalu Anda dapat memilih versi Proton pada menu drop down.

## Beberapa game seperti Witcher 3 mengalami missing textures/enemies.

Ini sudah diperbaiki sejak DXVK Versi [0.90](https://github.com/doitsujin/dxvk/releases/tag/v0.90) dan Vulkan 1.1.88. Pengguna Nvidia perlu driver minimal versi 415.22, dan pengguna AMD perlu minimal Mesa versi 18.3.

## Mengapa beberapa game stutter pada saat dimulai?

Ini normal. Karena pada saat game dimulai shader perlu dimuat terlebih dahulu, sehingga selanjutnya tidak stutter lagi. Mereka dituliskan ke dalam shader cache.

Catatan bahwa dxvk cache tidak ada kaitannya dengan "Shader Pre-Caching" di Steam.

## Saya memiliki masalah suara seperti gemericik/berisik misalnya.

Pada kebanyakan kasus, perlu install xaudio2 (xact) tetapi pada kasus seperti Skyrim, misalnya, itu dapat menyelesaikan beberapa masalah tetapi menyebabkan masalah baru, tetapi tidak ada salahnya dicoba dulu.

Sejak Proton versi [3.16-5](https://github.com/ValveSoftware/Proton/wiki/Changelog#316-5) Anda tidak perlu melakukan apapun, kecuali Anda menggunakan Proton versi lama maka ikuti langkah berikut:

Cukup set "xaudio2_7.dll" ke native, built-in dalam winecfg atau install xact menggunakan winetricks.

[Disini](#some-reports-say-they-made-the-game-running-by-installing-some-software-how-do-i-do-that) Anda akan menemukan informasi tambahan tentang bagaimana memasang program tambahan pada gameprefix Anda.

## Saya ingin memainkan game tanpa DXVK.

Jika Anda benar-benar ingin memainkan game tanpa DXVK, maka cobalah menjalankan game dengan [launch parameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947)
```
PROTON_USE_WINED3D11=1 %command%
```
Catatan: Anda mungkin akan menemukan error grafik atau performa yang kurang tergantung game yang dijalankan.

Jika game Anda tidak berjalan atau crash maka game Anda tidak dapat dijalankan dengan wine3d11

## Bagaimana saya membuat logs dari sebuah game yang saya jalankan dengan Proton?

Proton akan membuat log file untuk game terkait, jika Anda [set launch parameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947) menjadi:
```
PROTON_LOG=1 %command%
```
Log file akan dibuat di home folder dengan skema nama `steam-$STEAMID.log`. Misalnya:
```
$HOME/steam-379720.log
```

## Beberapa laporan mengatakan mereka membuat game bisa dijalankan dengan memasang beberapa software, bagaimana saya melakukannya?

Ada dua cara untuk memasang software tambahan ke dalam gameprefix:

#### Gunakan Winetricks
Pastikan Anda memiliki winetricks terpasang dalam sistem. Paket ini seharusnya ada dalam repositori distro Anda.

Buka Terminal dan gunakan
```
WINEPREFIX=(Steam-folder)/steamapps/compatdata/(GAME-ID)/pfx/ winetricks
```
(GAME-ID) harus diganti dengan game id misalnya 4000 untuk Garry´s Mod, Anda dapat menggunakan [SteamDB](https://steamdb.info) untuk mencari tahu game id.

(Steam-folder) harus diganti dengan lokasi .steam folder.

Ini contohnya

```
WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ winetricks
```
##
#### Penggunaan Tool

Dua yang paling populer adalah [Protontricks](https://github.com/Sirmentio/protontricks) dan [ProtonFixes](https://github.com/simons-public/protonfixes).

Tolong baca instruksi tentang tool-tool tersebut pada website masing-masing.

## Bagaimana saya menjalankan game Windows yang tidak saya miliki di Steam?

Tambahkan Non-Steam game ke library Anda (set File Type menjadi "All Files") dan pilih .exe

Klik kanan pada game di Library Anda lalu di Properties - Enable "Force the use of a specific Steam Play compatibility Tool"

Jika ada spasi dalam nama path menuju .exe Anda perlu memperbaiki path "Target:" dalam Properties dan kosongkan "Set Launch Options"

Akan tetapi, kami menyarankan [Lutris](https://lutris.net/) untuk menjalankan non Steam game melalui Wine. Lutris adalah sebuah game manager yang memberikan dukungan untuk banyak compatibility layer/emulator, termasuk Wine/Proton.

## Saya memiliki masalah pada controller saya!

Kasus #1: Controller saya bisa dikenali sebagai player 1 & player 2 dalam game LEGO.

- Penyelesaian  #1: Buka controller settings dalam gameprefix dengan perintah misalnya:`WINEPREFIX=/home/alexander/.steam/steam/steamapps/compatdata/4000/pfx/ wine control` dan matikan controller "js" & "event" setelah itu restart sesi Anda untuk memastikan bahwa Wine sudah tertutup sepenuhnya dan pergantian konfigurasi baru yang akan dimuat.

Kasus #2: Steam-Controller tidak dikenali bahkan oleh native game, hanya mouse yang berfungsi.

- Penyelesaian #2: Ini terjadi pada distro berbasis Gentoo atau Gentoo itu sendiri. Ditemukan oleh [@Alexander](https://github.com/Alexander88207)

Jika Anda bermain game di Linux menggunakan Steam dan memiliki sebuah Steam Controller Anda mungkin menemukan sesuatu yang menarik. Steam Controller sepertinya bekerja, tapi tidak bekerja di dalam game atau tidak ditampilkan pada wine control.

Kami menyarankan untuk menggunakan tool [sc-controller](https://github.com/kozec/sc-controller) untuk melakukan workaround atas masalah ini.

## Game yang disimpan di partisi Windows saya (NTFS) tidak mau dijalankan.

Secara default Linux memuat partisi NFTS hanya dapat ditulis oleh Root. Perlu untuk mount partisi tersebut dengan hak akses user biasa. Anda akan menemukan tutorial sederhana tentang bagaimana melakukan mount NTFS drive dengan hak akses user biasa pada [Proton Wiki](https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows).

## Punkbuster, Rockstar Social Club, dan sebagainya... gagal saat instalasi awal.

Bisa jadi mereka tidak terpasang dengan benar [awalnya](https://github.com/NoXPhasma/protondb_faq/raw/master/Initial%20installation%20example.png) lalu Steam tidak mencoba memasangnya kembali. 

Setiap game memiliki folder di dalam game folder yang misalnya disebut: "Installers" "Redist" dan semacamnya...... Folder ini berisi installer untuk PB atau RGSC, ini harus dijalankan pada gameprefix terkait dengan wine, contohnya: 

`WINEPREFIX='/home/alexander/.steam/steam/steamapps/compatdata/271590/pfx' wine '/home/alexander/.steam/steam/steamapps/common/Grand Theft Auto V/Installers/Social-Club-Setup.exe'`

## Game saya tidak mau menyimpan apapun atau crash saat membuat/memuat simpanan.

Anda dapat mencoba untuk menjalankan game dengan [launch parameter](https://support.steampowered.com/kb_article.php?ref=1040-JWMT-2947): `unset LC_ALL && %command%`

## Komputer saya hang total saat berada dalam game.

Bisa jadi ini adalah GPU hang, tetapi untuk memastikan ini bukan kesalahan Proton, tes game pada versi Wine terbaru.

Jika tetap terjadi pada Wine versi terbaru, hanya developer driver kartu grafis Anda ([nvidia](https://nvidia.custhelp.com/app/answers/detail/a_id/44) atau [mesa](https://www.mesa3d.org/bugs.html)) atau [dxvk](https://github.com/doitsujin/dxvk/issues) yang dapat membantu Anda.
