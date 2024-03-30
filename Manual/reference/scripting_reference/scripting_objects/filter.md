# Filter

The **Filter** object lets you create a [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md) of the type used by the **Find** tool and commands such as **Copy** to control recursive operations.

Use the **[dopusfactory](dopusfactory.md).Filter** method to create a new filter object. Once you have a **Filter** object you can:

- Use the **[item](item.md).MatchFilter** method to see if a file or folder matches the filter.
- Apply the filter to a command with the **[command](command.md).SetFilter** method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
lasterror</td><td>

*object:***[filterparseerror](filterparseerror.md)**</td><td>

If *valid* returns **False** you can use this property to discover information about the error.
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

Returns **True** if the filter was created successfully (i.e. no errors were encountered in parsing the filter text).
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<string:clause\>  
or \<object:**Filter**\>  
\[\<string:conjunction\>\]</td><td>

*bool*</td><td>

Adds a clause to the filter. If provided as a string, the clause will be parsed and the method returns **True** if parsing was successful. If parsing fails, use the **lasterror** property to find out why. Alternatively, you can add another **Filter** object.

The *clause* string must be a fully formed [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md) clause. For example, `size match > 2 mb`

The optional *conjunction* string lets you choose whether the clause is joined via **and** or **or**. If not specified, the default is **and**.
</td></tr><tr><td>
Clear</td><td>

*none*</td><td>

*none*</td><td>
Clears the contents of the filter.
</td></tr><tr><td>
Set</td><td>

\<string:clause\>  
or \<object:**Filter**\></td><td>

*bool*</td><td>

Initialises the filter with either a string or the contents of an existing **Filter** object. If provided as a string, the clause will be parsed and the method returns **True** if parsing was successful. If parsing fails, use the **lasterror** property to find out why.
</td></tr></tbody>
</table>

