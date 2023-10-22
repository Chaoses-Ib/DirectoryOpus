# QuickFilter

The **QuickFilter** object provides access to information about the quick filter state in a tab. It’s returned by the **[Tab](tab.md).quickfilter property.**

  

| **Property Name** | **Return Type** | **Description** |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns the current filter string, if any. |
| autoclear | *bool* | Returns **True** if the auto-clear mode is set in Preferences. |
| autostar | *bool* | Returns **True** if the auto-star mode is set in Preferences. |
| disable | *bool* | Returns **True** if the filter is disabled. |
| easymode | *bool* | Returns **True** if easy mode is selected. |
| filter | *string* | Returns the current filter string. |
| flatview | *bool* | Returns **True** if folder filtering in flatview is on. |
| hidealldirs | *bool* | Returns **True** if all folders are being hidden. |
| hideallfiles | *bool* | Returns **True** if all files are being hidden. |
| overrideflatview | *bool* | (Legacy flag.) Returns **True** if folder filtering in flatview is overrriden. Use the **flatview** flag to find out if it is actually on or off. |
| partial | *bool* | Returns **True** if partial matching is enabled. |
| realtime | *bool* | Returns **True** if realtime filtering is enabled. |
| regex | *bool* | Returns **True** if regular expression mode is enabled. |
| showalldirs | *bool* | Returns **True** if all folders are being shown. |
| showallfiles | *bool* | Returns **True** if all files are being shown. |
| showeverything | *bool* | Returns **True** if [Show Everything](/Manual/basic_concepts/searching_and_filtering/show_everything.md) mode is on, which overrides (almost) all filtering. |

