---
title: TeraCopy Setup
sidebar_label: TeraCopy Setup
sidebar_position: 1
---

## Installation

To use SubCopy, you must have a copy of the free [Teracopy](https://www.codesector.com/teracopy) utility installed on your Windows system.  If you do not have TeraCopy installed, navigate to [Code Sector Downloads](https://www.codesector.com/downloads) then download and install the latest version of the application.

## Configuration

Out of the box, TeraCopy comes configured to verify the available space on the target device before starting the copy process. Unfortunately, when updating the files on the target device, TeraCopy may report "More space is required" and abort the copy process. This is because TeraCopy checks the target drive for free space equal or grater than the size of the files being copied. 

When overwriting only older files (a MSFCopy and TeraCopy feature), it's possible that there will be enough space on the target drive, but TeraCopy doesn't know it. To get around this potential blocker, you must modify the TeraCopy configuration to disable the application's `CheckFreeSpace` option.

1. Navigate to the TeraCopy configuration folder:
  + Windows 10/11: C:\Users[YourUsername]\AppData\Roaming\TeraCopy.
  + Windows 7/Vista: Same location as above.
  + Windows XP: C:\Documents and Settings[YourUsername]\Application Data\TeraCopy.
2. Open the `Options.ini` file in a text editor.
3. Find the line `CheckFreeSpace=1` and change it to `CheckFreeSpace=0`.
4. Save the file and restart TeraCopy.

Here's an example from my system:

![Windows File Explorer open to the TeraCopy configuration folder](/images/msfcopy/teracopy-disk-space-fix-01.png)

And here's the configuration file with the required change highlighted.

![The TeraCopy Configuration modified with the required change.](/images/msfcopy/teracopy-disk-space-fix-02.png)