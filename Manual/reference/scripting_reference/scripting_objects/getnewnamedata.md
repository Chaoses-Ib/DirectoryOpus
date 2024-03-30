# GetNewNameData

If a [rename script](/Manual/scripting/rename_scripts/README.md) is implemented using the **[OnGetNewName](../scripting_events/ongetnewname.md)** method, it receives a **GetNewNameData** object for each item being renamed.  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
custom</td><td>

object:**[CustomFieldData](customfielddata.md)**</td><td>

Returns a **[CustomFieldData](customfielddata.md)** object which provides the values of any [custom fields](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) your script added to the *Rename* dialog.
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.md)**</td><td>

Returns an **[Item](item.md)** object representing the file or folder being renamed.
</td></tr><tr><td>
newname</td><td>

*string*</td><td>

Returns the proposed new name of the item. This will be the result of the application of any selected standard options in the [rename dialog](/Manual/file_operations/renaming_files/advanced_rename/README.md) (numbering, capitalization, etc).
</td></tr><tr><td>
newname_ext</td><td>

*string*</td><td>
Returns the file extension of the proposed new name. Does not take multi-part extensions into account (e.g. will return ".rar" rather than ".part1.rar").
</td></tr><tr><td>
newname_ext_m</td><td>

*string*</td><td>
Returns the file extension of the proposed new name, taking multi-part extensions into account (e.g. will return ".part1.rar" rather than ".rar").
</td></tr><tr><td>
newname_field</td><td>

*string*</td><td>

Returns the contents of the *New Name* field (that is, not the calculated new name after all the options have been applied, but the actual text contents of the field as entered by the user).
</td></tr><tr><td>
newname_stem</td><td>

*string*</td><td>
Returns the file stem of the proposed new name. Does not take multi-part extensions into account (e.g. will return "catpictures.part1" rather than "catpictures").
</td></tr><tr><td>
newname_stem_m</td><td>

*string*</td><td>
Returns the file stem of the proposed new name, taking multi-part extensions into account (e.g. will return "catpictures" rather than "catpictures.part1").
</td></tr><tr><td>
oldname_field</td><td>

*string*</td><td>

Returns the "old name" pattern as entered by the user in the [rename dialog](/Manual/file_operations/renaming_files/advanced_rename/README.md).
</td></tr><tr><td>
preview</td><td>

*bool*</td><td>

Returns **True** if the script is being called to generate a preview for the rename dialog, **False** if the file is being renamed for real.
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the tab the rename operation is taking place in. If there is no tab, returns **False** instead.
</td></tr></tbody>
</table>

