After a month of development, it is the time to release version 7.3.0. It has a new source code and lot of bug fix. A notable fix is for ubuntu 14.10 and above. Due to some bug in the rpm packaging, it is advisable to run multibootusb from source code for rpm based distros. Some of the highlights of this release are:-

* Rewrite of the source code. It is easier to read source code now.
* UDisks2 has been added for detecting and getting USB details under Linux.
* Patch for ubuntu 14.10 and above which uses isolinux version 6.
* Added persistence for ubuntu and its derivatives. Maximum persistence can be up to 4GB.
* No USB label error has been solved. It now works with USB drives even without names.
* Corrected wait time to 30 sec.
* Updating GUI is now handled by QThread
* Added following distros:-
– Trinity Rescue Kit
– DBan
* Check for QEMU installation before doing any QEMU related operations.
* Feedback after installing syslinux (under syslinux tab).
* psutil dependency has been dropped.
* As usual for rest of the commits please go to this page.

 Head over to [this link](https://github.com/mbusb/multibootusb/releases) for old releases...
