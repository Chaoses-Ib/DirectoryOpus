## Var

The **Var** object represents an individual user or script-defined variable. Individual **Var** objects can be accessed or enumerated from the **[Vars](vars.md)** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*variant*  
or *string*</td><td>

The default value of the **Var** object returns the value of the variable itself, with one exception. If the **Var** object is being accessed as part of an enumeration of the **[Vars](vars.md)** collection, the default value returns the variable name.

So for instance,

For Each Var in DOpus.Vars  
DOpus.Output("Variable name = " & Var)  
Next

Versus:

Set Var = DOpus.Vars("myvar")  
DOpus.Output("Variable value = " & Var)
</td></tr><tr><td>
name</td><td>

*string*</td><td>

Returns the name of the variable. You cannot change the name of a variable once it has been assigned - instead, delete the variable from its collection and add a new one.
</td></tr><tr><td>
persist</td><td>

*bool*</td><td>

Returns **True** if the variable is persistent (saved) or **False** if not. You can set this property to change the persistence state.
</td></tr><tr><td>
value</td><td>

*variant*</td><td>

Returns the value of the variable. You can set this property to change the value of the variable.

You can store any type of variable in a **Var** object, although not all types can be saved to disk. If you want your variable to be persistent you should only use *bool*, *int*, *string*, *date*, *currency* or a **[Vector](vector.md)** of those types.
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

*none*</td><td>

*none*</td><td>
Deletes this variable from its parent collection.
</td></tr></tbody>
</table>

