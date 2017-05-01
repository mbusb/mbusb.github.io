---
layout: 	page
title:      Guide
subtitle: 	Learn how to use MultiBootUSB...
comments:   false
noToc:      true
group:      navigation
---   

## Table of content:

[What does multibootusb do?](#what-does-multibootusb-do)  
[Minimum Requirements](#requirements)  
[Install  MultiBootUSB - Windows and Linux](#installation)  
[Creating live linux on USB disk](#creating-live-linux-on-usb-disk)  
[Adding new/additional live Linux](#adding-an-additional-live-linux)  
[Removing or Uninstalling a distro](#removing-or-uninstalling-distro)    
[Reinstalling Syslinux](#reinstalling-syslinux)   
[Edit Syslinux config files](#edit-syslinux-config-files)   
[Test ISO and USB with QEMU option](#test-your-iso-and-usb-with-qemu-option)

---

## What does multibootusb do?

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
    * The windows version of multbootusb is not a standalone program. You need to install it after download. Download the latest 
    setup binary (.exe) file from [here](http://multibootusb.org/page_download/)
    * The installation is fairly simple. Double click on the executable and follow the on-screen instructions.

* On Linux:

    **Pre-packaged:**
    
    * Packages for various distros available [here](http://multibootusb.org/page_download/)
    
    **...or from source code:**
    
    * The install.py script provided with multibootusb should take care of all dependencies and install multibootusb.
    Assuming that you have downloaded the archive named **multibootusb.tar.gz** in your home directory, issue the 
	following commands to install multibootusb:

```sh
    tar -zxf ./multibootusb.tar.gz
    cd multibootusb
    chmod +x ./install.py   
    sudo ./install.py
``` 

---

## Creating live Linux on USB disk:

* Creating bootable live Linux on a USB disk essentially involves three steps:

  1. Step 1	- Insert USB disk and start the program
  2. Step 2 - Choose your ISO
  3. Step 3	- Click `Install distro` button.
  
* **Step 1	- Insert USB disk and start the program**
	* Insert USB disk and wait for a few seconds so that operating oystem can detect it.
	
	<div style="text-align:center"><img src ="../img/select-usb-disk.png" /></div>
		
	* `Linux:`
		* All modern Linux distros should mount USB disks automatically after insertion. MultiBootUSB also has function to auto mount USB drive. 
		However, if you still find your USB disk is not mounted, then open file manager and 
		click on the USB disk icon to mount it. 
		* MultiBootUSB needs administrator privileges to run. When running as normal user, a password window will popup and ask for your password.
		
	* `Windows:` Open multibootusb under `Start --> Program Files --> multibootusb --> Click multibootusb`
	
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

## Adding additional live Linux distros:
* You can follow **Step 1**, **Step 2** and **Step 3** mentioned above for adding a new distro agan.

---

## Removing/uninstalling distro:
* You can only uninstall distros installed by multibootusb.

 <div style="text-align:center"><img src ="../img/remove-distro.png" /></div>
 
* Select disto from the list and click `Uninstall Distro`.

* You will be notified after successful uninstallation.

---

## Reinstalling Syslinux:
* There may be a situation when you want to install syslinux for various reasons (e.g. using other live usb creator will 
remove syslinux installation performed by multibootusb). In such cases situation you can reinstall syslinux from the `Install syslinux` tab.

<div style="text-align:center"><img src ="../img/install-syslinux.png" /></div>

* First, choose an USB disk partition (eg. **/dev/sdb1** or G:), then choose method and click **Install**.

* This will install syslinux in the **multibootusb** directory on the selected USB partition.

---

## Edit Syslinux config files:

 * **Please perform this action with caution. Any change in the path will make your distro install completely useless.**
 
 * View and edit syslinux.cfg file from the `Install syslinux` tab.
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
     
   * Go to `Boot ISO/USB --> Select USB Disk --> Choose RAM size --> Click on Boot USB`.
   
   * Your USB disk listed in the combobox will boot in a separate window.
   
   * `Linux:` You must select the whole disk (e.g. **/dev/sdb**) and **NOT** the device partition (e.g. **/dev/sdb1**).

---
