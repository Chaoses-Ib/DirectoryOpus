#### Vars

The **Vars** object represents a collection of user and script-defined variables. There are a number of different sets of variables, with differing scopes. Some sets support persistent variables, that are saved and re-loaded from one session to the other.

<table>
<thead><tr><th>
Scope</th><th>
Accessed by</th><th>

**Supports Persistence**</th><th>
Description
</th></tr></thead><tbody><tr><td>
Global</td><td>

**[DOpus](dopus.md).vars**</td><td>
Yes</td><td>
Variables that are available throughout Opus. They can be accessed by any function or script.
</td></tr><tr><td>
Lister</td><td>

**[Lister](lister.md).vars**</td><td>
Yes</td><td>
Variables that are local to a Lister. Persistent variables are saved on a per-Lister basis in Lister Layouts.
</td></tr><tr><td>
Tab</td><td>

**[Tab](tab.md).vars**</td><td>
Yes</td><td>
Variables that are local to a particular tab. Persistent variables are saved per-Tab in Lister Layouts.
</td></tr><tr><td>
Script</td><td>

**[Script](script.md).vars  
[ScriptInitData](scriptinitdata.md).vars**</td><td>
Yes</td><td>
Variables that are local to a particular script add-in.
</td></tr><tr><td>
Dialog</td><td>

**[Dialog](dialog.md).Vars**</td><td>
Yes</td><td>

Variables that are tied to a particular [script dialog](/Manual/scripting/script_dialogs/README.md).
</td></tr><tr><td>
Command</td><td>

**[Command](command.md).vars**</td><td>
No</td><td>
Variables that are local to a particular function. They are not saved from one invocation of the function to another and do not support persistence.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[Var](var.md)**</td><td>

Returns a collection of the variables in the collection. You can enumerate the **[Var](var.md)** elements or refer to a specific one by its index or by its name. An example of how to do that is in the **Set** documentation, below.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Delete</td><td>
\<string:name\></td><td>

*none*</td><td>

Deletes the named variable from the collection. You can also specify a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) to delete multiple variables (or \* for all).
</td></tr><tr><td>
Exists</td><td>
\<string:name\></td><td>

*bool*</td><td>

Returns **True** if the named variable exists in the collection, or **False** if it doesn't exist.
</td></tr><tr><td>
Get</td><td>
\<string:name\></td><td>

*variant*</td><td>

Returns the value of the named variable.  
You can use this method as an alternative to indexing the collection. One difference to note is that this method directly returns the *value* stored in the variable. If you need the **[Var](var.md)** object which contains the value (for example, to call **var.Delete** or change **var.persist**) then you should index the collection instead. An example of how to do that is in the **Set** documentation, just below.
</td></tr><tr><td>
Set</td><td>
\<string:name\>  
\<variant:value\></td><td>

*none*</td><td>

Sets the named value to the specified value. You can use this method as an alternative to indexing the collection.

You can store any type of variable in a **Vars** collection, although not all types can be saved to disk. If you want your variable to be persistent you should only use *bool*, *int*, *string*, *date*, *currency* or a **[Vector](vector.md)** of those types.  
Variables are not persistent by default. If you need them to be saved across a restart, you need to request it explicitly. Here is an example in VBScript:  
`Dim varName, varValue1, varValue2
 varName = "MyVariableName"

 if (DOpus.Vars.Exists(varName)) then
 varValue1 = DOpus.Vars.Get(varName)
 DOpus.Output varName & " = " & varValue1
 else
 DOpus.Output varName & " does not exist yet."
 end if

 varValue2 = "My Variable Value"

 DOpus.Vars.Set varName, varValue2
 DOpus.Vars(varName).persist = True`

Here is the same example in JScript:  
`var varName = "MyVariableName";

 if (DOpus.Vars.Exists(varName)) {
 var varValue1 = DOpus.Vars.Get(varName);
 DOpus.Output(varName + " = " + varValue1);
 } else {
 DOpus.Output(varName + " does not exist yet.");
 }

 var varValue2 = "My Variable Value";

 DOpus.Vars.Set(varName, varValue2);
 DOpus.Vars(varName).persist = true;`

On the first run, the example code will say the variable does not against and set it to a value, turning on persistence afterwards. If it is then run again, it will report the variable's value, and the value will persist across a restart.
</td></tr></tbody>
</table>

