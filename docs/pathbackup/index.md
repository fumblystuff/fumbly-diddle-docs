# Path Backup & Restore

A simple Path backup and Restore utility for Windows. In early versions of Windows, Windows users and applications set the path environment variable in the system's `autoexec.bat` file. Recently, Google won't tell me when, Microsoft split the path into two parts, the User Path and System Path and moved the Environment variable setting from the `autoexec.bat` file to the system's Registry.

In the old days, when you made changes to the Path, you could make a copy of the current path and put it back in the system's `autoexec.bat` file commented out. If the changes you made didn't work out, you could always copy the old path back and be done with it.

In Windows 11, Windows stores the User Path in `HKEY_CURRENT_USER\Environment\Path` and the System Path in `HKEY_LOCAL_MACHING\SYSTEM\CurrentControlSet\Control\Session Manager\Environment\Path`. If you're messing around with the Path and want to make a backup, you must open the Registry Editor app (or equivalent), navigate the Registry hierarchy to the two different locations specified above and copy the value from the registry into a text file or something. 
