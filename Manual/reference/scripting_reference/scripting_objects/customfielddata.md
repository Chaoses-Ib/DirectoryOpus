# CustomFieldData

The **CustomFieldData** object is provided to a [rename script](/Manual/scripting/rename_scripts/README.md) via the **[GetNewNameData](getnewnamedata.md).custom** property. It provides access to the value of any [custom fields](/Manual/scripting/rename_scripts/custom_fields_in_the_rename_dialog.md) that your script added to the *Rename* dialog.  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

\<custom field property\></td><td>

*variant*</td><td>

The properties of the **CustomFieldData** object are entirely determined by the script itself.

In the **[OnGetCustomFields](../scripting_events/ongetcustomfields.md)** method, assign the default values of any custom fields you want to the **[GetCustomFieldData](getcustomfielddata.md).fields** property. The type of each default value controls the type of the property.

The *Rename* dialog only supports certain types of variables for custom fields, so you must only assign properties of compatible types. Supported types are:

- Boolean options (**True** or **False**) - the variable type must be *bool*
- Numeric options - the variable type must be *int*
- String options - the variable type must be *string*
- Drop-down list - the variable type must be a **[Vector](vector.md)** with an *int* as the first element (to specify the default selection), and strings for the remaining elements.
</td></tr></tbody>
</table>

