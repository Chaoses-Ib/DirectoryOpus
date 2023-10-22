# Results

The **Results** object provides information about the outcome of a function run by the **[Command](command.md)** object. It is obtained from the **Command.results** property.

| Property Name | Return Type | Description |
| --- | --- | --- |
| result | *int* | Indicates whether or not the command ran successfully. Zero indicates the command could not be run or was aborted; any other number indicates the command was run for at least some files. (Note that this is not the "exit code" for external commands. For external commands it only indicates whether or not Opus launched the command. If you need the exit code of an external command, use the WScript.Shell Run or Exec methods to run the command.) |
| newtabs | *collection:***[Tab](tab.md)** | This property returns a collection of **[Tab](tab.md)** objects representing any new tabs created by the command. |
| newlisters | *collection:***[Lister](lister.md)** | This property returns a collection of **[Lister](lister.md)** objects representing any new Listers created by the command. |
| newviewers | *collection:***[Viewer](viewer.md)** | This property returns a collection of **[Viewer](viewer.md)** objects representing any new image viewers created by the command. (This is only for standalone viewers, not the viewer pane.) |

