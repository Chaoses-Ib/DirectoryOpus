# OnAfterFolderChange

The **OnAfterFolderChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) that wants to be notified after a new folder has been read in a tab. Use the **[OnBeforeFolderChange](onbeforefolderchange.md)** event to receive notification *before* the folder is read.

| **Method Name:** | OnAfterFolderChange |
| --- | --- |
| **Argument Type:** | **[AfterFolderChangeData](../scripting_objects/afterfolderchangedata.md)** |
| **Return Type:** | *bool* |
| **Description:** | The **AfterFolderChangeData.tab** property indicates the tab and the **path** property the path of the folder. The **result** property indicates the success or failure of the folder read.<br /><br />If **result** is **False** (i.e. the folder was not successfully read) then you can return **True** from this event to stop Opus from going back to the previous folder (which is what normally happens when a folder read fails). If **result** is **True** then the return value from this event is ignored. |

