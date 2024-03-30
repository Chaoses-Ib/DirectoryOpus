# Aliases

The **Aliases** object holds a collection of all the defined [folder aliases](/Manual/basic_concepts/the_lister/navigation/aliases.md). It is retrieved from the **[DOpus](dopus.md).aliases** method.  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[Alias](alias.md)**</td><td>

You can enumerate the **Aliases** object, or query the value of an individual alias by name (e.g. *DOpus.Output(DOpus.aliases("desktop").path);*)
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<string:name\>  
\<string:path\></td><td>

*none*</td><td>

Adds a new alias to the system with the specified name and path. Note that you should **not** provide the leading forward-slash (/) in the alias name.
</td></tr><tr><td>
Delete</td><td>

\<string:name\></td><td>

*none*</td><td>
Deletes the specified alias.
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

Updates the state of this object. When the **Aliases** object is first retrieved via **DOpus.aliases**, a snapshot is taken of the aliases at that time. If you make changes via the object it will reflect them but any changes made outside the script (e.g. via the **Favorites ADD=alias** command) will not be detected unless you call the **Update** method.
</td></tr></tbody>
</table>

