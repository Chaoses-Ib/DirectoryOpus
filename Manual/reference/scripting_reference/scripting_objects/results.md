# Results

The **Results** object provides information about the outcome of a function run by the **[Command](command.md)** object. It is obtained from the **Command.results** property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
result</td><td>

*int*</td><td>
Indicates whether or not the command ran successfully. Zero indicates the command could not be run or was aborted; any other number indicates the command was run for at least some files. (Note that this is not the "exit code" for external commands. For external commands it only indicates whether or not Opus launched the command. If you need the exit code of an external command, use the WScript.Shell Run or Exec methods to run the command.)
</td></tr><tr><td>
newtabs</td><td>

*collection:***[Tab](tab.md)**</td><td>

This property returns a collection of **[Tab](tab.md)** objects representing any new tabs created by the command.
</td></tr><tr><td>
newlisters</td><td>

*collection:***[Lister](lister.md)**</td><td>

This property returns a collection of **[Lister](lister.md)** objects representing any new Listers created by the command.
</td></tr><tr><td>
newviewers</td><td>

*collection:***[Viewer](viewer.md)**</td><td>

This property returns a collection of **[Viewer](viewer.md)** objects representing any new image viewers created by the command. (This is only for standalone viewers, not the viewer pane.)
</td></tr></tbody>
</table>

