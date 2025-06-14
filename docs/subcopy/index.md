---
title: Subdirectory Copy
---

# Subdirectory Copy

The Subdirectory Copy (SubCopy) application allows you to copy a set of subdirectories to a removable drive (flash drive). 

For example, if you have a Music directory on your computer organized by artist and album (the way iTunes organizes them) and you want to copy only a subset of those artists to a flash drive. If that's your use case, then this is the utility for you. We built this utility for that specific use case, but we assume there are other use cases this utility handles as well. Many modern automobiles allow owners to plug in an SD Memory card or flash drive full of music files and play them on the car's audio system. These cars often have restrictions on the size of the memory device and/or the maximum number of files you can serve from the device. For this reason, you may not be able to put all of your music files on the drive, so this application allows you to take just a subset with you when you travel.

You could create and maintain a simple Windows command (batch) file that copies all the artist subdirectories for you, but that's difficult to maintain. SubCopy delivers a clean interface for managing the source folder list and copying the files to the target drive. You can add the folders manually, or your can simply drag the folders onto the application window to add them to the source folder list.

Find the full application source on GitHub at [subdirectory-copy](https://github.com/fumblystuff/subdirectory-copy).

**Note:** The application uses the free [Teracopy](https://www.codesector.com/teracopy) utility to manage the copy process; so you must have TeraCopy installed to use this application. If you find you like the capabilities TeraCopy provides, please consider buying a license.
