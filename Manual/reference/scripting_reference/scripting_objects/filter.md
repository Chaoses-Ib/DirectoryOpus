# Filter

The **Filter** object lets you create a [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md) of the type used by the **Find** tool and commands such as **Copy** to control recursive operations.

Use the **[dopusfactory](dopusfactory.md).Filter** method to create a new filter object. Once you have a **Filter** object you can:

- Use the **[item](item.md).MatchFilter** method to see if a file or folder matches the filter.
- Apply the filter to a command with the **[command](command.md).SetFilter** method.

| Property Name | Return Type | Description |
| --- | --- | --- |
| lasterror | *object:***[filterparseerror](filterparseerror.md)** | If *valid* returns **False** you can use this property to discover information about the error. |
| valid | *bool* | Returns **True** if the filter was created successfully (i.e. no errors were encountered in parsing the filter text). |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Add | \<string:clause\>  <br />or \<object:**Filter**\>  <br />\[\<string:conjunction\>\] | *bool* | Adds a clause to the filter. If provided as a string, the clause will be parsed and the method returns **True** if parsing was successful. If parsing fails, use the **lasterror** property to find out why. Alternatively, you can add another **Filter** object.<br /><br />The *clause* string must be a fully formed [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md) clause. For example, `size match > 2 mb`<br /><br />The optional *conjunction* string lets you choose whether the clause is joined via **and** or **or**. If not specified, the default is **and**. |
| Clear | *none* | *none* | Clears the contents of the filter. |
| Set | \<string:clause\>  <br />or \<object:**Filter**\> | *bool* | Initialises the filter with either a string or the contents of an existing **Filter** object. If provided as a string, the clause will be parsed and the method returns **True** if parsing was successful. If parsing fails, use the **lasterror** property to find out why. |

