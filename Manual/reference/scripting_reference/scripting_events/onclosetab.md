# OnCloseTab

The **OnCloseTab** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when a tab is closed in a Lister.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnCloseTab
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[CloseTabData](../scripting_objects/closetabdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*bool*
</td></tr><tr><td>

**Description:**</td><td>

The **CloseTabData.tab** property identifies the tab that is closing. You can return **True** from this event to prevent the tab from closing, or **False** (which is the default) to allow it to close.

Note that when a Lister closes this event is **not** triggered for each of its tabs - the **[OnCloseLister](oncloselister.md)** event provides notification when a Lister closes, and all the tabs in that Lister as discoverable through the **CloseListerData.lister.tabs** property.
</td></tr></tbody>
</table>

