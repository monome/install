install
=======

installer for grids including monome_sum


windows: use as a .nsi script file for NSIS install packager
========

Name "Monome Device"
OutFile "MonomeDeviceInstaller.exe"

InstallDir $PROGRAMFILES\monome

DirText "This will install monome device support on your computer. Choose a directory"

Section "monome_sum"
	SetOutPath $TEMP
	File "monome_sum_win_v1.1.exe"
	Exec '"$TEMP\monome_sum_win_v1.1.exe"'
	createShortCut "$SMPROGRAMS\monome_sum.lnk" "$PROGRAMFILES\monome\monome_sum\monome_sum.exe"
SectionEnd

Section "serialosc Server"
	SetOutPath $TEMP
	File "serialosc-1.2a.exe"
	Exec '"$TEMP\serialosc-1.2a.exe"'
SectionEnd

Section "FTDI VCP Driver"
	SetOutPath $TEMP
	File "FTDI_VCP_Installer.exe"
	Exec '"$TEMP\FTDI_VCP_Installer.exe"'
SectionEnd
