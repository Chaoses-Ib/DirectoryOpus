# ScriptConfig

The **ScriptConfig** object is accessed via the **[ScriptInitData](scriptinitdata.md).config** and the **[Script](script.md).config** properties. The **[ScriptInitData](scriptinitdata.md).config** property allows a script (in its **[OnInit](../scripting_events/oninit.md)** method) to specify what configuration properties it supports, and provide default values for them. The properties assigned in **[OnInit](../scripting_events/oninit.md)** will then be available in Preferences for the user to edit, and the user-edited configuration can then be accessed by other script methods using **[Script](script.md).config**.  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

\<configuration property\></td><td>

*variant*</td><td>

The properties of the **ScriptConfig** object are entirely determined by the script itself.

In the **OnInit** method, assign the default values of any configuration properties you want to this object. The type of each default value controls the type of the property.

The Preferences page only supports editing certain types of variables, so you must only assign properties of compatible types. Preferences supports:

- Boolean options (**True** or **False**) - the variable type must be *bool*
- Numeric options - the variable type must be *int*
- String options - the variable type must be *string*
- Multi-line string options - the variable type must be string and must contain at least one *CR/LF* pair. Note that a trailing *CR/LF* will be removed from the default value.
- Multiple string options - the variable type must be a **[Vector](vector.md)** of *strings*
- Drop-down list - the variable type must be a **[Vector](vector.md)** with an *int* as the first element (to specify the default selection), and strings for the remaining elements.
</td></tr></tbody>
</table>

