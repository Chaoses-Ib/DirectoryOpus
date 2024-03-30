# FiletypeGroups

The **FileTypeGroups** object represents a collection of **[FiletypeGroup](filetypegroup.md)** objects. The object can be enumerated to retrieve the groups it represents.

You can obtain an object representing all the configured [file type groups](/Manual/file_types/file_type_groups.md) from the **[DOpus](dopus.md).filetypegroups** property. The **[Item](item.md).groupsobject** property returns a **FiletypeGroups** object restricted to just the groups the **[Item](item.md)**is a member of.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*collection:***[FiletypeGroup](filetypegroup.md)**</td><td>
Lets you enumerate the file type groups represented by this object.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
GetGroup</td><td>
\<string:group\></td><td>

*object:***[FiletypeGroup](filetypegroup.md)**  
or  
*bool (***False***)*</td><td>

Searches the file type group collection for the named group.  
If Opus is not running in English, the translated name is compared first; if not found, it will search for the native English name for the built-in groups.  
Returns a **[FiletypeGroup](filetypegroup.md)** object or **False** if not found.
</td></tr><tr><td>
MatchExt</td><td>
\<string:filename\></td><td>

*object:***FiletypeGroups**</td><td>

Returns a new **FiletypeGroups **object containing the subset of groups that the specified filename (or file extension) is a member of. You would normally only call this method on the object returned by the **[DOpus](dopus.md).filetypegroups** property.
</td></tr><tr><td>
Translate</td><td>
\<string:group\></td><td>

*string*</td><td>
Returns the translated name of the named built-in file type group.  
If not found, or no translation exists, the input string is returned.

For example, when running in French, calling this method with "Movies" as the input string would return "Vidéos".
</td></tr></tbody>
</table>

