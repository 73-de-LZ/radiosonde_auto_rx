RS
==

### Automatic Radiosonde RX Station Extensions ###
This fork of rs1279's excellent RS codebase is intended to produce a set of utilities to allow automatic
reception and uploading of radiosonde positions to APRS-IS and Habitat. 
Eventually I hope to have an automatic receive station installed at a strategic location in the 
Adelaide South Australia area, to better assist with gathering of RS41 radiosondes once they start being
launched.

The key changes from the RS master codebase are:
* Modification of rs92gps and rs41 for easier output parsing
* Addition of the auto_rx folder, containing automatic RX scripts
  
#### Wetterballon-Radiosonden  400-406 MHz  

* Decoder: <br />
  (compile: `gcc <decoder.c> -lm -o <decoder>`)

  `RS/rs92`: RS92-SGP, RS92-AGP <br />
  `RS/rs41`: RS41-SG(P) <br />
  `RS/dropsonde`: RD94 <br />
  `RS/m10`: M10 <br />
  `RS/dfm`: DFM-06, DFM-09 <br />
  `RS/imet`: iMet-1-AB, iMet-1-RS <br />
  `RS/c34`: C34, C50 <br />
  `RS/lms6`: LMS6 <br />
  `RS/mk2a`: MkIIa <br />
  `RS/meisei`: Meisei <br />

  `RS/rs_module`: separate Module, z.Z. RS92, RS41 <br />


  Die Decoder erwarten das FM-demodulierte wav-Audio des empfangenen Signals (kann auch mit 
sox gestreamt werden). Die weitere Demodulation ist sehr einfach gehalten (Nulldurchgaenge), 
so dass die Decodierung empfindlich auf Stoerungen reagiert und ein gutes Signal braucht. 
Oft hilft schon, z.B. mit sox einen lowpass-Filter zwischenzuschalten (fuer C34/C50 und iMet-1-RS
wird DFT verwendet). Je nach Empfangsgeraet oder SDR-Software kann das Signal invertiert sein 
(ebenso fuer neuere DFM-09 gegenueber DFM-06).

  `RS/ecc` - error correction codes (Reed-Solomon/BCH) <br />


* Diverses:

  `RS/IQ`: Beispiele für Behandlung von IQ-Signalen <br />
  `RS/scan`: einfaches Beispiel, wie man mit rtl_sdr-tools automatisch scannen kann <br />


* Videos & Bilder:

  https://www.youtube.com/user/boulderplex  
  https://www.flickr.com/photos/116298535@N06/albums/72157644377585863  


* erläuternde Beiträge:

  http://www.fingers-welt.de/phpBB/viewtopic.php?f=14&t=43&start=525#p50955  
  http://www.fingers-welt.de/phpBB/viewtopic.php?f=14&t=43&start=550#p64707  
  http://www.fingers-welt.de/phpBB/viewtopic.php?f=14&t=43&start=700#p75202  
  http://www.fingers-welt.de/phpBB/viewtopic.php?f=14&t=43&start=1000#p87987  
  http://www.fingers-welt.de/phpBB/viewtopic.php?f=14&t=43&start=1000#p88325  
  http://www.fingers-welt.de/phpBB/viewtopic.php?f=14&t=43&start=1000#p88845  
  http://www.fingers-welt.de/phpBB/viewtopic.php?f=14&t=43&start=1850#p155677  

