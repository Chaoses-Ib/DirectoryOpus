# OnActivateTab

The **OnActivateTab** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive a notification every time a tab becomes active (i.e. comes to the front of another tab in the same file display).

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnActivateTab
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ActivateTabData](../scripting_objects/activatetabdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **ActivateTabData.oldtab** property identifies the tab that was previously active, and the **newtab** property identifies the new active tab.
</td></tr></tbody>
</table>

