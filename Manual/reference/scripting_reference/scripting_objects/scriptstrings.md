# ScriptStrings

The **ScriptStrings** object is returned by the **[DOpus](dopus.md).strings** property. It lets you access any strings defined via [string resources](/Manual/scripting/resources/string_resources.md).  

| Property Name | Return Type | Description |
| --- | --- | --- |
| langs | *object:***[Vector](vector.md)** | Returns a **[Vector](vector.md)** of strings representing the languages that strings have been defined for.  <br />\</commandtable\><br /><br />\<commandtable columns="4" id="cmdtable_2"\> |
| Method Name | **Arguments** | Return Type |
| Description | Get | \<string:name\>  <br />\<string:language\> |
| *string* | Returns the text of a string specified by name. The name must match the name used in the string resources.  <br />Optionally you can provide a language name as the second parameter, to retrieve a string from a particular language. Otherwise, the string is returned in the current language. | HasLanguage |
| \<string:language\> | *bool* | Returns **True** if strings in the specified language are defined in the resources. |

