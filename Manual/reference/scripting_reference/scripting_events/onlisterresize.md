# OnListerResize

The **OnListerResize** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever a Lister window is resized.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnListerResize
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ListerResizeData](../scripting_objects/listerresizedata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **ListerResizeData.lister** property identifies the Lister, and the **action** property is a *string* indicating the element that resize action taken. Use the **width** and **height** properties to determine the new window size.
</td></tr></tbody>
</table>

