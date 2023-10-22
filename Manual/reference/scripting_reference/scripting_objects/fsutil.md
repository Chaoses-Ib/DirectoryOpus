# FSUtil

The **FSUtil** object provides several utility methods for dealing with the file system. It is obtained using the **DOpus.FSUtil** method.

\<commandtable columns="4" id="cmdtable_1"\> \$\$ Method Name \$\$ **Arguments** \$\$ Return Type \$\$ Description \$\$ CancelWatchChanges \$\$ \<string:id\> \$\$ *none* \$\$ Cancels folder or file change monitoring previously established by a call to the **WatchChanges** method. The **id** parameter is the ID you assigned to your watcher when it was created. \$\$ ComparePath \$\$ \<string:path1\>  
\<string:path2\>  
\<string:flags\> \$\$ *bool* \$\$ Compares the two provided path strings for equality - returns **True** if the two paths are equal, or **False** if otherwise.

The optional **flags** parameter lets you modify the comparison behavior. This parameter is a string containing zero or more of the following letters (case sensitive):

|       |                                                                     |
|-------|---------------------------------------------------------------------|
| **c** | Makes the path comparison **case sensitive**.                       |
| **p** | Returns **True** if *path2* is equal to or a **parent** of *path1*. |

\$\$ DisplayName \$\$ \<string:path\>  
\<string:flags\> \$\$ *string* \$\$ Retrieves the display name of a path. This is the form of a path that is intended to be displayed to the user, rather than used internally by Opus. For example, for a library path it will strip off the internal *?xxxxxxx* notation that Opus uses to identify library member folders.

The optional **flags** parameter lets you modify the behavior. This parameter is a string containing zero or more of the following letters (case sensitive):

|       |                                                                             |
|-------|-----------------------------------------------------------------------------|
| **e** | for editing (returns a string designed for editing rather than for display) |
| **f** | file part (returns the display filename rather than the entire path)        |
| **r** | resolve (resolves library paths to their underlying file system folder)     |

\$\$ Drives \$\$ *none* \$\$ **Vector:[Drive](drive.md)**  \$\$ Returns a **[Vector](vector.md)** of **[Drive](drive.md)** objects, one for each drive on the system. \$\$ Exists \$\$ \<string:path\>  
\<string:flags\> \$\$ *bool* \$\$ Returns **True** if the specified file, folder or device exists, or **False** otherwise.

The optional *flags* parameter can be set to **w** to use wildcards in the final path component. \$\$ GetADSNames \$\$ \<string:path\> \$\$ *object:***[StringSet](stringset.md)**  \$\$ Returns a **[StringSet](stringset.md)** containing the names of any alternate data streams (ADS) found for the specified file or folder. \$\$ GetErrorMsg \$\$ \<int:error\> \$\$ *string* \$\$ Returns the localized text description for a system error code. \$\$ GetFolderPair \$\$ \<string:path\>  
\<string:flags\> \$\$ *object:***[PairedFolder](pairedfolder.md)** \$\$ Returns the [pair](/Manual/preferences/preferences_categories/frequently_used_paths/paired_folders.md) of the specified folder, if one exists. The optional flags are compared against the configured options for the pair; they let you control in which conditions the pair is returned, and how to handle it if the paired folder doesn't exist.

|       |                                               |
|-------|-----------------------------------------------|
| **d** | Default dual-display folder                   |
| **v** | Default Navigation Lock target                |
| **n** | Turn on Navigation Lock automatically         |
| **y** | Default Synchronize target                    |
| **l** | Always display primary folder at the left/top |
| **u** | Use path even if it doesn't exist             |
| **i** | Ignore the pair                               |
| **g** | Go up to first existing parent                |

\$\$ GetItem \$\$ \<string:path\> \$\$ *object*:**[Item](item.md)**  \$\$ Creates an **[Item](item.md)** object for the specified file path. \$\$ GetMetadata \$\$ \<string:path\> \$\$ *object:***[Metadata](metadata.md)**  \$\$ Returns a **[Metadata](metadata.md)** object representing the metadata for the specified file. \$\$ GetShellProperty \$\$ \<string:path\>

\<string:property\> or \<**[Map](map.md)**:properties\>  
\<string:type\> \$\$ *variant* \$\$ Returns the value of one or more shell properties for the specified file.

The file path must be provided as the first parameter.

The second parameter can be the name (or PKEY) of a property to retrieve, in which case the property value will be returned.

