# [Flipper Zero Firmware](https://github.com/flipperdevices/flipperzero-firmware/blob/dev/ReadMe.md) <= READ THIS READ ME
- ****This software is for experimental purposes only and is not meant for any illegal activity/purposes. We do not condone illegal activity and strongly encourage keeping transmissions to legal/valid uses allowed by law.**
- FLASH STOCK FIRST BEFORE UPDATING TO CUSTOM FIRMWARE
- BUILD WITH COMPACT FLAG SINCE IT IS TOO LARGE
- CH0NG, CH33CH and N00BY rename your flipper.

# Clone the Repository

You should clone with 
```shell
$ git clone --recursive https://github.com/RogueMaster/flipperzero-firmware-wPlugins.git
$ docker-compose up -d
$ docker-compose exec dev make
```

Latest Updates:
- Updates to size down [Video Poker, Thanks To PixlEmly](https://github.com/PixlEmly/flipperzero-firmware-testing/blob/unleashed/applications/VideoPoker/poker.c).
- Spectrum Analyzer [Updates (for testing) Thanks to theY4Kman](https://github.com/theY4Kman/flipperzero-firmware)
- BadUSB and U2F re-added. Was removed on the debug removals for some reason...
- Added [Game of Life (Updated to work by tgxn)](https://github.com/tgxn/flipperzero-firmware/blob/dev/applications/game_of_life/game_of_life.c) Original By 
itsyourbedtime. (Hard Fault or Restart to quit?)

**Special Instructions:**
- Download these files into the subghz/assets folder on your SD card. Edit the two `_map` files to contain your specific subghz (.SUB) files.
- - Note 1: If you don't have a subghz/assets folder, you should ensure you have made at least one clean flash with stock firmware and your SD card installed in order to ensure the database structure is built, otherwise it will not exist for alternative forks.
- - Note 2: /any is a special keyword signifying either /int (internal storage) or /ext (external storage).
- - Note 3: the changes you are making to the `_map` files is to point to the location of the specific assets of the touchtunes folder as well as the universal RF map apps which you will have to develop or compile seperately and are not a part of this repo. 
- - Note 4: /any is effectively root, so the folder structure should start "/any/subghz/assets" and not what is based on the repo below do not blindly copy the repo it will not work.
- - [assets/resources/subghz/assets/universal_rf_map.txt](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/assets/resources/subghz/assets/universal_rf_map.txt)
- - [assets/resources/subghz/assets/touchtunes_map.txt](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/assets/resources/subghz/assets/touchtunes_map.txt)
- - [assets/resources/subghz/assets/setting_user](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/assets/resources/subghz/assets/setting_user)
- Download this file into the nfc/assets folder on your SD card. 
- - [assets/resources/nfc/assets/mf_classic_dict.nfc](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/assets/resources/nfc/assets/mf_classic_dict.nfc)
- Add a folder to SD card named `wav_player` (for 8bit 2ch unsigned wav files) 
- Add a folder to SD card named `music_player` (FMF and RTTTL/TXT files)

Special shout out to these libraries for giving us more fun:
- https://github.com/Gioman101/FlipperAmiibo
- https://github.com/jimilinuxguy/flipperzero-touchtunes
- https://github.com/Lucaslhm/AmiiboFlipperConverter
- https://github.com/MuddledBox/FlipperZeroCases
- https://github.com/MuddledBox/FlipperZeroSub-GHz
- https://github.com/neverfa11ing/FlipperMusicRTTTL
- https://github.com/UberGuidoZ/Flipper
- https://github.com/UberGuidoZ/Flipper-IRDB

Added Features:
- 10s+90s Timeout for Backlight Time [(By RogueMaster)](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/applications/notification/notification_settings_app.c)
- Actual PIN Lock [(By RogueMaster)](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/applications/desktop/desktop.c)
- Favorite Game by holding UP on Desktop [Thanks to gotnull](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/pull/57)
- Flashing the firmware using the blackmagic board with make blackmagic_load [From WeTox](https://github.com/wetox-team/flipperzero-firmware)
- Hold Center to change flipper idle animation. [Thanks to Zycenios](https://github.com/flipperdevices/flipperzero-firmware/commit/111786ef40e50a40d2e510595672b569d9b97bba) With changes by RogueMaster.
- Idle animations will show all animations regardless of level and butthurt [Thanks to MajiK]
- Keeloq update from [Xorist](https://github.com/xorist/FlipperX)
- Removing T5577 passwords via the cli command rfid clear_pass_t5577 using a dictionary attack [From WeTox](https://github.com/wetox-team/flipperzero-firmware)
- Scan names will have timestamp instead of random name assigned [(By RogueMaster)](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/lib/toolbox/random_name.c)
- Snake and Tetris show score. [Thanks to whoamins](https://github.com/flipperdevices/flipperzero-firmware/commit/7feda832ede1ba8468eff2ca055fef3ddbdc16ac) With changes by RogueMaster.
- SubGHz Protocols (Came Atomo, FAAC_SLH, Keeloq, Keeloq Common, Nice Flor S, SecPlus v1+v2 and Star Line) updates from [Eng1n33r](https://github.com/Eng1n33r/flipperzero-firmware)
- SubGHZ Scanning image with Pikachu [Thanks to Panzer00Z](https://github.com/Panzer00Z/flipperzero-firmware/blob/3a548ea9bb181c9348d8afb427890c411456134e/assets/icons/SubGhz/Scanning_123x52.png)

Open PRs Checkedout & Not Merged In Main:
- [On-device tag generator #1319 (By GMMan)](https://github.com/flipperdevices/flipperzero-firmware/pull/1319)
- [SubGhz: fix protocol scher_khan #1323 (By Skorpionm)](https://github.com/flipperdevices/flipperzero-firmware/pull/1323)
- [Bluetooth Remote Additions #1330 (By Cutch)](https://github.com/flipperdevices/flipperzero-firmware/pull/1330)

Plugins:
- [Arkanoid (By gotnull)](https://github.com/gotnull/flipperzero-firmware-wPlugins)
- [Clock/Stopwatch (By CompaqDisc, Stopwatch & Sound Alert By RogueMaster)](https://gist.github.com/CompaqDisc/4e329c501bd03c1e801849b81f48ea61)
- [Dice Roller Including SEX/WAR/8BALL/WEED DICE (By RogueMaster)](https://github.com/RogueMaster/flipperzero-firmware-wPlugins/blob/unleashed/applications/dice/dice.c)
- [Flappy Bird (By DroomOne)](https://github.com/DroomOne/flipperzero-firmware/tree/dev/applications/flappy_bird)
- [Game of Life (Updated to work by tgxn)](https://github.com/tgxn/flipperzero-firmware/blob/dev/applications/game_of_life/game_of_life.c) Original By 
itsyourbedtime. (Hard Fault or Restart to quit?)
- [Games Menu, Icons and Raycast exit (By Redlink)](https://github.com/redlink2/flipperzero-firmware/tree/menuChanges)
- [HID Analyzer (By Ownasaurus)](https://github.com/Ownasaurus/flipperzero-firmware/tree/hid-analyzer/applications/hid_analyzer)
- [RayCast (Bt Zlo)](https://github.com/flipperdevices/flipperzero-firmware/tree/zlo/raycast-game-engine)
- [RF Remix (By ESurge)](https://github.com/ESurge/flipperzero-firmware-unirfremix)[(Original By jimilinuxguy)](https://github.com/jimilinuxguy/flipperzero-universal-rf-remote/tree/028d615c83f059bb2c905530ddb3d4efbd3cbcae/applications/jukebox)
- [Spectrum Analyzer (By jolcese)](https://github.com/jolcese/flipperzero-firmware/tree/spectrum/applications/spectrum_analyzer) [Updates (for testing) Thanks to theY4Kman](https://github.com/theY4Kman/flipperzero-firmware)
- [Tanks (By Alexgr13)](https://github.com/alexgr13/flipperzero-firmware/tree/fork/dev/applications/tanks-game) Updated by RogueMaster To Work
- [Tetris (By jeffplang)](https://github.com/jeffplang/flipperzero-firmware/tree/tetris_game/applications/tetris_game)
- [Tic Tac Toe (By gotnull)](https://github.com/gotnull/flipperzero-firmware-wPlugins)
- [Video Poker (By PixlEmly)](https://github.com/PixlEmly/flipperzero-firmware-testing/blob/unleashed/applications/VideoPoker/poker.c)
- [WAV Player (By Zlo)](https://github.com/flipperdevices/flipperzero-firmware/tree/zlo/wav-player) Updated by Atmanos & RogueMaster To Work

Thank you, [MuddleBox](https://github.com/MuddledBox/flipperzero-firmware), [Eng1n33r](https://github.com/Eng1n33r/flipperzero-firmware), [WeTox-Team](https://github.com/wetox-team/flipperzero-firmware) & of course, most of all [Flipper Devices](https://github.com/flipperdevices/flipperzero-firmware)!
