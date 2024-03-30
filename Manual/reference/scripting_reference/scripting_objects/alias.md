# Alias

An **Alias** object represents a defined [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md). It is retrieved by enumerating or indexing the **[Aliases](aliases.md)** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the name of the alias.
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.md)**</td><td>

Returns the target of the alias as a **[Path](path.md)** object.
</td></tr><tr><td>
system</td><td>

*bool*</td><td>

**True** if the object is a system-defined alias, **False** if it is user defined.
</td></tr></tbody>
</table>

