# FileSize

The **FileSize** object is provided to make it easier to deal with variables representing file sizes. It's very common these days for files to be larger than 4GB but unfortunately ActiveX scripting does not have proper support for the 64-bit integers needed to represent such large numbers. Therefore, any time a file size or number representing a number of bytes is returned by the Opus scripting objects, it is as a **FileSize** object. For example, the **[Item](item.md).size** property returns a **FileSize** representing the size of a particular file or folder.

You can create a new **FileSize** object using the **[FSUtil](fsutil.md).NewFileSize** method. A FileSize object normally represents an *unsigned* 64 bit integer but if you specify the *"s"* flag on creation, it will store a *signed* integer instead.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

Returns the number of bytes represented by this **FileSize** object as a *string*.
</td></tr><tr><td>
cy</td><td>

*currency*</td><td>

Returns the number of bytes as a *currency* value. This is a 64 bit data type but it is stored as a fractional value, so you must multiply the returned value by 10000 to obtain the actual byte size.
</td></tr><tr><td>
fmt</td><td>

*string*</td><td>

Returns the number of bytes as an automatically formatted string (e.g. if the **FileSize** value is 1024, the string *1 KB* would be returned).
</td></tr><tr><td>
high</td><td>

*decimal*</td><td>
Returns the highest (most significant) 32 bits of the file size. Not all scripting languages support this data type (e.g. VBScript does not).
</td></tr><tr><td>
highhex</td><td>

*string*</td><td>
Returns the highest 32 bits of the file size as a hexadecimal string.
</td></tr><tr><td>
low</td><td>

*decimal*</td><td>
Returns the lowest (least significant) 32 bits of the file size.
</td></tr><tr><td>
lowhex</td><td>

*string*</td><td>
Returns the lowest 32 bits of the file size as a hexadecimal string.
</td></tr><tr><td>
val</td><td>

*decimal*</td><td>
Returns the number of bytes as a decimal value. This is a 64 bit data type but not all scripting languages support it (e.g. VBScript does not).
</td></tr><tr><td>
valhex</td><td>

*string*</td><td>
Returns the number of bytes as a hexadecimal string.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Add</td><td>

*variant*</td><td>

*none*</td><td>

Adds the supplied value to the value of this **FileSize** object. You can pass a *string*, *int* or *currency* type, or another **FileSize** object.  
Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy.
</td></tr><tr><td>
Clone</td><td>

*none*</td><td>

*object:***FileSize**</td><td>

Clones this **FileSize** object and returns a new one set to the same value.
</td></tr><tr><td>
Compare</td><td>

*variant*</td><td>

*int*</td><td>

Compares the supplied value with the value of this **FileSize** object. The return value will be **0** (equal), **1** (greater) or **-1** (less).
</td></tr><tr><td>
Div</td><td>

*variant*</td><td>

*none*</td><td>

Divides the value of this **FileSize** object with the supplied value. You can pass a *string*, *int* or *currency* type, or another **FileSize** object.  
Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy.
</td></tr><tr><td>
Mult</td><td>

*variant*</td><td>

*none*</td><td>

Multiplies the value of this **FileSize** object with the supplied value. You can pass a *string*, *int* or *currency* type, or another **FileSize** object.  
Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy.
</td></tr><tr><td>
Set</td><td>

*variant*</td><td>

*none*</td><td>

Sets the **FileSize** to the supplied value. You can pass a *string*, *int*,// decimal *or *currency// type, or another **FileSize** object. You can also pass a **[Blob](blob.md)**consisting of exactly 1, 2, 4 or 8 bytes, in which case the data contained in the **[Blob](blob.md)**will be used to form the number. You can use a hexadecimal string by pre-pending **\$** or **0x**.  
If the **FileSize** object is read-only, it will error if you try to modify it. Use **Clone** or **[FSUtil](fsutil.md).NewFileSize** to create a new object you can modify.
</td></tr><tr><td>
Sub</td><td>

*variant*</td><td>

*none*</td><td>

Subtracts the supplied value from the value of this **FileSize** object. You can pass a *string*, *int* or *currency* type, or another **FileSize** object. Note that the **FileSize** object is *unsigned* and so the value cannot go below zero.  
Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy.
</td></tr><tr><td>
ToBlob</td><td>

*int*</td><td>

*object:***[Blob](blob.md)**</td><td>

Returns a **[Blob](blob.md)**containing the bytes that make up the current value. By default 8 bytes will be copied to the **[Blob](blob.md)**(the full 64 bit number) but you can pass an alternative number of bytes (1, 2 or 4) as a parameter to truncate the value.
</td></tr></tbody>
</table>

