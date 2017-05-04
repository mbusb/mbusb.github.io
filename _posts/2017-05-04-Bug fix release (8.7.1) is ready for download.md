---
comments: true
---

This release is mainly a bug fix release. No new distros are added. However, new features for command line usage is added.
It is possible to install multiple distros at a time using command line options. The major bug fix is for rpm based distros which had an `import error`
with previous version of multibootusb install. Few of the changes since version 8.7.0 are:-

* Warning text under 'Write image to disk' tab
* Fix for rpm based distro which did not run due to import error
* Fix for suse package and it now checks for correct package dependencies
* Copy only multibootusb directory to USB if user accept installation choice
* Display human readable size for an ISO in terminal
* New command line option to skip confirmation message 'try multibootusb -c -h' for more details
* New command line option to install multiple distros at a time (Windows user should be able to run only under source code)
* Fix for crash when installing under Install syslinux tab
* Prevent read only filesystem under Linux
* Corrected setup file copy location preventing crash
* Improved multibootusb-pkexec script for working under rpm and deb based distros
* Create correct policy file during build time for various packages
* Improved user guide at http://multibootusb.org/page_guide/
* Various code cleanups
 
Go to [Download](http://multibootusb.org/page_download) page for download option...

