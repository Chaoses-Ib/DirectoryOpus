# Wild

The **Wild** object allows a script to access the in-built pattern matching functions in Opus. Even though most ActiveX scripting languages have their own pattern matching support (usually via a regular expression system of some sort), you may wish to use the one that Opus provides for consistency with internal Opus functions.

You can create a **Wild** object using the **[FSUtil](fsutil.md).NewWild** method. To use the **Wild** object, you must first give it the pattern to match against (this step is called "parsing the pattern"). You can do this when it is created or later on using the **Parse** method. Once the object has a pattern you can call the **Match** method to test a string against the pattern.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the current pattern in the Wild object |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| EscapeString | \<string:input\>  <br />\<string:type\> | *string* | Escapes all wildcard characters in the input string and returns the result. For example, "**the \* 'dog' said** \*" would be conterted to "**the '\* ''dog'' said '**\*".<br /><br />The optional type argument lets you specify the conversion:  <br />*none*: Escape characters used in [standard pattern matching](../../wildcard_reference/pattern_matching_syntax.md)  <br />**r**: Escape characters used in [regular expressions](../../wildcard_reference/regular_expression_syntax.md)   <br />**b**: Double all back-slashes  <br />**n**: Double all back-slashes that come before the letter '**n**'  <br />Note that these modes cannot be combined. |
| Match | \<string:test\> | *bool* | Compares the specified string against the previously-parsed pattern, and returns **True** if it matches. |
| Parse | \<string:pattern\>  <br />\<string:flags\> | *bool* | Parses the supplied pattern. The flags string is optional - if supplied it must be a string consisting of one or more of the following characters:<br /><br />**c** - case-sensitive (otherwise pattern matching is not case-sensitive)   <br />**d** - DOS only (only standard MS-DOS wildcards are supported)  <br />**f** - filename mode (special handling for matching filenames)  <br />**r** - regular expression (otherwise [standard pattern matching](../../wildcard_reference/pattern_matching_syntax.md) is used) |

