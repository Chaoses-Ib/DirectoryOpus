# OnFilesystemChange

The **OnFilesystemChange** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when monitored files or folders change. Monitoring is established by calling the **[FSUtil](../scripting_objects/fsutil.md).WatchChanges** method.

| **Method Name:** | OnFilesystemChange |
| --- | --- |
| **Argument Type:** | **[FilesystemChangeData](../scripting_objects/filesystemchangedata.md)** |
| **Return Type:** | *none* |
| **Description:** | The **id** property indicates which watcher detected a change. Note that you aren't told what changed, only that something meeting the specified conditions did change. |

