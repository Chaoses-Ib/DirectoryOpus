# BeforeFolderChangeData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnBeforeFolderChange](../scripting_events/onbeforefolderchange.md)** event, the method receives a **BeforeFolderChangeData** object before the new folder is read.

| Property Name | Return Type | Description |
| --- | --- | --- |
| action | *string* | Returns a string indicating the action that triggered the folder read. The string will be one of the following: *normal*, *refresh*, *refreshsearch*, *refreshsub*, *parent*, *root*, *back*, *forward*, *dblclk*.  <br />The *refreshsub* actions means the folder (and sub-folders) are being refreshed while Flat View is on. The other action names should be self-explanatory. |
| initial | *bool* | Returns **True** if this is the first path to be read into this tab (i.e. previously the tab was empty). |
| path | *object:***[Path](path.md)** | Returns a **[Path](path.md)** object representing the new path that is to be read. |
| qualifiers | *string* | Returns a string indicating any qualifier keys that were held down by the user when the event was triggered.  <br />The string can contain any or all of the following: *shift* *ctrl*, *alt*, *lwin*, *rwin*  <br />If no qualifiers were down, the string will be: *none* |
| tab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the tab that is changing folder. |

