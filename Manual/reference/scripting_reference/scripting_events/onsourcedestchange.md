# OnSourceDestChange

The **OnSourceDestChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever a tab's source/destination state changes.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnSourceDestChange
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[SourceDestData](../scripting_objects/sourcedestdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **SourceDestData.tab** property identifies the tab, and the **source** and **dest** properties identify the new state (if both are **False** it means the tab is "off" - this can only happen in a single file-display Lister).
</td></tr></tbody>
</table>

