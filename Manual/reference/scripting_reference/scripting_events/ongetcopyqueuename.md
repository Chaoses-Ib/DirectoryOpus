# OnGetCopyQueueName

The **OnGetCopyQueueName** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to override the default copy queue behavior when the *Automatically manage file copy queues* option on the **[Copying Files](/Manual/preferences/preferences_categories/file_operations/copying_files/README.md)** page in Preferences is turned on. The event is passed the default copy queue name along with information relating to the copy operation. It can accept the default queue name, provide its own or disable queuing and run the operation immediately. 

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnGetCopyQueueName
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[GetCopyQueueNameData](../scripting_objects/getcopyqueuenamedata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*string* to provide a new queue name.  
**False** to accept the default queue name.  
**True** to bypass the queue and run the copy immediately.
</td></tr><tr><td>

**Description:**</td><td>

The **GetCopyQueueNameData.sourcetab** and **desttab** properties identify the **[Tab](../scripting_objects/tab.md)** objects involved in the copy operation, and the **source** and **dest** properties provide the source and destination **[Path](../scripting_objects/path.md)** objects.  
The **source_drives** and **dest_drives** properties return a string consisting of **0** and **1** characters, indicating which physical drives are involved in the operation. For example, if drive A: was involved, the first character would be a **1**, otherwise it would be a **0**; if drive B: was involved, the second character would be a **1**, and so on.  
The **name** property indicates the default copy queue name, and **move** is **True** if the operation is a **move** rather than a copy.  
You can accept the default name by returning **False**, or return the a new queue name to use. If you return **True** the queue will be bypassed.
</td></tr></tbody>
</table>