Alternatively, the second argument can be a **[Map](map.md)**object which lets you retrieve multiple properties at once. Each property you want to retrieve should be added to the **[Map](map.md)**with its name as a key, with an empty string as its value. The values in the **Map** will be replaced by the property values.

The optional **type** argument is a string that lets you control how the properties are looked up by name (not case-sensitive):

|       |                                                             |
|-------|-------------------------------------------------------------|
| **R** | The first property whose raw name matches will be used.     |
| **D** | The first property whose display name matches will be used. |

If neither is specified, both raw and display names can match. Note that if a shell property is returned by the system as a SAFEARRAY type, it will be converted automatically to a **[Vector](vector.md)** object. \$\$ GetShellPropertyList \$\$ \<string:pattern\>  
\<string:type\> \$\$ *object:***[ShellProperty](shellproperty.md)** \$\$ Returns a **[Vector](vector.md)** of **[ShellProperty](shellproperty.md)** objects which represents all the possible shell properties available on the system.

You can optionally provide a wildcard *pattern* as the first argument - if you do, only properties whose names match the supplied pattern will be returned.

The optional **type** argument is a string that lets you restrict the list of properties further (not case-sensitive):

|       |                                                |
|-------|------------------------------------------------|
| **R** | Property raw names must match the pattern.     |
| **D** | Property display names must match the pattern. |

