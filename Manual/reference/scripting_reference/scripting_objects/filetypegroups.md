# FiletypeGroups

The **FileTypeGroups** object represents a collection of **[FiletypeGroup](filetypegroup.md)** objects. The object can be enumerated to retrieve the groups it represents.

You can obtain an object representing all the configured [file type groups](/Manual/file_types/file_type_groups.md) from the **[DOpus](dopus.md).filetypegroups** property. The **[Item](item.md).groupsobject** property returns a **FiletypeGroups** object restricted to just the groups the **[Item](item.md)**is a member of.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *collection:***[FiletypeGroup](filetypegroup.md)** | Lets you enumerate the file type groups represented by this object. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| GetGroup | \<string:group\> | *object:***[FiletypeGroup](filetypegroup.md)**  <br />or  <br />*bool (***False***)* | Searches the file type group collection for the named group.  <br />If Opus is not running in English, the translated name is compared first; if not found, it will search for the native English name for the built-in groups.  <br />Returns a **[FiletypeGroup](filetypegroup.md)** object or **False** if not found. |
| MatchExt | \<string:filename\> | *object:***FiletypeGroups** | Returns a new **FiletypeGroups **object containing the subset of groups that the specified filename (or file extension) is a member of. You would normally only call this method on the object returned by the **[DOpus](dopus.md).filetypegroups** property. |
| Translate | \<string:group\> | *string* | Returns the translated name of the named built-in file type group.  <br />If not found, or no translation exists, the input string is returned.<br /><br />For example, when running in French, calling this method with "Movies" as the input string would return "Vidéos". |

