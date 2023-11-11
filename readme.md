=================================
Reg To File Tune DLL
=================================

	Redirects registry configurations that the application creates
	into a disk file. It's in the form of a dynamic link library, DLL.

	It is intended to be attached to the target executable on its
	startup, and what registry keys it redirects should be specified
	in its INI configuration file.

	Enables creating of portable versions of applications that now
	store their configuration in a disk file, rather than in
	Windows Registry.


Configuration
---------------------

    It is done by editing the "reg_to_file_tune_dll.ini" file that
    accompanies the DLL in its directory.
    See the default INI file for the auto-documentation.

    For two versions of the DLL that exist, 32 and 64-bit,
    here are files that will be used:

		32-bit version:

			reg_to_file_tune_dll_32.dll
			reg_to_file_tune_dll.ini
			reg_to_file_tune_dll.reg.ini

		64-bit version:

			reg_to_file_tune_dll_64.dll
			reg_to_file_tune_dll.ini
			reg_to_file_tune_dll.reg.ini


Database INI
----------------------

	Once configured and attached, there will be another INI file
	created, that contains the redirected registry settings.
	This file will be created in the same directory the DLL file is in
	and will be named "reg_to_file_tune_dll.reg.ini"
	(ie. it'll use the ".reg.ini" suffix).


Installation
------------------------

	Possible ways to add the DLL to the target application:

		* Use a third party application to add the DLL to the target
		  executable's import table.

		* Use a launcher application that starts the executable and
		  auto-loads the DLL.

	Example applications:

		Tray Icon Launcher
		https://github.com/ike9000e/tray-icon-launcher

		CFF Explorer
		https://ntcore.com/?page_id=388


Build Instructions
---------------------------

	Compiler command-line arguments

		/EHsc
		/O1
		/FS
		/MP1
		/GL-
		/MT
		/D WIN32_LEAN_AND_MEAN
		/D _WIN32_WINNT=0x501
		/D _USING_V110_SDK71_
		/D NOMINMAX

	Linker command-line arguments

		detours64.lib
		kernel32.lib
		user32.lib
		comdlg32.lib
		winmm.lib
		advapi32.lib
		shell32.lib
		gdi32.lib
		psapi.lib
		dbghelp.lib
		/DEF:.\project_dll.def
		/MACHINE:X64


About
-------------

	Author: ike9000
	Website: https://github.com/ike9000e/Reg-To-File-Tune
