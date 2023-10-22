# Drive

The **Drive** object provides information about a drive (hard drive, CD ROM, etc) on your system. You can obtain a **[Vector](vector.md)** of **Drive** objects, one for each drive on your system, from the **[FSUtil](fsutil.md).Drives** method.

  

| **Property Name** | **Return** Type | Description |
| --- | --- | --- |
| *default value* | *string* | Returns the root of the drive (e.g. **C:\\**). |
| avail | *object:***[FileSize](filesize.md)** | Returns a **[FileSize](filesize.md)** object indicating the available free space on the drive. |
| bpc | *int* | Returns the bytes-per-cluster value for the drive. |
| filesys | *string* | Returns a string representing the filesystem type. |
| flags | *int* | Returns a value representing filesystem flags for the drive. |
| free | *object:***[FileSize](filesize.md)** | Returns a **[FileSize](filesize.md)** object indicating the total free space on the drive. |
| label | *string* | Returns the drive's label. |
| total | *object:***[FileSize](filesize.md)** | Returns a **[FileSize](filesize.md)** object indicating the total size of the drive. |
| type | *string* | Returns a string indicating the drive type (removable, fixed, remote, cdrom, ramdisk). |

