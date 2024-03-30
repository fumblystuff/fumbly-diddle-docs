---
title: Path Backup Usage
sidebar_label: Operation
sidebar_position: 1
---

# Using the Application

This utility automates backing up and restoring the path. When backing it up, the app saves the path settings in a JSON file. When restoring, just select a backup file and the app does the rest.

## Admin Privileges

Regular users can't access the Path on a Windows system, so you must run the application with Administrator privileges. The app is pre-configured to require Admin privileges, so when you try to run the app, Windows will prompt you to approve the upgraded privileges as shown in the following screenshot.

![Windows prompting to run the app with Administrator privileges](/images/pathbackup/windows-admin-prompt.png)

## The App Home Screen 

The application exposes two actions (Backup and Restore) and doesn't require any configuration to operate. Simply launch the app and click the appropriate button on the app: Backup or Restore.

![Application Home Screen](/images/pathbackup/app-main.png)

### Backing Up

To backup the system Path variables, click the **Backup** button. The app prompts you to select the backup file type (Registry file, JSON File, or YAML file).

![App activity after clicking the Backup button](/images/pathbackup/backup-click.png)

Once you make the selection, the app opens the standard Windows File Save dialog to allow you to select a location and backup file name. Select the output folder and either accept the default backup file name or provide your own.

![An example backup save dialog](/images/pathbackup/save-path-backup.png)

Click the **Save** button when done and the app will save the User and System path directory entries to the selected file.

### Restoring

To restore the Path, click the **Restore** button, the app prompts you to select the backup file type (JSON File, or YAML file). 

**Note:** Restoring from a Registry file is not an option because the app is not able to restore that type of backup file. Instead, you must open Windows File Explorer, navigate to the folder where the backup file resides, then double-click the file to launch the Windows Registry Editor app (regedit.exe) to import the file for you.

![App activity after clicking the Restore button](/images/pathbackup/restore-click.png)

Select the backup file you wish to restore then click the **Open** button. The app will read the selected file, import all the Path settings from the backup file, then restore them to the Path Registry locations.

![An example restore file selection dialog](/images/pathbackup/restore-file-selection.png)

## Editing a Backup File

You can open any of he generated backup files and edit their contents. Just make sure you don't modify the format of the file's entries. 

**Note:** In all of the supported backup file types, the backslash ('\') is a special character that must be escaped (with another backslash character) whenever used. Since Windows directory paths use the backslash as a path delimiter, you'll see a bunch of double backslashes in the backup file. Those are required, and the App will remove the duplicate backslash during the restore process. Here's an example of a JSON file:

```json
{
    "SystemPath": [
        "%SystemRoot%\\system32",
        "%SystemRoot%",
        "%SystemRoot%\\System32\\Wbem",
        "%SYSTEMROOT%\\System32\\WindowsPowerShell\\v1.0\\",
        "%SYSTEMROOT%\\System32\\OpenSSH\\"
    ],
    "UserPath": [
        "%USERPROFILE%\\AppData\\Local\\Microsoft\\WindowsApps",
        ""
    ]
}
```

![Backup file open in Notepad](/images/pathbackup/path-contents.png)
