# ShellProperty

The **ShellProperty** object represents a shell property - an item of metadata for a file or folder that comes from Windows or third-party extensions (as opposed to metadata from Opus's native metadata system).

The **[FSUtil](fsutil.md).GetShellPropertyList** method lets you retrieve a list of available shell properties. You can then use **[FSUtil](fsutil.md).GetShellProperty** or **[Item](item.md).ShellProp** to retrieve the value of a property for a particular file.

| Property Name | Return Type | Description |
| --- | --- | --- |
| **defwidth** | *int* | The default width in pixels a column displaying this property should use. |
| **display_name** | *string* | The display name of this property (the name that should be shown to users). |
| **justify** | *string* | The default column justification for this property (**left**, **right**, **center**). |
| **pkey** | *string* | The PKEY (property key) for this property. This is a property's unique ID and the canonical way to refer to a property. You can use the **raw_name** and **display_name** values to access properties as well, but they are potentially inaccurate (since it's possible to have two properties with the same name) and also slower as the property has to be looked up by name each time. |
| **raw_name** | *string* | An internal name used by the property provider. |
| **type** | *string* | The type of data this property returns; **string**, **number**, **datetime** are the only supported types currently. |

