# FileGroup

The **FileGroup** object exposes information about a file group (when the file display is set to group by a particular column). The **[Tab](tab.md).filegroups** property returns a collection representing the current file groups in that tab, and the **[Item](item.md).filegroup** property returns the current file group of a particular item.  
  
Note: If you need to find which *file type group* a file is part of, rather than how the file is grouping based on currently visible columns, see the [FiletypeGroup](filetypegroup.md) object instead.  

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the name of the group. |
| collapsed | *bool* | Returns **True** if the group is currently collapsed. |
| count | *int* | Returns the number of items in this group. Note that groups can be empty; empty groups are not displayed in the file display but will still be returned by the **Tab.filegroups** property. |
| id | *int* | Returns the id number of this group. Id numbers are arbitrary - you shouldn't place any meaning on the actual value, but you can compare the id fields as an easy way to tell if two items are in the same group. |
| members | *object:***[Items](items.md)** | Returns an **[Items](items.md)** object that represents all the files and folders in this group. |
| type | *string* | Returns a string indicating the collation type of the group. |

