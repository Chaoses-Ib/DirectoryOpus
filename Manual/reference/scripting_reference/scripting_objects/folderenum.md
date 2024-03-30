# FolderEnum

The **FolderEnum** object is returned from the **[FSUtil](fsutil.md).ReadDir** method. It lets you enumerate (optionally, recursively) the contents of a folder.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
complete</td><td>

*bool*</td><td>

**True** if the enumeration is complete, otherwise **False**.
</td></tr><tr><td>
error</td><td>

*int*</td><td>
If an error occurs this will return the error code. It will return 0 on success.
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

Closes the underlying file system handle used to perform the enumeration. You might call this method if you want to delete the folder you just enumerated. After this method is called the **complete** property will return **True**.
</td></tr><tr><td>
Next</td><td>

\<int:count\>  
\<**[Vector](vector.md)**:vector\></td><td>

*object:***[Item](item.md)** 

or

*object:***[Vector](vector.md)**</td><td>

Returns the next item in the enumeration.

By default (with no arguments provided) a single **[Item](item.md)** object is returned. For higher performance, you can specify a number as the first argument to return more than one item at once - in this case, a **[Vector](vector.md)** of **[Item](item.md)** objects is returned instead. Specify **-1** to return all items in the folder in one call.

You can also create your own **[Vector](vector.md)** and pass it as the second argument to stop Opus creating a new **[Vector](vector.md)** each time.
</td></tr></tbody>
</table>

