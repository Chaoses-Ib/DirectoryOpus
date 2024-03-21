# FilesystemChangeData

A [script add-in](/Manual/scripting/script_add-ins/README.md) can monitor file and folder changes by implementing the **[OnFilesystemChange](../scripting_events/onfilesystemchange.md)** event and calling the **[FSUtil](fsutil.md).WatchChanges** method to establish monitoring.

| Property Name | Return Type | Description |
| --- | --- | --- |
| id | *string* | Returns the ID of the watcher that detected a file or folder change. This ID is assigned when you create the watcher in the call to **[FSUtil](fsutil.md).WatchChanges**. |

