﻿This is a service to control the keyboard backlight behavior on Lenovo P and X series laptops (possibly other models).

It will ensure the keyboard backlight is on after boot and also turn it back on after the system comes out of a standby.

This also requires that the Lenovo Vantage software be installed and that the Keyboard_Core.dll is located in the following folder:
C:\ProgramData\Lenovo\ImController\Plugins\ThinkKeyboardPlugin\x86\Keyboard_Core.dll

For now, there is no installer but you can manually install using the following elevated command:
C:\Windows\Microsoft.NET\Framework\v4.0.30319\installutil.exe "path\to\LBCService.exe"

NOTE: This was only tested using the LOCAL SYSTEM account for the service logon



It is currently hardcoded but I plan on adding support for a config file so this path can be adjusted as well as the brightness
level, which currently is hardcoded to "High".

Of course, if you have Visual Studio, feel free to change and compile as needed.

TODOs:  Add support for config file
        Add support for a timeout
		Add support for enabling again after timeout via KB or mouse movement

This program was written using the work of liguis- here: https://github.com/ligius-/lenovo-backlight-control/
and Tam Bui's code to hook in to the system power changes here: 
https://social.msdn.microsoft.com/Forums/vstudio/en-US/a195860c-6a24-4526-8e96-06ea56690c12/windows-service-wont-stop-when-registerpowersettingnotification-is-used-to-detect-connected-standby?forum=netfxbcl