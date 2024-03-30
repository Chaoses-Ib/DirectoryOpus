# OnAboutScript

The **OnAboutScript** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to display an "about" dialog to the user. It is triggered when the user clicks the *About* button for a script on the **[Script Management](/Manual/scripting/script_management/README.md)** dialog.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnAboutScript
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[AboutData](../scripting_objects/aboutdata.md) **
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The usual implementation for this event would use the **AboutData.window** parameter to display a dialog using the **[Dialog](../scripting_objects/dialog.md)** object.
</td></tr></tbody>
</table>

