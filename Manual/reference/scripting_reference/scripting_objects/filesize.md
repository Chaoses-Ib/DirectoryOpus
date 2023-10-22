# FileSize

The **FileSize** object is provided to make it easier to deal with variables representing file sizes. It's very common these days for files to be larger than 4GB but unfortunately ActiveX scripting does not have proper support for the 64-bit integers needed to represent such large numbers. Therefore, any time a file size or number representing a number of bytes is returned by the Opus scripting objects, it is as a **FileSize** object. For example, the **[Item](item.md).size** property returns a **FileSize** representing the size of a particular file or folder.

You can create a new **FileSize** object using the **[FSUtil](fsutil.md).NewFileSize** method. A FileSize object normally represents an *unsigned* 64 bit integer but if you specify the *"s"* flag on creation, it will store a *signed* integer instead.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the number of bytes represented by this **FileSize** object as a *string*. |
| cy | *currency* | Returns the number of bytes as a *currency* value. This is a 64 bit data type but it is stored as a fractional value, so you must multiply the returned value by 10000 to obtain the actual byte size. |
| fmt | *string* | Returns the number of bytes as an automatically formatted string (e.g. if the **FileSize** value is 1024, the string *1 KB* would be returned). |
| high | *decimal* | Returns the highest (most significant) 32 bits of the file size. Not all scripting languages support this data type (e.g. VBScript does not). |
| highhex | *string* | Returns the highest 32 bits of the file size as a hexadecimal string. |
| low | *decimal* | Returns the lowest (least significant) 32 bits of the file size. |
| lowhex | *string* | Returns the lowest 32 bits of the file size as a hexadecimal string. |
| val | *decimal* | Returns the number of bytes as a decimal value. This is a 64 bit data type but not all scripting languages support it (e.g. VBScript does not). |
| valhex | *string* | Returns the number of bytes as a hexadecimal string. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Add | *variant* | *none* | Adds the supplied value to the value of this **FileSize** object. You can pass a *string*, *int* or *currency* type, or another **FileSize** object.  <br />Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy. |
| Clone | *none* | *object:***FileSize** | Clones this **FileSize** object and returns a new one set to the same value. |
| Compare | *variant* | *int* | Compares the supplied value with the value of this **FileSize** object. The return value will be **0** (equal), **1** (greater) or **-1** (less). |
| Div | *variant* | *none* | Divides the value of this **FileSize** object with the supplied value. You can pass a *string*, *int* or *currency* type, or another **FileSize** object.  <br />Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy. |
| Mult | *variant* | *none* | Multiplies the value of this **FileSize** object with the supplied value. You can pass a *string*, *int* or *currency* type, or another **FileSize** object.  <br />Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy. |
| Set | *variant* | *none* | Sets the **FileSize** to the supplied value. You can pass a *string*, *int*,// decimal *or *currency// type, or another **FileSize** object. You can also pass a **[Blob](blob.md)**consisting of exactly 1, 2, 4 or 8 bytes, in which case the data contained in the **[Blob](blob.md)**will be used to form the number. You can use a hexadecimal string by pre-pending **\$** or **0x**.  <br />If the **FileSize** object is read-only, it will error if you try to modify it. Use **Clone** or **[FSUtil](fsutil.md).NewFileSize** to create a new object you can modify. |
| Sub | *variant* | *none* | Subtracts the supplied value from the value of this **FileSize** object. You can pass a *string*, *int* or *currency* type, or another **FileSize** object. Note that the **FileSize** object is *unsigned* and so the value cannot go below zero.  <br />Some **FileSize** objects are read-only and will error if you try to modify them. This includes ones returned by **[Item](item.md).size**. Use the **Clone** method to create a modifiable copy. |
| ToBlob | *int* | *object:***[Blob](blob.md)** | Returns a **[Blob](blob.md)**containing the bytes that make up the current value. By default 8 bytes will be copied to the **[Blob](blob.md)**(the full 64 bit number) but you can pass an alternative number of bytes (1, 2 or 4) as a parameter to truncate the value. |

