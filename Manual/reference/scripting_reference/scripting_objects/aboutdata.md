# AboutData

If a [script add-in](/Manual/scripting/script_add-ins/README.md) provides an **[OnAboutScript](../scripting_events/onaboutscript.md)** method, it is passed an **AboutData** object when invoked via the user clicking the *About* button in Preferences.

| Property Name | Return Type | Description |
| --- | --- | --- |
| window | *int* | This is a handle to the parent window that the script should use if displaying a dialog via the **[Dialog](dialog.md)** object. Even though this is not a **[Lister](lister.md)** or **[Tab](tab.md)**, it can still be assigned to the **Dialog.window** property to set the parent window of the dialog. |

