# GetCopyQueueNameData

If a [script add-in](/Manual/scripting/script_add-ins/README.md)implements the **[OnGetCopyQueueName](../scripting_events/ongetcopyqueuename.md)** event, the method receives a **GetCopyQueueNameData** object whenever a copy operation begins that uses automatically-managed copy queues (i.e. the *Automatically manage file copy queues* option on the **[Copying Files](/Manual/preferences/preferences_categories/file_operations/copying_files/README.md)** page in Preferences is turned on).

| Property Name | Return Type | Description |
| --- | --- | --- |
| dest | *object:***[Path](path.md)** | Returns a **[Path](path.md)** object representing the destination path of the copy operation. |
| desttab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the destination folder tab. |
| dest_drives | *string* | Returns a binary string indicating the physical drive indices that the destination path is located on (if any). For example, 00100000000000000000000000 indicates that drive C: is the destination drive. |
| move | *bool* | Returns **True** if the operation is a move instead of a copy. |
| name | *string* | Returns the default queue name for this operation. |
| source | *object:***[Path](path.md)** | Returns a **[Path](path.md)** object representing the source path of the copy operation. |
| sourcetab | *object:***[Tab](tab.md)** | Returns a **[Tab](tab.md)** object representing the source folder tab. |
| source_drives | *string* | Returns a binary string indicating the physical drive indices that the source path is located on (if any). For example, 00001000000000000000000000 indicates that drive E: is the source drive. |

