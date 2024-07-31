# OnFileOperationComplete

**OnFileOperationComplete** 事件可以由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以在某些文件操作完成后接收通知。目前唯一支持此事件的文件操作是 **Rename** 命令，但将来可能会添加其它操作。

接收通知是一个两步过程。Opus 会首先调用您的脚本以查询您是否希望接收特定操作的通知。如果您回复肯定，您的脚本将在操作完成后再次被调用。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnFileOperationComplete
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[FileOperationCompleteData](../scripting_objects/fileoperationcompletedata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

当 **query** 属性设置为 **True** 时，返回 **True** 表示您希望为此操作接收通知。
</td></tr><tr><td>

**描述：**</td><td>

第一次调用此方法时，**[FileOperationCompleteData](../scripting_objects/fileoperationcompletedata.zh.md).query** 属性将设置为 **True**。您可以查看 **action** 和 **cmdline** 属性以决定是否需要为此操作接收通知。如果需要，则返回 **True**。

然后，您将再次被调用，此时 **query** 属性设置为 **False**。**data** 属性提供有关已完成操作的信息。
</td></tr></tbody>
</table>