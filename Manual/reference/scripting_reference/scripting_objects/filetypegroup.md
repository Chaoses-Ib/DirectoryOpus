# FiletypeGroup

The **FiletypeGroup** object represents a file type group (as configured in the [File Type Groups](/Manual/file_types/file_type_groups.md) section of the [file type editor](/Manual/file_types/README.md)). You can find out which groups a file belongs to by querying the **[Item](item.md)**.groups property, or by using the **[FiletypeGroups](filetypegroups.md)** object.  
  
Note: If you're looking for information on how the file display is grouping an item based on one of the displayed columns, rather than which *file type group* a file is part of, see the [FileGroup](filegroup.md) object instead.  
  
This object can be enumerated to retrieve the file extensions it represents.  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

Returns the internal name of this group.  
The internal name is always the same in all languages.  
Groups that come pre-defined when you install Opus have internal names like *"Archives"* and *"Music"* (which are also their English display names).  
User-defined groups have internal names which are unique, automatically generated GUID strings like *"{C4B716ED-2A9C-43C6-B325-7DADDEEFADA9}"*.
</td></tr><tr><td>
display_name</td><td>

*string*</td><td>

Returns the display name of this group.  
The display name is what you see in the File Types editor. Display names may be translated differently in different languages.
</td></tr><tr><td>
tiles</td><td>

*string*</td><td>
Returns the tiles mode definition string for this group.
</td></tr><tr><td>
tooltip</td><td>

*string*</td><td>
Returns the tooltip definition string for this group.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
MatchExt</td><td>

\<string:filename\></td><td>

*bool*</td><td>

Tests the filename (or extension) for membership of this group. Returns **True** if the file is a member of the group, or **False** if it is not.
</td></tr></tbody>
</table>

