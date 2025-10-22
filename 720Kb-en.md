### 720 Kb Floppy Disk

Modern operating systems no longer support formatting 720KB floppies, or rather, they do not support this format from the GUI, but now we will see how to perform this operation from the CLI.

Now we could se how perform this opeation whit:
- [Gnu/Linux (Debian)](#Format-720Kb-Floppy-disk-with-GNU/Linux-GNU/Linux)
- [MS-Windows](#Format-720Kb-Floppy-disk-with-MS-Windows)

### Format 720Kb Floppy disk with GNU/Linux

For this guide, I used Debian, but the commands can be adapted to other systems as well.

After connecting the USB floppy drive and inserting the 720KB disk, open a terminal window.
First, we need to figure out how our floppy disk was recognized. I think the easiest way is this command:

```
lsblk
```

You should have a similar output:

![lsblk](/assets/deb_lsblk.png)

As you can see, the floppy is recognized as device and as floppy.
For this reason, all old tools to manage floppy that use the device `/dev/fd0` o `/dev/fd1` are no longer working.

If you still want to use a floppy-specific utility, I suggest installing `ufiformat`.
On Debian-based systems, you can install it with this command:

```
sudo apt update && sudo apt install ufiformat
```

![install_ufiformat](/assets/deb_install_ufiformat_small.png)

Once installed, just type this command replacing **X** with the device previously identified with `lsblk`:

```
sudo ufiformat -f 720 -v /deb/sdX
```

In my case the device is **sdb**:

![ufiformat](/assets/deb_ufiformat.png)

Please note that you must insert a 720KB floppy disk, otherwise the system will warn you that there is an error.

![ufiformat_error](/assets/deb_ufiformat_type.png)

This is the most traditional way, but, since the system recognizes the floppy disk as a normal device, it is also possible to format it with the  `mkfs` command as illustrated below:

```
sudo mkfs.vfat /deb/sdX
```
Obviously replace **X** with the letter of your device.

![mkfs](/assets/deb_mkfs.png)

### Format 720Kb Floppy disk with MS-Windows

After connecting the USB floppy drive and inserting the 720KB disk, open a terminal window (it doesn't matter whether it's `CMD` or `PowerShell`) and type this command:

```
format a: /f:720
```
You should have a similar output (PowerShell):

![win_format](/assets/win_ps_format.png)

Also MS Operating System regognize if the floppy capacity is different from 720Kb (CMD):

![win_erroe](/assets/win_cmd_type_error.png)

After this, the floppy will also be recognized in the graphical environment:

![win_gui](/assets/win_gui_en.png)

## 🇬🇧 [English home page](/readme-en.md)
## 🇮🇹 [Italian home page](/readme.md)
