#### Var

The **Var** object represents an individual user or script-defined variable. Individual **Var** objects can be accessed or enumerated from the **[Vars](vars.md)** object.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *variant*  <br />or *string* | The default value of the **Var** object returns the value of the variable itself, with one exception. If the **Var** object is being accessed as part of an enumeration of the **[Vars](vars.md)** collection, the default value returns the variable name.<br /><br />So for instance,<br /><br />For Each Var in DOpus.Vars  <br />DOpus.Output("Variable name = " & Var)  <br />Next<br /><br />Versus:<br /><br />Set Var = DOpus.Vars("myvar")  <br />DOpus.Output("Variable value = " & Var) |
| name | *string* | Returns the name of the variable. You cannot change the name of a variable once it has been assigned - instead, delete the variable from its collection and add a new one. |
| persist | *bool* | Returns **True** if the variable is persistent (saved) or **False** if not. You can set this property to change the persistence state. |
| value | *variant* | Returns the value of the variable. You can set this property to change the value of the variable.<br /><br />You can store any type of variable in a **Var** object, although not all types can be saved to disk. If you want your variable to be persistent you should only use *bool*, *int*, *string*, *date*, *currency* or a **[Vector](vector.md)** of those types. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Delete | *none* | *none* | Deletes this variable from its parent collection. |

