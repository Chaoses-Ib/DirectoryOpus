# FiletypeGroup

The **FiletypeGroup** object represents a file type group (as configured in the [File Type Groups](/Manual/file_types/file_type_groups.md) section of the [file type editor](/Manual/file_types/RAEDME.md)). You can find out which groups a file belongs to by querying the **[Item](item.md)**.groups property, or by using the **[FiletypeGroups](filetypegroups.md)** object.  
  
Note: If you're looking for information on how the file display is grouping an item based on one of the displayed columns, rather than which *file type group* a file is part of, see the [FileGroup](filegroup.md) object instead.  
  
This object can be enumerated to retrieve the file extensions it represents.  

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the internal name of this group.  <br />The internal name is always the same in all languages.  <br />Groups that come pre-defined when you install Opus have internal names like *"Archives"* and *"Music"* (which are also their English display names).  <br />User-defined groups have internal names which are unique, automatically generated GUID strings like *"{C4B716ED-2A9C-43C6-B325-7DADDEEFADA9}"*. |
| display_name | *string* | Returns the display name of this group.  <br />The display name is what you see in the File Types editor. Display names may be translated differently in different languages. |
| tiles | *string* | Returns the tiles mode definition string for this group. |
| tooltip | *string* | Returns the tooltip definition string for this group. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| MatchExt | \<string:filename\> | *bool* | Tests the filename (or extension) for membership of this group. Returns **True** if the file is a member of the group, or **False** if it is not. |

