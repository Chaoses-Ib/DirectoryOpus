# Alias

An **Alias** object represents a defined [folder alias](/Manual/basic_concepts/the_lister/navigation/aliases.md). It is retrieved by enumerating or indexing the **[Aliases](aliases.md)** object.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the name of the alias. |
| path | *object:***[Path](path.md)** | Returns the target of the alias as a **[Path](path.md)** object. |
| system | *bool* | **True** if the object is a system-defined alias, **False** if it is user defined. |

