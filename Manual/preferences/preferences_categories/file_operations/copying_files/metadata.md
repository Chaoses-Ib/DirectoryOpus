# Metadata

### Copy Alternate Data Streams

This option controls the copying of metadata that is stored in NTFS *Alternate Data Streams* (ADS). This metadata can include things like comments, tags, rating information and [labels](/Manual/file_operations/labels.md), depending on the file formats and configuration involved.

This option only applies to metadata stored in separate NTFS data streams. For example, Office documents store things like author names and comments as part of the main file itself, and so that metadata would always be copied anyway. On the other hand, a basic text file has no facility to store such data directly, but may have it added within a separate stream.

NTFS ADS cannot be stored on drives which use a filesystem other than NTFS. Any metadata stored in NTFS ADS will be lost when copying to filesystems such as FAT32 or ExFAT (typically used on USB sticks), to some network drives (typically if the server is not running Windows), into archives and on to FTP sites.

- **Copy to new file**: Always copies the NTFS ADS metadata to the new file, where possible, even if it takes extra time. Choose this if you want it to be copied.
- **Copy to new file, unless slower**: Copies the NTFS ADS metadata to the new file if doing so is possible and does not take extra time. Choose this if you don't care if it is copied or not, and just want whatever is fastest.
- **Remove from new file**: Actively prevents the NTFS ADS metadata from being copied to the new file, even if doing so takes extra time. Choose this if you really do not want it to be copied.

The choice made here can be overridden by the `Copy` command's `COPYPROPERTIES` argument.

The speed factor depends on how files are copied, which is configured via `copy_allow_delegation` ([Preferences / Miscellaneous / Advanced](../../miscellaneous/advanced_options.md)) and can be overridden by the `Copy` command's `DELEGATE` argument:

By default, file copying is delegated to a very-high-level API provided by Windows. When that API copies a file from one NTFS device to another, it always copies all ADS streams attached to it (there is no way to tell it not to). That means a little extra time is always spent copying ADS streams, but this is often offset by the API being faster in other ways. However, if you really don't want the ADS streams preserved then additional time must be spent to delete them after the API has copied them.

On the other hand, if you configure Opus to copy files using custom, lower-level code, then Opus can choose when to copy the NTFS ADS streams and will only copy them if you really want them. That may be slightly faster, but the custom code may also be slower in other ways (depending on hardware, drivers, etc.).

### Copy file descriptions

This attempts to preserve any description assigned to the copied files, if it is not already being preserved via the **Copy to new file** option above.

This can be overridden by the `Copy` command's `COPYDESC` argument.

Turning this option on imposes extra per-file overheads when copying. You should generally only turn this on when using the DESCRIPT.ION file comment system that stores descriptions in a special file within each folder. If you are using NTFS ADS to store file comments, use the **Copy to new file** option above, instead.

### Copy sparse files as sparse

Sparse files are a special feature of the NTFS file system that allows regions of a file to be marked as "empty" (containing all zero bytes), with those regions not using up any drive space. For example, a sparse 1GB file consisting of all zeroes could occupy almost no space. Sparse files are used in specialized applications like virtual machines. Some download tools also use them to track which regions of files have been downloaded.

Normally, copying a sparse file results in a copy which is no longer sparse, meaning the copy occupies its full size on disk and the empty regions look like normal data, indistinguishable from any other sequence of zeros. On the other hand, if you turn this option on, any sparse regions in the source file will be recreated in the copy.

This can be overridden by the `Copy` command's `COPYSPARSE` argument.

Turning this option on will force Opus to use custom file-copying code *when copying sparse files*. Normal files will still be delegated to the very-high-level API, if it is enabled.

### Strip zone information (Mark of The Web)

Downloaded files are often "marked" by the program that downloads them as having come from the Internet, which causes Windows to show a warning when opening them. Turn this option on to strip the "Mark of The Web" when copying files.
