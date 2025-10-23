## Winimage

Winimage was a Shareware software that allowed you to copy disks with exotic formats, such as DMF disks

![Winimage](/assets/winimage-screenshot-461707024.png)

The software home page is empty, but if you want to take a look at it, it is still available on the net. I won't tell them about its use, because I prefer the FOSS solutions that I have illustrated, but I will report an examination on the DMF format that (at the time I made this guide) is still readable on their site, but which I report in full below for backup purposes.

[link to the examination on the Winimage website](https://www.winimage.com/wimushlp/wini1a1y.htm)

#### the examination

**Disclaimer**: *The following text is copied entirely from the winimage website, **I assume no responsibility** for what is written*

---

## About DMF
**DMF and 1.68 MB** formats are the same physical format of 80 tracks and 21 sectors per track. The 1.68 MB format has 224 entries in the root directory, and a cluster size is 512 bytes. DMF format has only 16 entries in the root directory (you need create a subdirectory to copy more than 16 files), and the cluster size is 1024 (DMF 1024) or 2048 bytes (DMF 2048). You can check the cluster size in the Image Information...

Microsoft uses DMF 2048 for the floppy version of some of their newer software. Windows 95/98/Me and Windows NT/2000/XP/2003 read and write directly in DMF format. You will need FDREAD for this format under MSDOS or Windows 3.1.

1.72 MB format uses 82 tracks and is not compatible with Windows NT/2000/XP/2003. 1.68 MB and DMF are the same physical format, and are compatible with Windows NT/2000/XP/2003. **I highly suggest you don't use 1.72 MB** .

Some Microsoft DMF floppy disks contain information to make them write-protected under Windows 95/98 or Windows NT 3.5x. To write to these floppy disks, you will need to reformat them first to remove this.

The DMF 2048 format is often used for distribution floppies under Windows 95/98 and Windows NT.

Under Windows 95/98, unlike other operating systems, formatting for DMF uses the BIOS. This may cause compatibility problem on some computers. If you experience such problems, I suggest you try the following:

- If your system has a flash BIOS, upgrade the BIOS to the latest release. If you have an Intel motherboard, you can find BIOS upgrades at ftp://ftp.intel.com/pub/bios.

- Format the floppy to 1.44 MB before trying DMF.

- Try to get more conventional memory (ideally by having a near empty config.sys) .

- Try using both winimage.exe and winima16.exe under Windows 95/98. (Ignore the message from winima16.exe that suggests not running using this O.S.) . Note : The latest 16 bits version of WinImage is WinImage 3.0. The latest 32 bits version of WinImage compatible with Windows 3.1+Win32s is 6.0.

- download FDFormat (from http://www.winimage.com/othertl.htm ). Under DOS (or the Windows 95/98/Me command line without the graphical interface - this is accomplished by pressing F8 and selecting 6 when booting) try 'FDFORMAT A: F168'. As is true with WinImage, FDFormat uses the BIOS. If FDFormat cannot format a disk at 1.68 MB, WinImage will also be unable to. FDFormat package contain also FDRead to read DMF/1.68 MB/1.72 MB floppy under MSDos.

Some problems with DMF formatting under Gateway 2000 computers can be solved by downloading a BIOS update from the Intel FTP (ftp://ftp.intel.com/pub/bios) or their web site (http://www.intel.com).

Under Windows 95/98, the following options are available In the Options Settings, Disk tab:

- If Use new DMF format technology and Use new DMF technology for writing data are both selected, WinImage will use the new 3.0 DMF formatting code by default.

- If Use new DMF format technology and Use new DMF technology for writing data are both unselected, WinImage will use a slightly fixed version of the 2.5 DMF formatting code.

- If Use new DMF format technology is unselected, WinImage uses the same code as version 2.20 to format.

**Some DMF related problems** can be corrected by adjusting the disk gap. To change this setting, you must modify the registry. Be very careful! The key value to modify is HKEY_CURRENT_USER\Software\WinImage\iGapDmf. A value of "0" specifies the standard DMF GAP. A WinImage user needs "17" for a 2.88 driver.

Please report any problems solved by modifying the GAP.

---

### 🇮🇹 [Italian home page](/readme.md)
### 🇬🇧 [English home page](/readme-en.md)
