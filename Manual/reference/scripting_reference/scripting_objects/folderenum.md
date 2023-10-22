# FolderEnum

The **FolderEnum** object is returned from the **[FSUtil](fsutil.md).ReadDir** method. It lets you enumerate (optionally, recursively) the contents of a folder.

| Property Name | Return Type | Description |
| --- | --- | --- |
| complete | *bool* | **True** if the enumeration is complete, otherwise **False**. |
| error | *int* | If an error occurs this will return the error code. It will return 0 on success. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Close | *none* | *none* | Closes the underlying file system handle used to perform the enumeration. You might call this method if you want to delete the folder you just enumerated. After this method is called the **complete** property will return **True**. |
| Next | \<int:count\>  <br />\<**[Vector](vector.md)**:vector\> | *object:***[Item](item.md)** <br /><br />or<br /><br />*object:***[Vector](vector.md)** | Returns the next item in the enumeration.<br /><br />By default (with no arguments provided) a single **[Item](item.md)** object is returned. For higher performance, you can specify a number as the first argument to return more than one item at once - in this case, a **[Vector](vector.md)** of **[Item](item.md)** objects is returned instead. Specify **-1** to return all items in the folder in one call.<br /><br />You can also create your own **[Vector](vector.md)** and pass it as the second argument to stop Opus creating a new **[Vector](vector.md)** each time. |

