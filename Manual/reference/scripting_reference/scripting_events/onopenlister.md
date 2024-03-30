# OnOpenLister

The **OnOpenLister** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when a new Lister is opened.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnOpenLister
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[OpenListerData](../scripting_objects/openlisterdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*bool*
</td></tr><tr><td>

**Description:**</td><td>

The **OpenListerData.lister** property identifies the newly opened Lister.

This event is initially called immediately after the Lister has been created, before any folders have been read or any tabs have been opened. If you return **True** from this event, it will be called again after all tabs have been created. You can use the OpenListerData.after property to distinguish between these calls.
</td></tr></tbody>
</table>

