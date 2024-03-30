# OnFileOperationComplete

The **OnFileOperationComplete** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification when certain file operations have been completed. Currently the only file operation that supports this is the **Rename** command, but others may be added in the future. 

Receiving notifications is a two-step process. Opus will initially call your script to query whether you want notification for a particular operation. If you respond affirmatively, your script will be called again when the operation is complete.

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnFileOperationComplete
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[FileOperationCompleteData](../scripting_objects/fileoperationcompletedata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

When the **query** property is set to **True**, return **True** to indicate that you want to be notified for this operation.
</td></tr><tr><td>

**Description:**</td><td>

The first time this method is called the **[FileOperationCompleteData](../scripting_objects/fileoperationcompletedata.md).query** property will be set to **True**. You can look at the **action** and **cmdline** properties to decide if this is an operation you want notification for. Return **True** if so.

You'll then be called again with the **query** property set to **False**. The **data** property provides information about the operation that was completed.
</td></tr></tbody>
</table>

