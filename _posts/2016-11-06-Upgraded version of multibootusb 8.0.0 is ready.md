---
comments: true
---
Here comes the latest and upgraded version of multibootusb (version 8.0.0). I would like to thank all people who had helped and
contributed code since last version (7.5.0). More importantly, 'Lee' who had ported isodump script to work with python3 within
short period of time. [Jookia](https://github.com/Jookia), who contributed many code improvements. Fry-kun pointed me 
in the right direction to use pkexec which is default now. [yurikhan](https://github.com/yurikhan) had correctly pointed out the bugs
and offered the solution for distros shipping with 32 bit syslinux binaries which is now integrated in to the latest multibootusb.
There are other who also contributed code and some gave important feedbacks. Thanks you all.
 
Some of the chages made in this release are listed below:-

* This version is written in python 3
* GUI toolkit moved to pyqt5
* Upgraded isodump.py to support python 3 (Thanks to LiQiong Lee)
* Option to choose the desired persistence size using slide
* Introduces command line option (install and uninstall distros as of now and will be extended later)
* Progress can be monitered when running from terminal
* Multibootusb should be started with admin/ root privilage under Linux
* Fixed the bug which causing USB disk to set read only
* Fixed 'Undef symbol FAIL: __syslinux_debug_enabled' error for gparted, clonezilla and some other (Thanks to yurikhan for pointing to right direction)
* Fixed the bug which crashes multibootusb when non-ascii charecters are present in the ISO link
* Fixed the bug which prevent multibootusb not to install syslinux
* Now debain installer can be installed
* Updated dependency packages stddeb, pyinstaller and pyudev to latest version
* Fixed hiren's boot cd bug (but user has to avoid "'" in the path)
* Updated install.py script to include all missing dependencies
* pkexec is required now undaining Linux for obtaining admin permission
* Fixed dban not supported error
* Fixed AVG rescue disk not supported error
* Added Offline Windows Password and registry editor (latest version)
* Added F4UBCD iso
* Fixed the crash when mountpath contain space
* Dropped udisk version 1 for obtaining details of USB disks
* Now the GUI responds smoothly when using ISO Imager option (dd)
* Fixed superficial duplicate devices on Refresh USB under ISO Imager tab
* Corrected some typo errors
* version bumped to 8.0.0 as it is a major upgrade
* Added support for bl-Hydrogen Linux
* Many other improvements and bug fixes...

For Windows users:-
-------------------
Size of the upgraded version is little heavier than previous versions. This is mainly due to upgrade of python3 and pyqt5. 
I have also disabled UPX compression as it took lot of time for launching application.

This version also introduces the command line options as well (only for Linux). At the moment, install and uninstall can be done from terminal.
Example to install distro from command line should like like is:-

```sudo multibootusb -c -i ../../favourite.iso -t /dev/sdb1```

Example to uninstall distro from command line should like like is:-

```sudo multibootusb -c -u -t /dev/sdb1```

To know the supported command line options are simply invoke '-h' or '--help' like this:-

```sudo multibootusb -h```

Head over to [download](http://multibootusb.org/page_download/) section for downloading binaries...
