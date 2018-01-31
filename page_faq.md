---
layout: 	page
title:      FAQ
subtitle: 	Answers for the most commonly asked questions...
comments:   false
noToc:      true
group:      navigation
---   

## Table of content:

[What should I do if I get a message `"Sorry. xyz.iso is not supported at the moment"`?](#what-should-i-do-if-i-get-a-iso-not-supported-error-message)      
[Where is multibootusb log file located?](#where-is-multibootusb-log-file-located)   
[Can you help me in adding my favourite distro in to multibootusb?](#can-you-help-me-in-adding-my-favourite-distro-in-to-multibootusb)    
[Live USB created using multibootusb works perfectly. But I cant install in to hard disk](#i-cant-install-live-usb-created-using-multibootusb-on-to-my-computers-hard-disk)      
[Does multibootusb support exFAT file system?](#does-multibootusb-support-exfat-file-system)  
[Does multibootusb support GRUB boot loader?](#does-multibootusb-support-grub-boot-loader)  
[Does multibootusb support EFI/UEFI booting?](#does-multibootusb-support-efi-or-uefi-booting)  
[Does multibootusb support persistence?](#does-multibootusb-support-persistence)  
[Your package for my favourite distro never worked for me. What can I do now](#your-package-for-my-favourite-distro-never-worked-for-me-what-can-i-do-now)        
[Is there a support for command line option instead of GUI?](#is-there-a-support-for-command-line-option-instead-of-gui)  
[Debian error "no common CD ROM drive was detected" during installation](#debian-error-no-common-cd-rom-drive-was-detected-during-installation)       
[I found a bug and would like to submit a patch. How do I do that](#i-found-a-bug-and-would-like-to-submit-a-patch-how-do-i-do-that)     
[How often multibootusb is released?](#how-often-multibootusb-is-released)   
[How do you give version number to each release?](#how-do-you-give-version-number-to-each-release)  
[Your english is pathetic](#your-english-is-pathetic)  

---

## What should I do if I get a iso not supported error message?

 * [Read this information carefully](#can-you-help-me-in-adding-my-favourite-disto-in-to-multibootusb).
 * You can submit this issue in github page at [https://github.com/mbusb/multibootusb/issues](https://github.com/mbusb/multibootusb/issues). 
 * It is OK to send it on email but it is not reccommended. The github issue will remind me of pending work or someone else can also can read and solve your issue. 

---

## Where is multibootusb log file located?

 * `Linux :`  **'/tmp/multibootusb.log'**
 * `Windows :` **'C:\Program Files (x86)\multibootusb\multibootusb.log'** 

---

## Can you help me in adding my favourite distro in to multibootusb?

 * Yes I can. But you have to help me to help you. Simply saying "my distro xyz.iso is not working" does not convey anything. 
 I need **at least** the following information to try from my side:
   1. Host Operating system information (Linux/ Windows) and version.
   2. The ISO your are trying to create and ISO download link.
   3. USB disk information such as partition type, size, file system and so on.
   4. MultiBootUSB version you are using. 
   5. More importantly, you should provide the log file when raising an issue.
   6. Any other information, not listed above, you feel will help me in figure out your issue.
 
 * Once you have all the information head over to [https://github.com/mbusb/multibootusb/issues](https://github.com/mbusb/multibootusb/issues) and raise a new issue.

---

## I can't install Live USB created using multibootusb on to my computer's hard disk.

 * I can't do anything about it.
 * The main purpose of multibootusb is to create (multiple) live Linux and able to boot from it.
 * Installing from USB is not the scope of this project. 

---

## Does multibootusb support exFAT file system?

 * No.
 * Support for file system is depend on bootloader and ISO file you are using.
 * The main bootloader used in syslinux is [syslinux](http://www.syslinux.org/). Read the file system support provided by syslinux project from [here](http://www.syslinux.org/wiki/index.php?title=Filesystem).
 * For maximum compatibility use FAT32 filesystem. 

---

## Does multibootusb support GRUB boot loader?

 * Yes. 
 * It supports GRUB2 bootloader.
 * GRUB2 is automatically added during installation of first distro.
 * You can change over to GRUB boot menu when booting from USB by selecting `Load GRUB2 BootManager` option.

---

## Does multibootusb support EFI or UEFI booting?

 * Yes, but with limited support.
 * It is supported through the use of the GRUB2 bootloader.
 * Reason for limited support being that the menu entries for GRUB2 are generated/converted using
 syslinux config files. Some menu options specially available for syslinux does not have support under GRUB2.

---

## Does multibootusb support persistence?

 * Yes.
 * Read the relevant portion from user guide [here.](http://multibootusb.org/page_guide/#adding-persistence-file)

---

## Your package for my favourite distro never worked for me. What can I do now?
 
 ** On Linux: **
    
   * multibootusb depends on the following packages under Linux:
            * python3-pyqt5
         * p7zip-full
         * parted 
         * util-linux 
         * python3-pyudev
         * mtools
         * python3-dbus
         * python3-six
    * Install above packages using your package manager. Remember that package name may not be identical for all distros. You need to search equivalent package for your distro and install it.
    * `You must uninstall your previous installation of multibootusb, if you have done it earlier.`
    * Download source code of stable version from [here](https://codeload.github.com/mbusb/multibootusb/zip/master) or development version from [here](https://codeload.github.com/mbusb/multibootusb/zip/devel)
    * Extract to local directory and move in to `multibootusb` directory.
    * Issue `sudo python3 ./multibootusb` command to start GUI

 ** On Windows: **
    
   * Download and install following packages:
            * [Python 3](https://www.python.org/downloads/windows/). I use python version 3.5 but it should work on higher versions as well.
         * [PyQt5](https://www.riverbankcomputing.com/software/pyqt/download5) and installation instruction are [here](http://pyqt.sourceforge.net/Docs/PyQt5/installation.html)
         * [wmi](https://pypi.python.org/pypi/WMI) module
         * [pywin32](https://pypi.python.org/pypi/pywin32)
         * [psutils](https://pypi.python.org/pypi/psutil)
         * [Git](https://git-scm.com/download/win), if you wish to contribute back to multibootusb project
    * `Installation and configuration of above packages/ modules is not a part of this documentation. You must use Google for that.`
    * If you have installed python correctly on windows, it is recommanded that you use `pip3.exe` for installing above packages.
    * Download source code of stable version from [here](https://codeload.github.com/mbusb/multibootusb/zip/master) or development version from [here](https://codeload.github.com/mbusb/multibootusb/zip/devel)
    * Open command prompt with admin privilage and move in to `multibootusb` directory.
    * Issue `python3.exe multibootusb` command to start GUI
 
---

## Is there a support for command line option instead of GUI?

 * Yes.
 * Read the relevant portion from user guide [here.](http://multibootusb.org/page_guide/#using-mltibootusb-using-command-line-options)

---

## Debian error "no common CD ROM drive was detected" during installation

 * Any type of errors related to hardware install are not a relevant scope of the multibootusb project.
 * However, there is an user solved this issue successfully. You can refer [this](https://github.com/mbusb/multibootusb/issues/85) link to overcome this issue.

---

## I found a bug and would like to submit a patch. How do I do that?

 * You are most welcome to submit a patch.
 * Before submitting a patch, ensure that the code is well tested and does not break 
 existing functionality.
 * Then submit a pull request on [devel branch](https://github.com/mbusb/multibootusb/tree/devel)
 * You can also send patch files directly through email. I will integrate in to main repo later post testing.
 
---

## How often multibootusb is released?

 * There is no fixed time line. 
 * It depends on number of distros added, bug fix, new functionality and packaging related issue.

---

## How do you give version number to each release?

 * This is based on various factors.
 * If it is only minor bug release, then the release will have minor version number. 
 * Version will be major if more distros, newer functinality and major change to code etc are added.

---

## Your english is pathetic.  

 * Fully agree with you. But I can't help that.
 * You are most welcome to correct it and send to me for improving.

---
