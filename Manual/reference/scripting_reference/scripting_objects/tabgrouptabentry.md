# TabGroupTabEntry

The **TabGroupTabEntry** object represents a single [folder tab](/Manual/basic_concepts/the_lister/tabs/README.md). The folder tabs in a tab group can be enumerated via the **[TabGroupTabList](tabgrouptablist.md)** object.

| Property Name | Return Type | **Description** |
| --- | --- | --- |
| color | *string* | Returns the color, if any, assigned to this tab. |
| format | object:**[Format](format.md)** | Returns the folder format of this tab. |
| linkid | *int* | Returns the link ID of this tab, if it is linked to another tab. Both tabs will have the same link ID but otherwise the value is meaningless. Use the **[TabGroup](tabgroup.md).Link** and **Unlink** methods to change tab linkage. |
| linktype | *string* | If this tab is linked as a slave, returns the string **"slave"**. |
| locked | *string* | Returns the lock type of this tab. Valid values are **"on"**, **"off"**, **"changes"** and **"reuse"**. |
| name | *string* | Returns the name of this tab if one is assigned. Tabs that don't have specific names assigned will usually show the last component of the path as their name. |
| path | *object:***[Path](path.md)** | Returns the path that this tab will load when it's opened. |

  

| **Method Name** | **Arguments** | **Return Type** | **Description** |
| --- | --- | --- | --- |
| Duplicate | *none* | *object:***TabGroupTabEntry** | Returns a duplicate of this tab entry. |

 
