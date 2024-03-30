# AboutData

If a [script add-in](/Manual/scripting/script_add-ins/README.md) provides an **[OnAboutScript](../scripting_events/onaboutscript.md)** method, it is passed an **AboutData** object when invoked via the user clicking the *About* button in Preferences.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
window</td><td>

*int*</td><td>

This is a handle to the parent window that the script should use if displaying a dialog via the **[Dialog](dialog.md)** object. Even though this is not a **[Lister](lister.md)** or **[Tab](tab.md)**, it can still be assigned to the **Dialog.window** property to set the parent window of the dialog.
</td></tr></tbody>
</table>

