# Drive

The **Drive** object provides information about a drive (hard drive, CD ROM, etc) on your system. You can obtain a **[Vector](vector.md)** of **Drive** objects, one for each drive on your system, from the **[FSUtil](fsutil.md).Drives** method.

  

<table>
<thead><tr><th>

**Property Name**</th><th>

**Return** Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*default value*</td><td>

*string*</td><td>

Returns the root of the drive (e.g. **C:\\**).
</td></tr><tr><td>
avail</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns a **[FileSize](filesize.md)** object indicating the available free space on the drive.
</td></tr><tr><td>
bpc</td><td>

*int*</td><td>
Returns the bytes-per-cluster value for the drive.
</td></tr><tr><td>
filesys</td><td>

*string*</td><td>
Returns a string representing the filesystem type.
</td></tr><tr><td>
flags</td><td>

*int*</td><td>
Returns a value representing filesystem flags for the drive.
</td></tr><tr><td>
free</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns a **[FileSize](filesize.md)** object indicating the total free space on the drive.
</td></tr><tr><td>
label</td><td>

*string*</td><td>
Returns the drive's label.
</td></tr><tr><td>
total</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns a **[FileSize](filesize.md)** object indicating the total size of the drive.
</td></tr><tr><td>
type</td><td>

*string*</td><td>
Returns a string indicating the drive type (removable, fixed, remote, cdrom, ramdisk).
</td></tr></tbody>
</table>

