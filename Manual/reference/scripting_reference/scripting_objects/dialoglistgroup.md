# DialogListGroup

The **DialogListGroup** object represents a group in a *list view* control in a [script dialog](/Manual/scripting/script_dialogs/README.md). It's returned by the **[Control](control.md).GetGroupById** method.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
expanded</td><td>

*bool*</td><td>

Returns or sets the expansion state of this group. The group must have been added as "collapsible" via the **Control.AddGroup** method.
</td></tr><tr><td>
id</td><td>

*int*</td><td>
Returns the ID of this group.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns the name of this group.
</td></tr></tbody>
</table>

