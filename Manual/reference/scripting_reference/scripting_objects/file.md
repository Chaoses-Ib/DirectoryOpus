# File

The **File** object lets you read and write binary data from and to a file on disk (or in a Zip file, FTP site, etc). While the Microsoft *Scripting.FileSystemObject* object lets you read and write files already, it only supports text, not binary data. You can also use the **File** object to modify a file's attributes and timestamps.

You can obtain a **File** object using the **[FSUtil](fsutil.md).OpenFile** and **[Item](item.md).Open** methods. You can open a file in one of three modes:

- *read mode* - you can read data from the file via the **Read** method. You cannot write to it or modify its attributes.
- *write mode* - you can write data to the file via the **Write** method, and you can also modify the file's attributes. You cannot read data from it.
- *modify mode* - you can modify the file's attributes and timestamps, but you cannot read or write data.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the full pathname of the file.
</td></tr><tr><td>
error</td><td>

*int*</td><td>

Returns a Win32 error code that indicates the success or failure of the last operation. If the previous operation succeeded this will generally be **0**.

For example, if you try to open a non-existing file for reading using **FSUtil.OpenFile**, a valid **File** object will be returned - but the file itself would not be open. You can check if **error** returns **0** before proceeding to use the **File** object.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns the full pathname of the file as a **[Path](path.md)** object.
</td></tr><tr><td>
size</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns a **[FileSize](filesize.md)** object representing the size of this file, in bytes.
</td></tr><tr><td>
tell</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns a **[FileSize](filesize.md)** object representing the current position of the read or write cursor within this file, in bytes.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Close</td><td>

*none*</td><td>

*none*</td><td>

Closes the underlying file handle. After this call the **File** object is still valid but it can no longer read or write data.

If you want to use the **SetAttr** method to modify the attributes of a file you have created, you may want to call **Close** first otherwise the file system will set the *A* (archive) attribute on the file whether you want it set or not.

You may also want to close a file manually if you want to delete it, as some scripting languages (e.g. *JScript*) have lazy garbage collection and otherwise may keep the file handle open much longer than you intend.
</td></tr><tr><td>
Read</td><td>

\<<blob:target>\>  
\<int:size\></td><td>

*int* or  
*object:***[Blob](blob.md)**</td><td>

Reads data from the file. If you provide a *target* **[Blob](blob.md)** as the first parameter, the data will be stored in that **Blob**. Otherwise, a **Blob** will be created automatically.  
The optional *size* parameter specifies the number of bytes to read - the default behavior is to read the remaining contents of the file.  
A maximum of 1 GB (1073741824 bytes) can be read per call, whether a size is specified or implicit. To read a larger file, you must call **Read** multiple times.  
If you provide a **Blob** then the return value indicates the number of bytes read successfully from the file. If a **Blob** isn't provided then the return value is the automatically created **Blob** - you can use its **size** property to discover the number of bytes that were read.  
If **Read** returns zero (or an empty **Blob**), you can use the **error** property to test if anything went wrong, or if the file simply had no more data.
</td></tr><tr><td>
Seek</td><td>

\<int:delta\>  
\<string:method\></td><td>

*object:***[FileSize](filesize.md)**</td><td>

Moves the read or write cursor within this file. The *delta* parameter specifies how many bytes to move - how this is interpreted depends on the optional *method* parameter:

*b* - move relative to the beginning of the file  
*e* - move relative to the end of the file  
*c* - move relative to the current position (this is the default method)

The return value is a **[FileSize](filesize.md)** object indicating the new cursor position.
</td></tr><tr><td>
SetAttr</td><td>

*object:***[FileAttr](fileattr.md)**  
or \<string:attributes\></td><td>

*bool*</td><td>

Modifies the attributes of this file. You can either pass a string indicating the attributes to set, or a **[FileAttr](fileattr.md)**object. When using a string, valid attributes are:

*a* - archive  
*c* - compressed  
*e* - encrypted  
*h* - hidden  
*n* - normal  
*r* - read-only  
*s* - system  
p - pinned  
i - non-content indexed

Note that both *c* and *e* attributes cannot be set at the same time.

When you pass a string you can also use **+** and **-** to turn some attributes on or off without affecting others. For example, **SetAttr("-r")** would turn off the read-only attribute.

The return value is **True** if the operation was successful.
</td></tr><tr><td>
SetTime</td><td>

\<date:modify\>  
\<date:create\>  
\<date:access\></td><td>

*bool*</td><td>

Modifies one or more of the file's timestamps. The *create* and *access* parameters are optional. If you wish to specify no change for a timestamp, specify **0**.

Timestamps are specified as local time - use **SetTimeUTC** to specify them as UTC.

The return value is **True** for success.
</td></tr><tr><td>
SetTimeUTC</td><td>

\<date:modify\>  
\<date:create\>  
\<date:access\></td><td>

*bool*</td><td>

Modifies one or more of the file's timestamps. The *create* and *access* parameters are optional. If you wish to specify no change for a timestamp, specify **0**.

Timestamps are specified as UTC time - use **SetTime** to specify them as local time.

The return value is **True** for success.
</td></tr><tr><td>
Truncate</td><td>

*none*</td><td>

*bool*</td><td>

Truncates the file at the current position of the write cursor. You can use this in conjunction with the **Seek** method to pre-allocate a file's space on disk, for greater performance (i.e. seek to the final size of the file, truncate at that point, and then seek back to the start and write the data).

The return value is **True** for success.
</td></tr><tr><td>
Write</td><td>

\<<blob:source>\> or \<string:source\>  
\<int:from\>  
\<int:size\></td><td>
int</td><td>

Writes data from the specified **Blob** (or array) or *string* to the file.  
By default the entire contents of the **Blob** will be written, but you can use the optional *from* parameter to specify the source byte offset, and the *size* parameter to specify the number of bytes to write.  
A maximum of 1 GB (1073741824 bytes) can be written per call, whether a size is specified or implicit. To write a larger amount of data, you must call **Write** multiple times.  
If you provide a *string* rather than a Blob, the string will be automatically encoded as UTF-8.  
The return value indicates the number of bytes successfully written to the file.  
If **Write** returns zero, you can use the **error** property to test if anything went wrong or if there was simply no data to write (e.g. the specified **Blob** was empty).
</td></tr></tbody>
</table>

