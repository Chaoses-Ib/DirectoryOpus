# OnGetCustomFields

The **OnGetCustomFields** event can be implemented by a [rename script](/Manual/scripting/rename_scripts/RAEDME.md) to add [custom fields](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) to the *Rename* dialog. This lets you provide one or more controls that users can use to pass parameters to your script.

| **Method Name:** | OnGetCustomFields |
| --- | --- |
| **Argument Type:** | **[GetCustomFieldData](../scripting_objects/getcustomfielddata.md)** |
| **Return Type:** | *none* |
| **Description:** | The *Rename* dialog will call this method when your script is loaded from a preset (or when you click the **Refresh** button in the integrated script editor).<br /><br />The **GetCustomFieldData.fields** property lets you add one or more custom fields to the Rename dialog. For each field you can:<br /><br />- Provide a label<br />- Specify a cue banner for edit fields<br />- Add up/down spinners to numeric edit controls<br />- Specify a length limit for edit fields<br /><br />See [Custom Fields in the Rename Dialog](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) for more information. |

