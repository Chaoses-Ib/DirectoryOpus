#### Vars

The **Vars** object represents a collection of user and script-defined variables. There are a number of different sets of variables, with differing scopes. Some sets support persistent variables, that are saved and re-loaded from one session to the other.

| Scope | Accessed by | **Supports Persistence** | Description |
| --- | --- | --- | --- |
| Global | **[DOpus](dopus.md).vars** | Yes | Variables that are available throughout Opus. They can be accessed by any function or script. |
| Lister | **[Lister](lister.md).vars** | Yes | Variables that are local to a Lister. Persistent variables are saved on a per-Lister basis in Lister Layouts. |
| Tab | **[Tab](tab.md).vars** | Yes | Variables that are local to a particular tab. Persistent variables are saved per-Tab in Lister Layouts. |
| Script | **[Script](script.md).vars  <br />[ScriptInitData](scriptinitdata.md).vars** | Yes | Variables that are local to a particular script add-in. |
| Dialog | **[Dialog](dialog.md).Vars** | Yes | Variables that are tied to a particular [script dialog](/Manual/scripting/script_dialogs/RAEDME.md). |
| Command | **[Command](command.md).vars** | No | Variables that are local to a particular function. They are not saved from one invocation of the function to another and do not support persistence. |

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *collection:***[Var](var.md)** | Returns a collection of the variables in the collection. You can enumerate the **[Var](var.md)** elements or refer to a specific one by its index or by its name. An example of how to do that is in the **Set** documentation, below. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Delete | \<string:name\> | *none* | Deletes the named variable from the collection. You can also specify a [wildcard pattern](../../wildcard_reference/pattern_matching_syntax.md) to delete multiple variables (or \* for all). |
| Exists | \<string:name\> | *bool* | Returns **True** if the named variable exists in the collection, or **False** if it doesn't exist. |
| Get | \<string:name\> | *variant* | Returns the value of the named variable.  <br />You can use this method as an alternative to indexing the collection. One difference to note is that this method directly returns the *value* stored in the variable. If you need the **[Var](var.md)** object which contains the value (for example, to call **var.Delete** or change **var.persist**) then you should index the collection instead. An example of how to do that is in the **Set** documentation, just below. |
| Set | \<string:name\>  <br />\<variant:value\> | *none* | Sets the named value to the specified value. You can use this method as an alternative to indexing the collection.<br /><br />You can store any type of variable in a **Vars** collection, although not all types can be saved to disk. If you want your variable to be persistent you should only use *bool*, *int*, *string*, *date*, *currency* or a **[Vector](vector.md)** of those types.  <br />Variables are not persistent by default. If you need them to be saved across a restart, you need to request it explicitly. Here is an example in VBScript:  <br />`Dim varName, varValue1, varValue2<br /> varName = "MyVariableName"<br /><br /> if (DOpus.Vars.Exists(varName)) then<br /> varValue1 = DOpus.Vars.Get(varName)<br /> DOpus.Output varName & " = " & varValue1<br /> else<br /> DOpus.Output varName & " does not exist yet."<br /> end if<br /><br /> varValue2 = "My Variable Value"<br /><br /> DOpus.Vars.Set varName, varValue2<br /> DOpus.Vars(varName).persist = True`<br /><br />Here is the same example in JScript:  <br />`var varName = "MyVariableName";<br /><br /> if (DOpus.Vars.Exists(varName)) {<br /> var varValue1 = DOpus.Vars.Get(varName);<br /> DOpus.Output(varName + " = " + varValue1);<br /> } else {<br /> DOpus.Output(varName + " does not exist yet.");<br /> }<br /><br /> var varValue2 = "My Variable Value";<br /><br /> DOpus.Vars.Set(varName, varValue2);<br /> DOpus.Vars(varName).persist = true;`<br /><br />On the first run, the example code will say the variable does not against and set it to a value, turning on persistence afterwards. If it is then run again, it will report the variable's value, and the value will persist across a restart. |

