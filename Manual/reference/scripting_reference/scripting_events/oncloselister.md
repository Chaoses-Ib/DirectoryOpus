# OnCloseLister

The **OnCloseLister** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever a Lister is closed.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnCloseLister
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[CloseListerData](../scripting_objects/closelisterdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*bool*
</td></tr><tr><td>

**Description:**</td><td>

The **CloseListerData.lister** property identifies the Lister that is closing. The **shutdown** property is **True** if the Lister is closing because Opus (or Windows) is shutting down.  
If shutdown is **False**, you can prevent the Lister from closing by returning **True** from this event (or **False** to allow the close, which is the default). If Opus or Windows is shutting down then you can't prevent the Lister from closing.
</td></tr></tbody>
</table>

