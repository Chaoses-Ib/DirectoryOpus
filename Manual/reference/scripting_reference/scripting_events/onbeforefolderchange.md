# OnBeforeFolderChange

The **OnBeforeFolderChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to receive notification before a new folder is read in a tab. Use the **OnAfterFolderChange** event if you want notification *after* a folder has been read.

| **Method Name:** | OnBeforeFolderChange |
| --- | --- |
| **Argument Type:** | **[BeforeFolderChangeData](../scripting_objects/beforefolderchangedata.md)** |
| **Return Type:** | *bool* or *string* |
| **Description:** | The **BeforeFolderChangeData.tab** property identifies the tab, and the **path** property identifies the folder about to be read. The **initial** property indicates if this is the first folder read into this tab - if **True**, it means the tab was previously empty or newly opened.<br /><br />You can return two different types from this event:<br /><br />- *bool*: If you return **True**, the folder read will be blocked and the tab will be unchanged. If you return **False** the read will be allowed to continue (this is the default).<br />- *string*: You can return a *string* (or a **[Path](../scripting_objects/path.md)** object) to change the folder path to be read. |

