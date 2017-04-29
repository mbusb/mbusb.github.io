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

MultiBootUSB allows you to do the following:-

1.  Install multiple live Linux and other Operating Systems in to a USB disk and make it bootable without erasing existing data.
2.  Ability to uninstall installed OS later.
3.  Write ISO image directly to a USB disk (you can think of GUI for Linux `dd` command).
4.  Boot ISO images directly without rebooting your system using QEMU option.
5.  Boot bootable USBs without rebooting your system using QEMU option.
6.  Boot USB on UEFI/EFI system through GRUB2 bootloader support (limited support).

---

## Requirements:

1. USB disk formatted in one of the following filesystem:-
    * FAT32, NTFS, ext2/3/4 or Btrf filesystem. However, **FAT filesystem is recommended** and ext2/3/4 or Btrf filesystems will only work under Linux.
    * Keep single partition (primary) for avoiding failure later.
2. Live Linux/OS as an **ISO** file of your choice.
3. Latest release of MultiBootUSB.

---

## Installation:

* On Windows:-
    * The windows version of multbootusb is not a standalone program. You need to install it on windows after download. Download the latest 
    precompiled setup binary (.exe) file from 
     [here](http://multibootusb.org/page_download/)
     * The installation is farley simple. Double click on the executable and follow the onscreen instruction.

* On Linux:-

    **Using binary method:-**
    
    * Download the installation and source files for various distros from 
    [here](http://multibootusb.org/page_download/)
    * Use your favourite package manager to install multibootusb.
    
    **Using source code method `Linux`:-**
    
    * The install.py script provided with multibootusb should take care of all dependencies and install multibootusb.
    Assume that you have downloaded the package named **multibootusb.tar.gz** in to your home directory.
    Issue the following commands to install multibootusb:-

```sh
    tar -xf ./multibootusb.tar.gz
    cd multibootusb
    chmod +x ./install.py   
    sudo ./install.py
``` 

---

## Creating live linux on USB disk:

* Creating bootable live Linux on a USB disk essentially involves three steps:-

  1. Step 1 	:	Insert USB disk and start the program
  2. Step 2	    :	Choose your ISO
  3. Step 3.	:	Click on Install distro push button.
  
  Read the detailed instruction with screenshots below for further reading.

* **Step 1**
	* Insert USB disk and wait for few seconds so that Operating System can detect it.
	
	<div style="text-align:center"><img src ="../img/select-usb-disk.png" /></div>
		
	* `Linux:` All modern Linux distros should mount USB disks automatically after insertion. MultiBootUSB also has function to auto mount USB drive. 
		However, if you still find your USB disk is not mounted, then open file manager and 
		click on the USB disk icon to mount it. 
		
	* `Windows:` Open multibootusb under `Start --> Program Files --> multibootusb --> Click multibootusb`
	
	    `Linux`: MultiBooUSB can be found under `system menu`. On Ubuntu click on `Dash --> type "multibootusb"` and click on the multibootusb icon.
		For GNOME3 based distros, select `Activities overview` and type `multibootusb` and click on the multibootusb icon. 
		
		* If you are running as normal user, a password window will popup for user input. Provide sudo password.
		 
	* Once multibootusb GUI is opened, you can see the list of USB disk in the combobox close to **Select USB disk** text. You can find the details of currently selected USB disks just below combobox.
	
	* Use the `Detect Drives` button to detect USB disks if you have inserted the disk after opening multibootusb GUI.
	
	* You can click on `All Drives` option to show all connected drives. You must be careful with option. 
	  
	 
* **Step 2**
	* Clicking on `Browse` button located next to `select image` text, should bring file chooser dialog. Navigate to 
	choose an ISO. The chosen ISO path will be available in the line edit for your review.
	
	<div style="text-align:center"><img src ="../img/browse-iso.png" /></div>
	
* **Step 3**
	* The third and final step is to simply click on `Install distro` button. multibootusb will 
	 analyse the ISO and check if ISO is supported by the program.
	  
	 <div style="text-align:center"><img src ="../img/install-distro.png" /></div>
	 
	* If the live Linux is supported then a `Review Selection` window will appear and wait for your confirmation. 
	The review window will indicate the selected USB disk, mount path of the disk and a the name of a selected ISO.
	 
	* Choose **Yes** if you are OK with the selections.
	
	<div style="text-align:center"><img src ="../img/review-selection.png" /></div>   
	
	* Wait for a moment for program to installation ISO on a disk. If your installation is success, name os an ISO 
	should appear in the listbox. The list box will list all the distros installed via multibootusb every time you open multibootusb.
	
	<div style="text-align:center"><img src ="../img/install-progress.png" /></div>
	---
	<div style="text-align:center"><img src ="../img/install-success.png" /></div>
	---
	<div style="text-align:center"><img src ="../img/install-distro-list.png" /></div>

---

## Adding an additional live Linux:
* You can follow **Step 1**, **Step 2** and **Step 3** mentioned above for adding a new distro agan.

---

## Removing or uninstalling distro:
* You can only uninstall distros installed by multibootusb.

 <div style="text-align:center"><img src ="../img/remove-distro.png" /></div>
 
* To do that you must select a disto from the list of installed distros and choose "Uninstall Distro" button. A Review Selection window will 
popup and ask you to confirm. 

* Click on the Yes btton to remove installed distro. The progress bar will indicate the 
progress of the uninstall process. You will get the completion message after successful uninstall of the selected distro.

---

## Reinstalling Syslinux:
* There may be a situation you want to install syslinux for various reasons like using other live usb creator will 
remove syslinux installation performed by multibootusb. In such cases situation you can reinstall syslinux using syslinux tab.

<div style="text-align:center"><img src ="../img/install-syslinux.png" /></div>

* Go to `Install Syslinux`, choose an USB disk partition (eg. **/dev/sdb1**), choose method and click on **Install** button.

* This will install syslinux on **multibootusb** directory in a selected USB disk.

---

## Edit Syslinux config files:

 * Please perform this action with caution. Any change in the path will make your distro install completely useless.   
 
 * You can view and edit syslinux.cfg file located under multibootusb directory using the feature provided with multibootusb.
    `Install Syslinux --> Edit Syslinux.cfg --> Click on Edit` button. This action will open syslinux.cfg in a default text 
    editor for your review.

---

## Test your ISO and USB with QEMU option:
 * Testing your downloaded ISO and USB installation is useful as need of rebooting your system is not required. multibootusb provides 
 an option to do this as well. 
 
 * QEMU binaries are shipped with Windows setup file by default. But for Linux you need to install "qemu" package to avail this feature.  
  
  <div style="text-align:center"><img src ="../img/boot-qemu.png" /></div>
  
   **Booting ISO**
   
   <div style="text-align:center"><img src ="../img/boot-qemu-iso.png" /></div>
   
   * Go to `Boot ISO/USB --> Browse ISO --> Choose RAM size --> Click on Boot ISO`.
   
   * Your ISO will boot in a separate window.
   
   * Maximum RAM size supported as of now limited to 2GB.
   
      
   **Booting USB**
   
   <div style="text-align:center"><img src ="../img/boot-qemu-usb.png" /></div>
     
   * Booting USB also similar to booting ISO as mentioned above. 
   
   * Go to `Boot ISO/USB --> Select USB Disk --> Choose RAM size --> Click on Boot USB`.
   
   * Your USB disk as listed in the combobox will boot in a separate window.
   
   * `Linux:` You must select the whole disk (**/dev/sdb**) and not the device partition.

---