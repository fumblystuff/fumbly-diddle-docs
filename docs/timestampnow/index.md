---
title: Timestamp Now
---

# Timestamp Now

**Timestamp Now** allows you to quickly and easily change the Created, Modified, and/or Created timestamp(s) on one or more Windows files and directories to the current date/time.

The application installs as a Windows Shell Extension, available in the Windows File Explorer context menu. Select one or more files and/or directories in Windows File Explorer, right click on any of the selected files, then choose **Timestamp Now...**.

![Windows File Explorer context menu](/images/timestampnow/windows-options-menu.png)

In the application window that opens, you control which file or directory timestamps the app updates and the format of the current time saved to file properties.

Enable or disable the checkboxes for the Created, Modified, and Created timestamps. Based on your settings, the app updates only the selected timestamps for each file or directory.

![Timestamp Now UI](/images/timestampnow/timestampnow-ui.png)

With timestamp options, the application allows you to optionally zero out the milliseconds and/or seconds of the current time written to the file or directory's properties.

| Option        | Description | 
| ------------- | ----------- |
| `##:##:##:##` | Use the full time as the timestamp value. |
| `##:##:##:00` | Use the current time with milliseconds zeroed out. |
| `##:##:00:00` | Use the current time with seconds and milliseconds zeroed out. |

Make the appropriate configuration changes that match your use case then click the **OK** button to apply the changes to the selected files.

At this point, the application opens a processing window that displays the status of the file and directory property updates. 

## Limitation

Windows often doesn't display all of the shell extensions registered with the system. Its a context menu, so Windows tries to list capabilities based on the type of file or files selected. If you find that the **Timestamp Now** menu item doesn't appear, try selecting a few more files.
