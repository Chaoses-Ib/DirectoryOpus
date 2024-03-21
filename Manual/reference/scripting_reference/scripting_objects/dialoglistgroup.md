# DialogListGroup

The **DialogListGroup** object represents a group in a *list view* control in a [script dialog](/Manual/scripting/script_dialogs/README.md). It's returned by the **[Control](control.md).GetGroupById** method.

| Property Name | Return Type | Description |
| --- | --- | --- |
| expanded | *bool* | Returns or sets the expansion state of this group. The group must have been added as "collapsible" via the **Control.AddGroup** method. |
| id | *int* | Returns the ID of this group. |
| name | *string* | Returns the name of this group. |

