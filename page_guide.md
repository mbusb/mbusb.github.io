---
layout:     page
title:      Guide
subtitle:   Learn how to use MultiBootUSB...
comments:   false
noToc:      true
group:      navigation
---

## Table of content:  


[What does MultiBootUSB do?](#what-does-multibootusb-do)  
[Minimum Requirements](#requirements)  
[Install MultiBootUSB - Windows and Linux](#installation)  
[Creating live Linux on USB disk](#creating-live-linux-on-usb-disk)  
[Adding new/additional live Linux distro](#adding-an-additional-live-linux-distro)  
[Adding Persistence file](#adding-persistence-file)  
[Removing or Uninstalling a distro](#removing-or-uninstalling-a-distro)  
[Writing ISO image directly to USB disk](#writing-iso-directly-to-usb-disk)   
[Reinstalling Syslinux](#reinstalling-syslinux)   
[Editing Syslinux config files](#editing-syslinux-config-files)   
[Test ISO and USB with QEMU option](#test-your-iso-and-usb-with-qemu-option)  
[Using MultiBootUSB command line options](#using-multibootusb-command-line-options)  
[What if something goes wrong?](#what-if-something-goes-wrong)

---

## What does MultiBootUSB do?

MultiBootUSB allows you to do the following:

1.  Install multiple live Linux distros and other operating systems to a USB disk and make it bootable without erasing existing data.
2.  Uninstall installed OSes later.
3.  Write ISO images directly to a USB disk (GUI for Linux `dd` command).
4.  Boot ISO images and USB disks directly without rebooting your system using QEMU.
5.  Boot USB on UEFI/EFI systems through GRUB2 bootloader support (limited support).

---

## Requirements:

1. Formatted USB disk:
    * FAT32, NTFS, ext2/3/4 or Btrfs filesystem. However, **FAT filesystem is recommended** and ext2/3/4 or Btrfs filesystems will only work under Linux.
    * Keep single partition (primary) to avoid later problems.
2. **ISO** file of live Linux distro of your choice.
3. Latest release of MultiBootUSB.

---

## Installation:

* On Windows:
    * The windows version of MultiBootUSB is not a standalone program. You need to install it after download. Download the latest setup binary (.exe) file from [here](http://multibootusb.org/page_download/)
    * The installation is fairly simple. Double click on the executable and follow the on-screen instructions.

* On Linux:

    **Pre-packaged:**

    * Packages for various distros available [here](http://multibootusb.org/page_download/)

    **...or from source code:**

    **On Linux:**

     * MultiBootUSB depends on the following packages under Linux: 

        * python3-pyqt5 
        * p7zip-full 
        * parted  
        * util-linux  
        * python3-pyudev 
        * mtools 
        * python3-dbus 
        * python3-six
    * Install above packages using your package manager. Remember that package name may not be identical for all distros. You need to search equivalent package for your distro and install it.
     * `You must uninstall your previous installation of MultiBootUSB, if you have done it earlier.`
     * Download source code of stable version from [here](https://codeload.github.com/mbusb/multibootusb/zip/master) or development version from [here](https://codeload.github.com/mbusb/multibootusb/zip/devel)
     * Extract to local directory and move in to `multibootusb` directory.
     * Issue `sudo python3 ./multibootusb` command to start GUI

     **On Windows:**

     * Download and install following packages: 

        * [Python 3](https://www.python.org/downloads/windows/). I use python version 3.5 but it should work on higher versions as well. 
        * [PyQt5](https://www.riverbankcomputing.com/software/pyqt/download5) and installation instruction are [here](http://pyqt.sourceforge.net/Docs/PyQt5/installation.html)
        * [wmi](https://pypi.python.org/pypi/WMI) module
        * [pywin32](https://pypi.python.org/pypi/pywin32)
        * [psutils](https://pypi.python.org/pypi/psutil)
        * [Git](https://git-scm.com/download/win), if you wish to contribute back to MultiBootUSB project

    * `Installation and configuration of above packages/ modules is not a part of this documentation. You must use Google for that.`
     * If you have installed python correctly on windows, it is recommanded that you use `pip3.exe` for installing above packages.
     * Download source code of stable version from [here](https://codeload.github.com/mbusb/multibootusb/zip/master) or development version from [here](https://codeload.github.com/mbusb/multibootusb/zip/devel)
     * Open command prompt with admin privilage and move in to `multibootusb` directory.
     * Issue `python3.exe multibootusb` command to start GUI

---

## Creating live Linux on USB disk:

* Creating bootable live Linux on a USB disk essentially involves three steps:

  1. Step 1	- Insert USB disk and start the program
  2. Step 2 - Choose your ISO
    3. Step 3- Click `Install distro` button.

  * **Step 1- Insert USB disk and start the program**
  * Insert USB disk and wait for a few seconds so that operating oystem can detect it.

  <div style="text-align:center"><img src ="../img/select-usb-disk.png" /></div>
  ​	
  * `Linux:`
    * All modern Linux distros should mount USB disks automatically after insertion. MultiBootUSB also has function to auto mount USB drive. 
      However, if you still find your USB disk is not mounted, then open file manager and 
      click on the USB disk icon to mount it. 
    * MultiBootUSB needs administrator privileges to run. When running as normal user, a password window will popup and ask for your password.

  * `Windows:` Open MultiBootUSB under `Start --> Program Files --> MultiBootUSB --> Click MultiBootUSB`

  * Once started, the list of USB disks can be found under the **Select USB disk** combo box.
    You can find the details of currently selected USB disks just below combo box.

  * Use the `Detect Drives` button to detect USB disks inserted after starting the program.

  * You can click on `All Drives` option to show all connected drives (including fixed system drives). **Be careful with this option!**

* **Step 2 - Choose your ISO**
  * Clicking on `Browse` button located next to `select image` text, should bring file chooser dialog.
    The chosen ISO path will be available in the line edit for your review.

  <div style="text-align:center"><img src ="../img/browse-iso.png" /></div>

* **Step 3 - Click `Install distro` button**
  * The third and final step is to simply click on `Install distro`.
     MultiBootUSB will check if ISO is supported by the program.

   <div style="text-align:center"><img src ="../img/install-distro.png" /></div>

  * If the live Linux distro is supported, then a `Review Selection` window will appear and wait for your confirmation. 
    The review window will indicate the selected USB disk, mount path of the disk and the selected ISO.

  * Choose **Yes** if you are ready to proceed.

  <div style="text-align:center"><img src ="../img/review-selection.png" /></div>   

  * Wait for the program to install ISO on a disk. If the installation is successful, the distro name 
    should appear in the list box. The list box will show all the distros installed every time you open MultiBootUSB.

  <div style="text-align:center"><img src ="../img/install-progress.png" /></div>
  ---
  <div style="text-align:center"><img src ="../img/install-success.png" /></div>
  ---
  <div style="text-align:center"><img src ="../img/install-distro-list.png" /></div>

---

## Adding an additional live Linux distro:
* You can follow **Step 1**, **Step 2** and **Step 3** mentioned above for adding a new distro again.

---

## Adding persistence file:
* Only distros based on Ubuntu, Fedora and Debian are supported.  

* Once you complete the **step 2** (Choose an ISO), MultiBootUSB will detect the type of
  distro and a persistence size chooser slider would appear below MultiBootUSB tab. 
   The maximum size of the persistence also automatically calculated according to the USB disk filesystem.

<div style="text-align:center"><img src ="../img/persistence-bar.png" /></div>

* Choose the desired persistence size by dragging the slider to right and follow the **Step 3** as usual.

* Once distro installes successfully, you will find the additional persistence file under distro install directory.

<div style="text-align:center"><img src ="../img/applying-persistence.png" /></div>   


* Reboot your system to choose your favourite distro as persistence menu will be added automatically to menu entry.


Note: Few users have reported that Debian persistence option does'nt work properly.

---

## Removing or uninstalling a distro:
* You can only uninstall distros installed by MultiBootUSB.

 <div style="text-align:center"><img src ="../img/remove-distro.png" /></div>

* Select distro from the list and click `Uninstall Distro`.

* You will be notified after successful uninstallation.

---

## Writing ISO directly to USB disk:

`Be warned that this method will destroy all data on target USB disk.`  

* MultiBootUSB also has an option to write ISO file directly to an USB disk.
   You can choose this option if any of the above method fails to create live usb disk.

* You can think of this method as a GUI to `dd` under Linux. In fact, it actually uses `dd` for writing to disk.

 <div style="text-align:center"><img src ="../img/write-image-to-disk.png" /></div>

 * To write to USB disk, you need to choose, the USB disk, ISO image and click on the 
    `Write image to disk` push button available under **Write image to disk** tab.

 * A review window will appear for confirmation and select yes to proceed. Once selected, ISO writing will start and progress will be indicated in progressbar.

 <div style="text-align:center"><img src ="../img/imager-progress.png" /></div>

 * Please note that you need to select the whole disk `/dev/sdb` and not the device partition `/dev/sdb1`.

 * You need to format the USB disk if you have to revert back to original state and start using nondestructive method. 


---

## Reinstalling Syslinux:
* There may be a situation when you want to install Syslinux for various reasons (e.g. using other live USB creator will remove Syslinux installation performed by MultiBootUSB). In such cases you can reinstall Syslinux from the `Install syslinux` tab.

<div style="text-align:center"><img src ="../img/install-syslinux.png" /></div>

* First, choose an USB disk partition (eg. **/dev/sdb1** or G:), then choose method and click **Install**.

* This will install syslinux in the **multibootusb** directory on the selected USB partition.

---

## Editing Syslinux config files:

 * **Please perform this action with caution. Any change in the path will make your distro install completely useless.**

 * View and edit syslinux.cfg file from the `Install Syslinux` tab.
    This action will open syslinux.cfg in a default text editor.

---

## Test your ISO and USB with QEMU option:
 * Test your downloaded ISOs and USB disks without rebooting your system.

 * QEMU binaries are shipped with Windows setup file by default. For Linux you need to install "qemu" package to enable this feature.  

  <div style="text-align:center"><img src ="../img/boot-qemu.png" /></div>

   **Booting ISO**

   <div style="text-align:center"><img src ="../img/boot-qemu-iso.png" /></div>

   * Go to `Boot ISO/USB --> Browse ISO --> Choose RAM size --> Click on Boot ISO`.

   * Your ISO will boot in a separate window.

   * Maximum RAM size is currently limited to 2GB.


   **Booting USB**

   <div style="text-align:center"><img src ="../img/boot-qemu-usb.png" /></div>
​     
   * Go to `Boot ISO/USB --> Select USB Disk --> Choose RAM size --> Click on Boot USB`.

   * Your USB disk listed in the combobox will boot in a separate window.

   * `Linux:` You must select the whole disk (e.g. **/dev/sdb**) and **NOT** the device partition (e.g. **/dev/sdb1**).

---

## Using MultBootUSB command line options:

 * You can invoke command line options using `multibootusb -c`.
 * Windows users must use source code to avail this option.
 * Here is the text retrieved using `multibootusb -c -h` command and 
    ensure to run with admin privilege:

```sh
An advanced MultiBoot live USB creator which can be used from the command line or via a GUI.

Usage: python3 multibootusb [option(s)]

Options:
  -h or --help        :   Print this help message and exit
  -c or --command     :   Invoke command line usage.  This option is required;
                          if omitted, the GUI will be launched.
  -i or --iso         :   Path to ISO file(s).  If many ISOs are supplied,
                          they should be separated by ',' with no spaces in
                          between.
  -t or --target      :   Path to target USB device partition (e.g. "/dev/sdb1").
  -y or --yes         :   Default yes for user input during install.
                          Will not wait for user.
  -u or --uninstall   :   List and uninstall distro from an USB disk.
  -d or --debug       :   Enable debug messages (very verbose!)

```

Example for making a bootable USB from the command line:

```sh
Linux:
    python3 multibootusb -c -i ../../favourite.iso -t /dev/sdb1

Windows:
    python3 multibootusb -c -i ../../favourite.iso -t G:
```

Example for uninstalling a distro from a USB:

```sh
Linux:
    python3 multibootusb -c -u -t /dev/sdb1

Windows:
    python3 multibootusb -c -u -t G:
```

Example for installing multiple distros without user intervention:

```sh
Linux:
    python3 multibootusb -c -y -i ../../favourite.iso,../../other-distro.iso -t /dev/sdb1

Windows:
    python3 multibootusb -c -i ../../favourite.iso,../../other-distro.iso -t G:

```

---

## What if something goes wrong?

 * Check if your issue is addressed in the Frequently Asked Section (FAQ) [here](http://multibootusb.org/page_faq) .
 * If not raise an issue at [Github Issue Tracker](https://github.com/mbusb/multibootusb/issues)

---
