# OnBeforeFolderChange

The **OnBeforeFolderChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification before a new folder is read in a tab. Use the **OnAfterFolderChange** event if you want notification *after* a folder has been read.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnBeforeFolderChange
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[BeforeFolderChangeData](../scripting_objects/beforefolderchangedata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*bool* or *string*
</td></tr><tr><td>

**Description:**</td><td>

The **BeforeFolderChangeData.tab** property identifies the tab, and the **path** property identifies the folder about to be read. The **initial** property indicates if this is the first folder read into this tab - if **True**, it means the tab was previously empty or newly opened.

You can return two different types from this event:

- *bool*: If you return **True**, the folder read will be blocked and the tab will be unchanged. If you return **False** the read will be allowed to continue (this is the default).
- *string*: You can return a *string* (or a **[Path](../scripting_objects/path.md)** object) to change the folder path to be read.
</td></tr></tbody>
</table>

