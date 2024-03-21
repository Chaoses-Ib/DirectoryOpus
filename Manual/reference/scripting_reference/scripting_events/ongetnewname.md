# OnGetNewName

The **OnGetNewName** event is one of the three alternate entry points for [rename scripts](/Manual/scripting/rename_scripts/README.md). The other two events - **Rename_GetNewName** and **Rename_GetNewName2**, are deprecated should only be used for backwards compatibility with Opus 10.

| **Method Name:** | OnGetNewName |
| --- | --- |
| **Argument Type:** | **[GetNewNameData](../scripting_objects/getnewnamedata.md)** |
| **Return Type:** | *bool* or *string* |
| **Description:** | When using a rename script, the **OnGetNewName** event is called for every selected file and folder, giving the script a chance to modify the name.  <br />The **GetNewNameData.item** property identifies the item being renamed. You can access the item's metadata and other information using the various **[Item](../scripting_objects/item.md)** properties.  <br />The **oldname** property returns the "old name" pattern as entered by the user in the [rename dialog](/Manual/file_operations/renaming_files/advanced_rename/README.md). The **newname** property returns the proposed new name of the item. This represents the result of all the other non-scripted options in the rename dialog (capitalization, automatic numbering, etc).<br /><br />You can return two different types from this event:<br /><br />- *bool*: If you return **True**, the item will not be renamed. If you return **False** (this is the default) the item will be renamed to the proposed new name (the **newname** property).<br />- *string*: You can return a *string* to specify a new name for the item. |

