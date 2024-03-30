---
title: Path Backup
---

# Path Backup & Restore

A free and easy to use Path Backup and Restore utility for Windows. 

Microsoft Windows uses the `PATH` environment variable to provide a list of directories where the operating system can locate executable programs. The Path makes it easy to execute Windows applications from a command prompt or terminal window without knowing the full path to the executable file name. Also, some Windows applications rely upon other Windows applications and path tells them how to find those dependent applications.

Many Windows application installations modify your system's System Path and User Path variables, adding entries that allows the system to quickly find application executables when typed on a command line or launched arbitrarily from an application. Sometimes these processes corrupt your system's path removes your ability to get things done.

Internally, Windows splits the path into two parts: the User Path and System Path. Windows stores the User Path in `HKEY_CURRENT_USER\Environment\Path` and the System Path in `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Environment\Path`. Microsoft offers no simple way to backup those settings. When you're messing around with the Path and want to make a backup, you must open the Registry Editor app (or equivalent), navigate the Registry hierarchy to the two locations specified above and export the values into a registry file (.reg). Path Backup & Restore automates that process for you and backs up your system Path to a broader range of output file formats.

The **Path Backup & Restore** application allows you to quickly backup your system's path to a local file the restore the path using a backup file later. The application supports backing up the system's path to:

+ Registry file (.reg)
+ JSON file (.json)
+ YAML file (.yaml)

The Registry file is unique in that you can simply double-click the file in Windows File Explorer to restore path entries (replacing the existing entries). The other file formats don't provide any additional features or capabilities but you can only restore them using the Path Backup & Restore application.
