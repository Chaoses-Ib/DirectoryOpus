# Wild

The **Wild** object allows a script to access the in-built pattern matching functions in Opus. Even though most ActiveX scripting languages have their own pattern matching support (usually via a regular expression system of some sort), you may wish to use the one that Opus provides for consistency with internal Opus functions.

You can create a **Wild** object using the **[FSUtil](fsutil.md).NewWild** method. To use the **Wild** object, you must first give it the pattern to match against (this step is called "parsing the pattern"). You can do this when it is created or later on using the **Parse** method. Once the object has a pattern you can call the **Match** method to test a string against the pattern.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the current pattern in the Wild object
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
EscapeString</td><td>
\<string:input\>  
\<string:type\></td><td>

*string*</td><td>

Escapes all wildcard characters in the input string and returns the result. For example, "**the \* 'dog' said** \*" would be conterted to "**the '\* ''dog'' said '**\*".

The optional type argument lets you specify the conversion:  
*none*: Escape characters used in [standard pattern matching](../../wildcard_reference/pattern_matching_syntax.md)  
**r**: Escape characters used in [regular expressions](../../wildcard_reference/regular_expression_syntax.md)   
**b**: Double all back-slashes  
**n**: Double all back-slashes that come before the letter '**n**'  
Note that these modes cannot be combined.
</td></tr><tr><td>
Match</td><td>
\<string:test\></td><td>

*bool*</td><td>

Compares the specified string against the previously-parsed pattern, and returns **True** if it matches.
</td></tr><tr><td>
Parse</td><td>
\<string:pattern\>  
\<string:flags\></td><td>

*bool*</td><td>

Parses the supplied pattern. The flags string is optional - if supplied it must be a string consisting of one or more of the following characters:

**c** - case-sensitive (otherwise pattern matching is not case-sensitive)   
**d** - DOS only (only standard MS-DOS wildcards are supported)  
**f** - filename mode (special handling for matching filenames)  
**r** - regular expression (otherwise [standard pattern matching](../../wildcard_reference/pattern_matching_syntax.md) is used)
</td></tr></tbody>
</table>