If neither is specified, both raw and display names can match. \$\$ GetTempDirPath \$\$ \<int:lifetime\> \$\$ *object:***[Path](path.md)** \$\$ Creates a temporary folder (with a unique name) and returns the path to it in a **[Path](path.md)** object. Temporary folders created with this method have a limited lifetime after which Opus will automatically delete them (it will also clean them up when it's shutdown and restarted). The default lifetime is 20 minutes; you can change this using the optional parameter. \$\$ GetTempFile \$\$ \<string:suffix\>  
\<string:prefix\>  
\<string:flags\>  
\<object:window\> \$\$ *object:***[File](file.md)**  \$\$ Creates a temporary file and returns a **[File](file.md)** object ready to be written to.

The returned object supports both reading and writing, without having to open the file a second time (although you can do that if it is easier).

You can obtain the name of the file using the **[File](file.md)**.path property.

An optional filename **suffix** can be specified; if not provided (or an empty string is passed), the default is ".tmp".

An optional **prefix** can also be specified; if not provided (or an empty string is passed), the default is "dop".

Between the suffix and prefix, Opus will insert additional characters into the name to ensure it is unique.

As an example, **DOpus.FSUtil.GetTempFilePath(".txt","cat-")** might generate *C:\Users\Leo\AppData\Local\Temp\cat-202106230928470962.txt* for a file path.

The optional **flags** parameter can include zero or more of these letters (not case-sensitive):

|       |                                                                  |
|-------|------------------------------------------------------------------|
| **d** | delete-on-close. File will be deleted automatically when closed. |
| **p** | permit deletion. Other processes can delete the file.            |
| **r** | read shareable. Other processes can read the file.               |
| **w** | write shareable. Other processes can write to the file.          |

The read, write and deletion sharing modes affect what other processes are allowed to do while the file is still open. Once the file is closed (assuming it has not been auto-deleted), other processes are always free to read, write or delete the file.

When delete-on-close is used, other things may not be able to open the file unless they specifically permit the file to be deleted at the time they open it.

The optional **window** parameter lets you associate the **File** object with a **[Tab](tab.md)** or a **[Lister](lister.md)**, which will be used if Opus needs to display any dialogs (e.g. a UAC elevation dialog).   \$\$ GetTempFilePath \$\$ \<string:suffix\>  
\<string:prefix\>  
\$\$ *object:***[Path](path.md)** \$\$ Creates a temporary file (with a unique name) and returns the path to it in a **[Path](path.md)** object.

An optional filename **suffix** can be specified; if not provided (or an empty string is passed), the default is ".tmp".

An optional **prefix** can also be specified; if not provided (or an empty string is passed), the default is "dop".

Between the suffix and prefix, Opus will insert additional characters into the name to ensure it is unique.

As an example, **DOpus.FSUtil.GetTempFilePath(".txt","cat-")** might generate *C:\Users\Leo\AppData\Local\Temp\cat-202106230928470962.txt* for a file path. \$\$ GetType \$\$ \<string:path\>  
\<string:flags\> \$\$ *string* \$\$ Returns a string indicating the item type of the specified file path. The string will be either **file**, **dir** or **invalid** if the path doesn't exist.

The optional **flags** argument is used to control the behavior with archives. Normally, an archive will be reported as **dir**, but if you specify "**a**" for the flags parameter it will be reported as **file**.

This method is different to **PathType** which tells you the underlying "namespace" type rather than whether something is simply a file or a folder. \$\$ Hash \$\$ \<string:path\> or  
\<object:**[Blob](blob.md)**\>

\<string:type\> \$\$ *string* or *object:***[Vector](vector.md)**  \$\$ Calculates a checksum for the specified file or **[Blob](blob.md)**.  
By default, the MD5 hash is calculated, but you can use the optional **type** parameter to change the hash/checksum algorithm. Valid values are (not case-sensitive) **md5**, **blake3**, **sha1**, **sha256**, **sha512**, **crc32**, **crc32_php** and **crc32_php_rev**.

You can also specify multiple types (e.g. *"md5,sha1,sha256"*) at once, in which case the specified checksums will be calculated at the same time, and the result will be returned as a **[Vector](vector.md)** of *strings* (in the same order as you requested them).

Unlike the other algorithms, CRC32 is a concept rather than a well-defined standard. We have provided the three CRC32 implementations you're most likely to encounter:

- *CRC32* is most common in the Windows world and matches what tools like 7-Zip and PKZip call "CRC32", and what PHP calls "CRC32b".
- *CRC32_PHP* is less common and matches what BZIP2 uses and what PHP outputs by default.
- *CRC32_PHP_REV* is the same as *CRC32_PHP* but with the result's byte-order reversed, as output by some tools.

*Example (VBScript):*

    DOpus.FSUtil.Hash("C:\Windows\Notepad.exe","md5")

\$\$ NewFileAttr \$\$ *\<attributes\>*  
\$\$ *object:***[FileAttr](fileattr.md)**  \$\$ Creates a new **[FileAttr](fileattr.md)** object, which represents file attributes.

You can initialize the new object by passing either a string representing the attributes to turn on (e.g. *"hsr"*) or another **[FileAttr](fileattr.md)** object. If you don't pass a value, the new object will default to all attributes turned off. \$\$ NewFileSize \$\$ *\<size\>*  
or  
\<string:"s"\>  
*\<size\>* \$\$ *object:***[FileSize](filesize.md)**  \$\$ Creates a new **[FileSize](filesize.md)** object, which makes it easier to handle 64 bit file sizes.

You can initialize this with a number of data types (*int*, *string*, *decimal*, *currency*, another **[FileSize](filesize.md)** object, or a **[Blob](blob.md)** containing exactly 1, 2, 4 or 8 bytes). You can use a hexadecimal string by pre-pending **\$** or **0x**.

*Example (VBScript):*

    DOpus.FSUtil.NewFileSize(1024)

When only a size is specified, the result will be an *unsigned* value, which means it can represent larger size values but cannot represent negative values.

To create a *signed* value instead, specify "**s**" as the first parameter and specify the size as the second parameter. This is case-sensitive; it must be a lowercase "s".

*Example (VBScript):*

    DOpus.FSUtil.NewFileSize("s", -1024)

\$\$ NewPath \$\$ \<string:path\> \$\$ *object:***[Path](path.md)** \$\$ Creates a new **[Path](path.md)**object initialised to the provided path string. \$\$ NewWild \$\$ \<string:pattern\>  
\<string:flags\>  
\$\$ *object:***[Wild](wild.md)**  \$\$ Creates a new **[Wild](wild.md)** object.

If a **pattern** and **flags** are provided, the pattern will be parsed automatically; otherwise, you must call the **Parse** method on the returned object before using it.

See the description of the **[Wild](wild.md).Parse** method for a list of the valid flags. \$\$ OpenFile \$\$ \<string:path\> or \<object:**[Blob](blob.md)**\>  
\<string:mode\>  
\<object:window\> or \<string:elevation\> \$\$ *object:***[File](file.md)**  \$\$ Opens or creates a file and returns a **[File](file.md)** object that lets you access its contents as binary data.

A **File** object is always returned, even if the file could not be opened. Check **File.error** on the returned object immediately after creating it to see if opening the file succeeded.

Even if a file was not be opened, some of the returned object's methods may still work. For example, if a file exists but permissions block you from opening it, you may still be able to change its attributes, or vice versa.

The first argument can be either:

- A string or **[Path](path.md)**object which specifies the file to open.
- An existing **[Blob](blob.md)**object to create a **[File](file.md)** object that gives you read/write stream access to a chunk of memory.

When opening a **[Blob](blob.md)**, the created object will always be in *read-write mode* and the rest of the parameters (**mode** and **window**/**elevation**) are not used and need not be specified.

When opening a file, the optional **mode** parameter specifies how to open it (case sensitive):

|        |                                                                           |
|--------|---------------------------------------------------------------------------|
| **r**  | *Read mode*. The file can be read but not written. (This is the default.) |
| **w**  | *Write mode*. The file can be written, but not read.                      |
| **rw** | *Read-write mode*. The file can be read and written from the same object. |

When opening in *write mode* or *read-write mode*, you can specify additional **mode** flags that control how the file is created or opened (case sensitive):

|       |                                                                                                                                                                               |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **c** | Create a new file, only if it doesn't already exist. The call will fail if the file already exists.                                                                           |
| **a** | Create a new file, always. If the file already exists, it will be overwritten, i.e. truncated to zero length. (This is the default if **w** or **rw** are used on their own.) |
| **e** | Open existing file. The call will fail if the file does not already exist.                                                                                                    |
| **o** | Open existing file. The file will be created if it does not exist.                                                                                                            |
| **t** | Truncate existing file. If the file exists, it will be truncated to zero length. If the file doesn't exist, the call will fail.                                               |

The **mode** flags can also include these letters (case sensitive):

|       |                                                                                                                                                                                                                                                                                                         |
|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **d** | Delete-on-close. The file will be automatically deleted when closed. (If something else also has the file open, it won't be deleted until everything closes it.)                                                                                                                                        |
| **f** | Force. Opus will clear the file's read-only attribute if it blocks opening the file for writing; otherwise, attempting to open a read-only file for writing will fail. For example, "**wof**" is like "**wo**" mode but also clears the read-only attribute.                                            |
| **m** | Modify mode. Use this if you want to use the **File** object to read or modify the file's attributes, or get the file's size, without reading or writing the actual file contents.                                                                                                                      |
| **p** | Permit deletion. Other processes can delete the file before it has been closed, although any deletion will not take place until it is closed. Files opened via this method always permit other readers and writers. Your script should not assume it has an exclusive lock on the file or its contents. |

When opening an existing file which something else already flagged for deletion, including files already open in *delete-on-close* mode, the **p** (permit deletion) flag must be specified.

Non-Windows filesystems may have different locking and sharing rules. Opus will pass the requested flags to them, but it is ultimately up to them how they behave.

The optional third parameter takes either a **window** object or a string indicating **elevation** mode. This parameter influences the behavior of UAC elevation prompts (and potentially other user interface elements) that may be triggered when opening the file. It can be one of the following:

- An Opus **[Tab](tab.md)** or **[Lister](lister.md)** object which UAC prompts will appear over if elevation is required and has not already been obtained.
- The string "**NoElevate**" to prevent UAC elevation entirely when opening this file.
- The string "**ElevateNoAsk**" to prevent UAC prompts while still gaining elevation if something else already got it (e.g. a previous **OpenFile** call).

*Example (VBScript):*

    Set F = DOpus.FSUtil.OpenFile("C:\Test.txt","wrcf","NoElevate")

\$\$ PathType \$\$ \<string:path\> \$\$ *string* \$\$ Returns a string indicating the underlying "namespace" type of the specified file path. Possible values are:

|             |                                                                                 |
|-------------|---------------------------------------------------------------------------------|
| **shell**   | The path refers to the Windows shell - e.g. a virtual folder like This PC       |
| **filesys** | The path is a real filesystem path - e.g. C:\Windows                            |
| **ftp**     | The path is an FTP path                                                         |
| **zip**     | The path is a zip file                                                          |
| **mtp**     | The path is an MTP path (i.e. a portable device like a phone or a tablet)       |
| **lib**     | The path is a library                                                           |
| **coll**    | The path is a collection                                                        |
| **plugin**  | The path is a plugin-provided namespace, most probably an archive (but not Zip) |

This method is different to **GetType** which tells you whether something is a file or a directory. \$\$ ReadDir \$\$ \<string:path\>  
\<string:flags\>  
\$\$ *object:***[FolderEnum](folderenum.md)**  \$\$ Returns a **[FolderEnum](folderenum.md)** object that lets you enumerate the contents of the specified folder.

The optional **flags** string can include zero or more flag characters (not case-sensitive):

|       |                                                                                                                                                                                                                                                                                                                                                               |
|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **r** | Recursively enumerate the folder, listing the contents of the folder, its sub-folders, their sub-folders, and so on.                                                                                                                                                                                                                                          |
| **l** | Skip links. Prevents the traversal of symbolic links and junctions when recursively enumerating folders.                                                                                                                                                                                                                                                      |
| **s** | Shell enumeration. Ask's the Windows Shell to enumerate non-filesystem folders. For example, the *Quick Access* folder on Windows 10 could be enumerated with **ReadDir("/quickaccess","s")**; it would not work without the "**s**" because Quick Access is not a real filesystem directory. If you don't need any flags, skip the second argument entirely. |

You may see older scripts pass **True** and **False** as the second argument, to turn recursion on and off; that is deprecated but remains supported for compatibility. \$\$ Resolve \$\$ \<string:path\>  
\<string:flags\> \$\$ *object:***[Path](path.md)** \$\$ Resolves the specified path string to its real filesystem path, with support for converting:

- **[Folder Aliases](/Manual/basic_concepts/the_lister/navigation/aliases.md)** to the real paths they point to.
- **Library** and **File Collection** items to their real filesystem paths.
- Application paths in the **{apppath\|*appname*}** form.
- Environment variables.
- Optionally, **junctions** and **symbolic links** can be resolved to their targets.

It is safe to pass a path which does not need resolving; the path will be returned unmodified, so you can call this on things without checking if it is needed first.

Scripts which pass the current directory to external software should generally call Resolve on the path first, otherwise they risk passing aliases like */desktop* to things which won't understand them.

The optional **flags** string can include the following letter (not case-sensitive):

|       |                                                             |
|-------|-------------------------------------------------------------|
| **j** | resolve junctions and symbolic links to their target folder |

Note that **[Path](path.md)** objects also have a similar **Resolve** method which modifies them in-place. \$\$ SameDrive \$\$ \<string:path1\>  
\<string:path2\>  
\<string:flags\> \$\$ *bool* \$\$ Returns **True** if the two specified paths both refer to the same drive or partition.

The optional **flags** string can contain zero or more of the following letters (case sensitive):

|       |                                                                                                                                                                                                 |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **c** | Consider the **CD burning staging area** the same as the CD (or other writable optical media) itself.                                                                                           |
| **m** | Handle **NTFS mount points**. (Slower but more accurate if either path may be below a mount point which really points to a different drive.)                                                    |
| **r** | Real paths only. (Skip extra processing that is only useful for things like FTP sites and MTP devices.)                                                                                         |
| **s** | Test if paths point to the same drive via drive letters created by the Windows **subst** command.                                                                                               |
| **u** | Compare **FTP users**. (By default, FTP paths are considered the "same drive" if they point to the same FTP site. The **u** flag adds the requirement that both paths have the same user name.) |
| **z** | If **path1** is *inside* a Zip file or other archive, only consider **path2** on the "same drive" if it is the archive itself or is *inside* the same archive.                                  |
| **Z** | If **path1** is *inside* a Zip file or other archive, only consider **path2** on the "same drive" if it is *inside* the same archive.                                                           |

When neither **z** nor **Z** are specified, archives are essentially treated like normal directories and will be considered on the "same drive" as any path pointing to the same drive the archive is on, including other archive paths on that drive. \$\$ WatchChanges \$\$ \<string:id\>  
\<string:path\>  
\<string:flags\> \$\$ *int* \$\$ Establish monitoring of a folder or file for changes. Returns **0** for success or an error code on failure.

When a change occurs to a monitored file or folder, the script's [OnFilesystemChange](/Manual/reference/scripting_reference/scripting_events/onfilesystemchange.md) event is triggered.

The **id** argument lets you provide an ID for this watcher that's used to identify it when changes occur. **dir** is the full path to a filesystem folder, or a file if the **i** flag is set.

The optional flags are:

|       |                                                                 |
|-------|-----------------------------------------------------------------|
| **f** | monitor for file change in folder (e.g. file created)           |
| **d** | monitor for directory change in folder (e.g. directory created) |
| **r** | recursive - monitor sub-folders                                 |
| **a** | monitor for file attribute changes                              |
| **s** | monitor for file size changes                                   |
| **w** | monitor for last write time changes                             |
| **i** | monitor a single file rather than a folder                      |

Use the **CancelWatchChanges** method to cancel monitoring.

\</commandtable\>
