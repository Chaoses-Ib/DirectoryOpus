# OnOpenTab

The **On** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when a new tab opens.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnOpenTab
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[OpenTabData](../scripting_objects/opentabdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **OpenTabData.tab** property identifies the newly opened tab. Note that this method is not called when a new Lister is opened, irrespective of how many tabs it contains - instead, you can identify all the tabs in the newly opened Lister by implementing the **OnOpenLister** event.
</td></tr></tbody>
</table>

