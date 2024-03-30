# QuickFilter

The **QuickFilter** object provides access to information about the quick filter state in a tab. It’s returned by the **[Tab](tab.md).quickfilter property.**

  

<table>
<thead><tr><th>

**Property Name**</th><th>

**Return Type**</th><th>

**Description**
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>
Returns the current filter string, if any.
</td></tr><tr><td>
autoclear</td><td>

*bool*</td><td>

Returns **True** if the auto-clear mode is set in Preferences.
</td></tr><tr><td>
autostar</td><td>

*bool*</td><td>

Returns **True** if the auto-star mode is set in Preferences.
</td></tr><tr><td>
disable</td><td>

*bool*</td><td>

Returns **True** if the filter is disabled.
</td></tr><tr><td>
easymode</td><td>

*bool*</td><td>

Returns **True** if easy mode is selected.
</td></tr><tr><td>
filter</td><td>

*string*</td><td>
Returns the current filter string.
</td></tr><tr><td>
flatview</td><td>

*bool*</td><td>

Returns **True** if folder filtering in flatview is on.
</td></tr><tr><td>
hidealldirs</td><td>

*bool*</td><td>

Returns **True** if all folders are being hidden.
</td></tr><tr><td>
hideallfiles</td><td>

*bool*</td><td>

Returns **True** if all files are being hidden.
</td></tr><tr><td>
overrideflatview</td><td>

*bool*</td><td>

(Legacy flag.) Returns **True** if folder filtering in flatview is overrriden. Use the **flatview** flag to find out if it is actually on or off.
</td></tr><tr><td>
partial</td><td>

*bool*</td><td>

Returns **True** if partial matching is enabled.
</td></tr><tr><td>
realtime</td><td>

*bool*</td><td>

Returns **True** if realtime filtering is enabled.
</td></tr><tr><td>
regex</td><td>

*bool*</td><td>

Returns **True** if regular expression mode is enabled.
</td></tr><tr><td>
showalldirs</td><td>

*bool*</td><td>

Returns **True** if all folders are being shown.
</td></tr><tr><td>
showallfiles</td><td>

*bool*</td><td>

Returns **True** if all files are being shown.
</td></tr><tr><td>
showeverything</td><td>

*bool*</td><td>

Returns **True** if [Show Everything](/Manual/basic_concepts/searching_and_filtering/show_everything.md) mode is on, which overrides (almost) all filtering.
</td></tr></tbody>
</table>

