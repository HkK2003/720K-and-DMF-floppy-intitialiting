## Floppy Disk 720 Kb

I sistemi operativi moderni non contemplano più la formattazione di dischi nel formato 720Kb, o meglio, non la supportano tramite il tool grafico (GUI), ma continua ad essere possibile effettuare questa operazione tramite riga di comando (CLI).

Ora vedremo come effettuare questa operazione con:
- [Gnu/Linux (Debian)](#Formattare-un-Floppy-disk-da-720Kb-in-ambiente-GNU/Linux)
- [MS-Windows](#formattare-un-floppy-disk-da-720kb-in-ambiente-ms-windows)

### Formattare un Floppy disk da 720Kb in ambiente GNU/Linux

Per questa guida ho utilizzato Debian, ma i comandi possono essere adattati anche ad altri sistemi.

Dopo aver collegato il lettore floppy USB ed inserito il disco da 720Kb, aprite una finestra di terminale.
Come prima cosa, dobbiamo capire con che nome di device è stato riconosciuto il nostro floppy, io credo che la maniera più semplice sia digitare:

```
lsblk
```

e l'output dovrebbe essere di questo tipo:

![lsblk](/assets/deb_lsblk.png)

Come si può vedere, il floppy viene riconosciuto come device e non come floppy.
Pertanto tutte i vecchi tools per floppy che tentano di accedere ai device `/dev/fd0` o `/dev/fd1` non sono più utilizzabili.
Volendo ancora utilizzare una utility specifica per floppy, io vi suggerisco di installare `ufiformat`.
Utilizzando sistemi basati su debian, potete installarlo con questo comando:

```
sudo apt update && sudo apt install ufiformat
```

![install_ufiformat](/assets/deb_install_ufiformat_small.png)

Una volta installato, basterà digitare questo comando sostituendo **X** con il device che abbiamo individuato in precedenza con `lsblk`:

```
sudo ufiformat -f 720 -v /deb/sdX
```

Nel mio caso userò **sdb**:

![ufiformat](/assets/deb_ufiformat.png)

Attenzione, dovete inserire un floppy da 720Kb, altrimenti il sistema vi avviserà che c'è un errore nel formato.

![ufiformat_error](/assets/deb_ufiformat_type.png)

Questa è la modalità più tradizionale, ma, visto che il sistema riconosce il floppy come un normale device, è altresì possibile eseguire la formattazione con il semplice comando mkfs coome illustrato di seguito:
```
sudo mkfs.vfat /deb/sdX
```
Ovviamente sostituite X con la lettera del vostro device.

![mkfs](/assets/deb_mkfs.png)


### Formattare un Floppy disk da 720Kb in ambiente MS-Windows

Dopo aver collegato il lettore floppy USB ed inserito il disco da 720Kb, aprite una finestra di terminale (è indifferente se `CMD` o `PowerShell`) e digitate questo comando:

```
format a: /f:720
```
e dovreste ottenere un risultato simile (cdm):

![win_format](/assets/win_cmd_format.png)

anche in ambiente Microsoft viene controllata che la capacità del floppy sia effettivamente 720Kb (PowerShell):

![wind_error](/assets/win_ps_type_error.png)

dopo di che il floppy verrà riconosciuto anche in ambiente grafico:

![win_gui](/assets/win_gui_it.png)

### 🇮🇹 [Italian home page](/readme.md)
### 🇬🇧 [English home page](/readme-en.md)
