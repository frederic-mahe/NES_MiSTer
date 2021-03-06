# NES for [MiSTer](https://github.com/MiSTer-devel/Main_MiSTer/wiki) 

This is an FPGA implementation of the NES/Famicom based on [FPGANES](https://github.com/strigeus/fpganes) by Ludvig Strigeus and ported to MiSTer.

## Features
 * Supports saves for most ROM games (FDS saves not currently supported)
 * FDS Support with expansion audio
 * Multiple Palette options
 * Supports expansion audio from mappers including VRC6 & 7, MMC5 and Sunsoft 5b
 * Supports many popular mappers including VRC1-7, MMC0-5, and many more (see below)
 * Supports large games such as Legend of Link and Rockman Minus Infinity

## Installation
Copy the NES_\*.rbf file to the root of the SD card. Create a **NES** folder on the root of the card, and place NES roms (\*.NES) inside this folder. The ROMs must have an iNES or NES2.0 header, which most already do. NES2.0 headers are prefered for the best accuracy. To have a game ROM load automatically upon starting the core and place it in the **NES** folder.
- boot0.rom = FDS BIOS file.  Will be used for any FDS images loaded
- boot1.rom = NES Cart file.  Can be used with boot0.rom (BIOS) in place
- boot2.rom = FDS image file.  Requires boot0.rom (BIOS)
- boot3.rom = FDS BIOS file.  Use instead of boot0.rom.  Will be used for any FDS images loaded, and will start running without an FDS image on core start

## Famicom Disk System Usage
Before loading \*.FDS files, you must first load the official, unpatched FDS BIOS. The BIOS file should be renamed to boot0.rom or boot3.rom and placed in the same folder as the ROMs (NES).  Alternatively, it can be loaded from the OSD if boot0.rom and boot3.rom don't exist. After loading the core and the bios you may select an FDS image. By default, the NES core will swap disk sides for you automatically. To suppress this behavior, hold the FDS button on the player 1 controller. The "Disk Swap" OSD option inverts this behavior (press FDS to swap disks). Currently, saves are not supported for FDS games.

## Saving and Loading
The battery backed RAM (Save RAM) for the NES does not write to disk automatically. When loading a game, you must select **Load Backup RAM** from the OSD menu. After saving in your game, you must then write the RAM to the SD card by selecting **Save Backup RAM** from the menu. If you do not save your RAM to disk, the contents will be lost next time you restart the core or switch games.

## Supported Mappers

|#||||||||||||||||
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**0**|**1**|**2**|**3**|**4**|**5**||**7**||**9**|**10**|**11**|~~12~~|**13**||**15**|
|**16**||**18**|**19**|**FDS**|**21**|**22**|**23**|**24**|**25**|**26**||**28**||**30**||
|**32**|**33**|**34**||~~36~~|**37**|**38**||~~40~~|**41**|**42**|~~43~~|~~44~~|~~45~~|~~46~~|**47**|
|**48**|~~49~~|~~50~~|~~51~~|~~52~~|~~53~~|~~54~~|~~55~~|~~56~~|~~57~~|~~58~~|~~59~~|~~60~~|~~61~~|~~62~~|~~63~~|
|**64**|**65**|**66**|**67**|**68**|**69**|**70**|**71**|**72**|**73**|**74**|**75**|**76**|**77**|**78**|**79**|
|**80**|~~81~~|**82**|~~83~~|~~84~~|**85**|**86**|**87**|**88**|**89**|~~90~~|~~91~~|**92**|**93**|**94**|**95**|
|~~96~~|**97**||~~99~~|~~100~~|**101**|||~~104~~|**105**||**107**|~~108~~|~~109~~|~~110~~|~~111~~|
|**112**|**113**|~~114~~|~~115~~|~~116~~|~~117~~|**118**|**119**|~~120~~||~~122~~|~~123~~||~~125~~|~~126~~|~~127~~|
|~~128~~|~~129~~|~~130~~|~~131~~|~~132~~|~~133~~|~~134~~|~~135~~||~~137~~|~~138~~|~~139~~|**140**|~~141~~|~~142~~|~~143~~|
|~~144~~|~~145~~|~~146~~|~~147~~|~~148~~|~~149~~|~~150~~|~~151~~|**152**|~~153~~|**154**|**155**|~~156~~|~~157~~|**158**|**159**|
|~~160~~|~~161~~|~~162~~|~~163~~|~~164~~|**165**|~~166~~|~~167~~|~~168~~|~~169~~|||||||
|||||**180**|~~181~~|~~182~~|~~183~~|**184**|**185**|~~186~~|~~187~~|~~188~~|~~189~~|**190**|**191**|
|**192**|~~193~~|**194**|**195**|~~196~~||~~198~~|~~199~~|~~200~~|~~201~~|~~202~~|~~203~~|~~204~~|~~205~~|**206**|**207**|
|~~208~~|~~209~~|**210**|~~211~~|~~212~~|~~213~~|~~214~~|~~215~~|~~216~~|~~217~~|**218**||||~~222~~||
|~~224~~|~~225~~|~~226~~|~~227~~|**228**|~~229~~|~~230~~|~~231~~|**232**|~~233~~|**234**|~~235~~|~~236~~|~~237~~|||
|~~240~~|~~241~~|~~242~~|~~243~~|~~244~~|~~245~~|~~246~~||~~248~~|~~249~~|~~250~~|~~251~~|~~252~~||~~254~~|~~255~~|

Key: **Supported**, ~~Not Supported~~. Mappers that are not existent or not useful are blank.

