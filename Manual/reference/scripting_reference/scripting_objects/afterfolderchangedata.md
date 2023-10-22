# AfterFolderChangeData

If a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md)implements the **[OnAfterFolderChange](../scripting_events/onafterfolderchange.md)** event, the method receives an **AfterFolderChangeData** object once the folder read is complete.

| Property Name | Return Type | Description |
| --- | --- | --- |
| action | *string* | Returns a string indicating the action that triggered the folder read. The string will be one of the following: *normal*, *refresh*, *refreshsearch*, *refreshsub*, *parent*, *root*, *back*, *forward*, *dblclk*.  <br />The *refreshsub* actions means the folder (and sub-folders) are being refreshed while Flat View is on. The other action names should be self-explanatory. |
| path | *object:***[Path](path.md)** | *If the read failed*, this will return a **[Path](path.md)**object representing the path that Opus tried to read.  <br />*If the read was successful, this property is not provided* - instead, the **tab** property provides access to this information.  <br />Use the **result** property to know if the read was a success. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| result | *bool* | Returns **True** if the folder was read successfully, or **False** on failure. |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab that read the folder. |

