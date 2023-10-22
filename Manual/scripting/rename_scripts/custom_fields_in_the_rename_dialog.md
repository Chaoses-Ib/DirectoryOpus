# Custom Fields in the Rename Dialog

Rename scripts can add their own fields to the rename dialog itself, by implementing the **[OnGetCustomFields](/Manual/reference/scripting_reference/scripting_events/ongetcustomfields.md)** event. This lets you provide one or more controls that users can use to pass parameters to your script. Users can also feed parameters to your script using the **SCRIPTARG** argument for the **Rename** command.

![](/Manual/images/media/image012_001.png)

Custom fields can use check boxes, string fields, number fields and drop-downs.

To add custom fields from your rename script, implement the **[OnGetCustomFields](/Manual/reference/scripting_reference/scripting_events/ongetcustomfields.md)** method. The above fields were added using the following code (in VBScript):

    Function OnGetCustomFields(ByRef getFieldData)

    ' Add a checkbox called "My Option", defaults to true (on)
    getFieldData.fields.my_option = True
    getFieldData.fields.my_option.label = "My Option"

    ' Add a text field called "My String Field" with a cue banner
    getFieldData.fields.my_field = ""
    getFieldData.fields.my_field.label = "My String Field"
    getFieldData.fields.my_field.tip = "Enter your text here"

    ' Add a numeric input field, default value 20. Maximum value 100
    getFieldData.fields.my_value = 20
    getFieldData.fields.my_value.label = "My Integer Value"
    getFieldData.fields.my_value.max = 100

    ' Add a dropdown with three options
    getFieldData.fields.my_combo = DOpus.Create.Vector(1, "Option 1", "Option 2", "Option 3") 
    getFieldData.fields.my_combo.label = "My Dropdown"

    End Function

  
Custom fields are defined in much the same way as [Script add-in](../script_add-ins/RAEDME.md) defines its configuration using the **[ScriptConfig](/Manual/reference/scripting_reference/scripting_objects/scriptconfig.md)** object. The **[OnGetCustomFields](/Manual/reference/scripting_reference/scripting_events/ongetcustomfields.md)** method is passed a **GetCustomFieldData** object. Fields are added by assigning properties of the **GetCustomFieldData.fields** object to the variable type you want the field to use (e.g. assign **True** or **False** for a Boolean, a string for a text string, etc.). The value you provide will become the default value for the field.

Each field can also have a label, and text fields can have a “cue banner” which is shown when the text field is empty (as seen above). There are two ways to configure these:

- Using sub-properties of the fields object. This is the easier way and also lets you access additional options besides label and cue banner.
- The older method is to use the two additional **[Map](/Manual/reference/scripting_reference/scripting_objects/map.md)** objects which are provided (**GetCustomFieldData.field_labels** and **GetCustomFieldData.field_tips**) to allow you assign these.

Using the sub-properties method above, the properties you can assign are:

|       |                                                                       |
|-------|-----------------------------------------------------------------------|
| label | Control label                                                         |
| tip   | Edit field cue banner                                                 |
| min   | Minimum value (for numeric controls, lets you add an up/down spinner) |
| max   | Maximum value                                                         |
| limit | Maximum input length for edit controls                                |

The *Rename* dialog will expand automatically to accommodate your custom fields – obviously, screen space isn’t infinite, so you shouldn’t add too many fields or the dialog will grow too big for the screen!

The values that the user enters into your custom fields are provided to your **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.md)** method via the **[CustomFieldData](/Manual/reference/scripting_reference/scripting_objects/customfielddata.md)** object passed as the **GetNewNameData.custom**. Each field you add in **OnGetCustomFields** will appear as a property of this object. For example, this function will print the provided values to the output log.

    Function OnGetNewName(ByRef getNewNameData)
    DOpus.Output "Option: " & getNewNameData.custom.my_option
    DOpus.Output "String: " & getNewNameData.custom.my_field
    DOpus.Output "Number: " & getNewNameData.custom.my_value
    DOpus.Output "Dropdown: " & getNewNameData.custom.my_combo
    OnGetNewName = True ' skip rename
    End Function

When the user automates the **[Rename](/Manual/reference/command_reference/internal_commands/rename.md)** command to run your rename script directly (using the **PRESET** argument), they can use the **SCRIPTARG** parameter to pass data for your custom fields through. This argument accepts multiple ***name:value*** pairs. For example, assume the above script was saved as the rename preset “MyRename”. The user might run the following command:

    Rename PRESET MyRename SCRIPTARG my_option:True my_field:moocow
