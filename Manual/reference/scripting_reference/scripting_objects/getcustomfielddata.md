# GetCustomFieldData

If a [rename script](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.md) implements the **[OnGetCustomFields](../scripting_events/ongetcustomfields.md)**event, the method receives a **GetCustomFieldData** object whenever the Rename dialog runs the script.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
fields</td><td>

*object:***[CustomFieldData](customfielddata.md)**</td><td>

Returns a **[CustomFieldData](customfielddata.md)** object, that the script can use to add custom fields to the *Rename* dialog. Each property added to the object in this method will be create a new field in the dialog, allowing the user to supply additional information to your rename script.
</td></tr><tr><td>
field_labels</td><td>

*object:***[Map](map.md)**</td><td>

This lets you assign labels to your script's custom fields, that are shown to the user in the *Rename* dialog. To do this, set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/label string pairs.
</td></tr><tr><td>
field_tips</td><td>

*object:***[Map](map.md)**</td><td>

This lets you assign "cue banners" to any edit fields created by your script. A cue banner is displayed inside an empty edit field to prompt the user what sort of data the field expects. To use this, set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/banner string pairs.
</td></tr><tr><td>
focus</td><td>

*string*</td><td>

You can use this field to specify which control gets the input focus by default when your fields appear for the first time. Set it to the name of the desired control. You can also specify **!oldname** or **!newname** to assign focus to the standard old and new name fields.
</td></tr></tbody>
</table>

