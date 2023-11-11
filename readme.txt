=================================
Reg To File Tune DLL
=================================

	Redirects registry configurations that the application creates into a disk file.
	It's in the form of a dynamic link library, DLL.

	It is intended to be attached to the target executable on its startup,
	and what registry keys it redirects should be specified in its INI
	configuration file.


Configuration
---------------------

    It is done by editing the "reg_to_file_tune_dll.ini" file that
    accompanies the DLL in its directory.
    See the default INI file for the auto-documentation.


Database INI
----------------------

	Once configured and attached, there will be another INI file created, that
	contains the redirected registry settings.
	This file will be created in the same directory the DLL file is in
	and will be named "reg_to_file_tune_dll.reg.ini"
	(ie. it'll use the ".reg.ini" suffix).


Installation
------------------------

	Possible ways to add the DLL to the target application:

		* Use a third party application to add the DLL to the target
		  executable import table.

		* Use a launcher application that starts the executable and
		  auto-loads the DLL on its startup.

	Example applications:

		Tray Icon Launcher
		https://github.com/ike9000e/tray-icon-launcher

		CFF Explorer
		https://ntcore.com/?page_id=388


About
-------------

	Author: ike9000
	Website: https://github.com/ike9000e/Reg-To-File-Tune
