---
title: Path Backup Automation
sidebar_label: Automation
sidebar_position: 2
---

# Automating Application Operation

The application supports automated operation through several command-line parameters passed to the application. When you launch the application without command-line parameters, you'll see the app UI shown earlier in this document. When you launch the app with command-line parameters, the app UI changes and the configured backup or restore tasks happen without user intervention.

**Note:** Even in automated mode, Windows will prompt you to authorize use of administrator privileges when running the application. Unfortunately, there's nothing the app can do to get around this limitation. This means that you can't use automated mode in unattended operations (build processes, automated batch file execution, etc.).

To add command-line options (run parameters) to the application, create or locate a shortcut for the application:

1. For the existing shortcut, right-click on the Start Menu shortcut for the application and select **Open file location**. 
2. Make a shortcut from the application executable and open it in Windows File Explorer.

Right-click on the shortcut and select **Properties**

In the shortcut's properties dialog, add the run parameters to the shortcut as shown in the following figure:

![](/images/pathbackup/shortcut-properties.png)

## Automated Backup

The application supports the following options for automated backup:

### Automated Backup to File

Run Parameters: `-backup <file-path>` or `/backup <file-path>`

Example: `-backup c:\john\backups\pathbackup.json`

Instructs the app to save the Windows Path settings to the file path specified in `<file-path>`.

### Automated Backup to Folder

Run Parameters: `-backup <folder-path>` or `/backup <folder-path>`

Example: `-backup c:\john\backups`

Instructs the app to save the Windows path settings to the folder specified in `<folder-path>`. Since the specified file path doesn't include a file name, the app will use the default backup file name of `path-backup-yyyy-mm-dd.json` substituting the current year, month, and day of the month for `yyyy-mm-dd`. For example: `path-backup-2024-01-31`.

If you don't include a file name in the backup path, the application automatically creates a Registry file (`.reg`) backup. You can use one of the additional run parameters to specify JSON or YAML file output:

Use `-json` to instruct the application to generate a file name with a `.json` extension. 

Example: `-backup c:\john\backups -json`

In this case, the app will create a backup file called `c:\john\backups\path-backup-2024-03-16.json` using the current date and the app name as the backup file root.

Use `-yaml` to instruct the application to generate a file name with a `.yaml` extension.

Example: `-backup c:\john\backups -yaml`

In this case, the app will create a backup file called `c:\john\backups\path-backup-2024-03-16.yaml` using the current date and the app name as the backup file root.

## Automated Restore

Run Parameters: `restore <file-path>` or `/restore <file-path>`

Example: `-restore c:\john\path-backup-2024-01-31.json`

Instructs the app to restore the Windows Path settings defined in `c:\john\path-backup-2024-01-31` to the system registry.

## Launching Help

When you include a `-h` or `-help` as a run parameter for the application, when the app launches, it will launch the system's default browser and open the online documentation for the app.