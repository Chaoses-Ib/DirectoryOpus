# GetNewNameData

If a [rename script](/Manual/scripting/rename_scripts/RAEDME.md) is implemented using the **[OnGetNewName](../scripting_events/ongetnewname.md)** method, it receives a **GetNewNameData** object for each item being renamed.  

| Property Name | Return Type | Description |
| --- | --- | --- |
| custom | object:**[CustomFieldData](customfielddata.md)** | Returns a **[CustomFieldData](customfielddata.md)** object which provides the values of any [custom fields](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) your script added to the *Rename* dialog. |
| item | *object:***[Item](item.md)** | Returns an **[Item](item.md)** object representing the file or folder being renamed. |
| newname | *string* | Returns the proposed new name of the item. This will be the result of the application of any selected standard options in the [rename dialog](/Manual/file_operations/renaming_files/advanced_rename/RAEDME.md) (numbering, capitalization, etc). |
| newname_ext | *string* | Returns the file extension of the proposed new name. Does not take multi-part extensions into account (e.g. will return ".rar" rather than ".part1.rar"). |
| newname_ext_m | *string* | Returns the file extension of the proposed new name, taking multi-part extensions into account (e.g. will return ".part1.rar" rather than ".rar"). |
| newname_field | *string* | Returns the contents of the *New Name* field (that is, not the calculated new name after all the options have been applied, but the actual text contents of the field as entered by the user). |
| newname_stem | *string* | Returns the file stem of the proposed new name. Does not take multi-part extensions into account (e.g. will return "catpictures.part1" rather than "catpictures"). |
| newname_stem_m | *string* | Returns the file stem of the proposed new name, taking multi-part extensions into account (e.g. will return "catpictures" rather than "catpictures.part1"). |
| oldname_field | *string* | Returns the "old name" pattern as entered by the user in the [rename dialog](/Manual/file_operations/renaming_files/advanced_rename/RAEDME.md). |
| preview | *bool* | Returns **True** if the script is being called to generate a preview for the rename dialog, **False** if the file is being renamed for real. |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab the rename operation is taking place in. If there is no tab, returns **False** instead. |

