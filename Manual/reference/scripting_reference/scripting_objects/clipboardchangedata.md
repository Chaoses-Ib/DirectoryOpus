# ClipboardChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md) implements the **[OnClipboardChange](../scripting_events/onclipboardchange.md)** event, the method receives a **ClipboardChangeData** object whenever the system clipboard contents change.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
count</td><td>

*int*</td><td>
Returns a count which increments each time the clipboard contents change (when Opus is running).
</td></tr><tr><td>
has_files</td><td>

*bool*</td><td>

Returns **True** if the clipboard now contains files.
</td></tr></tbody>
</table>

