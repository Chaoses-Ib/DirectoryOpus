# OnGetCustomFields

The **OnGetCustomFields** event can be implemented by a [rename script](/Manual/scripting/rename_scripts/README.md) to add [custom fields](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) to the *Rename* dialog. This lets you provide one or more controls that users can use to pass parameters to your script.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnGetCustomFields
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[GetCustomFieldData](../scripting_objects/getcustomfielddata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The *Rename* dialog will call this method when your script is loaded from a preset (or when you click the **Refresh** button in the integrated script editor).

The **GetCustomFieldData.fields** property lets you add one or more custom fields to the Rename dialog. For each field you can:

- Provide a label
- Specify a cue banner for edit fields
- Add up/down spinners to numeric edit controls
- Specify a length limit for edit fields

See [Custom Fields in the Rename Dialog](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) for more information.
</td></tr></tbody>
</table>

