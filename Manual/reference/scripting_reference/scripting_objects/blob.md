# Blob

A **Blob** object represents a chunk of binary data. Scripting languages like *VBScript* and *JScript* have no built-in support for binary data - this object can be used to allocate a chunk of memory and manipulate it in a similar way to low-level languages like C. You can use **Blob** objects in conjunction with the **[File](file.md)** object to read or write binary data from or to disk files.

**Blob** objects are convertible to and from two types of ActiveX arrays - a *SAFEARRAY* of type *VT_UI1* (known as an **array**) and a *SAFEARRAY* of type *VT_VARIANT*, with each variant holding a *VT_UI1* (known as a **VB array**). You can initialize a **Blob** with either of these two types of array (either when creating it via the **DOpusFactory.Blob** method or with the **Blob.CopyFrom** method), and you can also convert a **Blob** back to an array with the **ToArray** and **ToVBArray** methods. Support for these array types is dependent on the scripting language.

You can read and write individual bytes within the **Blob** by indexing the byte offset starting from 0. For example, *my_blob(5) = 128* would set the value of the sixth byte in the blob to 128.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
size</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns a **[FileSize](filesize.md)** object representing the size of this **Blob** in bytes.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Compare</td><td>

\<<Blob:source>\>  
\<int:to\>  
\<int:from\>  
\<int:size\></td><td>

*int*</td><td>

Compares the contents of this **Blob** against another **Blob** (or array). By default the entire contents of the two blobs are compared. The optional parameters that let you configure the operation are:

to - specifies the byte offset within this **Blob** to compare against. Defaults to 0.  
from - specifies the byte offset within the source **Blob** to compare with. Defaults to 0.  
size - specifies the number of bytes to compare. Defaults to the full size of the source **Blob**.

The return value is **0** if the two blobs are the same. A value of **-1** indicates this blob is less than the other blob, and **1** indicates this blob is greater than the other blob.
</td></tr><tr><td>
CopyFrom</td><td>

\<<Blob:source>\>  
\<int:to\>  
\<int:from\>  
\<int:size\>

*or*  
   
\<string\>  
\<type\></td><td>

*none*</td><td>

Copies data from the source **Blob** (or array) into this **Blob**. By default the entire contents of the source **Blob** will be copied over the top of this one. The optional parameters that let you configure the operation are:

to - specifies the byte offset within this **Blob** to copy to. Defaults to 0.  
from - specifies the byte offset within the source **Blob** to copy from. Defaults to 0.  
size - specifies the number of bytes to copy. Defaults to the full size of the source **Blob**.

As well as copying from another **Blob**, you can use this method to initialise a **Blob** from a string. By default the **Blob** will be set to the Unicode form of the string; if you pass **"utf8"** as the second parameter it will initialise the **Blob** with the UTF8-encoded form of the string.

If this **Blob** is not currently large enough to contain the copied data it will be resized automatically.
</td></tr><tr><td>
Find</td><td>

\<<Blob:search>\>  
\<int:from\>  
\<int:size\></td><td>

*object:***[FileSize](filesize.md)**</td><td>

Searches the contents of this **Blob** for the data contained in another **Blob** (or array). By default the entire contents of this **Blob** are searched. The optional **from** parameter lets you specify the starting position for the search, and the optional **size** parameter lets you specify the length of data in this Blob to search through.  
The return value is -1 if the search data were not found, otherwise the offset from the start of the **Blob** data is returned.
</td></tr><tr><td>
Free</td><td>

*none*</td><td>

*none*</td><td>

Frees the memory associated with this **Blob** and resets its size to 0.
</td></tr><tr><td>
Init</td><td>

*none*</td><td>

*none*</td><td>

Initialises the contents of the **Blob** (every byte within the blob will be set to 0). Equivalent to *Set(0)*.
</td></tr><tr><td>
Resize</td><td>

\<int:size\></td><td>

*none*</td><td>

Resizes the **Blob** to the specified number of bytes.
</td></tr><tr><td>
Reverse</td><td>

*none*</td><td>

*none*</td><td>

Reverses the contents of the **Blob**.
</td></tr><tr><td>
Set</td><td>

\<byte:value\>  
\<int:to\>  
\<int:size\></td><td>

*none*</td><td>

Sets the contents of the **Blob** to the specified byte value (every byte within the blob will be set to that value). By default the whole **Blob** will be affected. The option *to* parameter lets you specify a byte offset to start at, and the optional *size* parameter lets you control the number of bytes affected.
</td></tr><tr><td>
ToArray</td><td>

\<int:from\>  
\<int:size\></td><td>

SAFEARRAY of  
VT_UI1</td><td>

Converts the contents of this **Blob** to a *SAFEARRAY* of type *VT_UI1*. By default the entire contents of the **Blob** will be copied to the array. The optional parameters that let you configure the operation are:  
from - specifies the byte offset within the source **Blob** to copy from. Defaults to 0.  
size - specifies the number of bytes to copy. Defaults to the full size of the source **Blob**.
</td></tr><tr><td>
ToVBArray</td><td>

\<int:from\>  
\<int:size\></td><td>

SAFEARRAY of  
VT_VARIANT</td><td>

Converts the contents of this **Blob** to a *SAFEARRAY* of type *VT_VARIANT*. Each variant in the array contains a *VT_UI1*. By default the entire contents of the **Blob** will be copied to the array. The optional parameters that let you configure the operation are:

from - specifies the byte offset within the source **Blob** to copy from. Defaults to 0.  
size - specifies the number of bytes to copy. Defaults to the full size of the source **Blob**.
</td></tr></tbody>
</table>

