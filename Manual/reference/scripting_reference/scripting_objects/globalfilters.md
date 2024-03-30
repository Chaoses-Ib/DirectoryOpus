# GlobalFilters

The **GlobalFilters** object provides information about the global file and folder filter settings (configured on the **[Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.md)** page in Preferences). It is obtained from the **[DOpus](dopus.md)**.filters property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
enable</td><td>

*bool*</td><td>

Returns **True** if the global wildcard filters are enabled.
</td></tr><tr><td>
file</td><td>

*string*</td><td>

Returns the global filename filter wildcard pattern. If the wildcard is configured to use regular expressions, it will have a **regex:** prefix in front of the pattern.
</td></tr><tr><td>
folder</td><td>

*string*</td><td>

Returns the global folder filter wildcard pattern. If the wildcard is configured to use regular expressions, it will have a **regex:** prefix in front of the pattern.
</td></tr><tr><td>
hidehidden</td><td>

*bool*</td><td>

Returns **True** if the global option to hide hidden files is on.
</td></tr><tr><td>
hidesystem</td><td>

*bool*</td><td>

Returns **True** if the global option to hide operating system files is on.
</td></tr></tbody>
</table>

