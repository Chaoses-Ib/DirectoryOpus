# ScriptStrings

The **ScriptStrings** object is returned by the **[DOpus](dopus.md).strings** property. It lets you access any strings defined via [string resources](/Manual/scripting/resources/string_resources.md).  

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
langs</td><td>

*object:***[Vector](vector.md)**</td><td>

Returns a **[Vector](vector.md)** of strings representing the languages that strings have been defined for.
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Get</td><td>

\<string:name\>  
\<string:language\></td><td>

*string*</td><td>

Returns the text of a string specified by name. The name must match the name used in the string resources.  
Optionally you can provide a language name as the second parameter, to retrieve a string from a particular language. Otherwise, the string is returned in the current language.
</td></tr><tr><td>
HasLanguage</td><td>

\<string:language\></td><td>

*bool*</td><td>

Returns **True** if strings in the specified language are defined in the resources.
</td></tr></tbody>
</table>

