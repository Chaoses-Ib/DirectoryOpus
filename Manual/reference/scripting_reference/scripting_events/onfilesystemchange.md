# OnFilesystemChange

The **OnFilesystemChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when monitored files or folders change. Monitoring is established by calling the **[FSUtil](../scripting_objects/fsutil.md).WatchChanges** method.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnFilesystemChange
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[FilesystemChangeData](../scripting_objects/filesystemchangedata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **id** property indicates which watcher detected a change. Note that you aren't told what changed, only that something meeting the specified conditions did change.
</td></tr></tbody>
</table>

