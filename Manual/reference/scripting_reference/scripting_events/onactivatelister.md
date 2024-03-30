# OnActivateLister

The **OnActivateLister** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever a Lister window becomes the active window, or loses activation to another window.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnActivateLister
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ActivateListerData](../scripting_objects/activatelisterdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **ActivateListerData.lister** property identifies the Lister, and the **active** property indicates whether this Lister has become active or inactive. If the activation moves from one Lister to another this event would be called twice, once for each Lister.
</td></tr></tbody>
</table>

