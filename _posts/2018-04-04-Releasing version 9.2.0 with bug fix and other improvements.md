---
comments: true
---

This release comes after a gap of almost three months. During this period, lot of bug has been fixed and few improvements has been made to the code. Thanks to Shiniji Suzuki for his work on the project. Most of the fixes and improvements listed below are done by him. Some of the major changes since version 9.1.0 are:-

* Fix for crash under Windows
* Reimplemented Debian persistence feature under Linux and Windows
* Improved partition detection type
* Allow target drive specification using lower case letter in command line interface
* Added option to specify persistence option from commanl ine interface using 'persistence-size' or 'p'
* Better conversion of syslinux config files to grub compatible one (loopback.cfg)
* Prevent command line interface from installing over existing installation (similar to GUI)
* Fix distro detection going out of sync after uninstalling a distro
* Multibootusb remembers persistence size when trying next distro (having persistence feature)
* Better detection og GPT devices under Windows
* Fix linux (ubuntu16.04) incompatibility (7zip coding)
* Fix crashing of multibootusb when installing default syslinux
* Provide feedback after successful or failure of syslinux install
* General code cleanup
* Find and prompt for empty ISO files
* Fixed various typographical errors
* Fix wifi slax install issue
* Fix Antergos booting issue
* Fix slitaz rolling detection and install
* Fix wifi slax install issue
* Fix for syslinux install when USB disk is not inserted
* Fix parted magic grub label (Thanks to gabrielmagno)
* Intimate users if USB disk not inserted when trying to install syslinux
* Add support for AntiX 17.1
* Added Parabola Linux
* Sync with other multibootusb project

What I have noticed during this release cycle is that releasing of new version of the software takes too much time than actual coding on the project. Usually, time is spent on fixing the bug and pushed immediately to `devel` branch. Others contribution also reviewed and merged in to `devel` branch as soon as possible. But for newer release, I have to test each package individually before pushing in to github release repo. Moreover, I have to spend lot of time to write changelog and update website accordingly. Therefore, what I would request is that If anyone having issue with stable version, please download devel branch and directly from the source. Possibly, your bug is already solved in the devel branch.


Go to [Download](http://multibootusb.org/page_download) page for download option...

