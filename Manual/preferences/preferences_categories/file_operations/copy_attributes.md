# Copy Attributes

The options on this page control which file attributes and metadata are copied ("preserved") when you copy files in Directory Opus. In general, these options can be overridden at the command level by supplying different parameters to the [Copy](/Manual/reference/command_reference/internal_commands/copy.md) command.

Some of these options cause file copying to take slightly longer for each file. This is not something to worry about in general, but can cause speed differences when copying thousands of tiny files, or to slow devices (e.g. cheap/old USB sticks) or high-latency networks.

Options which apply to *copying* files also apply when *moving* files if the move is performed by creating a copy and then deleting the original. The other way of moving files is to simply rename them from one place to another, which inherently preserves all aspects of the original file, but that is only possible when the source and destination are on the same logical drive.

**Timestamps and Attributes:**

- **Copy timestamps**: This allows you to choose which timestamps are preserved when copying files, and which are reset to the time the copy is performed.

Three choices are provided:

**Copy Modified and Created to new file**: The original file's Modified and Created timestamps will be copied over to the new file.

**Copy Modified; Set Created to time of copy**: The original file's Modified timestamp will be copied to the new file. The new file's Created timestamp will be set to the current date and time. (This is File Explorer's default behavior.)

**Set Modified and Created to time of copy**: The new file's Modified and Created timestamps will both be set to the current date and time.

(The **Last Accessed** timestamp has the same logic applied as for the **Modified** timestamp; however, the **Last Accessed** timestamp is a legacy feature of Windows and is not usually worth thinking about.)

There may be a small performance difference depending on which timestamps and copied and reset, but it is very small and the fastest choice depends on exactly how the files are copied. With this particular option, you should generally choose the mode you prefer over worrying about speed.

This choice made here applies to both files and folders by default, but can be overridden (for either or both) via the **Copy** command's **COPYFILETIMES** and **COPYDIRTIMES** arguments. The **[Miscellaneous / Advanced](../miscellaneous/advanced_options.md)** page in Preferences also has a **no_copy_dir_dates** override.  
\* **Copy file attributes**: This preserves the attributes of files when they are copied. If this option is off, attributes will be reset on the new files.

Attributes are the single-letter flags shown in the **Attr** column which can mark a file as **R** (read-only), **H** (hidden), and so on.

This can be overridden by the **Copy** command's **COPYATTR** argument.  
\* **Mark copied files as archived (clear the A flag)**: This clears the **A** attribute on newly copied files. You can use this if you have a backup solution that looks for the **A** attribute to know if a file needs backing up, and you want to prevent it from backing up the copied file (unless further changes are made to it).

This can be overridden by the **Copy** command's **MARKDESTARCHIVE** argument.

Note that the **A** attribute in Windows is set on a file when the file has been modified and is *ready for archival*. Once a file has been archived, the **A** attribute is usually *cleared* by software which uses the attribute.  
\* **Clear read-only flag when copying from CDs**: Files that reside on CDs and DVDs are implicitly read-only, and normally this attribute is preserved along with any others when you copy these files. If this option is on, the **R** attribute will be cleared when these files are copied.

This can be overridden by the **Copy** command's **CLEARREADONLY** argument.  
\* **Mark original files as archived after being copied (clear the A flag)**: This clears the **A** attribute on the original files after they have been copied, which in turn indicates to some backup software that the original files already have backup copies.

This can be overridden by the **Copy** command's **MARKSOURCEARCHIVE** argument.

See ***Mark copied files as archived***, above, for discussion of the **A** attribute.

**Metadata and Filesystem:**

- **Copy NTFS ADS**: Copies metadata that is stored in NTFS *Alternate Data Streams* (ADS). This metadata can include things like comments, tags, rating information and [labels](/Manual/file_operations/labels.md), depending on the file formats and configuration involved.

This option only applies to metadata stored in separate NTFS data streams. For example, Office documents store things like author names and comments as part of the main file itself, and so that metadata would always be copied anyway. On the other hand, a basic text file has no facility to store such data directly, but may have it added within a separate stream.

NTFS ADS cannot be stored on drives which use a filesystem other than NTFS. Any metadata stored in NTFS ADS will be lost when copying to filesystems such as FAT32 or ExFAT (typically used on USB sticks), to some network drives (typically if the server is not running Windows), into archives and on to FTP sites.

Three choices are provided:

**Copy to new file**: Always copies the NTFS ADS metadata to the new file, where possible, even if it takes extra time. Choose this if you want it to be copied.

**Copy to new file, unless slower**: Copies the NTFS ADS metadata to the new file if doing so is possible and does not take extra time. Choose this if you don't care if it is copied or not, and just want whatever is fastest.  
**  
Remove from new file**: Actively prevents the NTFS ADS metadata from being copied to the new file, even if doing so takes extra time. Choose this if you really do not want it to be copied.

The choice made here can be overridden by the **Copy** command's **COPYPROPERTIES** argument.

The speed factor depends on how files are copied, which is configured via **copy_allow_delegation** ([Preferences / Miscellaneous / Advanced](../miscellaneous/advanced_options.md)) and can be overridden by the **Copy** command's **DELEGATE** argument:

By default, file copying is delegated to a very-high-level API provided by Windows. When that API copies a file from one NTFS device to another, it always copies all ADS streams attached to it (there is no way to tell it not to). That means a little extra time is always spent copying ADS streams, but this is often offset by the API being faster in other ways. However, if you really don't want the ADS streams preserved then additional time must be spent to delete them after the API has copied them.

On the other hand, if you configure Opus to copy files using custom, lower-level code, then Opus can choose when to copy the NTFS ADS streams and will only copy them if you really want them. That may be slightly faster, but the custom code may also be slower in other ways (depending on hardware, drivers, etc.).  
\* **Copy file descriptions (if not in ADS, or not already copying ADS)**: This attempts to preserve any description assigned to the copied files, if it is not already being preserved via the **Copy NTFS ADS** option.

This can be overridden by the **Copy** command's **COPYDESC** argument.

Turning this option on imposes extra per-file overheads when copying. You should generally only turn this on when using the DESCRIPT.ION file comment system that stores descriptions in a special file within each folder. If you are using NTFS ADS to store file comments, use the **Copy NTFS ADS** option, above, instead.  
\* **Copy sparse files as sparse**: Sparse files are a special feature of the NTFS file system that allows regions of a file to be marked as "empty" (containing all zero bytes), with those regions not using up any drive space. For example, a sparse 1GB file consisting of all zeroes could occupy almost no space. Sparse files are used in specialized applications like virtual machines. Some download tools also use them to track which regions of files have been downloaded. Normally, copying a sparse file results in a copy which is no longer sparse, meaning the copy occupies its full size on disk and the empty regions look like normal data, indistinguishable from any other sequence of zeros. On the other hand, if you turn this option on, any sparse regions in the source file will be recreated in the copy.

This can be overridden by the **Copy** command's **COPYSPARSE** argument.

Turning this option on will force Opus to use custom file-copying code *when copying sparse files*. (Normal files will still be delegated to the very-high-level API, if it is enabled.)  
**Permissions and Security:**

- **Copy file ownership**: This option copies file owner information, assuming the source and destination filesystems support the Windows concept of file owners. Normally, newly copied files will be owned by the user making the copy, but with this option on they would be owned by original file's owner. Because setting the file owner requires administrator permissions, this may cause a UAC prompt to be displayed if the original owner is not the current user.

You can opt to do this on **Local drives only** if desired.

This can be overridden by the **Copy** command's **COPYOWNER** argument.

Turning this option on will impose an extra per-file overhead.  
\* **Copy security permissions when copying, or moving between drives**: This reproduces the security permissions of each file on each respective copy, assuming the source and destination filesystems support Windows file permissions. When turned off, copied files inherit the permissions of the folders they are copied into, which is usually what you want.

This can be overridden by the **Copy** command's **COPYSECURITY** option.

Turning this option on will impose an extra per-file overhead.  
\* **Update permissions/encryption to match destination when moving on same drive**: Normally, when you move a file on the same drive (an operation that doesn't involve a new file being created), it will keep its original permissions. This can cause problems when you move files into a folder with different permissions. For example, if you moved a private file into a shared public folder, the file would keep its original permissions and not be accessible to users of the share. Turning on this option causes Opus to update the permissions of the moved file to match the folder it has been moved into.

Similarly, the moved file will be encrypted or decrypted if needed to match the normal state of the target folder. (This is about filesystem-level encryption, as provided by Windows/NTFS and controlled via a file or folder's standard Properties dialog, and not any other type of encryption.)

This can be overridden by the **Copy** command's **UPDATESECURITY** argument.

Turning this option on will impose an extra per-file overhead when moving files between folders on the same logical drive.  
\* **Update permissions even if it would trigger a UAC prompt**: When turned on, if a file was moved without elevation and there is an access-denied error when updating its permissions, Opus will display a UAC prompt and try to update the permissions again with elevation. When turned off, no UAC prompt will be displayed and updating permissions will be skipped if there is an access denied error.

Typically, and especially on network drives, if a folder is permissioned to allow you to move its contents without elevation then it will either allow you to modify the permissions without elevation as well (so no UAC prompt is required) or will block you from modifying permissions at all (so it will still fail even if you elevate, and the UAC prompt is just an annoyance).

If an access-denied error happens when moving the actual file (or one of the previous files), UAC elevation will still always be attempted and the elevation context will be re-used for updating file permissions without requiring a second UAC prompt.  
\* **Change ownership to match destination**: When turned on, Opus will attempt to set the file's owner to the account which owns the destination folder. When turned off, the owner will stay as-is when files are moved on the same drive. If the owner is not changed, extra permissions may be granted to it (e.g. if the destination folder passes rights to *CREATOR OWNER* on child files).  
\* **Preserve explicit (non-inherited) permissions**: When turned on, Opus will preserve any explicit, non-inherited permissions set on the file, merging them with the new permissions inherited from the destination folder; only old inherited permissions will be removed. When turned off, all old permissions will be removed and replaced by permissions inherited from the destination.
