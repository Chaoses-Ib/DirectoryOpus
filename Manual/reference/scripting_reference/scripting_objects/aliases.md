# Aliases

The **Aliases** object holds a collection of all the defined [folder aliases](/Manual/preferences/preferences_categories/favorites_and_recent/folder_aliases.md). It is retrieved from the **[DOpus](dopus.md).aliases** method.  

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *collection:***[Alias](alias.md)** | You can enumerate the **Aliases** object, or query the value of an individual alias by name (e.g. *DOpus.Output(DOpus.aliases("desktop").path);*) |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Add | \<string:name\>  <br />\<string:path\> | *none* | Adds a new alias to the system with the specified name and path. Note that you should **not** provide the leading forward-slash (/) in the alias name. |
| Delete | \<string:name\> | *none* | Deletes the specified alias. |
| Update | *none* | *none* | Updates the state of this object. When the **Aliases** object is first retrieved via **DOpus.aliases**, a snapshot is taken of the aliases at that time. If you make changes via the object it will reflect them but any changes made outside the script (e.g. via the **Favorites ADD=alias** command) will not be detected unless you call the **Update** method. |

