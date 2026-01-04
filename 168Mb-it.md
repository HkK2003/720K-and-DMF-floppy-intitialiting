## Floppy Disk DMF (1,68Mb)

#### Distribution Media Format

Il **Distribution Media Format** (DMF) è un formato per floppy disk usato da *Microsoft* per distribuire software, che permette di memorizzare 1680 Kb di dati su un singolo dischetto da 3½ pollici anziché i canonici 1440 Kb.
Il primo software distribuito da Microsoft in questo formato fu la revisione C del pacchetto Office 4.x.
fonte: [wikidedia](https://it.wikipedia.org/wiki/Distribution_Media_Format)

Questo formato di floppy, viene letto e riconosciuto nativamente dal sistema operativo a partire da MS-DOS 6.2 (Windows 3.1), ma non può essere copiato utilizzando i tools di sistema per la sua differente geometria:

|         | 1,44 |     DMF     |
| :--------: | :----: | :-----------: |
| Tracce  |  80  |     80     |
| Settori |  18  |     21     |
| Cluster | 512 | 1024 o 2048 |

Il metodo che vi illustrerò per formattare i floppy in modalità **DMF**, prevede l'utilizzo di tre software gratuiti:

- [fdformat](https://github.com/christoh/fdformat)
  - utility che gira in ambiente MS-DOS che ci permetterà di effettuare l'effettiva formattazione;
  - [la licenza](https://github.com/christoh/fdformat?tab=License-1-ov-file) ci permette libero utilizzo di questo software purché non a scopi commerciali.
- [FreeDOS](https://freedos.org/)
  - a meno che non abbiate un vecchio computer con MS-DOS installato, dobbiamo creare un ambiente a 32 bit in eseguire *fdformat*. FreeDOS ci permette di creare questo ambiente;
  - la licenza [Creative Commons Attribution ShareAlike](https://creativecommons.org/licenses/by-sa/4.0/) ci permette di usare, modificare, distribuire questo programma per qualsiasi fine.
- solo per ambiente MS-Windows [rufus](https://rufus.ie/it/)
  - famosissima utiliy che ci permetterà di creare una memoria usb avviabile con FreeDOS;
  - nota di merito per questo sviluppatore che realizza questo tools senza nemmeno voler mettere il pulsante *donazioni* ;
  - [la licenza GPL-3.0](https://github.com/pbatard/rufus?tab=GPL-3.0-1-ov-file) ci permette libero utilizzo di questo software anche a scopi commerciali a patto che vengano rilasciati a nostra volta i sorgenti.

#### Preparazione USB con FreeDOS avviabile con sistema Windows
Dopo aver scaricato **Rufus** aprite la sua interfaccia grafica, inserite una chiavetta usb anche piccola (bastano 2Gb) dopo di che seguite la seguente procedura:

![Rufus](/assets/rufus_it_arrow.png)

1. selezionare il device su cui scrivere l'immagine
2. selezionare dal menu a tendina la voce *Free DOS*
3. avviate la scrittura dell'immagine

Ora dobbiamo procurarci il binario di **fdformat**, possiamo andare a scaricare i sorgenti da [GitHub](https://github.com/christoh/fdformat), oppure scaricare in un unico pacchettino che contiene sia i sorgenti che il binario già compilato da [questo link](http://ftp.sunet.se/mirror/archive/ftp.sunet.se/pub/simtelnet/msdos/diskutil/fdfrm18.zip).

Se il precedente link non dovesse funzionare, ho caricato il medesimo pacchetto in questo repository, pertanto è reperibile anche [quì](/assets/fdfrm18.zip).
Una volta recuperato il binario (fdformat.exe), non dobbiamo fare altro che copiarlo nella directory principale della pendrive.

Ora sarà sufficiente avviare il nostro sistema da chiavetta usb, ma solo dopo aver collegato il lettore floppy al computer (se si tratta di un letore USB come in questo caso).

Una volta che il sistema verrà avviato e vedremo il prompt di comando;

Sarà sufficiente digitare il seguente comando per esefuire la formattazione da 1,68Mb:

```
FDFORMAT A: F168
```

*** 

### Metodo GNU/Linux

sudo fdisk /dev/sdb
sudo parted /dev/sdb mkpart primary fat32 0% 1.68MB
sudo mkfs.vfat /dev/sdb1

#Secondo metodo
dd if=/dev/zero of=/tmp/floppy.img bs=1024 count=1680
mkfs.vfat /tmp/floppy.img
sudo dd if=/tmp/floppy.img of=/dev/sdb bs=1M

In chiusura, vi lascio le note che rilasciava **winimage** a proposito del formato DMF. Con l timore che possano scomparire, le ho riportate per intero in [questa pagina in lingua inglese](/winimage_DMF.md).

### 🇮🇹 [Italian home page](/readme.md)

### 🇬🇧 [English home page](/readme-en.md)

https://it.wikipedia.org/wiki/Distribution_Media_Format
http://justsolve.archiveteam.org/wiki/DMF_(Distribution_Media_Format)
https://forum.winworldpc.com/discussion/7406/formatting-floppies-in-1-68-mb

https://en.wikipedia.org/wiki/Fdformat
