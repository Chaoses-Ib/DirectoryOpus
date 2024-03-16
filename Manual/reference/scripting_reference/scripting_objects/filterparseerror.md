# FilterParseError

If a **[Filter](filter.md)** object fails to parse the [textual filter](/Manual/file_operations/filtered_operations/textual_filters.md) string you provide, you can retrieve this object from the **Filter.lasterror** property to find out what went wrong.

| Property Name | Return Type | Description |
| --- | --- | --- |
| length | *int* | Returns the length of the token that caused the parsing error. |
| message | *string* | Returns the error description. |
| position | *int* | Returns the position of the parsing error in the input string. |
| token | *string* | Returns the token that caused the parsing error. |

