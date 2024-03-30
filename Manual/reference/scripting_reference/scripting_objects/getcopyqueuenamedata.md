# GetCopyQueueNameData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnGetCopyQueueName](../scripting_events/ongetcopyqueuename.md)** event, the method receives a **GetCopyQueueNameData** object whenever a copy operation begins that uses automatically-managed copy queues (i.e. the *Automatically manage file copy queues* option on the **[Copying Files](/Manual/preferences/preferences_categories/file_operations/copying_files/README.md)** page in Preferences is turned on).

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
dest</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object representing the destination path of the copy operation.
</td></tr><tr><td>
desttab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the destination folder tab.
</td></tr><tr><td>
dest_drives</td><td>

*string*</td><td>
Returns a binary string indicating the physical drive indices that the destination path is located on (if any). For example, 00100000000000000000000000 indicates that drive C: is the destination drive.
</td></tr><tr><td>
move</td><td>

*bool*</td><td>

Returns **True** if the operation is a move instead of a copy.
</td></tr><tr><td>
name</td><td>

*string*</td><td>
Returns the default queue name for this operation.
</td></tr><tr><td>
source</td><td>

*object:***[Path](path.md)**</td><td>

Returns a **[Path](path.md)** object representing the source path of the copy operation.
</td></tr><tr><td>
sourcetab</td><td>

*object:***[Tab](tab.md)**</td><td>

Returns a **[Tab](tab.md)** object representing the source folder tab.
</td></tr><tr><td>
source_drives</td><td>

*string*</td><td>
Returns a binary string indicating the physical drive indices that the source path is located on (if any). For example, 00001000000000000000000000 indicates that drive E: is the source drive.
</td></tr></tbody>
</table>

