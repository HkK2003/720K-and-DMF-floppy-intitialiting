## Floppy Disk DMF (1,68Mb)

#### Distribution Media Format
Il **Distribution Media Format** (DMF) è un formato per floppy disk usato da *Microsoft* per distribuire software, che permette di memorizzare 1680 Kb di dati su un singolo dischetto da 3½ pollici anziché i canonici 1440 Kb.
Il primo software distribuito da Microsoft in questo formato fu la revisione C del pacchetto Office 4.x.
fonte: [wikidedia](https://it.wikipedia.org/wiki/Distribution_Media_Format)

Questo formato di flopy, viene letto e riconosciuto nativametne dal sistema operativo a partire da MS-DOS 6.2 (Windows 3.1), ma non può essere copiato utilizando i tools di sitema per la sua differente geometria:

|  | 1,44 | DMF |
| --- | ------ |
| Tracce | 80 | 80
| Settori per traccia | 18 | 21
| Dimensioni cluster (byte) | 512 | 1024 o 2048 |
| Voci nella directory principale |	224	| 16 |

Il metodo che vi illustrerò per formattare i floppy in modalità **DMF**, prevede l'utilizzo di tre software gratuiti (2 se usate un sistema GNU/Linux):
- [fdformat](https://github.com/christoh/fdformat)
	- utility che gira in ambiente MS-DOS che ci permetterà di effettuare l'effettiva formatazzione;
	- [la licenza](https://github.com/christoh/fdformat?tab=License-1-ov-file) ci permette libero utilizzo di questo sfotware purchè non a scopi commerciali.
- [FreeDOS](https://freedos.org/)
	- a meno che non abbiate un vecchio computer com MS-DOS installato, dobbia crearci un abiente a 32 bit in eseguire *fdformat*. FreeDOS ci permette di creare questo ambiente;
	- la licenza [Creative Commons Attribution ShareAlike](https://creativecommons.org/licenses/by-sa/4.0/) ci permette di usare, modificare, distribuire questo programma per qualsiasi fine.
- solo per ambiente MS-Windows [rufus](https://rufus.ie/it/)
	- famosisstima utilizy che ci permetterà di creare una memoria usb avviabiel contenete FreeDOS;
	- nota di merito per questo sviluppatore che realizza questo tools senza nemmeno vole mettere il pulsante *donazioni* ;
	- [la licenza GPL-3.0](https://github.com/pbatard/rufus?tab=GPL-3.0-1-ov-file) ci permette libero utilizzo di questo sfotware anche a scopi commerciali a patto che vengano rilasciati a nostra volta i sorgenti.


	

In clhisura, vi lascio le note che rilasciava **winimage** a proposito del formato DMF. Con l timore che possano scoparire, le ho riportate per intero in [questa pagina in lingua inglese](/winimage_DMF.md).

### 🇮🇹 [Italian home page](/readme.md)
### 🇬🇧 [English home page](/readme-en.md)


https://it.wikipedia.org/wiki/Distribution_Media_Format
http://justsolve.archiveteam.org/wiki/DMF_(Distribution_Media_Format)
https://forum.winworldpc.com/discussion/7406/formatting-floppies-in-1-68-mb

https://en.wikipedia.org/wiki/Fdformat




