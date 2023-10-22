# OnGetCopyQueueName

The **OnGetCopyQueueName** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/RAEDME.md) to override the default copy queue behavior when the *Automatically manage file copy queues* option on the **[File Operations / Copy Options](/Manual/preferences/preferences_categories/file_operations/copy_options.md)** page in Preferences is turned on. The event is passed the default copy queue name along with information relating to the copy operation. It can accept the default queue name, provide its own or disable queuing and run the operation immediately. 

| **Method Name:** | OnGetCopyQueueName |
| --- | --- |
| **Argument Type:** | **[GetCopyQueueNameData](../scripting_objects/getcopyqueuenamedata.md)** |
| **Return Type:** | *string* to provide a new queue name.  <br />**False** to accept the default queue name.  <br />**True** to bypass the queue and run the copy immediately. |
| **Description:** | The **GetCopyQueueNameData.sourcetab** and **desttab** properties identify the **[Tab](../scripting_objects/tab.md)** objects involved in the copy operation, and the **source** and **dest** properties provide the source and destination **[Path](../scripting_objects/path.md)** objects.  <br />The **source_drives** and **dest_drives** properties return a string consisting of **0** and **1** characters, indicating which physical drives are involved in the operation. For example, if drive A: was involved, the first character would be a **1**, otherwise it would be a **0**; if drive B: was involved, the second character would be a **1**, and so on.  <br />The **name** property indicates the default copy queue name, and **move** is **True** if the operation is a **move** rather than a copy.  <br />You can accept the default name by returning **False**, or return the a new queue name to use. If you return **True** the queue will be bypassed. |

