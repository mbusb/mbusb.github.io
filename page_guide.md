---
layout: page
title:      Guide
comments:   false
noToc:      true
group:      navigation
---

## Requirements:

* USB disk formatted in one of the following filesystem:-
    * FAT, NTFS, ext2/3/4 and or Btrf filesystem. However, **FAT filesystem is recommended** and ext2/3/4 and or Btrf 
    filesystems will only work under Linux.
* Live linux as an ISO file of your choice.
* Latest version of MultiBootUSB.

## Installation:

* On Windows:-
    * The windows version of multbootusb is a standalone program. No installation is required. Simply download the 
    precompiled binary (.exe) file from here:-
     http://multibootusb.org/download/
     * The program can be launched directly just by double clicking on the downloaded ".exe" file.

* On Linux:-

    **Using binary method:-**
    
    * Download the installation files (.deb and .rpm) files for various distros from here:-
    http://multibootusb.org/download/
    * Use your favourite package manager to install multibootusb.
    
    **Using source code method:-**
    
    * The install.py script provided with multibootusb should take care of all dependencies and install multibootusb.
    Assume that you have downloaded the package named "multibootusb.tar.gz" in to your home directory.
    Issue the following commands to install multibootusb:-

    tar -xf ./multibootusb.tar.gz    
    cd multibootusb    
    chmod +x ./install.py    
    sudo ./install.py    
    

## Creating live linux on USB disk:

* Creating live Linux on a USB disk involves three steps and clearly written as **Step 1**, **Step 2** and **Step 3** in 
**bold** letters on the right side of multibootusb GUI. Step wise operations are shown below:- 
    * **Step 1**
        * Insert USB disk and wait for few seconds so that Operating System can detect it.
            * All modern Linux distros should mount USB disks automatically after insertion. If not, open file manager and 
            click on the USB disk icon to mount it. The same thing can be done from terminal also. But I am not going in to details.
        * Open multibootusb by double clicking on the downloaded ".exe" file under Windows. Under Linux, multibootusb can 
        be found under system menu. On Ubuntu click on dash --> type "multibootusb" and click on the multibootusb icon.
            * Under Linux a password window will popup for user input. Provide sudo password. If you are running as root 
            then no window will popup.
        * Once multibootusb is opened you can see the list of USB disk on the combobox close to **Step 1**.The USB details are listed 
        below "Refresh USB" button. Review it and choose the disk of your desire.
        * Use the "Refresh USB" button to detect USB disks if you have inserted the disk after opening multibootusb GUI.
    * **Step 2**
        * Now the **Step 1** is over and proceed to **Step 2**. Clicking on "Browse ISO" button should bring file chooser dialog 
        and you can choose your live Linux. The choosen live Linux path will be available in the line edit for your view.
    * **Step 3**
        * The third and final step is to simply click on "Create" button available close to **Step 3** text. multibootusb will 
         analyse the ISO and check if ISO is supported. 
        * If the live Linux is supported then a "Review Selection" window will appear and wait for your confirmation. 
        The review window will indicate the selected USB disk, mount path of the disk and a selected ISO. You can create 
        live USB disk by clicking "Yes" button on the review selection window.
        * The progress bar will indicate the progress on live Linux installation. The text label just above the progress bar 
        will indicate the current operation of the installation process (like Extracting some file...).
        * You will get the completion message after successful installation of live Linux. Now the installation is 
        complete and you can reboot to live Linux after setting your BIOS to boot from USB disk.
        * After successful install, the installed distro is displayed in the list box, seen on the left side of GUI. 
        The list box will list all the distros installed via multibootusb every time you open multibootusb. 

## Adding new/additional live Linux:
* Adding addition and new live linux is simple process. Just follow the **Step 1**, **Step 2** and **Step 3** mentioned in the
     **Creating live linux on USB disk** section above. 

## Removing/Uninstalling distro:
* You can only uninstall distros installed by multibootusb. 
* To do that you must select a disto from the list and choose "Uninstall Distro" button. A Review Selection window will 
popup and ask you to confirm. Click on the Yes btton to remove installed distro. The progress bar will indicate the 
progress of the uninstall process. You will get the completion message after successful uninstall of the selected distro.
 
## Reinstalling Syslinux:
* There might be a situation you may want to install syslinux for various reasons like using other live usb creator will 
remove syslinux installation performed by multibootusb. In such a situation you can reinstall syslinux using syslinux tab.
* Go to Syslinu tab --> Install Syslinux section --> Choose any of the method listed and click on "Install" button.
* This will install syslinux on multibootusb directory in a selected USB disk.

## Edit Syslinux config files:
 * Please perform this action with caution. Any change in the path will make your distro install completely useless. 
 * You can view and edit syslinux.cfg file located under multibootusb directory using the feature provided with multibootusb.
    Syslinu tab --> Edit Syslinux.cfg section --> Click on "Edit" button. This action will open syslinux.cfg in a text editor.
    
## Test your ISO and USB with QEMU option:
 * Testing your downloaded ISO and USB installation is useful as need of rebooting your system is not required. multibootusb provides 
 an option to do this as well. 
 * QEMU binaries are shipped with Windows as default. But for Linux you need to install "qemu" package to avail this feature.  
  
    **Booting ISO**
     
     * Go to --> QEMU tab --> Boot ISO section --> Click on Browse ISO to choose an ISO file.
     * Then choose your desired ram size and click on Boot ISO button.
     * Your ISO will boot in a new separate window. 
      
    **Booting USB**
     
     * Booting USB also similar to booting ISO as mentioned above. 
     * Go to --> QEMU tab --> Boot USB section.
     * Then choose your desired ram size and click on Boot USB button.
     * Your USB as listed in the combobox (in **Step 1**) will boot in a new separate window. 

### Author
 * Sundar.