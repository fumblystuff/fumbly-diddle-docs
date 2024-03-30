---
title: Path Backup Troubleshooting
sidebar_label: Error Messages
sidebar_position: 3
---

# Understanding Error Messages

The application generates the following error messages when encountering an issue performing an automated operation:

* **Invalid command-line parameters you cannot use both `-backup` and `-restore` simultaneously.** This error occurs when you pass both the `-backup` and `-restore` runtime parameters to the application when launching (passed as command-line parameters to the application executable in the shortcut that launches the application). The application can't do a backup and restore at the same time (actually it could, but it makes no sense to do so), so rather than decide which one to do, the application aborts after displaying the error message. Remove one of the options from the command-line and try again.

* **Automated operation is enabled, but the runtime parameters is missing the required backup file or folder path.** In this case, the application launches with the command-line parameter to do an automated backup or restore, but the command-line doesn't include an additional parameter specifying the folder path or file path to backup to or the file path to restore from. Update the runtime paramaters to include a backup file or target folder path and try again.

* **The provided folder path contains invalid characters.** With this error, the application is telling you that the backup or restore filepath has invalid characters in the folder path portion of the specified path. Refer to [Naming Files, Paths, and Namespaces](https://learn.microsoft.com/en-us/windows/win32/fileio/naming-a-file) for additional information. Double check the target folder to ensure it has only valid characters and try again.

* **The provided file name contains invalid characters.** Like with the previous error, this error message indicates that the backup or restore file name contains invalid characters. Refer to [Naming Files, Paths, and Namespaces](https://learn.microsoft.com/en-us/windows/win32/fileio/naming-a-file) for additional information. Double check the target file path to ensure it has only valid characters and try again.

* **Target folder "%s" does not exist.** This error indicates that the folder path or the folder path portion of the file path specified for backup or restore does not exist on the target system. When specifying a file path for a backup or restore operation, the application strips the folder portion of the file path and verifies it exists before continuing. When specifying a folder path for a backup operation, the application does the same thing with the specified folder path. Check to ensure you're passing a valid file or folder path to the application and try again.

* **The specified backup file "%s" does not exist.** This occurs during an automated restore operation and indicates that the file name (referenced using the `%s` in the error message) doesn't exist on the system. The application can't restore a file it can't find. Double check the file name and try again.

* **The application is unable to restore Registry files, you must launch them manually from Windows File Explorer.** This error appears when you try to use the application to restore a path backup from a Registry (.reg) file. The application could restore the path backup, but Windows already includes an application to do this (Registry Editor: regedit.exe), so rather than duplicating existing functionality, the application simply informs you to let the existing Windows application handle the restore. Nothing do to here except to double-click the file in Windows File Explorer and let the Registry Editor app handle importing the Path settings.

* **Invalid backup file extension: "%s.** This error occurs when performing an automated backup operation and the target file name is either missing a file extension or has a file extension that isn't `.json`, `.reg`, or `.yaml`. Fix the backup file name and try again.

* **Invalid file extension: "%s".** This error occurs when performing an automated restore operation and the target file name is either missing a file extension or has a file extension that isn't `.json`, `.reg`, or `.yaml`. Fix the restore file name and try again.