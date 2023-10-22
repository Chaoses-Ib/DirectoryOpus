# GetCustomFieldData

If a [rename script](/Manual/file_operations/renaming_files/advanced_rename/rename_scripts.md) implements the **[OnGetCustomFields](../scripting_events/ongetcustomfields.md)**event, the method receives a **GetCustomFieldData** object whenever the Rename dialog runs the script.

| Property Name | Return Type | Description |
| --- | --- | --- |
| fields | *object:***[CustomFieldData](customfielddata.md)** | Returns a **[CustomFieldData](customfielddata.md)** object, that the script can use to add custom fields to the *Rename* dialog. Each property added to the object in this method will be create a new field in the dialog, allowing the user to supply additional information to your rename script. |
| field_labels | *object:***[Map](map.md)** | This lets you assign labels to your script's custom fields, that are shown to the user in the *Rename* dialog. To do this, set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/label string pairs. |
| field_tips | *object:***[Map](map.md)** | This lets you assign "cue banners" to any edit fields created by your script. A cue banner is displayed inside an empty edit field to prompt the user what sort of data the field expects. To use this, set this property to a **[Map](map.md)** created via the **[DOpusFactory](dopusfactory.md).Map** method, filled with name/banner string pairs. |
| focus | *string* | You can use this field to specify which control gets the input focus by default when your fields appear for the first time. Set it to the name of the desired control. You can also specify **!oldname** or **!newname** to assign focus to the standard old and new name fields. |

