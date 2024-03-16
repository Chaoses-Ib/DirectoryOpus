# GlobalFilters

The **GlobalFilters** object provides information about the global file and folder filter settings (configured on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences). It is obtained from the **[DOpus](dopus.md)**.filters property.

| Property Name | Return Type | Description |
| --- | --- | --- |
| enable | *bool* | Returns **True** if the global wildcard filters are enabled. |
| file | *string* | Returns the global filename filter wildcard pattern. If the wildcard is configured to use regular expressions, it will have a **regex:** prefix in front of the pattern. |
| folder | *string* | Returns the global folder filter wildcard pattern. If the wildcard is configured to use regular expressions, it will have a **regex:** prefix in front of the pattern. |
| hidehidden | *bool* | Returns **True** if the global option to hide hidden files is on. |
| hidesystem | *bool* | Returns **True** if the global option to hide operating system files is on. |

