# OnTabClick

The **OnTabClick** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when a tab is clicked with a qualifier key held down. You can use this to override the default behavior (e.g. control-clicking tabs normally links them).

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnTabClick
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[TabClickData](../scripting_objects/tabclickdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*bool*
</td></tr><tr><td>

**Description:**</td><td>

The **TabClickData.tab** property identifies the tab that was clicked. You can return **True** from this event to prevent the default action, or **False** (which is the default) to allow it to proceed.
</td></tr></tbody>
</table>

