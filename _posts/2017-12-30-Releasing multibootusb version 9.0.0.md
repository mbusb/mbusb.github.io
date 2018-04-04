---
comments: true
---

Sorry guys for the delay. It is a long pending release after implementing EFI support.
There has been lot of feedbacks and issues reported related to EFI implimentation. Done some bit in this respect. Hopefully, it should be better than previos release. 
Also, this release takes care of crash on Windows and rpm based distros. Therfore, it is strongly recommended to upgared your multibootusb to this latest version.
This release is not compatable with previous release. Please use fresh install of each distro. You must not have EFI and multibootusb directory on USB before using this version due to binary conflicts.

Major changes since version 8.9.0 are:-

* Improved UEFI support (thanks to many users for testing reporting back the problem, especially `eaglerainbow`)
* New efi binary based on latest grub2 source
* Added grub2 efi modules
* Fix for crash when Windows system language is non set to English
* Fis for rpm based packages during start of the programe
* Improved the GPT detection under Windows and it is much faster than previous release
* Corrected partedmagic path issues (thanks to user `gabrielmagno`)
* Improved GPT detection under Linux
* Check for root privilege when using CLI
* Fix crash when installing ISO from CLI due to GPT check
* Fix crash when installing syslinux from CLI due to GPT check
* Install extlinux under Linux for NTFS filesystem
* Correct usage instructions in help text
* Added option to choose install distro using memdisk. Beware that not all distros would work. But you can uninstall it any time.
* Added Xenial Puppy
* Added OSFclone
* Added Redcore Linux
* Added Slacko Puppy

Go to [Download](http://multibootusb.org/page_download) page for download option...

